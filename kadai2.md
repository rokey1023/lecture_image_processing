# 課題2レポート
## 原画像の白黒表示
「neko.png」を原画像とする。縦600画素、横400画素による長方形のディジタルカラー画像である。
以下のコードにより、表示した結果を図1に示す。
    ORG=imread('nuko.png'); %   
    ORG = rgb2gray(ORG); colormap(gray); colorbar;  
    imagesc(ORG); axis image;   
![原画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai2/k2_1.png?raw=true)
図1　原画像

## 2階調表示
以下のコードにより、輝度値が128より高い画素を1(白)、それ以外を0(黒)とした2階調の画像が生成される。
     IMG = ORG>128;     
生成された2階調の画像を図2に示す。
![2階調の画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai2/k2_2.png?raw=true)
図2　2階調の画像

## 4階調表示
以下のコードにより、輝度値が192より高い画素を3(白)、128より高い画素を2、64より高い画素を1、それ以外を0(黒)とした4階調の画像が生成される。
    IMG0 = ORG>64;  
    IMG1 = ORG>128; 
    IMG2 = ORG>192; 
    IMG = IMG0 + IMG1 + IMG2;   
生成された4階調の画像を図3に示す。
![4階調の画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai2/k2_3.png?raw=true)
図3　4階調の画像


## 8階調表示
以下のコードにより、輝度値が224より高い画素を7(白)、192より高い画素を6、160より高い画素を5、128より高い画素を4、96より高い画素を3、64より高い画素を2、32より高い画素を1、それ以外を0(黒)とした8階調の画像が生成される。
    IMG0 = ORG>32;  
    IMG1 = ORG>64;  
    IMG2 = ORG>96;  
    IMG3 = ORG>128; 
    IMG4 = ORG>160; 
    IMG5 = ORG>192; 
    IMG6 = ORG>224; 
    IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;   
生成された4階調の画像を図4に示す。
![2階調の画像](https://github.com/rokey1023/lecture_image_processing/blob/master/result/kadai2/k2_4.png?raw=true)
図4　8階調の画像
