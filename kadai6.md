# 課題6レポート
## 原画像の白黒表示
「neko.png」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。 以下のコードにより、表示した結果を図1に示す。

```
  ORG=imread('neko.png'); 
  ORG = rgb2gray(ORG);
  imagesc(ORG); colormap(gray); colorbar; 
```
![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai6/k6_1.png)  
図1　原画像の白黒表示

## 閾値を128しての二値化
以下のコードにより、二値化出来る。次に、閾値を128として二値化した画像を図2に示す。

```
  IMG = ORG>128; % 128による二値化  
```

![閾値を128しての二値化画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai6/k6_2.png)  
図2　閾値を128しての二値化画像

## ディザ法による二値化
以下のコードにより、ディザ法による二値化が行える。次にディザ法によって二値化した画像を図3に示す。

```
  IMG = dither(ORG); % ディザ法による二値化 
```

![ディザ法による二値化画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai6/k6_3.png)  
図　ディザ法による二値化画像
