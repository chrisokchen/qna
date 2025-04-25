# 諮詢服務系統 RDB Schema

- [KnowledgeBase(知識庫)](##KnowledgeBase(知識庫))
- [DocBase(文件集)](##DocBase(文件集))
- [ReferChunk(資料塊)](##ReferChunk(資料塊))
- [QABase(問答集)](##QABase(問答集))
- [QAotherQ(更多問法)](##QAotherQ(更多問法))

## KnowledgeBase(知識庫)

|欄位名稱|標題|資料型別|長度|鍵值|Null|備註|
|-----|-----|-----|-----|-----|-----|-----|
|kbId|知識庫ID|uniqueidentifier||Y||
|kbName|知識庫名稱|nvarchar|50|||
|isUse|啟用狀態|bit|||預設:1-啟用|
|iCreator|建立者|nvarchar|60|||||
|dAddDate|建立日期|smalldatetime|4||||
|iEditor|編修者|nvarchar|60|||||
|dEditDate|編修日期|smalldatetime|4||||

## DocBase(文件集)

|欄位名稱|標題|資料型別|長度|鍵值|Null|備註|
|-----|-----|-----|-----|-----|-----|-----|
|kbId|知識庫ID|uniqueidentifier||||
|docId|文件guid|uniqueidentifier||Y||
|docTitle|標題/檔名|nvarchar|50|||
|docType|文件類型|nvarchar|50|||txt, md, pdf, doc, url
|docUri|Uri/Url|nvarchar|300|||url型是url, 其它型是 實體檔案uri|
|totalChunk|資料塊總數|int|
|iCreator|建立者|nvarchar|60|||||
|dAddDate|建立日期|smalldatetime|4||||
|iEditor|編修者|nvarchar|60|||||
|dEditDate|編修日期|smalldatetime|4||||


## ReferChunk(資料塊)

|欄位名稱|標題|資料型別|長度|鍵值|Null|備註|
|-----|-----|-----|-----|-----|-----|-----|
|docId|文件guid|uniqueidentifier||||
|seqNum|此文件的第幾塊|int|
|chunkId|資料塊guid|uniqueidentifier||Y||
|content|文字資料內容|nvarchar(MAX)|
|modDate|異動日|smalldatetime||||更新VDB用|
|modType|異動類型|nvarchar|50|||UDA|
|modState|異動狀態|int||||0:待異動, 1:完成|

## QABase(問答集)

|欄位名稱|標題|資料型別|長度|鍵值|Null|備註|
|-----|-----|-----|-----|-----|-----|-----|
|kbId|知識庫ID|uniqueidentifier||||
|qaId|QAguid|uniqueidentifier||Y||
|qaTitle|代表問題/標題|nvarchar|300|||
|qaAnswer|答案|nvarchar(MAX)|||Y|
|catL1|主分類|nvarchar|50||Y|
|catL2|小分類|nvarchar|50||Y|
|status|狀態|nvarchar|50||Y|待審核0、啟用中1、已停用9|
|avBegin|上架日|smalldatetime|||Y|有填才上架|
|avEnd|下架日|smalldatetime|||Y|沒填不下架|
|iCreator|建立者|nvarchar|60|||||
|dAddDate|建立日期|smalldatetime|4||||
|iEditor|編修者|nvarchar|60|||||
|dEditDate|編修日期|smalldatetime|4||||
|goodCount|int|
|badCount|int|
|modDate|異動日|smalldatetime||||更新VDB用|
|modType|異動類型|nvarchar|50|||UDA|
|modState|異動狀態|int||||0:待異動, 1:完成|

## QAotherQ(更多問法)

|欄位名稱|標題|資料型別|長度|鍵值|Null|備註|
|-----|-----|-----|-----|-----|-----|-----|
|oqId|其它問法id|int||unique|||
|qaId|QAguid|uniqueidentifier||F||
|otherQ|更多問法|nvarchar|300|||
|iCreator|建立者|nvarchar|60|||||
|dAddDate|建立日期|smalldatetime|4||||
|iEditor|編修者|nvarchar|60|||||
|dEditDate|編修日期|smalldatetime|4||||
|modDate|異動日|smalldatetime||||更新VDB用|
|modType|異動類型|nvarchar|50|||UDA|
|modState|異動狀態|int||||0:待異動, 1:完成|