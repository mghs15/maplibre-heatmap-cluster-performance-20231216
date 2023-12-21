# maplibre-heatmap-cluster-performance-20231216
Maplibre でヒートマップとクラスタリングの描画速度測定

## 結果
コンソールに出力される情報は、以下の内容の CSV となっている。
以下をヘッダとして、CSV ファイルへ転記して保存しておく。
```
testname,event,treatment,start,load,style.load,idle,features_number
```

## 結果の分析方法
R での分析スクリプトを例示。
```
df <- read.csv("./コンソールに出力された結果を転記した.csv")

fm <- df$idle ~ df$treatment
boxplot(fm, xlab="処理", ylab="時間（ミリ秒）")

t.test(fm)
```
