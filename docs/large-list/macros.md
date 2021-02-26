# Macros

```vbscript
Sub TidyList()

    Dim A1 As Worksheet
    Set A1 = Worksheets("A1. List")
    A1.Cells.Replace "www.youtube.com/watch?v=", "youtu.be/", xlPart, xlByRows, False, False, False, False
    A1.Cells.Replace "&feature=youtu.be", "", xlPart, xlByRows, False, False, False, False
    A1.Columns("D").Replace ",", ".", xlPart, xlByRows, False, False, False, False
    A1.Hyperlinks.Delete
    
End Sub

Sub MakeVariations()

    ' Defining variables
    Dim A1 As Worksheet
    Set A1 = Worksheets("A1. List")
    Dim SheetsToDelete
    SheetsToDelete = Array("A2. List (wrapped)", "A3. List (wiki)", "A4. List (no header)")
    Dim Element
    
    ' Remove existing sheets
    For Each Element In SheetsToDelete
        For Each Sheet In ActiveWorkbook.Worksheets
                If Sheet.Name = Element Then
                    Application.DisplayAlerts = False
                    Worksheets(Element).Delete
                    Application.DisplayAlerts = True
                End If
        Next Sheet
    Next Element

    ' Reset view
    ActiveWindow.ScrollRow = 1
    ActiveWindow.ScrollColumn = 1
    Range("A1:B1").Select
    
    ' Copying sheets
    A1.Copy After:=Worksheets("A1. List")
    A1.Copy After:=Worksheets("A1. List (2)")
    A1.Copy After:=Worksheets("A1. List (3)")
    Dim A2 As Worksheet
    Dim A3 As Worksheet
    Dim A4 As Worksheet
    Set A2 = Worksheets("A1. List (2)")
    Set A3 = Worksheets("A1. List (3)")
    Set A4 = Worksheets("A1. List (4)")
    A2.Name = "A2. List (wrapped)"
    A3.Name = "A3. List (wiki)"
    A4.Name = "A4. List (no header)"
    
    ' Do specific stuff on each sheet
    A2.Cells.WrapText = True
    A2.Rows(1).EntireRow.WrapText = False
    A2.Rows(2).EntireRow.WrapText = False
    A2.Rows(4).EntireRow.WrapText = False
    For Each Shape In A2.Shapes
       Shape.Delete
    Next Shape
    A2.Columns("L").EntireColumn.WrapText = False
    A3.Columns("F").EntireColumn.Delete
    A3.Columns("G").EntireColumn.Delete
    A3.Columns("K").EntireColumn.Delete
    For Each Shape In A3.Shapes
       Shape.Delete
    Next Shape
    A4.Rows(3).EntireRow.Delete
    A4.Rows(2).EntireRow.Delete
    A4.Rows(1).EntireRow.Delete
    For Each Shape In A4.Shapes
       Shape.Delete
    Next Shape
    
    ' Go back to the first sheet
    A1.Activate
    Range("A1:B1").Select
End Sub

Sub SaveAsCSV()

    FirstName = ThisWorkbook.FullName
    TempName = ThisWorkbook.FullName & ".csv"
    Filename = Application.GetSaveAsFilename(TempName, "CSV (Comma delimited) (*.csv), *.csv")

    If Filename <> False Then
    
        ActiveWorkbook.Save
        Application.DisplayAlerts = False
    
        Dim Element

        For Each Sheet In ActiveWorkbook.Worksheets
            If Sheet.Name = "TempSheet" Then
                Application.DisplayAlerts = False
                Worksheets("TempSheet").Delete
                Application.DisplayAlerts = True
                End If
        Next Sheet
    
        Dim A1 As Worksheet
        Set A1 = Worksheets("A1. List")
        A1.Copy Before:=Worksheets("A1. List")
        Dim TempSheet As Worksheet
        Set TempSheet = Worksheets("A1. List (2)")
        TempSheet.Name = "TempSheet"
        
        TempSheet.Rows(3).EntireRow.Delete
        TempSheet.Rows(2).EntireRow.Delete
        TempSheet.Rows(1).EntireRow.Delete
        
        Application.DisplayAlerts = False
        TempSheet.SaveAs Filename, 6
        Application.DisplayAlerts = True
        
        For Each Sheet In ActiveWorkbook.Worksheets
            If Sheet.Name = "TempSheet" Then
                Application.DisplayAlerts = False
                Worksheets("TempSheet").Delete
                Application.DisplayAlerts = True
                End If
        Next Sheet
        
        Dim SavedWS As Workbook
        Set SavedWS = ActiveWorkbook
        Workbooks.Open FirstName
        SavedWS.Close (True)
        
    End If
  
End Sub
```