****課題1****
***kadai***
- 画像を1/2倍に縮小してもう一度元の大きさに戻す

```c:kadai1.m
clear; % 変数のオールクリア



ORG=imread('Lenna.png'); % 原画像の入力

imagesc(ORG); axis image; % 画像の表示

pause; % 一時停止



IMG = imresize(ORG,0.5); % 画像の縮小

IMG2 = imresize(IMG,2,'box'); % 画像の拡大

imagesc(IMG2); axis image; % 画像の表示

pause; % 一時停止
```

これを実行すると最初の一時停止のところでオリジナルの画像が表示され、次の一時停止で
