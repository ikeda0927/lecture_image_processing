# 課題4レポート


 課題４　画像のヒストグラム
 画素の濃度ヒストグラムを生成せよ．

森の中で撮った「im.png」を原画像とする．
この画像は縦2160画像，横3840画素による長方形のディジタルカラー画像である．

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/im.png?raw=true)  
図1

clear; % 変数のオールクリア

ORG=imread('im.png'); % 原画像の入力
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;
pause;

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理4_1.png?raw=true)  
図2

imhist(ORG); % ヒストグラムの表示


原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理4_2.png?raw=true)  
図3

濃度のヒストグラムから、図2の画像に含まれる色の濃さが読み取れる。
