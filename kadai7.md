# 課題7レポート
## 原画像の白黒表示
「neko.jpg」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。 以下のコードにより、表示した結果を図1に示す。

```
  ORG = imread('neko.jpg'); % 画像の読み込み
  ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
  imagesc(ORG); colormap(gray); colorbar; % 画像の表示
```

![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai7/k7_1.png)  
図1 原画像  

## 濃度ヒストグラムの表示
以下のコードにより、濃度ヒストグラムを表示する。次に、表示した結果を図2に示す。

```
  imhist(ORG); % 濃度ヒストグラムを生成、表示 
```

![濃度ヒストグラム](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai7/k7_2.png)  
図2 濃度ヒストグラム 

## ダイナミックレンジの拡大
以下のコードにより、濃度ヒストグラムのダイナミックレンジの拡大を行う。次に、変更後の画像を図3に示す。

```
  ORG = double(ORG);  
  mn = min(ORG(:)); % 濃度値の最小値を算出  
  mx = max(ORG(:)); % 濃度値の最大値を算出  
  ORG = (ORG-mn)/(mx-mn)*255; 
```

![濃度ヒストグラム](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai7/k7_4.png)  
図3 ダイナミック拡大後の画像

## ダイナミックレンジ拡大後の濃度ヒストグラムの表示
以下のコードにより、表示を行う。変更後のヒストグラムを図3に示す。

```
  ORG = uint8(ORG);   
  imhist(ORG);  
```

![変更後の濃度ヒストグラム](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai7/k7_3.png)  
図4 ダイナミック拡大後の濃度ヒストグラム 

上記のコードのunit8()では、符号なし8ビット整数に変換を行っている。
