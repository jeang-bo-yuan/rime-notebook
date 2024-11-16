如果要讓東風破能夠安裝你的輸入方案，你需要：

- 將輸入方案上傳到github上
- 撰寫配方（`recipe.yaml`） *(optional)*

如果沒有`recipe.yaml`，東風破會安裝github庫中的`*.schema.yaml`、`*.dict.yaml`、`*.txt`、`*.gram`、`opencc/*.*`到用戶資料夾下

# 寫法

> [!Note]
> 因為東風破是用簡易的sed指令來讀yaml檔，所以在讀取時並沒有百分百遵守yaml的語法。
> 
> 例如：注釋不能放在行尾且要跟著縮排

```yaml
# 若檔名為 ***.recipe.yaml，則 Rx 後要填 ***
# 若檔名為 recipe.yaml，則 Rx 後的內容不強制
recipe:
  Rx: 名字

# 從網上下載檔案到package的目錄，每一項為一個url
download_files:
  - 要下載的檔案1
  - 要下載的檔案2

# 要從 package的目錄 安裝到 用戶資料夾 的檔案
# 每一項為一個檔名（可包含萬用字元）
install_files:
  - 要安裝的檔案1
  - 要安裝的檔案2
```

# 範例

我在行列輸入方案寫的[recipe.yaml](https://github.com/jeang-bo-yuan/rime-array-extended/blob/master/recipe.yaml)。