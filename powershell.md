# Bulk rename

``` powershell
ls | Sort-Object LastWriteTime | %{Rename-Item $_ -NewName ("FILENAME - {0}.EXT" -f $nr++)}
```
