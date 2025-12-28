# Calibre-Web Automated _(旧 Calibre-Web Automator)_

![Calibre-Web Automated](README_images/CWA-banner.png "Calibre-Web Automated")

## Calibre-Webを、あなたの「夢」のオールインワン自己ホスト型デジタルライブラリソリューションへ。

![Docker Pulls](https://img.shields.io/docker/pulls/crocodilestick/calibre-web-automated)
![GitHub Release](https://img.shields.io/github/v/release/crocodilestick/calibre-web-automated)
![GitHub commits since latest release](https://img.shields.io/github/commits-since/crocodilestick/calibre-web-automated/latest)
![OAuth 2.0 + OIDC](https://img.shields.io/badge/OAuth-2.0%20%2B%20OIDC-blue?style=flat&logo=oauth)


## _クイックアクセス_

- [機能](#features) 🪄
- [リリース](https://github.com/crocodilestick/Calibre-Web-Automated/releases) 🆕
- [ロードマップ](#features-currently-under-active-development-and-on-our-roadmap-️️) 🛣️
- [インストール方法](#how-to-install-): 📖
  - [クイックインストール](#quick-install-) 🚀
  - [Docker Compose](#using-docker-compose-recommended) 🐋⭐(推奨)
  - [通常のCalibre Webからの移行](#users-migrating-from-stock-calibre-web) 🔄
  - [インストール後のタスク](#post-install-tasks) 🏁
    - [デフォルトのログイン情報 🔑](#default-admin-login)
- [使い方](#usage-) 🔧
  - [ライブラリへの本の追加](#adding-books-to-your-library)
  - [KOReader 同期 (KOSync)](#koreader-syncing-kosync-) 📖⚡
  - [OAuth 認証設定](#enhanced-oauth-20oidc-authentication-) 🔐
- [開発者向け](#for-developers---building-custom-docker-image) 🚀
- [今後の開発](#further-development-️) 🏗️
- [サポート / コーヒーをおごる](https://ko-fi.com/crocodilestick) ☕

## なぜこのプロジェクトが存在するのか？ 🔓

Calibreは、その歴史を考えると素晴らしいツールですが、コンテナ化して利用する際にはいくつかの問題を抱えています。特にUIのためにKasmVNCサーバーインスタンスに依存している点は、モバイルでの利用をほぼ不可能にし、私のような小規模で省電力なサーバーで運用するには比較的リソースを多く消費します。

多くの人にとって、Calibre-Webは救世主のように現れ、コンテナ化されたCalibreインスタンスの代替として、軽量かつモダンなUIを提供してきました。

しかし、フル機能のCalibreと比較すると、残念ながらいくつかのコア機能が欠けています。その結果、多くのユーザーが両方のサービスを並行して稼働させ、互いの不足部分を補い合うという、しばしば不格好で不完全な解決策をとることになっています。

## プロジェクトの目標 🎯

Calibre-Web Automatedは、Calibre-Webのモダンで軽量なWeb UIと、Calibreの堅牢で多機能なセットを組み合わせ、さらに多くの追加機能と自動化を盛り込んだ、オールインワンのソリューションを目指しています。

![Calibre-Web Automated Example Homepage](README_images/CWA-Homepage.png)
<p style="text-align:center;"><i>CWAを使えば、電子書籍ライブラリを整理してアクセスしやすくし、見た目も美しく保てます</i> 😎🦚</p>

## _関連プロジェクト_ 👬

### Calibre-Web Automated Book Downloader

- Calibre-Web-Automatedとシームレスに連携するように設計された、書籍の検索とダウンロードリクエストのための直感的なWebインターフェースです。書籍のダウンロードからCalibreライブラリへの統合準備までのプロセスを効率化します。

[<img src="https://raw.githubusercontent.com/vadret/android/master/assets/get-github.png" alt="Get it on GitHub" height="80">](https://github.com/calibrain/calibre-web-automated-book-downloader)

___

### Calibre-Web Companion

- **Flutter** と **Material You** で構築された [**Calibre Web Companion**](https://github.com/doen1el/calibre-web-companion) は、**Calibre Web** および **Calibre Web Automated** 向けの **非公式コンパニオンアプリ** です。デバイス上で直接書籍コレクションを閲覧・ダウンロードでき、どちらのサービス単体よりもはるかに **モダンでモバイルフレンドリーなUX** を提供します。

<br>

[![Calibre Web Companion Preview](README_images/cw-companion-screenshots.png)](https://github.com/doen1el/calibre-web-companion)

[<img src="README_images/google-play.png" alt="Get it on Google Play" height="80">](https://play.google.com/store/apps/details?id=de.doen1el.calibreWebCompanion)
[<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png" alt="Get it on F-Droid" height="80">](https://f-droid.org/en/packages/de.doen1el.calibreWebCompanion/)
[<img src="https://raw.githubusercontent.com/vadret/android/master/assets/get-github.png" alt="Get it on GitHub" height="80">](https://github.com/doen1el/calibre-web-companion)

## コミュニティに参加しよう！ ❤️

- このプロジェクトのテストや開発に参加してくださったコミュニティメンバーの皆様に **大きな感謝** 🙏 を申し上げます。どのような形であれ貢献したいという方を歓迎します。どんなレベルの方でも大歓迎ですし、どんな些細なことでも助けになります！
- **このプロジェクトに何らかの形で貢献したい方** は、Discordサーバーにご参加いただき、どのような関わり方が最適かご確認ください:\
    \
    [![](https://dcbadge.limes.pink/api/server/https://discord.gg/EjgSeek94R)](https://discord.gg/EjgSeek94R)

- あるいは、独自のコンパニオンプロジェクトを作成したり、遊びに来たり、問題に直面した場合に助けを求めたりしてください :)

## 🚨 ネットワーク共有（特にNFS）経由でのデプロイを計画しているユーザーへ 🚨

- Calibre、Calibre-Web、そしてCWAはすべてSQLite3ベースのアプリケーションであり、**ネットワーク共有（特にNFS）上での実行を好みません**。
    - SQLiteは軽量なファイルベースのデータベースシステムとして設計されており、基礎となるファイルシステムが **ファイルロック、アトミック書き込み、整合性** に関する特定の保証をサポートしていることを前提としています。
    - **ネットワークファイルシステム（例：NFS, SMB/CIFSなど）は、しばしばこれらの前提を満たさないことがあり、問題を引き起こす可能性があります。**
  - NFS共有上でCWAを展開して成功しているユーザーもいますが、そうすることで **診断が困難な問題が多数発生する可能性があり**、実際の問題を抱えているユーザーのサポートに時間を割くことになりかねません。
  - **したがって、V3.0.0以降、NFS共有上での展開は「非サポート」となります**。つまり、**自由に行っていただけますが**、**問題が発生した場合のサポートは提供されません**。

### ネットワーク共有とSQLite WALモード

- CWAは、ローカルディスク上でWrite-Ahead Logging (WAL) を有効にすることでSQLiteの並行性を最適化しています。
- 一部のネットワークファイルシステム (NFS/SMB) はWALや信頼性の高いファイルロックを完全にはサポートしておらず、断続的な「データベースがロックされています」エラーや破損のリスクを引き起こす可能性があります。
- ネットワーク共有上にデプロイする場合は、以下の環境変数を設定してWALを無効にしてください:

  - `NETWORK_SHARE_MODE=true`

これにより、Calibreの `metadata.db` および `app.db` 設定データベースでWALを有効にしないようCWAに指示します。また、ネットワークファイルシステム上の権限問題を回避するために、初期化/メンテナンススクリプトによる再帰的な所有権変更 (`chown`) も無効化します。デフォルトは `false` (WAL有効) で、ローカルディスクでのパフォーマンスが向上します。

#### ネットワーク共有でのファイル監視

- デフォルトでは、CWAはLinuxの `inotify` (`inotifywait`経由) を使用して、取り込み（Ingest）ディレクトリ内の新しいファイルを最小限の遅延とオーバーヘッドで検出します。
- ネットワーク共有 (NFS/SMB) 上では、ファイルシステムイベントが信頼できないか、利用できない場合があります。`NETWORK_SHARE_MODE=true` が設定されると、CWAは取り込みおよびメタデータ監視サービスを、定期的に変更をスキャンするポーリングベースの監視に切り替えます。これにより、NAS/ネットワークマウント上での信頼性は向上しますが、I/Oがわずかに増加し、最大数秒の遅延が発生します。
- Docker Desktop (Windows/macOS) 上では、コンテナはLinuxKit/WSL2 VM上で実行され、ホストマウントされたパスは `inotify` イベントを確実に伝播しない場合があります。CWAは起動時にDocker Desktopを自動検出し、信頼性のために同様のポーリング監視を優先します。
- 上級者向け: `CWA_WATCH_MODE=poll` を設定することで、共有モードに関係なくポーリングを強制することもできます。

### 複数のプロキシ（Cloudflare Tunnel、リバースプロキシ）の背後での実行

- CWAはWerkzeugのProxyFixミドルウェアを使用して、`X-Forwarded-For`、`X-Forwarded-Proto`、その他のプロキシヘッダーを適切に処理します。
- デフォルトでは、チェーン内の **1つのプロキシ** を信頼します。複数のプロキシがある場合（例：Cloudflare Tunnel → nginx → CWA）、以下を設定してください:

  - `TRUSTED_PROXY_COUNT=2` (またはチェーン内のプロキシの総数)

- **これが重要な理由**: セッション保護はクライアントのIPアドレスに基づいてリクエストを検証します。ProxyFixが十分な数のプロキシを信頼していない場合、リクエスト間で異なるIPが見えてしまい、「セッション保護がトリガーされました」という警告が発生し、再ログインを強制される可能性があります。
- **トラブルシューティング**: ログに頻繁にセッション保護の警告が表示される場合は、プロキシチェーンの深さを確認し、この変数を適宜調整してください。

## **_機能:_**

### CWAは通常のCalibre-Webの全機能をサポートしています:
| | | |
|     :---:    |     :---:      |     :---:     |
| モダンでレスポンシブなBootstrap 3 HTML5インターフェース | ユーザーごとの権限設定を含む包括的なユーザー管理 | 電子書籍リーダーアプリ向けOPDSフィード |
| 電子書籍メタデータの編集と削除サポート | 様々なソースからのメタデータダウンロード（プラグインで拡張可能） | ログインユーザーへの電子書籍ダウンロード制限 |
| 公開ユーザー登録のサポート | ワンクリックで電子書籍リーダーへ送信 | KoboデバイスとCalibreライブラリの同期 |
| ブラウザ内での複数形式電子書籍閲覧サポート | カテゴリおよびカスタムカラムの内容に基づいたユーザーごとのコンテンツ非表示 | 電子書籍リーダーからの簡単なアクセスのための「マジックリンク」ログイン |
| 自動検出を備えた強化されたOAuth 2.0/OIDC認証 | 高度な検索とフィルタリングオプション | 20以上の[言語](https://github.com/janeczku/calibre-web/wiki/Translation-Status)に対応した多言語ユーザーインターフェース |

## さらに、以下の _**CWA独自の機能**_ が追加されています:

#### 詳細を読むには機能をクリックしてください:

| | | |
|     :---:    |     :---:      |     :---:     |
| [自動取り込みサービス ✨](#automatic-ingest-service-) | [自動変換サービス 🔃](#automatic-conversion-service-) | [表紙・メタデータの変更を自動適用 👀📔](#automatic-enforcement-of-changes-made-to-covers--metadata-through-the-calibre-web-ui-) |
| [一括編集・削除 🗂️](#batch-editing--deletion-️️) | [自動バックアップサービス 🔒](#automated-back-up-service-) | [新規ユーザー向け自動セットアップ 🦮](#library-auto-detect-️) |
| [自動EPUB修復サービス 🔨](#automatic-epub-fixer-service-) | [マルチ形式変換サービス 🌌](#simple-to-use-multi-format-conversion-service-) | [ライブラリ自動検出 📚🕵️](#library-auto-detect-️) |
| [サーバー統計追跡ページ 📍](#server-stats-tracking-page-) | [サーバー統計追跡 📊](#server-stats-tracking-page-) | [簡単ダーク/ライトモード切替 ☀️🌙](#easy-dark-light-mode-switching-️) |
| [内部アップデート通知システム 🛎️](#internal-update-notification-system-️) | [バックアップファイルの自動圧縮 🤐](#auto-compression-of-backed-up-files-) | [追加のメタデータプロバイダー 🗃️](#additional-metadata-providers-️) |
| [KOReader 同期 (KOSync) 📖⚡](#koreader-syncing-kosync-) | [強化されたOAuth 2.0/OIDC認証 🔐](#enhanced-oauth-20oidc-authentication-) | |

#### **自動取り込みサービス** ✨
- CWAは現在、27種類の一般的な電子書籍形式の自動取り込みをサポートしています。
- ユーザーは管理者パネルで、特定の形式を無視したり、他の形式へ自動変換したりするように動作を設定できます。

<!-- - **重み付け変換アルゴリズム:** ⚖️
  - どの形式がEPUBに最適に変換されるかというCalibreの電子書籍変換ドキュメントの情報を利用し、CWAは複数の電子書籍形式を含むダウンロードから、どの形式が最も最適に変換されるかを判断し、他の形式を無視して **可能な限り最高の品質** を確保し、**重複インポート** を防ぎます -->

#### **自動変換サービス** 🔃
- デフォルトでオンになっていますが、CWA設定ページでオフに切り替えることもできます。デフォルトのターゲット形式はEPUBです。
  - _利用可能なターゲット形式:_ **EPUB**, **MOBI**, **AZW3**, **KEPUB** & **PDF**
- 取り込みディレクトリ内の新しいファイルを検出すると、ユーザーが自動変換するように設定した形式のファイルがある場合、ターゲット形式へ変換されます。
- 現在、以下の **28種類のファイル形式がサポートされています:**
  - _.acsm, .azw, .azw3, .azw4, .mobi, .cbz, .cbr, .cb7, .cbc, .chm, .djvu, .docx, .epub, .fb2, .fbz, .html, .htmlz, .lit, .lrf, .odt, .pdf, .prc, .pdb, .pml, .rb, .rtf, .snb, .tcr, .txtz_
  - _注: .acsm には追加のCalibreプラグインが必要です_

#### **Calibre-Web UIで行った表紙・メタデータの変更を自動適用！** 👀📔
- 通常のCalibre-Webでは、本の **表紙やメタデータ** に加えた変更はCalibre-Web UI上の表示にのみ適用され、期待に反して電子書籍ファイル自体には何も変更が加えられません。
- これは、CWのKindleへの送信機能を利用している多くのユーザーにとって不満の種となっており、せっかく選んだ高画質の表紙や慎重に選んだメタデータが他のデバイスでは完全に欠落していることに失望することになります！うわぁ！
- CWAの **自動表紙・メタデータ適用機能** により、**あなたの** 本に加えた **どのような** 変更も、Web UIだけでなく **_本そのものにも適用され_**、**見たままが得られるようになります。**

![Cover Enforcement CWA](README_images/cwa-enforcer-diagram.png "CWA 1.2.0 Cover Enforcement Diagram")

#### **一括編集・削除！** 🗂️🗄️
- たった一つのシリーズを削除したり編集したりするためだけに、編集ボタンを何度も何度もクリックするのはもう終わりです！
- 利用するには、Web UIの左側にある `本の一覧` ページに移動し、編集/削除したい本を選択して、テーブルの上またはヘッダー内のボタンを使って必要な操作を行うだけです！
- _提供: [@jmarmstrong1207](https://github.com/jmarmstrong1207)_

![](/README_images/cwa-bulk-editting-diagram.png)

#### **自動バックアップサービス** 🔒
- CWAの自動機能中に何か問題が起きたらどうしようと心配ですか？心配無用です！
- デフォルトでは、CWAによって処理されたすべてのファイルのオリジナルは `/config/processed_books` に保存されます。これはCWA設定パネルで切り替えることができます。

#### **自動EPUB修復サービス** 🔨
- 次の本を読み始めようとワクワクしているのに、なぜかAmazonのSend-to-Kindleサービスが拒否し続ける、という経験はありませんか？もうそんなことはありません！

- 元々は [innocenat](https://github.com/innocenat/kindle-epub-fix) によって開発されたこのツールは、CWAによって処理されるすべてのEPUBについて、以下の潜在的な問題を修正します:
  - エンコーディングが指定されていない場合にUTF-8宣言を追加してUTF-8エンコーディング問題を修正
  - NCX目次がIDハッシュ付きの `<body>` にリンクしている場合のハイパーリンク問題を修正（AmazonがEPUBを拒否する原因となります）
  - メタデータ内の無効または欠落している言語タグを検出し、ユーザーに新しい言語を選択するよう促す
  - ソースフィールドのない迷子の `<img>` タグを削除
  - UTF-8エンコーディング、ハイパーリンクの問題、無効/欠落した言語タグ、迷子の画像タグなど、いくつかのEPUB互換性の問題を解決
- これにより、各EPUBファイルとAmazon **Send-to-Kindle** サービスとの **最大限の互換性を確保** し、Amazonデバイスを使用していないユーザーにとっても、低品質なファイルをクリーンアップできるという副次的なメリットがあります！
- デフォルトで有効ですが、設定で切り替えることができます。
- EPUB修復サービスによって処理されたファイルは、デフォルトで自動的に `/config/processed_books` にバックアップされますが、これも設定で切り替えることができます。
- 管理者パネルで進捗追跡可能なライブラリ全体の一括処理が利用可能です。
- Web UIとCLIの両方から利用可能です。

#### **使いやすいマルチ形式変換サービス** 🌌
- このユーティリティは、変換されたすべてのファイルのオリジナルを `/config/processed_books` に保存するか、プロセスを信頼してCWAに単純にファイルを変換・置換させるか（非推奨）のオプションをユーザーに提供します。
- 完全な使用方法は [こちら](#the-convert-library-tool) をご覧ください。

![CWA Convert Library Web UI](/README_images/CWA-new-process-ui.gif)

#### **追加のメタデータプロバイダー** 🗃️
- ユーザーは、ライブラリ内の本のメタデータを取得する際に、[isbndb.com](https://isbndb.com/) の巨大なデータベースを利用できるようになりました！
- [@chad3814](https://www.github.com/chad3814) によるコミュニティへの寛大な寄付のおかげで、[ibdb.dev](https://ibdb.dev/) を通じてアクセスが提供されています。
- [Hardcover](https://hardcover.app/) も現在、メタデータプロバイダーとしてCWAに追加する作業が進められています。

#### **KOReader 同期 (KOSync)** 📖⚡
自動書籍識別機能を備えた組み込みのKOReader進捗同期:
- **書籍識別:** すべての書籍に対してKOReader互換の部分MD5チェックサムを自動生成
- **統合された進捗:** KOReader → CWA読書状況 → Koboデバイス間の同期
- **ゼロ設定:** 起動時およびインポート時にチェックサムを生成するため、手動設定は不要
- **モダンな認証:** 既存のCWAアカウントを使用したRFC 7617 HTTP Basic認証
- **プラグイン利用可能:** CWAインスタンスの `/kosync` エンドポイントからダウンロード可能

#### **強化されたOAuth 2.0/OIDC認証** 🔐
- **自動検出:** Keycloak, Authentik, Google, Azure ADなどのプロバイダーとのシームレスなセットアップのための、OIDCメタデータURLによる自動エンドポイント設定
- **手動オーバーライド:** 自動検出が利用できない場合のOAuthエンドポイントの完全な手動制御
- **フィールドマッピング:** あらゆるプロバイダーのトークン構造に対応するための、ユーザー名とメールアドレスのJWTフィールド抽出設定
- **グループベースのロール:** OAuthプロバイダーのグループに基づいた管理者ロールの自動割り当て
- **テストツール:** 本番稼働前に設定が機能することを確認するための組み込みの接続テストと検証機能
- **エンタープライズ対応:** カスタムスコープ、複数の認証方法、包括的なトラブルシューティングのサポート
- 詳細なセットアップ手順については **📖 [完全なOAuth設定ガイド](https://github.com/crocodilestick/Calibre-Web-Automated/wiki/OAuth-Configuration)** をご覧ください

#### **サーバー統計追跡ページ** 📍📊
  - CWAがバックグラウンドでどれだけあなたを支えてきたか気になったことはありませんか？CWA統計ページをチェックして、あなたの生活を少しだけ楽にするためにCWAがどれだけ働いたかを示す楽しい統計リストを見てみましょう。
- 安心のため、そしてバグや奇妙な挙動の確認を容易にするために、すべての適用、インポート、変換、修正を記録するデータベースも存在します。
  <!-- - 完全なドキュメントは以下の [こちら](#checking-the-cover-enforcement-logs) にあります -->

![CWA Server Stats Page](/README_images/cwa-server-stats-page.png)

#### **ライブラリ自動検出** 📚🕵️
  - **新規ユーザーと既存ユーザー** の両方にとって、セットアッププロセスを **大幅に** 簡素化するために作られました。
  - **既存のライブラリを持たない新規ユーザー:** 🆕
    - **ライブラリがない？問題ありません！**
    - 既存のCalibreライブラリを持たない新規ユーザーは、もう `metadata.db` ファイルをコピー＆ペーストしてWeb UIでその場所を指定する必要はありません。CWAは指定されたバインド内にライブラリがないことを自動的に検出し、新しいライブラリを自動作成します！さらにWeb UIに自動的に登録するので、すぐに使い始めることができます。
  - **既存のライブラリを持つ新規または既存ユーザー:**
    - Calibreライブラリを含むディレクトリをバインドするだけで（再帰的に検索されるため、ディレクトリの深さは関係ありません）、CWAが自動的にそれを見つけてWeb UIにマウントします。
    - 複数のCalibreライブラリを含むディレクトリをバインドした場合、CWAは発見されたすべてのライブラリのディスクサイズを賢く比較し、最大のものをマウントします。
      - _CWAはインスタンスごとに1つのライブラリのみサポートしていますが、将来のリリースに向けて複数ライブラリのサポートが検討されています_
      - _それまでの間、統合したくない複数のライブラリを持つユーザーは、複数の並行したインスタンスを実行することをお勧めします_

#### **簡単ダーク/ライトモード切替** ☀️🌙
  - **Web UIのどこからでもワンクリックでライトモードとダークモードを切り替えられます！**
  - Web UIのナビゲーションバーにある 🕶️ アイコンをクリック/タップするだけで、いつでもテーマを切り替えられます。

#### **内部アップデート通知システム** 🛎️
  - ユーザーは、Web UI内から新しいアップデートの利用可能性を自動的に通知されるようになります。
  - 最新のGitHubリリースのバージョン番号とインストールされているバージョンの違いによって自動的にトリガーされます。
  - 煩わしくないように、アップデートされるまで1暦日につき1回のみ表示されるように設定されています。
  - _管理者ユーザーにのみ表示されます_

#### **手動ライブラリ更新** ♻️
  - 予期せぬ停電などで、本が取り込みフォルダに残ってしまったことはありませんか？もう手動で本を取り込みフォルダに出し入れする必要はありません。Web UIのナビゲーションバーにある `ライブラリ更新` ボタンを押すだけで、取り込みフォルダに残っているものはすべて自動的に取り込まれます！

#### **バックアップファイルの自動圧縮** 🤐
  - 毎日深夜の直前に、CWA-Auto-Zipperサービスがその日に処理されたすべてのファイルを自動的にzip圧縮します。
  - ディスク使用量を最小限に抑え、バックアップファイルを可能な限り整理された状態に保つのに役立ちます。
  - __デフォルトで有効ですが、管理者パネルのCWA設定ページで無効にすることができます__

![Calibre-Web Automated](README_images/cwa-bulk-editting-diagram.png "Calibre-Web Automated Bulk Editing & Bulk Deletion")

# 現在開発中でロードマップにある機能 🏗️🛣️

#### 優先度 高 🚨

- CWAと [Hardcover](https://hardcover.app/) の統合 📚
  - メタデータプロバイダーとしてのHardcoverの使用機能
  - 読書進捗をHardcoverアカウントと同期する機能！（Koboユーザーのみ）
- インターネット上で最もフレンドリーで暖かい場所とCWAを統合するためのコンパニオンプロジェクト 🐭🧀
- Calibreプラグインのサポート（例：deDRM） 🔌
- ライブラリ分割（Calibreライブラリと書籍ファイルを別の場所に配置）

#### 優先度 低 🌱

- 通知システムの統合（例：Telegram, Gotify, ntfyなど） 📧
- Prowlarr統合の可能性 🐯

アイデアや要望があればぜひ提案してください！どんなことでも歓迎します！

# インストール方法 📖

## クイックインストール 🚀

1. 以下のコマンドを使用してDocker Composeテンプレートファイルをダウンロードします:

```
curl -OL https://raw.githubusercontent.com/crocodilestick/calibre-web-automated/main/docker-compose.yml
```

2. Composeファイルを空のフォルダ（例：~/docker/calibre-web-automated/docker-compose.yml）に移動します。これはサーバーデータとライブラリを保存するために使用されます。

3. コメントを参考にComposeファイルを編集し、タイムゾーン（オプション）と希望するバインドを入力します。

4. `cd` を使用してComposeファイルをダウンロードした場所に移動し、以下を実行します:

```
docker compose up -d
```

これで準備完了です！ 🥳 ただし、潜在的な問題を回避し、機能を最大限に活用するために、これらの [インストール後のタスク](#post-install-tasks) を実行することをお勧めします。

---
## Docker Composeの使用 🐋⭐(推奨)

### 1. 以下のDocker Composeテンプレートを使用してコンテナをセットアップします: 🐋📜

~~~ bash
---
services:
  calibre-web-automated:
    image: crocodilestick/calibre-web-automated:latest
    container_name: calibre-web-automated
    environment:
      # 理解している場合のみ変更してください
      - PUID=1000
      - PGID=1000
      # お住まいのタイムゾーンに合わせて編集してください https://en.wikipedia.org/wiki/List_of_tz_database_time_zones
      - TZ=UTC
      # Hardcoverをメタデータプロバイダーとして使用する場合に必要なHardcover APIキー。こちらで入手: https://docs.hardcover.app/api/getting-started/
      - HARDCOVER_TOKEN=your_hardcover_api_key_here
      # ライブラリがネットワーク共有（例：NFS/SMB）上にある場合、ロックの問題を減らすためにWALを無効にします
      # 指定可能: true/false (デフォルト: false)
      - NETWORK_SHARE_MODE=false
      # Webサーバーのデフォルトポート (8083) を上書きします。
      # 任意の有効なポート番号を指定可能。
      - CWA_PORT_OVERRIDE=8083
    volumes:
      # 移行するCWユーザーは、既存のCWインスタンスを停止し、configフォルダのコピーを作成して、ここにバインドしてすべてのユーザー設定などを引き継ぐ必要があります。
      - /path/to/config/folder:/config
      # これは取り込みディレクトリであり、ライブラリディレクトリではありません。ここに追加されたものはすべて、CWA設定ページで設定した内容に従って自動的にライブラリに追加されます。ここに置かれたすべてのファイルは処理後に削除されます
      - /path/to/the/folder/you/want/to/use/for/book/ingest:/cwa-book-ingest
      # 既存のライブラリがない場合、CWAはここに提供されたバインドで自動的にライブラリを作成します
      - /path/to/your/calibre/library:/calibre-library
      # calibreプラグインを使用している場合、プラグインフォルダをここにバインドしてCWAのワークフローに追加させることができます（開発中）
      # 新規インストールで始める場合、Calibreプラグインの親ディレクトリから customize.py.json を上記のCalibre configボリュームの /path/to/config/folder/.config/calibre/customize.py.json にコピーする必要があります。詳細は下記を参照してください
      - /path/to/your/calibre/plugins/folder:/config/.config/calibre/plugins
    ports:
      # 2番目の数字ではなく、最初の数字を変更してWeb UIにアクセスしたいポートを変更してください
      - 8083:8083
    # CWA_PORT_OVERRIDEを1024未満のポートに設定した場合、以下の行のコメントを解除する必要があるかもしれません:
    # cap_add:
    #   - NET_BIND_SERVICE
    restart: unless-stopped
~~~

### コンテナバインディングの説明:

3つのメインボリュームバインディングがすべて別々のディレクトリであることを確認してください。他のバインドの中にバインドを作成するとエラーが発生する可能性があります。

- `/config` - CWAを稼働させ続けるためのログやその他の様々なファイルを保存するために使用されます
  -  **新規ユーザー** - 空のフォルダを使用してください（問題が発生した場合は、メインOSでそのフォルダの所有権が `root:root` でないことを確認してください）
  -  **既存/CWユーザー** - 既存のCalibre-Webセットアップをお持ちの方は、設定やユーザーが引き継がれるように、`app.db` を含む既存の `/config` ディレクトリをここにマップしてください
- `/cwa-book-ingest` - **注意** ⚠️ - このフォルダ内のすべてのファイルは処理後に **削除** されます。このフォルダは、インポートや自動変換のために新しい本をダンプするためだけに使用してください
- `/calibre-library` - これは `metadata.db` と書籍ファイルが存在するCalibreライブラリフォルダにバインドする必要があります。
  - **新規ユーザー** - 空のフォルダを使用してください（問題が発生した場合は、メインOSでそのフォルダの所有権が `root:root` でないことを確認してください）
  - **既存/CWユーザー** - マウントされたディレクトリに複数のライブラリがある場合、CWAは自動的に最大のものを見つけてマウントします - どの `metadata.db` が利用されたかの詳細はログを確認してください
- `/config/.config/calibre/plugins` - これは既存のCalibreプラグインのコピーを含むディレクトリにバインドする必要があります。設定は保持されます。（現在、CWA経由でプラグインを設定する方法はありません。）
  - プラグインが登録され機能するためには、Calibreプラグインの親ディレクトリから `customize.py.json` ファイルを上記の正しいconfigフォルダ、例：`/path/to/config/folder/.config/calibre/customize.py.json` にコピーする必要もあります。このファイルがどこにあるかわからない場合は、以下のセクションを参照してください。
<!-- - `/books` _(オプション)_ 別の場所に書籍ファイルのコレクションがあり、コンテナ内からアクセスできるようにしたい場合に利用します。大多数のユーザーにとっては不要であり、`/calibre-library` をマウントするだけで十分です -->
- `/app/calibre-web-automated/gmail.json` _(オプション)_ - これは、電子メールで本を送信するためにGmailアカウントでCalibre-WebやCWAをセットアップするために使用されます。興味がある場合は [こちら](https://github.com/janeczku/calibre-web/wiki/Setup-Mailserver#gmail) のガイドに従ってください。ただし、非常に面倒なプロセスになる可能性があるため、個人的にはシンプルなSMTPサーバーをお勧めします。

### `customize.py.json` はどこにありますか:

- macOSでは、通常 `~/Library/Preferences/calibre/customize.py.json` にあります。
- Linuxでは、通常 `~/.config/calibre/customize.py.json` にあります。
- Windowsでは、通常 `%APPDATA%\calibre\customize.py.json` (一般的に `C:\Users\<YourUsername>\AppData\Roaming\calibre\customize.py.json`) にあります。古いインストールでは `C:\Program Files\Calibre\customize.py.json` や `C:\Program Files\Calibre2\customize.py.json` にあるかもしれません。

**注:** このファイルが見つからない場合、まだCalibreプラグインを設定していないことを意味します。Calibreプラグインを使用しない場合は、プラグインボリュームのバインディングをスキップできます。


これで、Calibre-Web Automatedが稼働しているはずです！ **ただし**、潜在的な問題を回避し、機能を最大限に活用するために、これらの [インストール後のタスク](#post-install-tasks) を実行することをお勧めします。

# 通常のCalibre-Webからの移行ユーザー

- CWAは移行をできるだけ簡単にするように設計されています。CWインスタンスをCWAに移行するには、単に以下を行います:
  1. CWインスタンスがまだ実行中の場合は停止します
  2. Calibre-Webでの `/books` バインドが何であれ、CWAの `/calibre-library` バインドにする必要があります
  2. Docker ComposeでCWに使用していたのと同じ `/config` フォルダ（念のためコピーを使用することをお勧めします）をマウントします
  3. Calibreライブラリを含む同じフォルダをマウントします（LinuxserverのCalibre WebイメージのDocker Composeではデフォルトで `/books` になっています）
- これで完了です！すべてのユーザー、設定などが自動的に新しいCWAインスタンスに引き継がれます！お楽しみください！
- Web UIが読み込まれない問題が発生した場合は、CWと同じポートを使用してみて、セットアップが完了してから必要に応じて再構成してください

# インストール後のタスク:

## _Calibre-Web クイックスタートガイド_

1. ブラウザを開き、http://localhost:8083 または OPDSカタログの場合は http://localhost:8083/opds にアクセスします
2. デフォルトの管理者認証情報（_下記_）でログインします
3. 管理者ページからCalibre-Web Automatedインスタンスを設定します
  - すべての通常のCW設定の機能についてのガイドは [こちら](https://github.com/janeczku/calibre-web/wiki/Configuration#basic-configuration) にあります
  - `設定 -> 基本設定 -> 機能設定` で `アップロードを有効にする` が有効になっていることを確認してください
4. CWA設定パネルでCWAをお好みの動作になるように設定します
  - ここでは、特定の機能のオン/オフ、ターゲット形式の設定、どのファイル形式を無視し、どれを自動変換するかなどを設定できます
6. 本を取り込みフォルダにドロップして、すべてが機能していることを確認し、お楽しみください！

## デフォルトの管理者ログイン:

> **ユーザー名:** admin\
> **パスワード:** admin123

# 使い方 🔧

## ライブラリへの本の追加

- 新しくダウンロードした、または既存の電子書籍ファイルを `/cwa-book-ingest` である取り込みフォルダに移動するだけです
- このフォルダに入れたものはすべて自動的に分析され、必要に応じて変換され、CWA設定パネルで無視するように指定した形式でない限り、Calibre-Webライブラリにインポートされます
  - **⚠️ 注意 ⚠️**
    - _`/cwa-book-ingest` にファイルを直接ダウンロードすることはサポートされていません。重複インポートやデータベースの破損を引き起こす可能性があります。問題を避けるため、まず本を完全にダウンロードしてから、`/cwa-book-ingest` に転送することをお勧めします_
    - `/cwa-book-ingest` に転送する本が、rootではなくユーザーによって所有されていることを確認してください。そうしないと、権限エラーが発生し、インポートが不完全になる可能性があります。
    - 本が取り込まれるはずなのに取り込まれていない場合は、上部ナビゲーションバーの「ライブラリ更新」ボタンを使用して、取り込みプロセスを手動でトリガーしてください

## KOReader 同期 (KOSync) 📖⚡

CWAにはKOReader同期機能が組み込まれており、KOReaderを使用してデバイス間で読書進捗を同期できます。この機能は、従来のKOReader同期サーバーに代わるモダンで安全な代替手段を提供します。ブラウザで `http://your-cwa-instance:8083/kosync` にアクセスすると、CWA KOReaderプラグインのダウンロードリンクとインストール手順が表示されます。

---

## ローカル開発セットアップ

1. **イメージのビルド**
   [`build.sh`](https://github.com/crocodilestick/Calibre-Web-Automated/blob/main/build.sh) を編集して実行し、Calibre-Web-AutomatedのローカルDockerイメージをビルドします。使用法の詳細についてはスクリプト自体を参照してください。

2. **[`docker-compose.yml.dev`](https://github.com/crocodilestick/Calibre-Web-Automated/blob/main/docker-compose.yml.dev) の編集**
   最低限以下を更新してください:
   - `image:` → ステップ1のイメージタグ
   - `volumes mounts` → config, ingest, library, plugins のパス

 コード変更に応じてアプリを動的にリフレッシュさせるには、「ライブ編集」マウントの詳細と例について [`docker-compose.yml.dev`](https://github.com/crocodilestick/Calibre-Web-Automated/blob/main/docker-compose.yml.dev)** 内のコメントを参照してください。

3. **サービスの開始**
```
$ docker compose -f docker-compose.yml.dev up -d
```

4. **ログイン & 設定**
   - [デフォルトの管理者ログイン](https://github.com/crocodilestick/Calibre-Web-Automated?tab=readme-ov-file#default-admin-login) でサインインします
   - 必要に応じて [インストール後のタスク](https://github.com/crocodilestick/Calibre-Web-Automated?tab=readme-ov-file#post-install-tasks) に従ってください-

---

# 今後の開発 🏗️

- CWAは、CWAを今日のような形にするために本当に役立っている、非常に情熱的で活発なコミュニティを持っていることは本当に幸運です
- プロジェクトにアイデアがある、または貢献したい場合は、大歓迎です！スキルレベルや専門知識に関係なく、どなたでも受け入れています！
- 良いアイデアがある、または単に改善を提案したい場合は、Discordサーバー [こちら](https://discord.gg/EjgSeek94R) でご連絡ください！
