# LEDDriver
2021年度のロボットシステム学課題１で製作したデバイスドライバです。


## 目次
- 概要
- 使用部品
- 回路図
- コマンド
- ライセンス

## 概要
課題の一環として製作したもので動作は以下のようになります。
- 入力した数値で発光のモードが変わります。
![全体図](https://user-images.githubusercontent.com/76143173/145820546-46356170-83a0-4b4f-8b58-25d1b0d5822c.JPG)




## 必要部品
- Raspberry Pi 4 
- ブレッドボード(小)
- Kingbright DLC/6SRD　(データシートはこちらhttps://www.mouser.jp/datasheet/2/216/DLC-6SRD-57425.pdf)
- ジャンパ線

## 回路図
回路図

![回路図](https://user-images.githubusercontent.com/76143173/145818996-b4e57e7e-b5b0-4b9b-a59d-da202c960d8c.png)



## コマンド
# 1リポジトリをRaspberry Pi 4にクローンする(gitのインストール前提)
```
SSHの場合 
git clone git@github.com:Sugar310-system/kadai1.git
HTTPSの場合　
git clone https://github.com/Sugar310-system/kadai1.git
```
# 2クローンしたディレクトリ内で実行可能状態にする
```
make
sudo insmod leddrv.ko
sudo chmod 666 /dev/leddrv
```
# 3LEDを点灯させる
-全消灯
```
echo 0 > /dev/leddrv
```
-全点灯
```
echo 1 > /dev/leddrv
```
-蛍
```
echo 2 > /dev/leddrv
```
-回転灯
```
echo 3 > /dev/leddrv
```
# 4プログラムを終了する
```
sudo rmmod leddrv
sudo rm /dev/leddrv
```
動作している様子()
## ライセンス
[GNU GENERAL PUBLIC LICENSE 3.0]https://github.com/Sugar310-system/kadai1/blob/main/COPYING
