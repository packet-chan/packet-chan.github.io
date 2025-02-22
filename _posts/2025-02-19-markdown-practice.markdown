---
layout: post
title: "GitHubPagesとJeykyllを用いたHP開設"
date: 2025-02-19
categories: tech blog
---

# はじめに
　春からNAISTの情報科学領域への進学が決まり、入学までに情報関連のことを勉強したいと思い、このHPを開設することにしました。GitHubPagesとJeykyllを利用して無料での実装を目指しました。

---
# 前提条件
GitとGitHubの導入が完了していること

---
# 手順１
　はじめに、Jekyllを導入します。Windowsの方は[Rubyをインストール](https://zenn.dev/tmasuyama1114/books/ab51fea5d5f659/viewer/ruby-environment-setup)する必要があります。  
  
インストール完了後、こちらを起動  
![画像]( {{ site.baseurl }}/static/images/ruby.png )

Jekyllのインストール  
 `gem install jekyll bundler`  

---
# 手順２
　WindowsPowershellを管理者権限で起動します。  
  
①ディレクトリの移動  
 `cd C:\Users\（ユーザー名）\Desktop`  

② Jekyllの新しいプロジェクトを作成  
 `jekyll new myblog`  
これで myblog というフォルダが作られ、Jekyll用のファイル構成が生成されます。  

③生成されたフォルダに移動  
 `cd myblog` 

④ローカルで動作確認
Jekyllのサーバーを起動して、ブラウザで確認できます。  
 `bundle exec jekyll serve --livereload`  
[http://127.0.0.1:4000/](http://127.0.0.1:4000/)にアクセスすると、Jekyllのデフォルトサイトが表示されるはずです。

---
# 手順３
　GitHubで新しいリポジトリを作成します。名前は「（ユーザー名）.github.io」  

①GemFileの編集
プロジェクトフォルダ内の Gemfile を開いて、以下の行を見つけてコメントアウト（# を削除）します。   
  
`# gem "github-pages", group: :jekyll_plugins`  
  
そして、以下のコマンドをPowerShellで実行してgithub-pages をインストール  
 `bundle install`

②_config.yml の編集  
Jekyllの設定ファイル _config.yml を開いて、以下のように変更  
```
title: （好きなタイトル）
description: "（）"
baseurl: ""
url: "https://（ユーザー名）.github.io"
theme: minima # デフォルトテーマを指定
```

③.gitignore の設定
.gitignore を作成し、以下を追加  
```
_site/
.sass-cache/
.jekyll-cache/
.bundle/
```

# 手順４
ブログ記事は /_posts/ フォルダ内にMarkdown形式で保存します。  

①記事の作成  
ファイル名は YYYY-MM-DD-タイトル.md の形式にする必要があります。 例えば「2025-02-18-first-post.md」などです。

このファイルを _posts フォルダに作成し、中身は例として以下のように書きます
```
---
layout: post
title: "Jekyllでブログを書く"
date: 2025-02-18
categories: tech blog
---

Jekyllを使ってGitHub Pagesでブログを始めました！
```

②GitHubへアップロード  
GitHubに変更を反映させるため、以下の手順を実行します。
```
git add .
git commit -m "Jekyllブログをセットアップ"
git push origin main
```

しばらくすると https://（ユーザー名）.github.io/ にJekyllブログが反映されます！