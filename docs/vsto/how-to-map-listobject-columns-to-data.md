---
title: "How to: Map ListObject Columns to Data | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "data [Office development in Visual Studio], mapping to ListObject column"
  - "ListObject control, mapping data"
ms.assetid: 2108d0c3-d595-410e-a0ae-3dd53bf6bcc7
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# How to: Map ListObject Columns to Data
  When you bind a <xref:Microsoft.Office.Tools.Excel.ListObject> control to a <xref:System.Data.DataTable>, you might not want to display all the columns in a list, or you might have certain columns that are not bound to data. You can map which columns you want to appear in the <xref:Microsoft.Office.Tools.Excel.ListObject> when you call the <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> method.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 ![link to video](../vsto/media/playvideo.gif "link to video") For a related video demonstration, see [How Do I: Create a List in Excel that is Connected to a SharePoint List?](http://go.microsoft.com/fwlink/?LinkID=130263).  
  
## Mapping Columns  
  
#### To map a data table to columns in a list  
  
1.  Create the <xref:System.Data.DataTable> at the class level.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#16)]
     [!code-vb[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#16)]  
  
2.  Add sample columns and data in the `Startup` event handler of the `Sheet1` class (in a document-level project) or `ThisAddIn` class (in an VSTO Add-in project).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#17)]
     [!code-vb[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#17)]  
  
3.  Call the <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> method and pass in the column names in the order they should appear. The list object will be bound to the newly-created <xref:System.Data.DataTable>, but the order of the columns in the list object will differ from the order they appear in the <xref:System.Data.DataTable>.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#18)]
     [!code-vb[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#18)]  
  
## Specifying Unmapped Columns  
 When you map columns to a <xref:System.Data.DataTable>, you can also specify that certain columns should not be bound to data by passing in an empty string. A new column that is not bound to data is then added to the <xref:Microsoft.Office.Tools.Excel.ListObject> control.  
  
#### To specify an unmapped column when mapping ListObject columns  
  
1.  Call the <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> method and pass in the column names in the order they should appear. Use an empty string to indicate where an unmapped column is added; in this case, between the title column and the last name column.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#19)]
     [!code-vb[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#19)]  
  
## Compiling the Code  
 This code example assumes you have an existing <xref:Microsoft.Office.Tools.Excel.ListObject> named `list1` on the worksheet in which this code appears.  
  
## See Also  
 [Extending Word Documents and Excel Workbooks in VSTO Add-ins at Run Time](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Controls on Office Documents](../vsto/controls-on-office-documents.md)   
 [Adding Controls to Office Documents at Run Time](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [How to: Fill ListObject Controls with Data](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Automating Excel by Using Extended Objects](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject Control](../vsto/listobject-control.md)  
  
  