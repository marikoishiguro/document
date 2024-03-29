# nodenvを使用して最新と一つ前のNodejsをインスールする方法

## 実行環境

```
macOS Ventura 13.5.2
```

## ターミナルを起動します

ターミナルについて

## nodenvのダウンロード

まず、nodenvのソースをGitHubからcloneする

```
git clone https://github.com/nodenv/nodenv.git ~/.nodenv
```


## nodenvのビルド

ダウンロードしてきたソースからnodenvをビルドして実行可能な状態にする

```
cd ~/.nodenv && src/configure && make -C src
```



## bash,zsh等の確認する

```
echo $SHELL
```



## pathを通す

コマンドを叩けるように該当パスを通す

- zshの場合

```
echo 'export PATH="$HOME/.nodenv/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(nodenv init -)"' >> ~/.zshrc
```


- シェルを再起動する

```
exec $SHELL -l
```


- コマンドが正しくインストールされているか確認する

```
nodenv --version
```



## nodeのインストール

- インストールできるnodeのバージョンの確認
  
```
nodenv install --list
```

*コマンドが使用できない場合は※1を実行する*



- nodeのインストール（最新バージョンを指定） 

```
nodenv install 21.7.1
```


- ひとつ前のバージョンのインストール

```
nodenv install 21.7.0
```



- nodenvからnodeやグローバルなnpmパッケージを見えるようにするためにrehashを行う

```
nodenv rehash
```



## インストールしているnodeのバージョン確認

```
nodenv versions
```



## nodeのバージョンの指定

- グローバルで使うnodeのバージョンを指定する

```
nodenv global 21.7.1
```


- バージョンの確認

```
node -v
```


### ※1 nodenv installが使えない時の対処法

```
mkdir plugins
```

```
cd plugins
```

```
git clone https://github.com/nodenv/node-build.git
```









Macで「ターミナル」を開く/終了する
Macの「ターミナル」は、macOSにコマンドラインインターフェイスを提供します。
support.apple.com
