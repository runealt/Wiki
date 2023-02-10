<h2>使用Excel制表并导入到Wiki对应页面</h2>

如何通过Excel制表就不过多赘述了，此处主要说明如何将你制作好的表格导入至Wiki中。

### 直接插入文件的预览

优点: 简单快捷<br>
缺点: 无法自定义背景颜色，文字颜色，文字对齐方式(默认为第一行自动加粗和居中对齐)

首先确定你所需要的表格的数量，由于我们的技术有限，无法做到数量自适应，所以需要你手动设置数量，并且数量不能多于实际表格量。<br>
例如我需要插入2个表格<br>
则应当在对应页面的页首/页尾插入如下内容(插入在页首和页尾是为了便于后期的修改)

```
<script type="text/javascript" src="assets/xlsx-loader/num/01.js"></script>
<script type="text/javascript" src="assets/xlsx-loader/num/02.js"></script>
<xlsx-render01 content="path/to/your/excel/01.xlsx"></xlsx-render01>
<xlsx-render02 content="path/to/your/excel/02.xlsx"></xlsx-render02>
```

content后的参数为xlsx文件的路径<br>
对于xlsx文件，你应当上传至对应页面所属文件夹的xlsx文件夹下<br>
例如对于英语版Wiki的Table of Content中的Chest Reels页面，若我需要插入Excel表格<br>
那么我应当提前将文件上传至`wiki/en/table_of_content/xlsx/`下<br>
则我的调用则应该写为

```
<script type="text/javascript" src="assets/xlsx-loader/num/01.js"></script>
<xlsx-render01 content="wiki/en/table_of_contents/xlsx/chest_reels.xlsx"></xlsx-render01>
```
当然路径也可以使用`/xlsx/chest_reels.xlsx`简化
此时，如果我想在任意位置插入引用的表格，则需要在对应位置插入

```
<div id="result01"></div>
```

或

```
<div id="result02"></div>
```

来在此代码所在的位置插入对应的表格

### 将xlsx输出为Markdown表格代码

优点: 便于直接编辑
缺点：不支持文字颜色和背景颜色的表格，并且不支持单元格合并操作。

### 将xlsx输出为HTML表格代码

优点: 可自定义背景颜色，文字颜色，文字对齐方式。
缺点: 不支持导出Excel中设置的文字颜色，背景颜色和文字对齐方式。且如果重新输出，则需要重新自定义背景颜色，文字颜色，文字对齐方式。
