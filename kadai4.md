# 課題4レポート
## 原画像の白黒表示
「neko.png」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。 以下のコードにより、表示した結果を図1に示す。

  ORG=imread('neko.png'); %   
  ORG = rgb2gray(ORG); colormap(gray); colorbar;  
  imagesc(ORG); axis image; 

![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai4/k4_1.png) 
図1　原画像の白黒表示

## ヒストグラムの表示
以下のコードにより、画像のヒストグラムを表示する。

  imhist(ORG); % ヒストグラムの表示  

ヒストグラムを図2に示す。
![ヒストグラム](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai4/k4_2.png) 
図2　ヒストグラム
