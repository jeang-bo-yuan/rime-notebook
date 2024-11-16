字典是用來將「字碼」和「文字」對應在一起的表格，當輸入特定的「字碼」後Rime會用一個稱作**translator**的組件來將它轉成要上屏的「文字」。

字典文件的副檔名為`.dict.yaml`，其檔案格式為：
``` yaml
# ***.dict.yaml
---
name: "***"               # 要和檔名相同
version: "版本號"
sort: "候選字排序方式"      # original:依字典中的順序     by_weight:依權重
import_tables:            # optional
  - 引入其他字典的內容
...

# 從這之後，每一行都是一組映射關係
# 文字 <Tab> 字碼
你	ni
我	wo

# 文字 <Tab> 字碼 <Tab> 權重
的	de	99%
的	di	1%
地	de	10%
地	di	90%

# 詞組
我的
我的天
天地	tian di
```


> [!Note]- 候選字的排序
> 上方的`sort`是用來設定**同樣字碼**的文字應該如何排序，以上面的字典為例：
> - 如果是`original`，則輸入`di`後，「的」會排在「地」的前面
> - 但如果是`by_weight`，則輸入`di`後，「地」會排在「的」的前面
>
> ---
> 
> 如果在translator的設定中將`enable_completion`設為true，候選字中會出現自動補齊後的文字，這些文字的排序方式則是：
> 1. 字碼長度少的在前面
> 2. 字碼一樣長時，依字碼的字典序排列
> 3. 字碼完全一樣時，依`sort`決定

---

# Reference

- [碼表與詞典](https://github.com/rime/home/wiki/RimeWithSchemata#%E7%A2%BC%E8%A1%A8%E8%88%87%E8%A9%9E%E5%85%B8)
