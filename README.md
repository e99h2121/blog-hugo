# blog-hugo

githubからzipをダウンロード
githubのHugoでhttps://github.com/spf13/hugo/releasesよりwindowsの64bitバージョンを選ぶ

C:\hugo_0.83.1_Windows-64bit に置く

Hugoのbinフォルダを作る。
C:\hugo_0.83.1_Windows-64bit\bin\hugo.exe


環境変数パスを通す

```
set path=%path%;C:\hugo_0.83.1_Windows-64bit\bin;
```

`hugo help` などが使えることを確認


Hugoの初期フォルダを作る
cd C:\git\blog-hugo


```
hugo new site InitialSites
```

```
C:\git\blog-hugo>hugo new site InitialSites
Congratulations! Your new Hugo site is created in C:\git\blog-hugo\InitialSites.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>\<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```


テーマをインストール。今回は以下。
https://themes.gohugo.io/github-style/


cd InitialSites
mkdir themes
cd themes

git clone https://github.com/MeiK2333/github-style


```
C:\git\blog-hugo\InitialSites>hugo new readme.md
C:\git\blog-hugo\InitialSites\content\readme.md created
```

//InitialSitesに戻る。
cd ..


```
hugo server -t github-style -D -w
```

https://localhost:1313/

```config.toml
baseURL = "https://e99h2121.github.io/blog-hugo/"
languageCode = "ja-ja"
title = "e99h2121's New Hugo Site"
theme = "github-style"
googleAnalytics = "UA-123456-789"
pygmentsCodeFences = true
pygmentsUseClasses = true

[params]
  author = "e99h2121"
  description = "In solitude, where we are least alone."
  github = "e99h2121"
  facebook = "yamada_n"
  twitter = "e99h2121"
  linkedin = "e99h2121"
  instagram = "e99h2121"
  tumblr = "e99h2121"
  url = "https://e99h2121.github.io/blog-hugo/"
  keywords = "blog, google analytics"
  rss = true
  lastmod = true
  location = "Japan"

  [[params.links]]
    title = "Link"
    href = "https://github.com/e99h2121"

[frontmatter]
  lastmod = ["lastmod", ":fileModTime", ":default"]

```

サイトプレビュー停止
中断コマンドのCtrl+C


https://yonehub.y10e.com/2019/10/22/20191022_hugo_githubio/

`hugo -t github-style` で公開ファイルを生成



