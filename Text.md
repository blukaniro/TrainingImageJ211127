ImageJ Training 211127 by Ryosuke TAJIMA  
==============  
  

# ダウンロード  
- [ImageJ](https://imagej.nih.gov/ij/)  
- [Fiji](https://imagej.net/software/fiji/downloads)  
  
# 基本操作  
- 画像を開く，ドラッグ，またはOpen image  
- ズームイン，ズームアウト：ショートカットで「+」「^」か「-」を使うと便利  
- 画像の切り抜き：Image>Crop  
  
# Measure
- Oval  
- Polygon  
- line  
- Angle  
- Multi-point  
- 長押しまたは右クリックでメニューが選べる  
- Analyze > Measure  
  
# ROI manager
- Analyze > Tools > ROI Manager  
- 複数の選択をまとめておける  
- 足したり引いたりもできる  
- Show Allを選択するとまとめて解析できる  
- 解析結果はテキストファイルで保存できる  
  
# Analyse particle  
## 基本の二値化  
- バイナリイメージが必要  
- カラーの場合，グレースケール -> 二値化  
    - グレースケール：Image > Type > 8-bit  
    - 二値化：Image > Adjust > Threshold  
    - 二値化はオートでもマニュアルでもできる  
- 「バイナリイメージ問題」がある -> 反転「invert」を使うこともある：Edit > Invert  
- Analyze > Analyze Particle...  
- チェックボックスの左側有用，右側特殊(たまたま)  
- ゴミを取り除く：Edit > Copy&Pasteでできるが改竄になるリスクあり  
- 測定のサイズや真円度に制限をつけられる  
- 複数の「particle」を評価するのには便利  
  
## RGB分解  
- Image > Color > Split channels  
- (例えば)緑のチャンネルを選んで二値化して解析  
- Image calculatorで演算できる: Process > Image calculator  
  
# マクロ  
## 自分の作業を記録する  
- 記録開始，Plugins > Macros > Record...  
- (例えば)RGB分解して，緑を選んで，二値化して解析
    - RGB分解：Image > Color > Split channels  
    - greenを選んで二値化：Image > Adjust > Threshold  
    - もしかしたら反転が必要：Edit > Invert  
    - 解析：Analyze > Analyze Particle  
  
## 記録したマクロをテスト，編集する  
- RecorderでCreateをクリック  
- 同じ画像を開いてRun  
- 違う画像を開いてRun  
- 諸々編集：削除したり，selectImageを追加  
- 使ってみながら修正(一度ではうまくはいかない)  
- 完成したらメモ帳などテキスト編集アプリにコピペ  
- マクロの拡張子はtxt以外に, ImageJmacro, ijmも使える  
  
## マクロを使ってみる
- マクロを読み込ませる：Plugins > Macros > Install...  
- マクロを動かす：Plugins > Macros > 名前(一番下に出てくる)  
  
# 根長測定マクロ  
- [根長測定マクロ](https://github.com/blukaniro/rootmeasure)  
- 解析よりも画像の取得が重要！  
- フォルダ「roots」，「dimeters」を所定の位置に設置する  
    - Macはホームフォルダ(家のアイコン)の直下  
    - Windowsは「C:\Users\コンピュータ名」の「コンピュータ名」の直下  
- マクロを読み込ませて動かす  
- マクロを調整する  
    - 「バイナリイメージ問題」に対処する(L72,L74)  
    - 枠を避けて切り抜く(L8)  
    - 全根長だけ複数のdpiに対応(L14)  
