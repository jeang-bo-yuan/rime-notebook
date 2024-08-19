# 共享資料夾

> 包含預設輸入方案的源文件。 這些文件屬於 Rime 所發行軟件的一部份，在訪問權限控制較嚴格的系統上對用戶是只讀的，因此**謝絕軟件版本更新以外的任何修改**—— 一旦用戶修改這裏的文件，很可能影響後續的軟件升級或在升級時丟失數據。
> [Rime 中的數據文件分佈及作用](https://github.com/rime/home/wiki/RimeWithSchemata#rime-%E4%B8%AD%E7%9A%84%E6%95%B8%E6%93%9A%E6%96%87%E4%BB%B6%E5%88%86%E4%BD%88%E5%8F%8A%E4%BD%9C%E7%94%A8)

|發行版  | 共享資料夾 |
|----    |------     |
|小狼毫| `安裝目錄\data` |
|鼠鬚管| `/Library/Input Methods/Squirrel.app/Contents/SharedSupport/` |
|ibus-rime | `/usr/share/rime-data/` |
|同文（Trime） | 應該在`/data/data/...`，一般沒辦法存取 |

> [!Note]
> 雖然Trime的設定中可以設定「共享資料夾」，但那是指「回廠」時檔案要存在哪。

---

# 用戶資料夾

用戶資料夾是用來存放全域設定文件（`default.yaml`）和輸入方案（`×××.schema.yaml`及`×××.dict.yaml`）的文件夾；每個發行版通常也有自己的配置文件，如Trime的`trime.yaml`主要是用來設定虛擬鍵盤的外觀。

| 發行版  | 用戶資料夾 | 發行版的配置文件 |
|------|---|---|
| 小狼毫| `%AppData%\Rime` | `weasel.yaml` |
| 鼠鬚管| `~/Library/Rime/` | `squirrel.yaml` |
| ibus-rime | `~/.config/ibus/rime/` | `ibus_rime.yaml` |
| 同文（Trime） | `/storage/emulated/0/rime` | `trime.yaml` |

## 常見檔案

檔案名稱 | 用途
-----|-----
📑<br>default.yaml | 全域設定
📑<br>default.custom.yaml | default.yaml的[補靪](../Chapter2/01%20file_format.md#補靪文件)
📑<br>×××.schema.yaml | ×××輸入法的定義
📑<br>×××.dict.yaml | ×××字典，內含×××輸入法的字碼表

🗂rime/build資料夾：
內含「『部署』後產生的字典」和「配置文件的副本」，**你不應該修改這些檔案**。

下方三個檔案是在「部署」輸入法後會產生的二進制字典：

檔案名稱|用途
--- | ---
📑<br>×××.prism.bin | ×××輸入法的**棱鏡**<br>包含了「拼寫運算」轉換的結果
📑<br>×××.reverse.bin | ×××字典的**反查字典**<br>從「文字」反查「字碼」
📑<br>×××.table.bin | ×××字典的**固態字典**<br>以「字碼」查詢「文字」

🗂rime/×××.userdb：
×××字典的用戶字典，紀錄用戶打字的習慣並據此調整候選字順序

🗂rime/opencc：
內含繁簡轉換組建

---

# Reference

- [Rime中的數據文件分佈及作用](https://github.com/rime/home/wiki/RimeWithSchemata#rime-%E4%B8%AD%E7%9A%84%E6%95%B8%E6%93%9A%E6%96%87%E4%BB%B6%E5%88%86%E4%BD%88%E5%8F%8A%E4%BD%9C%E7%94%A8)
- [Trime User Guide](https://github.com/osfans/trime/wiki/UserGuide)