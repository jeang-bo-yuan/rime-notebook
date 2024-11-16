方案定義的副檔名為`.schema.yaml`，是用來描述輸入方案具體功能的文檔。

首先會包含`schema`來描述輸入方案的資訊：
``` yaml
# ***.schema.yaml
schema:
  schema_id: "***"         # 內部用的id，和檔名相同
  name: "顯示在方案選單的名字"
  version: "版本號"
  author:
    - 作者 <email>
  description: |
    說明
  dependencies:            # optional
    - 依賴的輸入方案的id
```

接著會有`switches`來定義可用的開關，如：
```yaml
switches:
  # processors/ascii_composer 使用的開關
  # 有這個才能切換中英文
  - name: ascii_mode
    reset: 0   # 設定預設值
    states: [ 中文, 西文 ]

  # 切換全角／半角
  - name: full_shape
    states: [ 半角, 全角 ]
    
  # filters/simplifier 使用的開關
  - name: simplification
    states: [ 漢字, 汉字 ]

  # 是否在候選字中顯示 罕用字(?
  - name: extended_charset
    reset: 1
    states: [ 常用, 增廣 ]

  # processors/punctuator 使用的開關
  # 是否啟用 punctuator
  - name: ascii_punct
    states: [ 。，, ．， ]
```

以及`menu`（如果沒有會使用`default.yaml`中的），如：
```yaml
menu:
  alternative_select_labels: [ ①, ②, ③, ④, ⑤, ⑥, ⑦, ⑧, ⑨ ]  # 修改候選標籤
  alternative_select_keys: ASDFGHJKL #如編碼字符佔用數字鍵則須另設選字鍵
  page_size: 9 # 每頁最多的候選字個數
```
