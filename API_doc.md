# /docb 文件集 APIs

* [GET /docb](##條列文件集) - 條列文件集
* [GET /docb/{docId}](##讀取文件集) - 讀取文件集
* [POST /docb](##新增文件集) - 新增文件集
* [PATCH /docb/{docId}](##修改文件集) - 修改文件集

---

## 條列文件集
**GET /docb**
列出所有文件集，可依 kbId 過濾。

### 輸入:
查詢參數（可選）:
- `kbId`: string  知識庫ID

### 輸出:
```json
{
    "return_code": "string",
    "return_message": "string",
    "doc_list": [
        {
            "docId": "uuid-doc-000",
            "kbId": "uuid-kb-000",
            "docTitle": "文件標題",
            "docType": "txt|md|pdf|doc|url",
            "docUri": "檔案uri或url",
            "totalChunk": 5,
            "dAddDate": "2024-06-01"
        }
    ]
}
```
docId      string  文件ID  
kbId      string  知識庫ID  
docTitle   string  文件標題  
docType    string  文件類型  
docUri     string  檔案uri或url  
totalChunk int     資料塊總數  
dAddDate   string  建立日期  

---

## 讀取文件集
**GET /docb/{docId}**
傳入 docId，回傳該文件集所有欄位。

### 輸入:
路徑參數:
- `docId`: string  文件ID

### 輸出:
```json
{
    "return_code": "string",
    "return_message": "string",
    "doc": {
        "docId": "uuid-doc-000",
        "kbId": "uuid-kb-000",
        "docTitle": "文件標題",
        "docType": "txt|md|pdf|doc|url",
        "docUri": "檔案uri或url",
        "totalChunk": 5,
        "dAddDate": "2024-06-01"
    }
}
```
docId      string  文件ID  
kBId      string  知識庫ID  
docTitle   string  文件標題  
docType    string  文件類型  
docUri     string  檔案uri或url  
totalChunk int     資料塊總數  
dAddDate   string  建立日期  

---

## 新增文件集
**POST /docb**
新增文件集

### 輸入:
```json
{
    "data": {
        "kbId": "uuid-kb-000",
        "docTitle": "文件標題",
        "docType": "txt|md|pdf|doc|url",
        "docUri": "檔案uri或url"
    }
}
```
### 輸出:
```json
{
    "return_code": "string",
    "return_message": "string"
}
```
kbId      string  知識庫ID  
docTitle   string  文件標題  
docType    string  文件類型  
docUri     string  檔案uri或url  

---

## 修改文件集
**PATCH /docb/{docId}**
修改文件集

### 輸入:
```json
{
    "docId": "uuid-doc-000",
    "data": {
        "docTitle": "新文件標題",
        "docType": "txt|md|pdf|doc|url",
        "docUri": "新檔案uri或url"
    }
}
```
### 輸出:
```json
{
    "return_code": "string",
    "return_message": "string"
}
```
docId      string  文件ID  
docTitle   string  文件標題  
docType    string  文件類型  
docUri     string  檔案uri或url
