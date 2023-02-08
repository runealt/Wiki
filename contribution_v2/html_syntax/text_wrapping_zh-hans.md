<h3>文本换行</h3>

在普通的段落中，你可以通过空行完成文本内容换行，但此类换行类似于更换段落，行于行之间的间隙较大，并不推荐为同段内容换行使用.<br>
例如:

```
text_line_1

text_line_2

text_line_3
```
效果:

>text_line_1
>
>text_line_2
>
>text_line_3

所以更加推荐通过代码`<br>`对文本进行换行<br>
例如:

```
text_line_1<br>text_line_2<br>text_line_3
```

效果:

>text_line_1<br>text_line_2<br>text_line_3

在Markdown中，单纯的换行渲染出来并不会换行，所以你可以通过在每行行末添加代码来实现换行，并便于后续的编辑。<br>
例如:

```
text_line_1<br>
text_line_2<br>
text_line_3
```

效果:

>text_line_1<br>
>text_line_2<br>
>text_line_3

此代码也可以在表格中使用(不论是Markdown表格还是HTML表格)，来实现单元格内文本内容的换行。
