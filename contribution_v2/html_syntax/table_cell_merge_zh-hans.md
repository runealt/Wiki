<h3>表格单元格合并</h3>

对于无需合并单元格的表格，推荐你使用Markdown表格进行编写，但如果涉及到单元格合并，那么你必须使用HTML表格。

如果你觉得编写HTML表格对你来说太难了，你也可以[点击此处](contribution_v2/html_syntax/table_by_excel_zh-hans)了解如何使用Excel制表，Excel制表同样支持单元格合并和更复杂的表格制作。但是这样制表，后续的数据修改都需要通过Excel，并且如果你对生成的HTML表格进行了部分外观微调，重新生成的HTML将需要再次修改(Excel输出的表格不包含你在Excel中设置的任何颜色设置和文本对齐设置)

在了解如何合并单元格前，你需要了解HTML表格的制作。

在HTML表格中，你将主要涉及到3个代码，分别是`<table>``<tr>``<td>`<br>
他们与`<br>`不同，他们需要对应的代码来表示结束，分别是`</table>``</tr>``</td>`<br>
他们的作用分别如下

- `<table>`表示表格的开始和结束
- `<tr>`表示行的开始和结束
- `<td>`表示行中的单元格(嵌套在`<tr>`中使用

同时对于`<tr>`和`<td>`也有很多参数可用于排版，此处仅列出常用参数，使用格式均为`parameter_name="parameter_set"`或`parameter_name="parameter_set:detail_set"`, 并且应用于`<tr>`中则对整行生效，应用于`<td>`则仅作用于对应单元格

`parameter_name="parameter_set"`:

- `alt`可设定任意内容，主要用于注释此代码所包含的内容
- `align`可设定文本的对齐方式，参数包含`left``right``center`
- `bgcolor`可设定单元格的颜色，参数为rgb代码，例如`#ff6666`
- `colspan`合并从当前格开始从左往右一定数量的单元格，参数为阿拉伯数字
- `rowspan`合并从当前格开始从上往下一定数量的单元格，参数为阿拉伯数字

`parameter_name="parameter_set:detail_set"`:

- `style`可设定多种内容，常用的主要为文本颜色<br>你可以通过`style="color:rgb_code"`设定此单元格的颜色

对于更多的使用方法，若有需要可在网络上进行搜索。

举个例子，想要设计一个物品分类表，且物品包含星级，可按如下方法写出:

```
<table>
  <tr alt="第一行">
    <td rowspan="2">物品</td>
    <td rowspan="2">分类</td>
    <td rowspan="2">料理能力/使用效果</td>
    <td colspan="5">效果加成</td>
    <td rowspan="2">堆叠数</td>
  </tr>
  <tr alt="第二行">
    <!-- 注意：第一行部分单元格已合并第二行的对应单元格，则这些单元格应当省略不写 -->
    <td alt="原第四格">1★</td>
    <td alt="原第五格">2★</td>
    <td alt="原第六格">3★</td>
    <td alt="原第七格">4★</td>
    <td alt="原第八格">5★</td>
  </tr>
  <tr alt="第三行">
    <!-- 在设定完成标题单元格后，即可按照对应单元格的位置填写内容 -->
    <td>血樱桃</td>
    <td>果实</td>
    <td>最大HP上升<br>诺艾儿的HP回复</td>
    <td>+10%</td>
    <td>+12%</td>
    <td>+14%</td>
    <td>+16%</td>
    <td>+18%</td>
    <td>8</td>
  </tr>
</table>
```

效果:

<table>
  <tr alt="第一行">
    <td rowspan="2">物品</td>
    <td rowspan="2">分类</td>
    <td rowspan="2">料理能力/使用效果</td>
    <td colspan="5">效果加成</td>
    <td rowspan="2">堆叠数</td>
  </tr>
  <tr alt="第二行">
    <!-- 注意：第一行部分单元格已合并第二行的对应单元格，则这些单元格应当省略不写 -->
    <td alt="原第四格">1★</td>
    <td alt="原第五格">2★</td>
    <td alt="原第六格">3★</td>
    <td alt="原第七格">4★</td>
    <td alt="原第八格">5★</td>
  </tr>
  <tr alt="第三行">
    <!-- 在设定完成标题单元格后，即可按照对应单元格的位置填写内容 -->
    <td>血樱桃</td>
    <td>果实</td>
    <td>最大HP上升<br>诺艾儿的HP回复</td>
    <td>+10%</td>
    <td>+12%</td>
    <td>+14%</td>
    <td>+16%</td>
    <td>+18%</td>
    <td>8</td>
  </tr>
</table>

做完表格后，你也可以利用各种参数来美化表格<br>
例如为表格标题格设置颜色，文字对齐方式和文字颜色：

```
<table>
  <tr alt="第一行" align="center" bgcolor="ff6666" style="color:#ffffff">
    <td rowspan="2">物品</td>
    <td rowspan="2">分类</td>
    <td rowspan="2">料理能力/使用效果</td>
    <td colspan="5">效果加成</td>
    <td rowspan="2">堆叠数</td>
  </tr>
  <tr alt="第二行" align="center">
    <td alt="原第四格">1★</td>
    <td alt="原第五格">2★</td>
    <td alt="原第六格">3★</td>
    <td alt="原第七格">4★</td>
    <td alt="原第八格">5★</td>
  </tr>
  <tr alt="第三行">
    <td>血樱桃</td>
    <td>果实</td>
    <td>最大HP上升<br>诺艾儿的HP回复</td>
    <td>+10%</td>
    <td>+12%</td>
    <td>+14%</td>
    <td>+16%</td>
    <td>+18%</td>
    <td>8</td>
  </tr>
</table>
```

效果:

<table>
  <tr alt="第一行" align="center" bgcolor="ff6666" style="color:#ffffff">
    <td rowspan="2">物品</td>
    <td rowspan="2">分类</td>
    <td rowspan="2">料理能力/使用效果</td>
    <td colspan="5">效果加成</td>
    <td rowspan="2">堆叠数</td>
  </tr>
  <tr alt="第二行" align="center">
    <td alt="原第四格">1★</td>
    <td alt="原第五格">2★</td>
    <td alt="原第六格">3★</td>
    <td alt="原第七格">4★</td>
    <td alt="原第八格">5★</td>
  </tr>
  <tr alt="第三行">
    <td>血樱桃</td>
    <td>果实</td>
    <td>最大HP上升<br>诺艾儿的HP回复</td>
    <td>+10%</td>
    <td>+12%</td>
    <td>+14%</td>
    <td>+16%</td>
    <td>+18%</td>
    <td>8</td>
  </tr>
</table>

当然HTML代码也可以不提行，如果你愿意也可以全部写为一行，但是这也并不利于编辑。你也可以利用这个特性将HTML代码排版为于表格对应的格式，例如:

```
<table>
  <tr alt="第一行" align="center" bgcolor="ff6666" style="color:#ffffff">
    <td rowspan="2">物品</td><td rowspan="2">分类</td><td rowspan="2">料理能力/使用效果</td><td colspan="5">效果加成</td><td rowspan="2">堆叠数</td>
  </tr>
  <tr alt="第二行" align="center">
    <td>1★</td><td>2★</td><td>3★</td><td>4★</td><td>5★</td>
  </tr>
  <tr alt="第三行">
    <td>血樱桃</td><td>果实</td><td>最大HP上升<br>诺艾儿的HP回复</td><td>+10%</td><td>+12%</td><td>+14%</td><td>+16%</td><td>+18%</td><td>8</td>
  </tr>
</table>
```

他们的显示效果并不会有任何区别
