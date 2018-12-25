# 課題5レポート
## 原画像の白黒表示
「neko.png」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。 以下のコードにより、表示した結果を図1に示す。

```
  ORG=imread('neko.png'); %   
  ORG = rgb2gray(ORG); colormap(gray); colorbar;    
  imagesc(ORG); axis image;   
```

![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai5/k5_1.png)  
図1　原画像の白黒表示

## 判別分析法
for分を用い閾値を1から255まで変化させ、クラス間分散とクラス内分散の比が最大になる閾値tを求める。

```
  H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納  
  myu_T = mean(H);  
  max_val = 0;  
  max_thres = 1;  
  for i=1:255 
  C1 = H(1:i); %ヒストグラムを2つのクラスに分ける 
  C2 = H(i+1:256);  
  n1 = sum(C1); %画素数の算出 
  n2 = sum(C2); 
  myu1 = mean(C1); %平均値の算出  
  myu2 = mean(C2);  
  sigma1 = var(C1); %分散の算出  
  sigma2 = var(C2); 
  sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出  
  sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出  
  if max_val<sigma_B/sigma_w  
  max_val = sigma_B/sigma_w;  
  max_thres =i; 
  end;  
  end;  
```

閾値がtのときの閾値処理の結果を図2に示す。

![判別分析法](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai5/k5_1.png)  
図2　閾値処理の結果
