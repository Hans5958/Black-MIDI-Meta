# Macros

```vbscript
Sub Rectangle1_Click()	
    ActiveSheet.Cells.Replace "www.youtube.com/watch?v=", "youtu.be/", xlPart, xlByRows, False, False, False, False	
    ActiveSheet.Cells.Replace "&feature=youtu.be", "", xlPart, xlByRows, False, False, False, False	
    ActiveSheet.Columns("D").Replace ",", ".", xlPart, xlByRows, False, False, False, False	
    ActiveSheet.Hyperlinks.Delete	
End Sub	
```