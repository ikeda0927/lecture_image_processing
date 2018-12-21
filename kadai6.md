# 課題6レポート

 課題６　画像の二値化
 下記のプログラムを参考にして画像を二値化せよ．

森の中で撮った「im.png」を原画像とする．この画像は縦2160画像，横3840画素による長方形のディジタルカラー画像である．

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/im.png?raw=true)  
図1

clear; % 変数のオールクリア
ORG=imread('im.png'); % 原画像の入力
ORG = rgb2gray(ORG);
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause; % 一時停止

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理6_1.png?raw=true)  
図2

IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理6_2.png?raw=true)  
図3

IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理6_3.png?raw=true)  
図3

128による二値化ではノイズは見られないが、白い部分と黒い部分ではっきり分かれており、細かいところが確認できない。
また、ディザ法による二値化では白い部分と黒い部分がはっきりとは分かれていないが、全体的にノイズのようなものが確認できる。
