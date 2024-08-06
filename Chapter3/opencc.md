OpenCC起初是用來做繁簡轉換的。

# OpenCC 設定檔

json設定檔：
```json
{ 
  "name": "名字",
  "segmentation": { 
    "type": "mmseg", 
    "dict": { "type": "text", "file": "字典.txt" } 
  },
  "conversion_chain": [{ 
    "dict": { "type": "text", "file": "字典.txt" }
  }] 
}
```

txt字典（寫法為`原本的字 <tab> 轉換後的字 <空格> 另一個字`），[如](https://github.com/rime/rime-emoji/blob/master/opencc/emoji_word.txt)：
```
一小會	一小會 ☝🏻️
一摞書	一摞書 📚️
```

# 在Rime中啟用

首先要在engine中新增一個`simplifier`：
```yaml
engine:
  # ...
  filters:
    # ...
    - simplifier@foo_name
```

然後新增一個開關來控制是否開啟，如：
```yaml
switches:
  - name: foo_option
    reset: 1  # (optional) 指定預設值
    states: [ "foo OFF", "foo ON"]
```

最後設定使用的json檔（[詳細設定](https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md#%E4%BA%94simplifier)），如：
```yaml
foo_name:
  opencc_config: foo.json
  option_name: foo_option
  tips: none
  inherit_comment: true
```

---

# Reference

- <https://www.cnblogs.com/skylee03/p/15636203.html>