# ros2のパッケージであるmypkgに含まれるコマンドの説明
* talkerコマンド  
パブリッシャを持つノードで、数字をカウントしてトピックの/countupを通じて送信される。

* listnerコマンド  
サブスクライバを持つノードで、トピックの/countupから数字を受け取って画面に出力する。

* talk‗listen.launchコマンド  
talkerとlistenerの2つのノードを同時に立ち上げ、数字をカウントしてトピックの/countupを通じて受けとったメッセージを画面に出力する。

## GitHub Actionsにおけるテスト
![test](https://github.com/osukeishihara/mypkg/actions/workflows/test.yml/badge.svg)

## インストール方法
 
 ```

 $ git clone https://github.com/osukeishihara/mypkg.git         #リポジトリをローカル環境に複製するコマンド

 ```

## コマンドの使い方
* talkerコマンド
 
 ```

 $ cd mypkg         #mypkgというディレクトリに移動する。
 $ ros2 run mypkg talker         #talkerノードを実行するコマンド
   (何も表示されない）

 $ ros2 topic echo /countup         #別にターミナルを開き、トピックの/countupを画面に出力する。
   data: 30
   ---
   data: 31

   ・・・           #このように画面に出力される。
 
 ```
