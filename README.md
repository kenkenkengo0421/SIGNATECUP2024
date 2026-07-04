# [【復刻版】SIGNATE Cup 2024](https://user.competition.signate.jp/ja/competition/detail/?competition=943670f905894d018078ff5605ffe059)

※このリポジトリは、SIGNATEの「旅行成約予測コンペ」への参加目的で作成したコードおよびデータです。
（特別規約に基づき公開しています）
 
>## 概要
>### 旅行会社の保有する顧客データ（属性や志向、営業担当との接触履歴等）を元に、旅行パッケージの成約率を予測するモデルを構築する。
 
 <br>
 
 >## 評価方法
 
>精度評価は、評価関数AUC(Area Under the Curve)を使用します。
>AUCはROC曲線の下の面積を表し、0から1の値を取ります。
AUCの値が1に近いほど、モデルの予測精度が高いことを示します。
一般に、ランダムな予測ではAUCの値は0.5となります。
AUCの値が0.5を下回る場合、モデルの予測は逆に外れている可能性が高いことを示します。
 
 [機械学習における評価プロセス（ROC-AUC）のまとめ](https://github.com/kenkenkengo0421/Binary-Classification-with-a-Bank-Dataset/blob/main/memo.md)

 
 
 
 
 
 
 ># データ内容
 
```
   1                      id  : 顧客ID : int64   
   2                     Age  : 顧客の年齢 : str   
   3           TypeofContact  : 顧客への連絡・接触方法 : str   
   4                CityTier  : 都市層(1>2>3) : int64   
   5         DurationOfPitch  : 営業担当者による顧客への商品のセールス時間 : str   
   6              Occupation  : 顧客の職業 : str   
   7                  Gender  : 顧客の性別 : str   
   8  NumberOfPersonVisiting  : 予定している旅行の同行者の数	 : int64   
   9       NumberOfFollowups  : セールス後に営業担当者が行ったフォローアップの回数 : float64   
   10          ProductPitched : 営業担当者のセールスした商品の種類 : str   
   11   PreferredPropertyStar : 顧客の希望するホテルのランク : float64   
   12           NumberOfTrips : 顧客の年間旅行数 : str   
   13                Passport : パスポートの所持(0: 不所持、1: 所持) : int64   
   14  PitchSatisfactionScore : 営業担当者のセールストークに対する顧客の満足度 : int64   
   15             Designation : 顧客の役職 : str   
   16           MonthlyIncome : 顧客の月収 : str   
   17           customer_info : 顧客の情報のメモ(婚姻状況や車の有無、旅行への子どもの同伴の有無) : str   
 
 =============================================================================================
         ProdTaken(目的変数): 商品の契約状態(0:不成約、1:成約) : int64 


 
```





>[年齢についての調査_sub_age.ipynb](https://github.com/kenkenkengo0421/SIGNATECUP2024/blob/main/sub_/sub_age.ipynb)
>
>
>[顧客の情報についての調査_sub_customer_info.ipynb](https://github.com/kenkenkengo0421/SIGNATECUP2024/blob/main/sub_/sub_customer_info.ipynb)
>
>
>[営業担当者による顧客への商品のセールス時間についての調査_sub_DurationOfPitch.ipynb](https://github.com/kenkenkengo0421/SIGNATECUP2024/blob/main/sub_/sub_DurationOfPitch.ipynb)



# スコア

```
V0.0
roc-auc :  0.8234335680793671
SIGNATE_public : 0.786826013700816

V1.0
roc-auc :  0.8271448485616526
SIGNATE_public : 0.8086726759862505

V2.0
roc-auc :  0.8299690424896355
SIGNATE_public : 0.8075962992111078 

V3.0
roc-auc :  0.8309285442728607
SIGNATE_public : 0.807742340281102

V4.0
roc-auc :  0.8359432988757536
SIGNATE_public : 0.8093650188365936

V5.0
roc-auc :  0.8414106486594131
SIGNATE_public : 0.8124048366638811

V6.0
roc-auc :  0.8522910368050401
SIGNATE_public : 0.8043590554929021　↓

V7.0
roc-auc :  0.8522910368050401
SIGNATE_public : 0.8043590554929021 （変化なし）
```
<br>
<br>
<br>

># 環境構築(windows)


zip解凍
```PowerShell
 Expand-Archive -Path .\data.zip
```

<br>

解凍後の中身移動
```PowerShell
mv .\data\data\* .\data\
```

<br>

いらんフォルダ消す
```PowerShell
rm -r -fo .\data\data
```

<br>

venv構築
```PowerShell
py -m venv .venv
```
<br>

venv有効化
```PowerShell
.\.venv\Scripts\Activate.ps1
```
<br>

必要pipinstall
```PowerShell
pip install -r requirements.txt
```

<br>

nb起動
```PowerShell
jupyter lab
```

<br>
