# 安裝輸入方案

## 輸入方案是什麼？

> 若要講，輸入引擎是跨輸入法的通用程序，_輸入方案／schema_ 即是那差異的部份。
> [認識 La Rime](https://github.com/rime/home/wiki/Introduction#%E6%A6%82%E5%BF%B5)

Rime引擎包含了許多通用的功能，如偵測按鍵、輸入碼分段、查找字典、候選字過濾……；而輸入方案則是將這些功能給串起來，進而實現出各式各樣的輸入方式。

要使用一個輸入方案，你需要安裝它的配置文件（`×××.schema.yaml`及`×××.dict.yaml`）到用戶資料夾中，並透過「[部署](04%20deploy.md)」使之生效。

## 方法1: 自己上網下載

你可以在網上找到一些寫好的輸入方案，[這裡有一些由官方維護的輸入方案](https://github.com/rime/plum#packages)。找到你要的輸入方案後將那些yaml檔下載下來，並複製到你的用戶資料夾中，最後再「部署」就能用了。

> [!TIP]
> 某些輸入方案會包含`.lua`檔來實現較複雜的功能，這些檔案要複製到`用戶資料夾/lua/`這個資料夾中。

## 方法2: 使用東風破

東風破是用來安裝Rime輸入方案的shell script。它可以將放在github上的輸入方案下載下來並安裝到用戶資料夾中。使用東風破後記得要「部署」。

### 小狼毫

「輸入法設定」->「獲取更多輸入法」開啟東風破的文字互動介面，之後再輸入要安裝的package的名稱。

### Bash （如：Linux、MaxOS、WSL）

```shell
git clone https://github.com/rime/plum
cd plum

# rime_dir變數指定用戶資料夾的位置，rime-install腳本則是用來安裝輸入方案
# 如果用的發行版是「鼠鬚管」或「ibus-rime」，則可以不用指定`rime_dir`
env rime_dir=/path/to/user/folder ./rime-install <package-name>
```

### Package的名稱

`user/repo`：指定github上的用戶名和庫的名稱

`user/repo@branch`：同上，但指定安裝特定分支的檔案

`rime-repo`：代表user為rime的輸入方案，這些方案是由官方維護的，例如[這些](https://github.com/rime/plum/tree/master?tab=readme-ov-file#packages)：

> ```shell
> # 從 https://github.com/rime/rime-luna-pinyin 下載輸入方案
> rime-install luna-pinyin
> ```