# 課題9レポート
## 原画像の白黒表示
「neko.jpg」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。 以下のコードにより、表示した結果を図1に示す。

```
  ORG = imread('neko.jpg'); % 画像の読み込み 
  ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
  imagesc(ORG); colormap(gray); colorbar; % 画像の表示 
```

![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai9/k9_1.png)  
図1 原画像

## ノイズ添付
以下のコードにより、原画像にノイズを添付する。次に、その結果を図2に示す。

```
  ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付  
```

![ノイズ添付した画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai9/k9_2.png)  
図2 ノイズ添付した画像

## 平滑化フィルタで雑音除去
以下のコードにより、平滑化フィルタでの雑音除去を行う。次に、その結果を図3に示す。

```
  IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去  
```

![平滑化フィルタで雑音除去した画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai9/k9_3.png)  
図3 平滑化フィルタで雑音除去した画像

## メディアンフィルタで雑音除去
以下のコードにより、メディアンフィルタでの雑音除去を行う。次に、その結果を図4に示す。

```
  IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去 
```

![メディアンフィルタで雑音除去した画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai9/k9_4.png)  
図4 メディアンフィルタで雑音除去した画像

## フィルタの設計と適用
以下のコードにより、フィルタの設計、適用を行う。次に、その結果を図5に示す。

```
  f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計  
  IMG = filter2(f,IMG,'same'); % フィルタの適用  
```

![フィルタの適用をした画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai9/k9_5.png)  
図5 フィルタの適用をした画像
