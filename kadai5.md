# 課題2レポート

 課題５　判別分析法
 判別分析法を用いて画像二値化せよ．

森の中で撮った「im.png」を原画像とする．この画像は縦2160画像，横3840画素による長方形のディジタルカラー画像である．

原画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/im.png?raw=true)  
図1


ORG=imread('im.png'); % 原画像の入力
ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理5_1.png?raw=true)  
図2

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

IMG = ORG > max_thres;
imagesc(IMG); colormap(gray); colorbar;
pause;

表示された画像
![原画像](https://github.com/ikeda0927/lecture_image_processing/blob/master/kadai_img/画像処理5_2.png?raw=true)  
図3

これらの図から、黒くつぶれてる部分もあるが大体は認識できる2値画像が得られると言うことが分かる。
