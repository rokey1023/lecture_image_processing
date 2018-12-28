# 課題8レポート
## 原画像の白黒表示
「neko.jpg」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。 以下のコードにより、表示した結果を図1に示す。

```
  ORG = imread('neko.jpg'); % 画像の読み込み 
  ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
  imagesc(ORG); colormap(gray); colorbar; % 画像の表示 
```

![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai8/k8_1.png)  
図1 原画像  

## 閾値を128にした場合の二値化
以下のコードにより、二値化を行う。次に、その結果を図2に表示する。

```
  IMG = ORG > 128; % 閾値128で二値化  
```

![閾値128の二値化](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai8/k8_2.png)  
図2 閾値128での二値化画像 

## ラベリング
以下のコードにより、ラベリングを行う。その結果を図3に表示する。

```
  IMG = bwlabeln(IMG);  
  imagesc(IMG); colormap(jet); colorbar; % 画像の表示  
```

![ラベリングの結果](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai8/k8_3.png)  
図3 ラベリングの結果 
