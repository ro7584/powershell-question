powershell-question

# Easy - 取得 `https://www.google.com` http response 
```powershell
invoke-webrequest https://www.google.com
```

# Medium - 建立 100 個目錄，目錄名稱依序為 example1, example2, ..., example100
```powershell
1..100 | foreach-object { mkdir "example$_" }
```

# Hard - 找出檔案內容中包含 `axios.create` 並列出檔案路徑
```powershell
# git clone https://github.com/axios/axios.git
get-childitem -recurse -file | where-object { `
    $fileContent = get-content $_; `
    $isIncludeKeyword = !!($fileContent -match 'axios.create'); `
    $isIncludeKeyword; `
}
```

