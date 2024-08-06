# 檔案格式

配置文件的格式為YAML，文字編碼為UTF-8，

> Rime 中所有文本文檔，均要求以 UTF-8 編碼，並建議使用 UNIX 換行符（LF）。
> 
> 鑑於一些文本編輯器會爲 UTF-8 編碼的文件添加 BOM 標記，爲防止誤將該字符混入文中， 不要從文件的第一行開始正文，而請在該行行首以 # 記號起一行註釋。
> 
> [Rime with Text Files](https://github.com/rime/home/wiki/RimeWithSchemata#rime-with-text-files)

---

# 補靪文件

要修改配置文件時，除了直接修改原文件外，還能透過補靪（副檔名：`.custom.yaml`）的方式來修改。

發行版更新時，原文件可能會一起更新，其中的修改將會一併丟失；但補靪並不會被一起更新，所以能夠保留修改的內容。

對於`default.yaml`和`＊＊＊．schema.yaml`而言，預設的補靪文件名稱為`default.custom.yaml`與`＊＊＊.custom.yaml`。
字典文件 _~~預設不會~~_ 不能載入補靪文件。

下面展示了補靪文件應該怎麼寫：
```yaml
# 補靪
patch:
  "一級設定項/二級設定項/三級設定項": 新的設定值
  "另一個設定項": 新的設定值
  "再一個設定項": 新的設定值
  "含列表的設定項/@n": 列表第 n 個元素新的設定值，從 0 開始計數
  "含列表的設定項/@last": 列表最後一個元素新的設定值
  "含列表的設定項/@before 0": 在列表第一個元素之前插入新的設定值（不建議在補靪中使用）
  "含列表的設定項/@after last": 在列表最後一個元素之後插入新的設定值（不建議在補靪中使用）
  "含列表的設定項/@next": 在列表最後一個元素之後插入新的設定值（不建議在補靪中使用）
  "含列表的設定項/+": 與列表合併的設定值（必須爲列表）
  "含字典的設定項/+": 與字典合併的設定值（必須爲字典，注意 YAML 字典的無序性）
```

---

# Reference

- [Rime定製指南](https://github.com/rime/home/wiki/CustomizationGuide)