# /qab 問答集 APIs

* [GET /qab](##條列問答集) - 條列問答集
* [GET /qab/{qaId}](##讀取問答集) - 讀取問答集
* [POST /qab](##新增問答集) - 新增問答集
* [PATCH /qab/{qaId}](##修改問答集) - 修改問答集

---

## 條列問答集
**GET /qab**
列出所有問答集，可依 kbId 過濾。

### 輸入:
查詢參數（可選）:
- `kbId`: string  知識庫ID

### 輸出:
```=json
{
    "return_code": "string",
    "return_message": "string",
    "qa_list": [
        {
            "qaId": "uuid-qa-000",
            "kbId": "uuid-kb-000",
            "qaTitle": "問題標題",
            "qaAnswer": "答案內容",
            "catL1": "主分類",
            "catL2": "小分類",
            "status": "1",
            "avBegin": "2024-06-01",
            "avEnd": null
        }
    ]
}
```
qaId      string  問答集ID  
kbId      string  知識庫ID  
qaTitle   string  問題標題  
qaAnswer  string  答案內容  
catL1     string  主分類  
catL2     string  小分類  
status    string  狀態  
avBegin   string  啟用起日  
avEnd     string  停用日  

---

## 讀取問答集
**GET /qab/{qaId}**
傳入 qaId，回傳該問答集所有欄位。

### 輸入:
路徑參數:
- `qaId`: string  問答集ID

### 輸出:
```json
{
    "return_code": "string",
    "return_message": "string",
    "qa": {
        "qaId": "uuid-qa-000",
        "kbId": "uuid-kb-000",
        "qaTitle": "問題標題",
        "qaAnswer": "答案內容",
        "catL1": "主分類",
        "catL2": "小分類",
        "status": "1",
        "avBegin": "2024-06-01",
        "avEnd": null
    }
}
```
qaId      string  問答集ID  
kbId      string  知識庫ID  
qaTitle   string  問題標題  
qaAnswer  string  答案內容  
catL1     string  主分類  
catL2     string  小分類  
status    string  狀態  
avBegin   string  啟用起日  
avEnd     string  停用日  

---

## 新增問答集
**POST /qab**
新增問答集

### 輸入:
```=json
{
    "data": {
        "kbId": "uuid-kb-000",
        "qaTitle": "問題標題",
        "qaAnswer": "答案內容",
        "catL1": "主分類",
        "catL2": "小分類",
        "status": "1",
        "avBegin": "2024-06-01",
        "avEnd": null
    }
}
```
### 輸出:
```=json
{
    "return_code": "string",
    "return_message": "string"
}
```
kbId      string  知識庫ID  
qaTitle   string  問題標題  
qaAnswer  string  答案內容  
catL1     string  主分類  
catL2     string  小分類  
status    string  狀態  
avBegin   string  啟用起日  
avEnd     string  停用日  

---

## 修改問答集
**PATCH /qab/{qaId}**
修改問答集

### 輸入:
```=json
{
    "qaId": "uuid-qa-000",
    "data": {
        "qaTitle": "新問題標題",
        "qaAnswer": "新答案內容",
        "catL1": "主分類",
        "catL2": "小分類",
        "status": "1",
        "avBegin": "2024-06-01",
        "avEnd": null
    }
}
```
### 輸出:
```=json
{
    "return_code": "string",
    "return_message": "string"
}
```
qaId      string  問答集ID  
qaTitle   string  問題標題  
qaAnswer  string  答案內容  
catL1     string  主分類  
catL2     string  小分類  
status    string  狀態  
avBegin   string  啟用起日  
avEnd     string  停用日
