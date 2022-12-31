# ros2のパッケージであるmypkgに含まれるコマンドの説明
/countupはros2におけるトピックの名前である。
* talkerコマンド  
パブリッシャを持つノードで、数字をカウントしてトピックの/countupを通じて送信される。

* listenerコマンド  
サブスクライバを持つノードで、トピックの/countupから数字を受け取って画面に出力する。

* talk_listen.launchコマンド  
talkerとlistenerの2つのノードを同時に立ち上げ、数字をカウントしてトピックの/countupを通じて受けとったメッセージを画面に出力する。

## GitHub Actionsにおけるテスト
![test](https://github.com/osukeishihara/mypkg/actions/workflows/test.yml/badge.svg)

## インストール方法
 
 ```

 $ git clone https://github.com/osukeishihara/mypkg.git         #リポジトリをローカル環境に複製するコマンド。

 ```

## コマンドの使い方
* talkerコマンド
 
 ```

 $ cd mypkg                         #mypkgというディレクトリに移動する。
 $ ros2 run mypkg talker            #talkerノードを実行するコマンド。
   (何も表示されない）

 $ ros2 topic echo /countup         #別にターミナルを開き、トピックの/countupを画面に出力するコマンド。
   data: 30
   ---
   data: 31                         #このように画面に出力される。 

   ・・・                            
 
 ```

* listenerコマンド

 ```

 $ cd mypkg                                                     #mypkgというディレクトリに移動する。
 $ ros2 run mypkg talker                                        #talkerノードを実行するコマンド
   (何も表示されない）

 $ ros2 run mypkg listener                                      #listenerノードを実行するコマンド
   [INFO] [1672472619.983395319] [listener]: Listen: 27
   [INFO] [1672472620.474658465] [listener]: Listen: 28         #このように画面に出力される。
                　　　　　
　　　　　　　　　　　　　・・・
 
 ```

* talk_listen.launchコマンド

 ```

 $ cd launch                                                                 #launchというディレクトリに移動する。
 $ ros2 launch mypkg talk_listen.launch.py                                   #launchファイルを実行するコマンドで、talkerとlistenerの2つのノードが同時に立ち上がる。   [listener-2] [INFO] [1672473573.473690948] [listener]: Listen: 0
   [listener-2] [INFO] [1672473573.962484471] [listener]: Listen: 1       
   [listener-2] [INFO] [1672473574.462271443] [listener]: Listen: 2          #このように画面に出力される。

                             　・・・

 ```

## 動作確認済み環境
* Ubuntu 22.04.1 LTS

## 必要なソフトウェア
* ROSのパージョン：ROS2
