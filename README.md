# vue_on_flask
vue と flaskを使ったspa(single page application)の練習です．

原則，[FlaskとVue.jsでSPA Webアプリ開発](https://qiita.com/y-tsutsu/items/67f71fc8430a199a3efd)に従っています．

# How to use

1. $ git clone
2. 事前準備の実行
3. $ pipenv run variable
でVue on Flaskの環境が立ち上がります．

詳しくは以下で説明します．

---

# 事前準備

``` 任意のディレクトリ
$ brew install nodebrew
$ vue --version
@vue/cli 4.5.12
node -v
v10.14.1
```

# Projectの作成

```
# 作りたいディレクトリ直下で 
$ mkdir myspa
$ cd myspa
# frontend, backend ディレクトリどちらも一緒に管理するためここでgit init
$ git init
```

## vueのProject作成

```
$ vue create frontend
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, Router, Vuex, Linter
? Use history mode for router? (Requires proper server setup for index fallback in product
ion) Yes
? Pick a linter / formatter config: Basic
? Pick additional lint features: Lint on save
? Where do you prefer placing config for Babel, ESLint, etc.? In dedicated config files
? Save this as a preset for future projects? No
```
一旦，vue.jsの準備が完了．

フロントエンドでサーバを起動してみる．
```
# myspa内で
$ cd frontend
$ npm run serve
```
フロントエンド単体での開発が可能になった．

## バックエンド(flask）のプロジェクト作成

```
$ brew install pipenv # インストールしていない人向け．私はしていませんでした．

$ pipenv --version
pipenv, version 2020.11.15

# myspa内で
$ mkdir backend
$ cd backend
$ pipenv --python 3.7
# これは初めての人だけが聞かれる警告だと思います．
Warning: Python 3.7 was not found on your system...
Would you like us to install CPython 3.7.9 with Pyenv? [Y/n]: y

# flaskのインストール
$ pipenv install flask
```

内容とは直接関係ないが，入れておくと便利なツールをインストールする．

flaskの開発をするときはとりあえず入れておけば良いということでしょうか．

とりあえず入れておきます．

```
$ pipenv install --dev autopep8 flake8 rope
```
ちなみに--devというのは開発環境のみでパッケージをインストールするオプションらしいです．
本番環境には出さないように設定できるということですね．よくできていますね．

バージョンコンフリクトのエラーがでたので，
```
$ pipenv uninstall importlib-metadata
$ pipenv install importlib-metadata==1.12.0
```
としておきました．（多分，pienvのバージョンが新しいためのエラーだと思います．）


あとは，リンクの内容に従ってflaskとVue.jsを連携した環境を立ち上げます．

```
$ cd backend
$ pipenv run start
```

control + c で立ち上げたサーバを落とすことができます．

# ちょっとした疑問点

## 1. Pipfileのscriptsとは何か

独自のスクリプトショートカットだそうです．

```
Pipfile
[scripts]
variable = "shell scripts..."
```

```
$ pipenv run variable
```
で，Pipfileで定義したvariableを実行できるみたいです．

## 2. public/ -> public/static/img/にしたのはなぜか

静的ファイルはpublic下に置くよりstatic下に置くほうが，管理しやすいということでしょうか．
よくわかりませんでした．
