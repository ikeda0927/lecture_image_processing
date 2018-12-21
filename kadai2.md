# 課題2レポート

森の中で撮った「im.png」を原画像とする．この画像は縦2160画像，横3840画素による長方形のディジタルカラー画像である．

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/im.png?raw=true)  
図1


clear; % 変数のオールクリア

ORG=imread('im.png'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示
pause; % 一時停止

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理2_1.png?raw=true)  
図2


% ２階調画像の生成
IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;


表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理2_2.png?raw=true)  
図3


% ４階調画像の生成
IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;


表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理2_3.png?raw=true)  
図4


% ８階調
IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>96;
IMG3 = ORG>128;
IMG4 = ORG>160;
IMG5 = ORG>192;
IMG6 = ORG>224;
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;


表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理2_4.png?raw=true)  
図5


これらの図から、階調をあげていくとより細かい部分まで表現できるようになるということが確認できる。
