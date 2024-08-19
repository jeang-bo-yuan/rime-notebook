# RIME

開源且可客製化的輸入法引擎。

# 下載發行版

不同的作業系統上有不同的發行版來將RIME的核心功能和作業系統接上。

| OS | 發行版  |
|----|------|
|Windows | 小狼毫|
|MacOS | 鼠鬚管|
|Linux| ibus-rime |
|Android | 同文（Trime） |

小狼毫和鼠鬚管的安裝器可在[RIME的官網](https://rime.im/download/)找到。

如果要安裝ibus-rime，可以參考[這篇](01-1%20ibus-rime.md)。

如果要安裝Trime，可以從[F-droid](https://f-droid.org/zh_Hant/)上下載。
> [!Note]
> 因為Trime沒有自帶`default.yaml`和`essay.txt`，所以需要自行下載。
> 你可以去github上下載[prelude](https://github.com/rime/rime-prelude)和[essay](https://github.com/rime/rime-essay)這兩個package，然後複製到[用戶資料夾](02%20important%20folder.md#用戶資料夾)。
> 
> 如果你有用Termux的話，也可以直接用[東風破](03%20install%20schema.md#方法2%20使用東風破)安裝：`rime-install prelude essay`