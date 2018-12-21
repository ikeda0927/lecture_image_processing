# 課題7レポート

課題7　ダイナミックレンジの拡大
画素のダイナミックレンジを０から２５５にせよ． 

森の中で撮った「im.png」を原画像とする．この画像は縦2160画像，横3840画素による長方形のディジタルカラー画像である．

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/im.png?raw=true)  
図1

ORG = imread('im.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理7_1.png?raw=true)  
図2

imhist(ORG); % 濃度ヒストグラムを生成、表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理7_2.png?raw=true)  
図3

ORG = double(ORG);
mn = min(ORG(:)); % 濃度値の最小値を算出
mx = max(ORG(:)); % 濃度値の最大値を算出
ORG = (ORG-mn)/(mx-mn)*255;
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理7_3.png?raw=true)  
図4

ORG = uint8(ORG); % この行について考察せよ
imhist(ORG); % 濃度ヒストグラムを生成、表示

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理7_4.png?raw=true)  
図5

ORG = uint8(ORG);
の行で、画像を8ビットの符号無し整数に変換して、情報量を少なくしているが、表示されている画像やそのヒストグラムにはあまり変化は見られないため、uint8()によってあまり影響を与えずに情報量を削減できているといえる。
