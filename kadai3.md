# 課題3レポート
## 原画像の白黒表示
「neko.png」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。 以下のコードにより、表示した結果を図1に示す。  

```
  ORG=imread('neko.png'); % 
  ORG = rgb2gray(ORG); colormap(gray); colorbar;  
  imagesc(ORG); axis image; 
```

![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai3/k3_1.png)  
図1　原画像の白黒表示

## 閾値処理
以下のプログラムによって輝度値が64より高い画素が1(白)，それ以外の画素が0(黒)に変換される。 
```
  IMG = ORG>64; 
```
変換された画像を図2に示す。

![閾値処理された画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai3/k3_2.png)  
図2　閾値処理された画像  

閾値を96、128、192にした場合の画像を図3、図4、図5に示す。  

![96で閾値処理された画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai3/k3_3.png) 
図3　96で閾値処理された画像 

![128で閾値処理された画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai3/k3_4.png)  
図4　128で閾値処理された画像  

![196で閾値処理された画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai3/k3_5.png)  
図5　192で閾値処理された画像  

上記の画像のように閾値を高く設定するほど0と判定される画素数が増えるため、画像に黒い部分が多くなる。
