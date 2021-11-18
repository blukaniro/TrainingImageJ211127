ImageJ Training 211127 by Ryosuke TAJIMA  
==============  
  

# ダウンロード  
[ImageJ](https://imagej.nih.gov/ij/)  
[Fiji](https://imagej.net/software/fiji/downloads)  
  
# 基本操作  
- ズームイン，ズームアウト：ショートカットで[+]か[-]が便利  
- 画像を開く，ドラッグ，またはOpen image  
- 画像の切り抜き：Image>Crop  
  
# Measure
- Rectangle  
- Oval  
- Polygon  
- line  
- Angle  
- Multi-point  
- 長押しまたは右クリックでメニューが選べる  
- Analyze > Measure  
  
# ROI manager
- Analyze > Tools > ROI Manager  
- 複数の解析をまとめておける  
  
# Analyse particle  
## 基本の二値化  
- バイナリイメージが必要  
- カラーの場合，グレースケール -> 二値化  
- グレースケール：Image > Type > 8-bit  
- 二値化：Image > Adjust > Threshold  
- 反転「invert」を使う場合もある(バイナリイメージ問題)：Edit > Invert  
- Analyze > Analyze Particle...  
- チェックボックスの左側有用，右側特殊(たまたま)  
- サイズや真円度に制限をつけられる  
- ゴミを取り除く：Edit > Copy&Paste (改竄疑惑リスクあり)  
  
## RGB分解  
- Image > Color > Split channels  
- (例えば)緑のチャンネルを選んで二値化して解析  
- Image calculatorで加減乗除できる: Process > Image calculator  
- Image > Type > RGB stackでもRGB分解できる(1つのウィンドウに表示)  
  
# マクロ  
## 自分の作業を記録する  
- 記録開始，Plugins > Macros > Record...  
- (例えば)RGB分解して，緑を選んで，二値化して解析
    - RGB分解：Image > Color > Split channels  
    - greenを選んで二値化：Image > Adjust > Threshold  
    - もしかしたら反転が必要：Edit > Invert  
    - 解析：Analyze > Analyze Particle  
  
## 記録したマクロをテスト，調整する  
- RecorderでCreateをクリック  
- 同じ元画像を開いてRun  
  
## マクロを(本格的に)編集する
- メモ帳などテキスト編集アプリにコピペ  
- 諸々編集：selectImage，rename等追加  
- できたら使ってみながら修正(一度ではうまくはいかない・・・)  
  
## マクロを使ってみる
- マクロを読み込ませる：Plugins > Macros > Install...  
- マクロの拡張子はtxt, ImageJmacro, ijmなら使える  
- マクロを動かす：Plugins > Macros > 名前(一番下に出てくる)  
  
# 根長測定マクロ  
- [根長測定マクロ](https://github.com/blukaniro/rootmeasure)  
- 上記につきるが・・・  
- 解析よりも画像の取得が重要！  
- フォルダ(roots, dimeters)を所定の位置に設置する  
- Macはホームフォルダ(家のアイコン)の直下  
- Windowsは「C:\Users\コンピュータ名」の「コンピュータ名」の直下  
- マクロを読み込ませて動かす  
- マクロを調整する  
    - バイナリイメージ問題に対処する(L77,79,117,119)  
    - 枠を避けて切り抜く(L3-6)  
    - 全根長だけ複数のdpiに対応(L82)  
  