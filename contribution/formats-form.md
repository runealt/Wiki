### Form

If your form is relatively complex, please [click here](contribution/formats-excel-to-form.md) to learn how to use Excel to make a table and import it to the page.

Tips: You can display the vertical bar `|` character in a table using the table's HTML character code `&#124;`.

#### Basic table syntax

```
| Syntax | Description |
| --- | --- |
| Header | Title |
| Paragraph | Text |
```

| Syntax | Description |
| --- | --- |
| Header | Title |
| Paragraph | Text |

#### Use `:` to set text alignment.

```
| Syntax | Description | Test Text |
| :--- | :---: | ---: |
| Header | Title | Here's this |
| Paragraph | Text | And more |
```

| Syntax | Description | Test Text |
| :--- | :---: | ---: |
| Header | Title | Here's this |
| Paragraph | Text | And more |

#### Use `<br>` to wrap text inside a cell.

```
| Syntax | Description |
| --- | --- |
| Header | Title_Line_1<br>Title_Line_2 |
| Paragraph | Text_Line_1<br>Text_Line_2<br>Text_Line_3 |
```

| Syntax | Description |
| --- | --- |
| Header | Title_Line_1<br>Title_Line_2 |
| Paragraph | Text_Line_1<br>Text_Line_2<br>Text_Line_3 |

#### Merge cells by adding parameters `colspan` and `rowspan`.

The number after `colspan` and `rowspan` indicates the number of cells merged to the right or down from this cell +1.

```
<table>
    <tr>
        <td>row/column</td> 
        <td>column2</td> 
        <td>column3</td> 
   </tr>
    <tr>
  		 <td>row2 column1</td> 
      	 <td colspan="2">Merge rows across two columns</td>    
    </tr>
    <tr>
        <td colspan="3">Merge rows across tree columns</td>    
    </tr>
</table>
```

<table>
    <tr>
        <td>row/column</td> 
        <td>column2</td> 
        <td>column3</td> 
   </tr>
    <tr>
  		 <td>row2 column1</td> 
      	 <td colspan="2">merge rows across two columns</td>    
    </tr>
    <tr>
        <td colspan="3">merge rows across tree columns</td>    
    </tr>
</table>

!>If you want to center the text, add `align="center"` to the <td> of the title. Also you can add `bgcolor="{rgb_code}"` to the <td> for Back Ground Color and add `style="color:{rgb_code}"` to the <td> for Text Color.

Example:

```
<table>
    <tr>
        <td>row/column</td> 
        <td>column2</td> 
        <td>column3</td> 
   </tr>
    <tr>
  		 <td>row2 column1</td> 
      	 <td colspan="2">Merge rows across two columns</td>    
    </tr>
    <tr>
        <td colspan="3" align="center" bgcolor="#ff6666" style="color:#ffffff">Merge rows across tree columns</td>    
    </tr>
</table>
```

<table>
    <tr>
        <td>row/column</td> 
        <td>column2</td> 
        <td>column3</td> 
   </tr>
    <tr>
  		 <td>row2 column1</td> 
      	 <td colspan="2">Merge rows across two columns</td>    
    </tr>
    <tr>
        <td colspan="3" align="center" bgcolor="#ff6666" style="color:#ffffff">Merge rows across tree columns</td>    
    </tr>
</table>

##### Another sample-1 of merged cells.

```
<table>
    <tr>
        <td>row1 column1</td> 
        <td>row1 column2</td> 
        <td>row1 column3</td> 
   </tr>
    <tr>
        <td rowspan="2">merge two columns</td>    
  		 <td>row2 column2</td> 
      	 <td>row2 column3</td> 
    </tr>
    <tr>
        <td>row3 column2</td> 
        <td>row3 column3</td>    
    </tr>
</table>
```
<table>
    <tr>
        <td>row1 column1</td> 
        <td>row1 column2</td> 
        <td>row1 column3</td> 
   </tr>
    <tr>
        <td rowspan="2">merge two columns</td>    
  		 <td>row2 column2</td> 
      	 <td>row2 column3</td> 
    </tr>
    <tr>
        <td>row3 column2</td> 
        <td>row3 column3</td>    
    </tr>
</table>

##### Another sample-2 of merged cells.

```
<table>
    <tr>
        <td>column1</td> 
        <td>column2</td> 
   </tr>
   <tr>
        <td colspan="2">merge row</td>    
   </tr>
   <tr>
        <td>column1</td> 
        <td>column2</td> 
   </tr>
    <tr>
        <td rowspan="2">merge column</td>    
        <td >row2 column2</td>  
    </tr>
    <tr>
        <td >row3 column2</td>  
    </tr>
</table>
```
<table>
    <tr>
        <td>column1</td> 
        <td>column2</td> 
   </tr>
   <tr>
        <td colspan="2">merge row</td>    
   </tr>
   <tr>
        <td>column1</td> 
        <td>column2</td> 
   </tr>
    <tr>
        <td rowspan="2">merge column</td>    
        <td >row2 column2</td>  
    </tr>
    <tr>
        <td >row3 column2</td>  
    </tr>
</table>
