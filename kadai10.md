# 課題10レポート

課題10 画像のエッジ抽出 
エッジ抽出を体験せよ．

森の中で撮った「im.png」を原画像とする．この画像は縦2160画像，横3840画素による長方形のディジタルカラー画像である．

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/im.png?raw=true)  
図1


ORG = imread('im.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); %カラーからグレイへの変換
imagesc(ORG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理10_1.png?raw=true)  
図2

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理10_2.png?raw=true)  
図3

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理10_3.png?raw=true)  
図4

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理10_4.png?raw=true)  
図5

元々の画像が煩雑なのでエッジ抽出の恩恵はあまり受けられないが、それでも奧の方に見える木や手前の倒木の輪郭がかろうじて確認できる。
この画像の場合、一番エッジ抽出が上手くいったなと感じられたのはプレウィット法である。
