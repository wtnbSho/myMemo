# about shell  
## PowerShell  
- ファイル名一括置換  
[Get-ChildItem | Rename-Item -NewName { $_.Name -replace 'model_details','model_index_details'}](https://kimama-engineer.com/powershell/batch-file-name-replacement-method-with-powershell/)