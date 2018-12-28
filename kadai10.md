# 課題10レポート
## 原画像の白黒表示
「neko.jpg」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。 以下のコードにより、表示した結果を図1に示す。

```
  ORG = imread('neko.jpg'); % 原画像の入力  
  ORG = rgb2gray(ORG); %カラーからグレイへの変換  
  imagesc(ORG); colormap('gray'); colorbar;% 画像表示 
```

![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai10/k10_1.png)  
図1 原画像

## プレウィット法
以下のコードにより、プレウィット法によるエッジ抽出を行う。その結果を図2に示す。

```
  IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法)   
```

![プレウィット法によるエッジ抽出](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai10/k10_2.png)  
図2 プレウィット法によるエッジ抽出

## ソベル法
以下のコードにより、ソベル法によるエッジ抽出を行う。その結果を図3に示す。

```
   IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
```

![ソベル法によるエッジ抽出](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai10/k10_3.png)  
図3 ソベル法によるエッジ抽出

## キャニー法
以下のコードにより、キャニー法によるエッジ抽出を行う。その結果を図4に示す。

```  
  IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法） 
```

![キャニー法によるエッジ抽出](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai10/k10_4.png)  
図4 キャニー法によるエッジ抽出
