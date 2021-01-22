# ros_count_twice

# 使用したもの

Raspberry Pi 4

---

# 動作環境

OS:ubuntu 10.04  
ROS_VERSION:noetic  

---

# インストール方法

動作させるワークスペースのsrcフォルダで以下のコマンドを実行してください。  

```sh
$ git clone https://github.com/ueshou/mypkg.git  
```

その後ワークスペースに戻り、以下のコマンドでmakeしてください。

```sh
$ catkin_make  
```

---

# 実行

makeが終わった後、以下のコマンドで実行してください。
実行する端末は、以下のコマンドでscriptsフォルダに移動してから実行してください。
```sh
$ cd src/mypkg/mypkg/scripts
```
```sh
端末1$ roscore
端末2$ chmod +x count.py
端末2$ rosrun mypkg count.py
端末3$ chmod +x twice.py
端末3S rosrun mypkg twice.py  
```
Ctr+cで終了することができます。


# パッケージ

・count.py
初期値n=0で、１秒毎にn+1のデータを投げる

・twice.py
count.pyからデータを受け取り、それを2倍にしてデータを出力

#### データの確認

出力されたデータは以下のコマンドで得られる

```sh
$ rostopic echo /count_up
$ rostopic echo /twice
```
---

# デモ動画

[実行動画](https://www.youtube.com/watch?v=8mPzvCJtwSg)  

# 著者
・Shota Ueda  
・コード：Ryuichi Ueda  

---

# ライセンス
[BSD 3-Clause "New" or "Revised" License](https://github.com/ueshou/mypkg/blob/main/LICENSE)
