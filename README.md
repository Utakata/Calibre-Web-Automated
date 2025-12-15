# Calibre-Web Automated _(旧 Calibre-Web Automator)_

![Calibre-Web Automated](README_images/CWA-banner.png "Calibre-Web Automated")

## Calibre-Webを、あなたの「夢」のオールインワン・セルフホスト型電子書籍ライブラリソリューションへ。

![Docker Pulls](https://img.shields.io/docker/pulls/crocodilestick/calibre-web-automated)
![GitHub Release](https://img.shields.io/github/v/release/crocodilestick/calibre-web-automated)
![GitHub commits since latest release](https://img.shields.io/github/commits-since/crocodilestick/calibre-web-automated/latest)
![OAuth 2.0 + OIDC](https://img.shields.io/badge/OAuth-2.0%20%2B%20OIDC-blue?style=flat&logo=oauth)


## _クイックアクセス_

- [機能](#機能) 🪄
- [リリース](https://github.com/crocodilestick/Calibre-Web-Automated/releases) 🆕
- [ロードマップ](#現在開発中およびロードマップ上の機能-️️) 🛣️
- [インストール方法](#インストール方法-): 📖
  - [クイックインストール](#クイックインストール-) 🚀
  - [Docker-Compose](#docker-composeの使用-推奨) 🐋⭐(推奨)
  - [通常のCalibre Webからの移行ユーザー](#通常のcalibre-webからの移行ユーザー) 🔄
  - [インストール後のタスク](#インストール後のタスク) 🏁
    - [デフォルトのログイン情報 🔑](#デフォルトの管理者ログイン)
- [使い方](#使い方-) 🔧
  - [ライブラリへの本の追加](#ライブラリへの本の追加)
  - [KOReader同期 (KOSync)](#koreader同期-kosync-) 📖⚡
  - [OAuth認証セットアップ](#強化されたoauth-20oidc認証-) 🔐
- [開発者向け](#ローカル開発環境のセットアップ) 🚀
- [今後の開発](#今後の開発-️) 🏗️
- [サポート / コーヒーをおごる](https://ko-fi.com/crocodilestick) ☕

## なぜ存在するのか？ 🔓

Calibreはその歴史を考えると素晴らしいツールですが、コンテナ化した場合にいくつかの問題を抱えています。特にUIのためにKasmVNCサーバーインスタンスに依存している点は、モバイルでの使用がほぼ不可能であり、私のように小規模で低電力なサーバーを運用している場合には比較的リソースを消費します。

多くの人にとって、Calibre-Webはまさに救世主となり、Calibreインスタンスのコンテナ化に対する代替手段を提供しています。リソースが軽量で、よりモダンなUIを備えています。

しかし、完全版のCalibreと比較すると、残念ながらいくつかのコア機能が欠けており、多くの人が両方のサービスを並行して実行し、互いに欠けている部分を補完し合うという、しばしば不格好で不完全なソリューションになってしまっています。

## プロジェクトの目標 🎯

Calibre-Web Automatedは、Calibre-Webのモダンで軽量なWeb UIと、Calibreの堅牢で多才な機能セットを組み合わせ、さらにその上に多数の追加機能と自動化を加えた、オールインワンのソリューションを目指しています。

![Calibre-Web Automated Example Homepage](README_images/CWA-Homepage.png)
<p style="text-align:center;"><i>CWAを使えば、電子書籍ライブラリを整理してアクセスしやすくし、見た目も良くすることができます</i> 😎🦚</p>

## _関連プロジェクト_ 👬

### Calibre-Web Automated Book Downloader

- 本の検索とダウンロードリクエストのための直感的なWebインターフェースで、Calibre-Web-Automatedとシームレスに連携するように設計されています。このプロジェクトは、本をダウンロードしてCalibreライブラリに統合する準備プロセスを合理化します。

[<img src="https://raw.githubusercontent.com/vadret/android/master/assets/get-github.png" alt="Get it on GitHub" height="80">](https://github.com/calibrain/calibre-web-automated-book-downloader)

___

### Calibre-Web Companion

- **Flutter**で構築され、**Material You**を使用している[**Calibre Web Companion**](https://github.com/doen1el/calibre-web-companion)は、**Calibre Web**および**Calibre Web Automated**の**非公式コンパニオンアプリケーション**です。デバイス上で直接本コレクションを閲覧およびダウンロードでき、どちらのサービスも単独では提供できない、はるかに**モダンでモバイルフレンドリーなUX**を提供します。

<br>

[![Calibre Web Companion Preview](README_images/cw-companion-screenshots.png)](https://github.com/doen1el/calibre-web-companion)

[<img src="README_images/google-play.png" alt="Get it on Google Play" height="80">](https://play.google.com/store/apps/details?id=de.doen1el.calibreWebCompanion)
[<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png" alt="Get it on F-Droid" height="80">](https://f-droid.org/en/packages/de.doen1el.calibreWebCompanion/)
[<img src="https://raw.githubusercontent.com/vadret/android/master/assets/get-github.png" alt="Get it on GitHub" height="80">](https://github.com/doen1el/calibre-web-companion)

## コミュニティに参加しよう！ ❤️

- このプロジェクトのテストと開発に参加してくださったコミュニティのすべてのメンバーに**心から感謝**🙏します。何らかの形で貢献したいという方を歓迎します。どんなレベルの方でも大歓迎で、どんな小さなことでも助けになります！
- **このプロジェクトに何らかの形で貢献したい方**は、Discordサーバーで連絡を取り、どのように関わるのが最適かを確認してください:\
    \
    [![](https://dcbadge.limes.pink/api/server/https://discord.gg/EjgSeek94R)](https://discord.gg/EjgSeek94R)

- または、独自のコンパニオンプロジェクトを作成したり、遊びに来たり、問題に直面している場合は助けを求めたりしてください :)

## 🚨 ネットワーク共有（特にNFS）経由でのデプロイを計画しているユーザーへ 🚨

- Calibre、Calibre-Web、そしてCWAはすべてSQLite3ベースのアプリケーションであり、その結果、**ネットワーク共有（特にNFS）上での実行を好みません**
    - SQLiteは軽量なファイルベースのデータベースシステムとして設計されており、基礎となるファイルシステムが**ファイルロック、アトミック書き込み、および一貫性**に関する特定の保証をサポートしていることを前提としています。
    - **ネットワークファイルシステム（NFS、SMB/CIFSなど）は、これらの前提を満たさないことが多く、問題を引き起こす可能性があります。**
  - 一部のユーザーはNFS共有経由でCWAを正常にデプロイしていますが、そうすることで**診断が困難な多くの問題が発生する可能性があり**、実際に問題を抱えているユーザーのサポート時間を奪うことになります。
  - **したがって、V3.0.0以降、NFS共有経由でのデプロイは「サポート対象外」となります**。つまり、**自由に行って構いませんが**、**問題に直面したユーザーへのサポートは提供されません**。

### ネットワーク共有とSQLite WALモード

- CWAは、ローカルディスク上で先行書き込みログ（WAL）を有効にすることで、SQLiteの同時実行性を最適化します。
- 一部のネットワークファイルシステム（NFS/SMB）は、WALや信頼性の高いファイルロックを完全にサポートしていないため、断続的な「データベースがロックされています」というエラーや破損のリスクを引き起こす可能性があります。
- ネットワーク共有上にデプロイする場合は、次の環境変数を設定してWALを無効にしてください:

  - `NETWORK_SHARE_MODE=true`

これにより、CWAはCalibreの`metadata.db`および`app.db`設定データベースでWALを有効にしないようになります。また、初期化/メンテナンススクリプトによって実行される再帰的な所有権の変更（`chown`）も無効になり、ネットワークファイルシステムでの権限の問題を回避します。デフォルトは`false`（WAL有効）で、ローカルディスクでのパフォーマンスが向上します。

#### ネットワーク共有でのファイル監視

- デフォルトでは、CWAはLinuxの`inotify`（`inotifywait`経由）を使用して、取り込み（ingest）フォルダ内の新しいファイルを最小限の遅延とオーバーヘッドで検出します。
- ネットワーク共有（NFS/SMB）では、ファイルシステムイベントが信頼できないか、利用できない場合があります。`NETWORK_SHARE_MODE=true`が設定されている場合、CWAは取り込みおよびメタデータ監視サービスを、変更を定期的にスキャンするポーリングベースの監視に切り替えます。これにより、NAS/ネットワークマウントでの信頼性が向上しますが、I/Oがわずかに増加し、最大数秒の遅延が発生します。
- Docker Desktop（Windows/macOS）では、コンテナはLinuxKit/WSL2 VM上で実行され、ホストマウントされたパスでは`inotify`イベントが確実に伝播しない場合があります。CWAは起動時にDocker Desktopを自動検出し、信頼性のために同じポーリング監視を優先します。
- 上級者向け: `CWA_WATCH_MODE=poll`を設定することで、共有モードに関係なくポーリングを強制することもできます。

### 複数のプロキシ（Cloudflare Tunnel、リバースプロキシ）の背後での実行

- CWAは、WerkzeugのProxyFixミドルウェアを使用して、`X-Forwarded-For`、`X-Forwarded-Proto`、およびその他のプロキシヘッダーを適切に処理します。
- デフォルトでは、チェーン内の**1つのプロキシ**を信頼します。複数のプロキシ（例：Cloudflare Tunnel → nginx → CWA）がある場合は、次のように設定してください:

  - `TRUSTED_PROXY_COUNT=2` (またはチェーン内のプロキシの総数)

- **これが重要な理由**: セッション保護は、クライアントのIPアドレスに基づいてリクエストを検証します。ProxyFixが十分な数のプロキシを信頼していない場合、リクエスト間で異なるIPが表示され、「セッション保護がトリガーされました」という警告が表示され、再ログインが強制される可能性があります。
- **トラブルシューティング**: ログに頻繁にセッション保護の警告が表示される場合は、プロキシチェーンの深さを確認し、それに応じてこの変数を調整してください。

## **_機能:_**

### CWAはすべての通常のCW機能をサポートしています:
| | | |
|     :---:    |     :---:      |     :---:     |
| モダンでレスポンシブなBootstrap 3 HTML5インターフェース | ユーザーごとの権限設定を含む包括的なユーザー管理 | 電子書籍リーダーアプリ用のOPDSフィード |
| 電子書籍メタデータの編集と削除のサポート | さまざまなソースからのメタデータダウンロード（プラグインで拡張可能） | ログインユーザーへの電子書籍ダウンロード制限 |
| 公開ユーザー登録のサポート | ワンクリックで電子書籍をE-Readerに送信 | KoboデバイスとCalibreライブラリの同期 |
| 複数のフォーマットに対応したブラウザ内電子書籍閲覧サポート | カテゴリおよびユーザーごとのカスタム列コンテンツに基づくコンテンツの非表示 | eReaderでのアクセスを容易にする「マジックリンク」ログイン |
| 自動検出による強化されたOAuth 2.0/OIDC認証 | 高度な検索とフィルタリングオプション | 20以上の[言語](https://github.com/janeczku/calibre-web/wiki/Translation-Status)をサポートする多言語ユーザーインターフェース |

## さらに、これらの _**CWA固有の機能**_ が追加されています:

#### 詳細を読むには機能をクリックしてください:

| | | |
|     :---:    |     :---:      |     :---:     |
| [自動取り込みサービス ✨](#自動取り込みサービス-) | [自動変換サービス 🔃](#自動変換サービス-) | [表紙とメタデータの自動強制適用 👀📔](#calibre-web-uiを通じて行われた表紙とメタデータの変更の自動強制適用) |
| [一括編集と削除 🗂️](#一括編集と削除-️️) | [自動バックアップサービス 🔒](#自動バックアップサービス-) | [新規ユーザー向けの自動セットアップ体験 🦮](#ライブラリ自動検出-️) |
| [自動EPUB修復サービス 🔨](#自動epub修復サービス-) | [マルチフォーマット変換サービス 🌌](#使いやすいマルチフォーマット変換サービス-) | [ライブラリ自動検出 📚🕵️](#ライブラリ自動検出-️) |
| [サーバースタート追跡ページ 📍](#サーバースタート追跡ページ-) | [サーバースタート追跡 📊](#サーバースタート追跡ページ-) | [ダーク/ライトモードの簡単切り替え ☀️🌙](#ダークライトモードの簡単切り替え-️) |
| [内部更新通知システム 🛎️](#内部更新通知システム-️) | [バックアップファイルの自動圧縮 🤐](#バックアップファイルの自動圧縮-) | [追加のメタデータプロバイダー 🗃️](#追加のメタデータプロバイダー-️) |
| [KOReader同期 (KOSync) 📖⚡](#koreader同期-kosync-) | [強化されたOAuth 2.0/OIDC認証 🔐](#強化されたoauth-20oidc認証-) | |

#### **自動取り込みサービス** ✨
- CWAは現在、27種類の一般的な電子書籍フォーマットの自動取り込みをサポートしています。
- ユーザーは、管理パネルで特定のフォーマットを無視したり、他のフォーマットに自動変換したりするようにサービスの動作を設定できます。

<!-- - **加重変換アルゴリズム:** ⚖️
  - どのフォーマットがepubに最適に変換されるかについてのCalibre eBook-converterのドキュメントで提供される情報を使用して、CWAは複数の電子書籍フォーマットを含むダウンロードから、どのフォーマットが最も最適に変換されるかを判断し、他のフォーマットを無視して、**可能な限り最高の品質**と**重複インポートなし**を保証します -->

#### **自動変換サービス** 🔃
- デフォルトでオンになっていますが、CWA設定ページでオフに切り替えることができます。デフォルトのターゲットフォーマットはEPUBです。
  - _利用可能なターゲットフォーマット:_ **EPUB**, **MOBI**, **AZW3**, **KEPUB**, **PDF**
- 取り込みディレクトリ内の新しいファイルを検出したときに、ファイルがユーザーの設定した自動変換対象のフォーマットである場合、現在のターゲットフォーマットに変換します。
- 以下の**28種類のファイルタイプが現在サポートされています:**
  - _.acsm, .azw, .azw3, .azw4, .mobi, .cbz, .cbr, .cb7, .cbc, .chm, .djvu, .docx, .epub, .fb2, .fbz, .html, .htmlz, .lit, .lrf, .odt, .pdf, .prc, .pdb, .pml, .rb, .rtf, .snb, .tcr, .txtz_
  - _注: .acsmには追加のCalibreプラグインが必要です_

#### **Calibre-Web UIを通じて行われた表紙とメタデータの変更の自動強制適用!** 👀📔
- 通常のCalibre-Webでは、本の**表紙やメタデータ**に加えられた変更は、Calibre-Web UIでの本の表示にのみ適用され、期待されるように電子書籍のファイル自体には何も変更されません。
- これにより、CWのSend-To-Kindle機能を利用する多くのユーザーにとって不満が生じます。せっかく選んだ高品質な表紙や慎重に選んだメタデータが、他のすべてのデバイスで完全に欠落していることにがっかりするのです！あーあ！
- CWAの**表紙とメタデータの自動強制適用機能**により、**あなたが**本に加えた変更は**何であれ**、**本自体**にも、Web UIにも適用され、**見たままの結果が得られます。**

![Cover Enforcement CWA](README_images/cwa-enforcer-diagram.png "CWA 1.2.0 Cover Enforcement Diagram")

#### **一括編集と削除!** 🗂️🗄️
- 1つのシリーズを削除または編集するためだけに、編集ボタンを何度も何度もクリックする必要はもうありません！
- 使用するには、Web UIの左側にある「本リスト」ページに移動し、編集/削除したい本を選択して、テーブルの上またはヘッダー内のボタンを使用して必要な操作を行うだけです！
- _協力: [@jmarmstrong1207](https://github.com/jmarmstrong1207)_

![](/README_images/cwa-bulk-editting-diagram.png)

#### **自動バックアップサービス** 🔒
- CWAの自動機能中に何かがうまくいかなかった場合にどうなるか心配ですか？心配無用です！
- デフォルトでは、CWAによって処理されたすべてのファイルのオリジナルは `/config/processed_books` に保存されますが、これはCWA設定パネルで切り替えることができます。

#### **自動EPUB修復サービス** 🔨
- 次の本を読み始めようとワクワクしているのに、なぜかAmazonのSend-to-Kindleサービスが拒否し続けるという経験はありませんか？もうそんなことはありません！

- 元々は [innocenat](https://github.com/innocenat/kindle-epub-fix) によって開発されたこのツールは、CWAによって処理されるすべてのEPUBについて、以下の潜在的な問題を修正します:
  - エンコーディングが指定されていない場合、UTF-8宣言を追加してUTF-8エンコーディングの問題を修正します。
  - NCX目次がIDハッシュ付きの `<body>` にリンクしている場合のハイパーリンクの問題（AmazonがEPUBを拒否する原因）を修正します。
  - メタデータの無効および/または欠落している言語タグを検出し、ユーザーに新しい言語を選択するように促します。
  - sourceフィールドのない迷子の `<img>` タグを削除します。
  - UTF-8エンコーディング、ハイパーリンクの問題、無効/欠落した言語タグ、迷子の画像タグなど、いくつかのEPUB互換性の問題を解決します。
- これにより、Amazon **Send-to-Kindle** サービスとの各EPUBファイルの**最大限の互換性を確保**し、Amazonデバイスを使用しないユーザーにとっても、低品質なファイルをクリーンアップできるという副次的な利点があります！
- デフォルトで有効になっていますが、設定で切り替えることができます。
- EPUB修復サービスによって処理されたファイルは、デフォルトで `/config/processed_books` に自動的にバックアップされますが、これも設定で切り替えることができます。
- 管理パネルで、進行状況の追跡が可能なライブラリ全体の一括処理を利用できます。
- Web UIとCLIの両方で利用可能です。

#### **使いやすいマルチフォーマット変換サービス** 🌌
- このユーティリティは、ユーザーに、変換されたすべてのファイルのオリジナルのコピーを `/config/processed_books` に保持するか、プロセスを信頼してCWAに単にそれらのファイルを変換して置き換えさせる（非推奨）かのオプションを提供します。
- 完全な使用法の詳細は[こちら](#the-convert-library-tool)にあります。

![CWA Convert Library Web UI](/README_images/CWA-new-process-ui.gif)

#### **追加のメタデータプロバイダー** 🗃️
- ユーザーは、ライブラリ内の本のメタデータを取得する際に、[isbndb.com](https://isbndb.com/) の巨大なデータベースを利用できるようになりました！
- アクセスは、[@chad3814](https://www.github.com/chad3814) によるコミュニティへの寛大な寄付のおかげで、[ibdb.dev](https://ibdb.dev/) を通じて提供されています。
- [Hardcover](https://hardcover.app/) も現在、メタデータプロバイダーとしてCWAに追加する作業が進行中です。

#### **KOReader同期 (KOSync)** 📖⚡
自動本識別機能を備えた組み込みのKOReader進行状況同期:
- **本識別:** すべての本に対してKOReader互換の部分的なMD5チェックサムを自動生成します。
- **統一された進行状況:** KOReader → CWA読書状況 → Koboデバイス間で同期します。
- **設定不要:** 起動時およびインポート時にチェックサムが生成され、手動設定は不要です。
- **モダンな認証:** 既存のCWAアカウントを使用したRFC 7617 HTTP Basic認証。
- **プラグイン利用可能:** CWAインスタンスの `/kosync` エンドポイントからダウンロードできます。

#### **強化されたOAuth 2.0/OIDC認証** 🔐
- **自動検出:** Keycloak、Authentik、Google、Azure ADなどのプロバイダーとシームレスに設定するための、OIDCメタデータURLによる自動エンドポイント設定。
- **手動オーバーライド:** 自動検出が利用できない場合のOAuthエンドポイントの完全な手動制御。
- **フィールドマッピング:** 任意のプロバイダーのトークン構造で動作するように、ユーザー名と電子メールのJWTフィールド抽出を設定可能。
- **グループベースのロール:** OAuthプロバイダーのグループに基づく自動管理者ロール割り当て。
- **テストツール:** 本番稼働前に設定が機能することを確認するための組み込みの接続テストおよび検証。
- **エンタープライズ対応:** カスタムスコープ、複数の認証方法、および包括的なトラブルシューティングのサポート。
- **📖 [完全なOAuth設定ガイド](https://github.com/crocodilestick/Calibre-Web-Automated/wiki/OAuth-Configuration)** 詳細な設定手順についてはこちらをご覧ください。

#### **サーバースタート追跡ページ** 📍📊
  - CWAがバックグラウンドでどれだけあなたのために働いてくれたか気になったことはありませんか？CWA統計ページをチェックして、CWAがあなたの生活を少し楽にするために何回そこにいたかを示す楽しい統計リストを見てみてください。
- 安心のため、そしてバグや奇妙な動作の確認を容易にするために、すべての強制適用、インポート、変換、および修正を追跡するデータベースも存在します。
  <!-- - 完全なドキュメントは[こちら](#checking-the-cover-enforcement-logs)にあります -->

![CWA Server Stats Page](/README_images/cwa-server-stats-page.png)

#### **ライブラリ自動検出** 📚🕵️
  - **新規ユーザーと既存ユーザーの両方**にとって、セットアッププロセスを**大幅に**簡素化するために作成されました。
  - **既存のライブラリを持たない新規ユーザー:** 🆕
    - **ライブラリがない？問題ありません！**
    - 既存のCalibreライブラリを持たない新規ユーザーは、`metadata.db` ファイルをコピーしてWeb UIでその場所を指定する必要がなくなりました。CWAは、指定されたバインドにライブラリがないことを自動的に検出し、自動的に新しいライブラリを作成します！さらに、Web UIに自動的に登録されるため、すぐに使い始めることができます。
  - **既存のライブラリを持つ新規または既存のユーザー:**
    - Calibreライブラリを含むディレクトリをバインドするだけで（検索は再帰的に行われるため、ディレクトリの深さは関係ありません）、CWAは自動的にそれを見つけてWeb UIにマウントします。
    - 1つ以上のCalibreライブラリを含むディレクトリをバインドした場合、CWAは発見されたすべてのライブラリのディスクサイズをインテリジェントに比較し、最大のものをマウントします。
      - _CWAはインスタンスごとに1つのライブラリのみをサポートしていますが、将来のリリースに向けて複数のライブラリのサポートが検討されています_
      - _それまでの間、統合したくない複数のライブラリを持つユーザーは、複数の並行インスタンスを実行することをお勧めします_

#### **ダーク/ライトモードの簡単切り替え** ☀️🌙
  - **Web UIのどこからでもワンクリックでライトモードとダークモードを切り替えられます！**
  - Web UIのナビゲーションバーにある 🕶️ アイコンをクリック/タップするだけで、テーマを自由に切り替えることができます。

#### **内部更新通知システム** 🛎️
  - ユーザーは、Web UI内から新しいアップデートの利用可能性を自動的に通知されるようになりました。
  - 最新のGitHubリリースのバージョン番号とインストールされているバージョンの違いによって自動的にトリガーされます。
  - 煩わしくないように、更新されるまで暦日ごとに1回だけ表示されるように設定されています。
  - _管理者ユーザーにのみ表示されます_

#### **手動ライブラリ更新** ♻️
  - 予期しない停電などの後に、本が取り込みフォルダに詰まってしまったことはありませんか？取り込みフォルダから手動で本を出し入れする必要はもうありません。Web UIのナビゲーションバーにある「ライブラリ更新」ボタンを押すだけで、取り込みフォルダに残っているものが自動的に取り込まれます！

#### **バックアップファイルの自動圧縮** 🤐
  - 毎日真夜中の直前に、CWA-Auto-Zipperサービスはその日に処理されたすべてのファイルを自動的に圧縮します。
  - ディスク使用量を最小限に抑え、バックアップファイルを可能な限り整理された状態に保つのに役立ちます。
  - __デフォルトで有効になっていますが、管理パネルのCWA設定ページで無効にすることができます__

![Calibre-Web Automated](README_images/cwa-bulk-editting-diagram.png "Calibre-Web Automated Bulk Editing & Bulk Deletion")

# 現在開発中およびロードマップ上の機能 🏗️🛣️

#### 高優先度 🚨

- CWAと[Hardcover](https://hardcover.app/)の統合 📚
  - Hardcoverをメタデータプロバイダーとして使用する機能
  - 読書進行状況をHardcoverアカウントと同期する機能！（Koboユーザーのみ）
- CWAをインターネット上で最もフレンドリーで温かい場所と統合するためのコンパニオンプロジェクト 🐭🧀
- Calibreプラグイン（例：deDRM）のサポート 🔌
- 分割ライブラリ（Calibreライブラリと本を別々の場所に配置する）

#### 低優先度 🌱

- 通知システムの統合（例：Telegram, Gotify, ntfyなど） 📧
- Prowlarr統合の可能性 🐯

アイデアや要望があれば提案してください！私たちは何でも受け入れます！

# インストール方法 📖

## クイックインストール 🚀

1. 以下のコマンドを使用してDocker Composeテンプレートファイルをダウンロードします:

```
curl -OL https://raw.githubusercontent.com/crocodilestick/calibre-web-automated/main/docker-compose.yml
```

2. Composeファイルを空のフォルダ（例：~/docker/calibre-web-automated/docker-compose.yml）に移動します。これはサーバーデータとライブラリを保存するために使用されます。

3. コメントを参考にしてComposeファイルを編集し、タイムゾーン（オプション）と希望するバインドを入力します。

4. `cd` を使用してComposeファイルをダウンロードした場所に移動し、以下を実行します:

```
docker compose up -d
```

これで準備完了です！🥳 ただし、潜在的な問題を回避し、機能を最大限に活用するために、これらの[インストール後のタスク](#インストール後のタスク)を実行することをお勧めします。

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
      # 何をしているかわかっている場合のみ変更してください
      - PUID=1000
      - PGID=1000
      # 現在のタイムゾーンに合わせて編集してください https://en.wikipedia.org/wiki/List_of_tz_database_time_zones
      - TZ=UTC
      # Hardcoverをメタデータプロバイダーとして使用するにはHardcover APIキーが必要です。こちらから入手してください: https://docs.hardcover.app/api/getting-started/
      - HARDCOVER_TOKEN=your_hardcover_api_key_here
      # ライブラリがネットワーク共有（例：NFS/SMB）上にある場合、ロックの問題を減らすためにWALを無効にしてください
      # 受け入れる値: true/false (デフォルト: false)
      - NETWORK_SHARE_MODE=false
      # Webサーバーのデフォルトポート (8083) をオーバーライドします。
      # 任意の有効なポート番号を受け入れます。
      - CWA_PORT_OVERRIDE=8083
    volumes:
      # 移行するCWユーザーは、既存のCWインスタンスを停止し、configフォルダのコピーを作成し、それをここにバインドして、すべてのユーザー設定などを引き継ぐ必要があります。
      - /path/to/config/folder:/config
      # これは取り込み（ingest）ディレクトリであり、ライブラリディレクトリではありません。ここに追加されたものは、CWA設定ページの設定に従って自動的にライブラリに追加されます。ここに配置されたすべてのファイルは処理後に削除されます
      - /path/to/the/folder/you/want/to/use/for/book/ingest:/cwa-book-ingest
      # 既存のライブラリがない場合、CWAはここで提供されたバインドに自動的にライブラリを作成します
      - /path/to/your/calibre/library:/calibre-library
      # calibreプラグインを使用している場合、プラグインフォルダをここにバインドして、CWAのワークフローに追加させることができます（作業中）
      # 新規インストールから始める場合は、Calibre設定ボリュームの /path/to/config/folder/.config/calibre/customize.py.json に customize.py.json もコピーする必要があります。詳細は下記の注記を参照してください。
      - /path/to/your/calibre/plugins/folder:/config/.config/calibre/plugins
    ports:
      # Web UIにアクセスしたいポートを変更するには、2番目の番号ではなく最初の番号を変更してください
      - 8083:8083
    # CWA_PORT_OVERRIDEを1024未満のポートに設定する場合、次の行のコメントを解除する必要がある場合があります:
    # cap_add:
    #   - NET_BIND_SERVICE
    restart: unless-stopped
~~~

### コンテナバインディングの説明:

3つのメインボリュームバインディングがすべて別々のディレクトリであることを確認してください。他のバインド内にバインドを作成するとエラーが発生する可能性があります。

- `/config` - CWAを実行し続けるためのログやその他のファイルを保存するために使用されます
  -  **新規ユーザー** - 空のフォルダを使用してください（問題が発生した場合は、メインOSでそのフォルダの所有権が `root:root` でないことを確認してください）
  -  **既存/CWユーザー** - 既存のCalibre-Webセットアップをお持ちの方は、設定とユーザーが引き継がれるように、`app.db` を含む既存の `/config` ディレクトリをマップしてください
- `/cwa-book-ingest` - **注意** ⚠️ - このフォルダ内のすべてのファイルは、処理後に**削除**されます。このフォルダは、インポートおよび自動変換のために新しい本をダンプするためだけに使用してください。
- `/calibre-library` - これは、`metadata.db` と本のファイルが存在するCalibreライブラリフォルダにバインドする必要があります。
  - **新規ユーザー** - 空のフォルダを使用してください（問題が発生した場合は、メインOSでそのフォルダの所有権が `root:root` でないことを確認してください）
  - **既存/CWユーザー** - マウントされたディレクトリに複数のライブラリがある場合、CWAは自動的に最大のものを見つけてマウントします - どの `metadata.db` が利用されたかについての詳細はログを確認してください
- `/config/.config/calibre/plugins` - これは、既存のCalibreプラグインのコピーを含むディレクトリにバインドする必要があります。設定は保持されます。（現在、CWA経由でプラグインを設定する方法はありません。）
  - プラグインが登録されて機能するためには、Calibreプラグインの親ディレクトリから上記の正しい設定フォルダに `customize.py.json` ファイルもコピーする必要があります（例：`/path/to/config/folder/.config/calibre/customize.py.json`）。このファイルが見つからない場合は、以下のセクションを参照してください。
<!-- - `/books` _(オプション)_ 別の場所に本のファイルのコレクションがあり、コンテナ内でアクセスできるようにしたい場合に利用します。大多数のユーザーにとって、これは不要であり、`/calibre-library` をマウントすれば十分です -->
- `/app/calibre-web-automated/gmail.json` _(オプション)_ - これは、電子メールで本を送信するためにCalibre-Webおよび/またはCWAをgmailアカウントでセットアップするために使用されます。興味がある場合は[こちら](https://github.com/janeczku/calibre-web/wiki/Setup-Mailserver#gmail)のガイドに従ってください。ただし、非常に面倒なプロセスになる可能性があるため、個人的にはシンプルなSMTPサーバーをお勧めします。

### `customize.py.json` はどこにありますか:

- macOSでは、通常 `~/Library/Preferences/calibre/customize.py.json` にあります。
- Linuxでは、通常 `~/.config/calibre/customize.py.json` にあります。
- Windowsでは、通常 `%APPDATA%\calibre\customize.py.json` にあります（通常 `C:\Users\<YourUsername>\AppData\Roaming\calibre\customize.py.json`）。古いインストールでは `C:\Program Files\Calibre\customize.py.json` または `C:\Program Files\Calibre2\customize.py.json` にある場合があります。

**注:** このファイルが見つからない場合は、まだCalibreプラグインを設定していないことを意味します。Calibreプラグインを使用しない場合は、プラグインのボリュームバインディングをスキップできます。


これで、Calibre-Web Automatedが稼働しているはずです！**ただし**、潜在的な問題を回避し、機能を最大限に活用するために、これらの[インストール後のタスク](#インストール後のタスク)を実行することをお勧めします。

# 通常のCalibre-Webからの移行ユーザー

- CWAは、切り替えを可能な限り簡単にするように設計されています。CWインスタンスをCWAに移行するには、単に以下を行います:
  1. CWインスタンスがまだ実行中の場合は停止します。
  2. Calibre-Webでの `/books` バインドを、CWAの `/calibre-library` バインドにします。
  2. CWに使用していたのと同じ `/config` フォルダ（念のためそのコピーを作成することをお勧めします）をDocker Composeにマウントします。
  3. Calibreライブラリを含む同じフォルダをマウントします（Calibre WebのLinuxserverイメージ用のDocker Composeではデフォルトで `/books` になっています）。
- これで完了です！すべてのユーザー、設定などが新しいCWAインスタンスに自動的に引き継がれます！お楽しみください！
- Web UIが読み込まれない問題が発生した場合は、CWと同じポートを使用して、セットアップが完了してから再設定してみてください。

# インストール後のタスク:

## _Calibre-Web クイックスタートガイド_

1. ブラウザを開き、http://localhost:8083 またはOPDSカタログ用の http://localhost:8083/opds にアクセスします。
2. デフォルトの管理者資格情報（_下記_）でログインします。
3. 管理ページからCalibre-Web Automatedインスタンスを設定します。
  - すべての通常のCW設定が何をするかについてのガイドは[こちら](https://github.com/janeczku/calibre-web/wiki/Configuration#basic-configuration)にあります。
  - `設定 -> 基本設定 -> 機能設定` で `アップロードを有効にする` が有効になっていることを確認してください。
4. CWA設定パネルで、CWAが希望どおりに動作するように設定します。
  - ここでは、特定の機能のオン/オフ、ターゲットフォーマットの設定、無視すべきファイルフォーマットや自動変換すべきフォーマットなどを設定できます。
6. 取り込みフォルダに本をドロップして、すべてが機能していることを確認し、お楽しみください！

## デフォルトの管理者ログイン:

> **ユーザー名:** admin\
> **パスワード:** admin123

# 使い方 🔧

## ライブラリへの本の追加

- 新しくダウンロードした、または既存の電子書籍ファイルを取り込みフォルダ（`/cwa-book-ingest`）に移動するだけです。
- このフォルダに配置したものはすべて自動的に分析され、必要に応じて変換され、CWA設定パネルで無視するように指定したフォーマットでない場合はCalibre-Webライブラリにインポートされます。
  - **⚠️ 注意 ⚠️**
    - _`/cwa-book-ingest` にファイルを直接ダウンロードすることはサポートされていません。重複インポートやデータベースの破損の原因となる可能性があります。問題を回避するために、まず本を完全にダウンロードしてから、`/cwa-book-ingest` に転送することをお勧めします。_
    - `/cwa-book-ingest` に転送する本が、rootではなくユーザーによって所有されていることを確認してください。そうしないと、権限エラーが発生し、インポートが不完全になる可能性があります。
    - 本が取り込まれるはずなのに取り込まれていない場合は、上部ナビゲーションバーの「ライブラリ更新」ボタンを使用して、取り込みプロセスを手動でトリガーしてください。

## KOReader同期 (KOSync) 📖⚡

CWAにはKOReader同期機能が組み込まれており、KOReaderを使用してデバイス間で読書進行状況を同期できます。この機能は、従来のKOReader同期サーバーに代わるモダンで安全な代替手段を提供します。ブラウザで `http://your-cwa-instance:8083/kosync` にアクセスすると、CWA KOReaderプラグインのダウンロードリンクとインストール手順が表示されます。

---

## ローカル開発環境のセットアップ

1. **イメージのビルド**
   [`build.sh`](https://github.com/crocodilestick/Calibre-Web-Automated/blob/main/build.sh) を編集して実行し、Calibre-Web-AutomatedのローカルDockerイメージをビルドします。使用方法の詳細についてはスクリプト自体を参照してください。

2. **[`docker-compose.yml.dev`](https://github.com/crocodilestick/calibre-web-automated/blob/main/docker-compose.yml.dev) の編集**
   少なくとも以下を更新してください:
   - `image:` → ステップ1のイメージタグ
   - `volumes mounts` → config, ingest, library, plugins

 コードの変更に応じてアプリを動的に更新するには、「ライブ編集」マウントの詳細と例について、[`docker-compose.yml.dev`](https://github.com/crocodilestick/calibre-web-automated/blob/main/docker-compose.yml.dev) 内のコメントを参照してください。

3. **サービスの開始**
```
$ docker compose -f docker-compose.yml.dev up -d
```

4. **ログインと設定**
   - [デフォルトの管理者ログイン](https://github.com/crocodilestick/Calibre-Web-Automated?tab=readme-ov-file#デフォルトの管理者ログイン)でサインインします。
   - 必要に応じて[インストール後のタスク](https://github.com/crocodilestick/Calibre-Web-Automated?tab=readme-ov-file#インストール後のタスク)を実行します。

---

# 今後の開発 🏗️

- CWAは、CWAを今日の姿にするために本当に協力してくれる、非常に情熱的で活発なコミュニティを持っており、本当に幸運です。
- アイデアがある場合やプロジェクトに貢献したい場合は、大歓迎です！スキルレベルや専門知識に関係なく、どなたでも受け入れます！
- 良いアイデアがある場合や、単に改善を提案したい場合は、[こちら](https://discord.gg/EjgSeek94R)のDiscordサーバーでお気軽にご連絡ください！
