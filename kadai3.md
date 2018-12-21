# 課題3レポート

課題３　閾値処理
閾値を4パターン設定し,閾値処理た画像を示せ．

森の中で撮った「im.png」を原画像とする．この画像は縦2160画像，横3840画素による長方形のディジタルカラー画像である．

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/im.png?raw=true)  
図1
clear; % 変数のオールクリア

ORG=imread('im.png'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理3_1.png?raw=true)  
図2

%1つめ
IMG = ORG > 32;
imagesc(IMG); colormap(gray); colorbar;
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理3_2.png?raw=true)  
図3

IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換
imagesc(IMG); colormap(gray); colorbar;
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理3_3.png?raw=true)  
図4

IMG = ORG > 96;
imagesc(IMG); colormap(gray); colorbar;
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理3_4.png?raw=true)  
図5

%2つめ
IMG = ORG > 112;
imagesc(IMG); colormap(gray); colorbar;
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理3_5.png?raw=true)  
図6

これらの図から、閾値処理をしていくと輪郭やだいたいの形状などが読み取れそうだと感じた。

