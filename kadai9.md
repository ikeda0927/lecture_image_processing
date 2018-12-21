# 課題2レポート

 課題９ メディアンフィルタと先鋭化
 メディアンフィルターを適用し，ノイズ除去を体験せよ．

森の中で撮った「im.png」を原画像とする．この画像は縦2160画像，横3840画素による長方形のディジタルカラー画像である．

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/im.png?raw=true)  
図1

ORG = imread('im.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理9_1.png?raw=true)  
図2

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理9_2.png?raw=true)  
図3

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理9_3.png?raw=true)  
図4

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理9_4.png?raw=true)  
図5

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理9_5.png?raw=true)  
図6

平滑化フィルタや、メディアンフィルタで雑音除去をした場合は元の画像にあまり影響を与えること無くノイズのみを消すことが出来たが、最後に設計したフィルタではノイズをなくすことが出来ても全体的に暗くなってしまったと言うことが分かる。
