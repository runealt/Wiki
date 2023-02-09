<script src="https://wiki.aliceincradle.org/assets/load-xlsx/xlsx.mini.js"></script>

<input type="file" id="file" style="display: none;"
    accept="application/vnd.openxmlformats-officedocument.spreadsheetml.sheet" />

  <h2>JS LOAD EXCEL</h2>
  <a href="javascript:selectFile()">Click to load excel form local</a>
  <p>Output</p>
  <div id="result"></div>

<script type="text/javascript">
  // 文件普通操作
  var handler = {};
  // 文件导出操作
  var exportHandler = {};

  function selectFile() {
    document.getElementById("file").click();
  }

  // 操作导出
  function exportTable(handlerName) {
    if (exportHandler[handlerName]) {
      exportHandler[handlerName]();
    }
  }

  document.getElementById("file").addEventListener("change", function (e) {
    var files = e.target.files;
    if (files.length == 0) return;
    var f = files[0];
    if (!/\.xlsx$/g.test(f.name)) {
      alert("only support xlsx file");
      return;
    }
    handler.readWorkbookFromLocalFile(f, function (workbook) {
      handler.readWorkbook(workbook);
    });
  });

  handler = {
    // 处理本地加载的文件
    readWorkbookFromLocalFile(file, callback) {
      var reader = new FileReader();
      reader.onload = function (e) {
        var data = e.target.result;
        var workbook = XLSX.read(data, { type: "binary" });
        if (callback) callback(workbook);
      };
      reader.readAsBinaryString(file);
    },

    readWorkbook(workbook) {
      var sheetNames = workbook.SheetNames; // 工作表名称集合
      var worksheet = workbook.Sheets[sheetNames[0]]; // 这里我们只读取第一张sheet
      var csv = XLSX.utils.sheet_to_csv(worksheet);
      document.getElementById("result").innerHTML = handler.csv2table(
        csv,
        true
      );

      // 合并单元格
      handler.mergeTable(workbook, true);
    },

    // csv 数据转换为 table
    csv2table(csv, showTab = false) {
      var html = "<table>";
      var rows = csv.split("\n");
      rows.pop(); // 最后一行没用的
      rows.forEach(function (row, idx) {
        var columns = row.split(",");
        if (showTab) {
          columns.unshift(idx + 1); // 添加行索引
          if (idx == 0) {
            // 添加列索引
            html += "<tr>";
            for (var i = 0; i < columns.length; i++) {
              html +=
                "<th>" +
                (i == 0 ? "" : String.fromCharCode(65 + i - 1)) +
                "</th>";
            }
            html += "</tr>";
          }
        }
        html += "<tr>";
        columns.forEach(function (column) {
          html += "<td>" + column + "</td>";
        });
        html += "</tr>";
      });
      html += "</table>";
      return html;
    },

    // 合并单元格
    mergeTable(workbook, hasTab = false) {
      let SheetNames = workbook.SheetNames[0];
      let mergeInfo = workbook.Sheets[SheetNames]["!merges"];
      console.log(mergeInfo);

      let result = document.getElementById("result");

      // 是否显示了tab
      let baiseAdd = hasTab ? 1 : 0;

      mergeInfo.forEach((item) => {
        let start_r = item.s.r + baiseAdd;
        let end_r = item.e.r + baiseAdd;

        let start_c = item.s.c + baiseAdd;
        let end_c = item.e.c + baiseAdd;

        for (let i = start_r; i <= end_r; i++) {
          let row = document.querySelectorAll("#result tr")[i];
          for (let child = start_c; child <= end_c; child++) {
            if (child === start_c && i === start_r) {
              // 循环到就是第一个单元格，以这个单元格为开始进行合并
              row.children[child].classList.add("will_span");
              row.children[child].setAttribute("row", end_r - start_r + 1);
              row.children[child].setAttribute("col", end_c - start_c + 1);
            } else {
              // 只做标记，不在这里删除
              row.children[child].classList.add("remove");
            }
          }
        }
      });

      // 移除对应的td
      document.querySelectorAll(".remove").forEach((item) => {
        item.parentNode.removeChild(item);
      });

      // 为大的td设置跨单元格合并
      document.querySelectorAll(".will_span").forEach((item) => {
        item.classList.remove("will_span");
        item.rowSpan = item.getAttribute("row");
        item.colSpan = item.getAttribute("col");
      });
    }
  };
</script>
