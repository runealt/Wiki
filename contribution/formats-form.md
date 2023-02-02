### Form

If your form is relatively complex, please follow the steps below to make the form.

1. Use Microsoft Excel to make tables and save as HTML
2. Open the saved htm/html file with a text editor
3. Copy everything from `<table>` to `</table>` (including `<table>` and `</table>`)
4. Paste them where needed (no need to delete any parameters)

Tips: You can display the vertical bar (|) character in a table using the table's HTML character code (&#124;).

#### Simple Sample 1

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

#### Simple Sample 2

```
| Syntax      | Description |
| --- | -------------------- |
| Header | Title |
| Paragraph | Text |
```
| Syntax      | Description |
| --- | -------------------- |
| Header | Title |
| Paragraph | Text |

#### Simple Sample 3

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

#### Complex Sample 1

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

#### Complex Sample 2

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

#### Complex Sample 3

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

#### Complex Sample 4

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