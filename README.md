# vue_on_flask
vue と flaskを使ったspa(single page application)の練習です．

原則，[FlaskとVue.jsでSPA Webアプリ開発](https://qiita.com/y-tsutsu/items/67f71fc8430a199a3efd)に従っています．


# 事前準備
```
$ brew install nodebrew
$ vue --version
@vue/cli 4.5.12
node -v
v10.14.1
```
# Projectの作成

```
$ mkdir myspa
$ cd myspa
$ git init

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
$ cd frontend
$ npm run serve
```
フロントエンド単体での開発が可能となった．
