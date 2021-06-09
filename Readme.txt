静的サイトジェネレータHugoインストール【windows10ローカル】
hugo

静的サイトジェネレータのHugoをwindows10のローカルに構築しました。コマンドプロンプト必須です。
マークアップやデザインが専門で、php等をあまり使わない方でも、将来的にはテーマ販売出来ると思います。

AWSのS3やAzure Storageなどで動的部分と切り分ける事で、サーバーやセキュリティのトラブルやコストを抑えられる事は大きいと感じています。
大企業や大学でも採用される可能性は十分にあります。身近な事例としては、Chatworkでphestを現役で利用して開発も行っている様です。

Hugoを選んだ理由
簡単そうだから(覚える事や調べる事は結構あるかも、パーツ別のディレクトリ構成など)。

githubや国内の様子や本家サイトなど、開発の継続性がありそうでユーザー数も伸びそうだから。

enbatomarketでCMSのテーマ購入時、同梱されてくる取説がHugoなどの静的サイトジェネレータで作られていると思われるものが結構あり、ドキュメントまで充実している点に感心していました。

インストール手順
目標5分以下です！行きます！

1.githubからzipをダウンロード
githubのHugoでhttps://github.com/spf13/hugo/releasesよりwindowsの64bitバージョンを選びました。

C:\hugo_0.83.1_Windows-64bit

2.フォルダを作る
Hugoのbinフォルダを以下のように作ってください。CドライブやDドライブなどはパソコンのパーティション設定などを見ながら決めてください。

//Hugoのbinフォルダを作る。
C:\Hugo\bin
3.zipを展開
1.でダウンロードしたzipを展開し、hugo.exeを2.で作ったbinフォルダ内に配置してください。

4.環境変数パスを通す
画面左下のウィンドウズマークを右クリック⇒システム⇒システムの詳細設定⇒環境変数に進みます。


```
set path=%path%;C:\hugo_0.83.1_Windows-64bit\bin;
```

windowsパソコンへログインしている現状のユーザーにパスを通す場合、上部の「ユーザーの環境変数」でPathをダブルクリック⇒新規まで進み、C:\Hugo\binを入力⇒OKで各ウィンドウを閉じる。

※2.でDドライブなどにした場合は、D:\Hugo\binなど、適宜最適化してください。
5.helpコマンド動作確認
cortanaなどでコマンドプロンプトを立ち上げます。
以下のへルプコマンドを入力し、パスが通ったか確認します。
ヘルプコマンド一覧が出てきたら、インストール完了です。




//hugo ヘルプコマンド
hugo help
Hugo作業用フォルダ作成、テーマを入れてローカルホストIPで実行/停止
1.Hugoフォルダに移動
//hugoフォルダに移動
cd C:\Hugo\
2.Hugoの初期フォルダを作る
VMの作業フォルダという感じです。

//初期フォルダを作る

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


https://themes.gohugo.io/github-style/



3.作ったフォルダに移動してテーマをインストール
テーマはhttp://themes.gohugo.io/よりhugo-bootstrap-premiumを選びました。

//作ったフォルダに移動
cd InitialSites
//テーマフォルダを作る
mkdir themes
//テーマフォルダへ移動
cd themes



//テーマをインストール
git clone https://github.com/appernetic/hugo-bootstrap-premium
gitを入れていない場合、手動ダウンロードを行ってください。




```
C:\git\blog-hugo\InitialSites>hugo new readme.md
C:\git\blog-hugo\InitialSites\content\readme.md created
```




4.サイトプレビュー生成
//InitialSitesに戻る。
cd ..


```
hugo server -t github-style -D -w
```


//サイトプレビュー生成
hugo server -t hugo-bootstrap-premium -D -w
localhost:1313

より確認できます。

config.tomlの設定ファイルや初期ページを制作していないので、上部のグロナビだけの状態です。

5.サイトプレビュー停止
中断コマンドのCtrl+Cを行ってください。停止しないとずっとプロセス続きます。

静的サイトジェネレータ各種（参考）
jekyll
phest（Chatwork）
Middleman
Metalsmith
Pelican
hugo
コメントをいただくことがしばしばあるため、コメント機能を有効化しました。わからないこと、間違っていること、疑問に思うこと、何でも質問受け付けます。間違っていることは適宜修正させていただきます。お気軽にコメントください。また、正しい回答を出来る方は、正しい回答でぶった斬ってコメントいただけますと幸いです。
