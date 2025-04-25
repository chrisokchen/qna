# /kb 知識庫 APIs

* [GET /kb](##條列知識庫) - 條列知識庫
* [POST /kb](##新增知識庫) - 新增知識庫
* [PATCH /kb/{kbId}](##修改知識庫) - 修改知識庫



## 條列知識庫
**GET /kb**
列出所有知識庫, 要作用中的知識庫條列，自行過瀘 $.inUse=1

### 輸入:
無

### 輸出:
```=json
{
    "return_code": "string",
    "return_message": "string",

    "kb_list": [
        {
            "kbId":   "uuid-kb-000",
            "kbName": "總館知識庫",
            "isUse": 1
        },
        {
            "kbId":   "uuid-kb-001",
            "kbName": "第一分館知識庫",
            "isUse": 0
        }
    ]
    ...
}
```
kbId      string  知識庫ID
kbName    string  知識庫名稱
isUse  int     啟用狀態: 1-啟用, 0-停用

## 新增知識庫
**POST /kb**
新增知識庫

### 輸入:
```=json
{
    "data": {
        "kbName": "總館知識庫",
        "isUse": 1
    }
}
```
### 輸出:
```=json
{
    "return_code": "string",
    "return_message": "string",
}
```
kbName    string  知識庫名稱
isUse  int     啟用狀態: 1-啟用, 0-停用


## 修改知識庫
**PATCH /kb/{kbId}**
新增知識庫

### 輸入:
```=json
{
    "kbId": "uuid-kb-000",

    "data": {
        "kbName": "總館知識庫",
        "isUse": 1
    }
}
```
### 輸出:
```=json
{
    "return_code": "string",
    "return_message": "string",
}
```
kbId      string  知識庫ID
kbName    string  知識庫名稱
isUse  int     啟用狀態: 1-啟用, 0-停用