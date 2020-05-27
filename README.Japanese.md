
# UTM(日本語)
[![Build](https://github.com/utmapp/UTM/workflows/Build/badge.svg?branch=master&event=push)][1]

 任意の計算可能なシーケンスを計算するために使用できる機械を発明することは、完全に可能である。（図霊）
-- <cite>Alan Turing, 1936</cite>

UTMは機能がそろっているiOS仮想マシンのホストです。つまり、WindowsやAndroidなどのOSをiPhoneやiPadで実行することができます。詳細はアクセスしてください。https://getutm.ap/

!iPhoneでUTMのスクリーンショットを実行します。][4]
## 特性
* 30+プロセッサに対応しています。x 86_を含みます。64、ARM 64とRISC-Vは後端のqemeのおかげです。
* SPICEのおかげで，準仮想化により高速なローカルパターンが実現した。
* qeme TCGを使ってJITによる加速を実現
* *作成、管理、デバイスから直接VMSを実行する
* 脱獄はいらない
## インストール

UTMを使いたいだけなら、ここは正しいところではないです。訪問してください。https://getutm.ap/install/for directions.

## コンパイル
また、clone Sub module-i-nit-recursive.」.最新バージョンを検索して構築し、arm 64から構築する（iOS用）またはx 86_64構築（iOSシミュレータ用）Sysrootワークをダウンロードします。SysrootをUTMのルートディレクトリに展開します。UTM.xcodeprojあなたの署名証明書を選択して、XcodeからUTMを実行します。
## 簡単:
依存関係を得るために推奨される方法は[ Github action ] [ 5 ]からビルドされたアーティファクトを使用することです。最新のリリースビルドを探して、どちらかのARM 64ビルド（IOS）またはX 86 RAW 64ビルド（IOSシミュレータ用）からsysrootアーティファクトをダウンロードしてください。その後、アーティファクトをutmのルートディレクトリに展開します。その後、`を開くことができますUTM.xcodeprojシグネチャ証明書を選択してから、xcodeからUTMを実行します。
### 高级：
依存項を自分で構築したいなら、新しいmacOS VMから始めることを強く勧めます。これは、いくつかの依存項が、アーキテクチャがマッチングしていないにもかかわらず、`。いくつかの取り付けられたライブラリは、例えば`libusb`と`gawk`のように破壊されて構築されます。
1.Xcodeコマンドラインの取り付けと以下の先決条件の構築
`brew install bison pkg-config gettext glib libgpg-error nasm`
「bison」をあなたの「$PATH」環境に追加してください。
2. `git submodule update --init --recursive` もしあなたがまだいないなら。
3.実行`。/scripts/build_dependencies.shコンパイルを開始します。シミュレータの構築のためなら、実行します`。dependences.sh-a x 86_64`。実行`。/scripts/build_dependencies.shコンパイルを開始します。シミュレータの構築のためなら、実行します`。dependences.sh-a x 86_64`。
4.開く`UTM.xcodeproj署名証明書を選択します。
5.Xcodeからの構築と配置。
## 署名する
Xcodeを使って構築すれば、自動的に署名が完了するはずです。署名機構のエラーのため、iOS 13.3.1はサポートされていません。13.3.1以下のいずれかのバージョンのIOSを使用することができます。

## 署名バージョン
`ipa`[署[3]はfake-`ipa`[署名][3]はfake-signedです。脱獄したら、サインしなくてもいいです。直接Filzaを使ってインストールしてもいいです。です。
在庫設備のために発行版をサインしたいなら、様々な方法があります。[iOSアプリケーション署名者][2]の使用を推奨します。多くの「クラウド」署名サービス（ApCakeなど）にはいくつかの既知の問題が存在し、UTMと互換性がないことに留意されたい。VM仮想マシンを起動しようとしたときにクラッシュした場合、署名証明書は無効です。
技術の詳細には、「開発」と「発表」の二つの署名証明書があります。UTMは「開発」が必要であり、「開発」は「任務の許可を得る」権利を有する。

### 署名開発

もしあなたがxcarchiveに署名したいなら、例えば「Githubアクション」から［1］built artfractから、以下のコマンドが使用できます。
`
./scripts/reign.shUTM.xcarchiveout putPath PROFILE_NAMEチームID
`
そのうち`PROFILE_NAME`は配置ファイルの名称であり、`TEAM_ID`は構成ファイルにおけるチーム名の隣の識別子である。署名鍵が鍵チェーンに導入され、アイテム設定ファイルがiOSデバイスにインストールされていることを確認します。
脱獄したios設備があれば、署名を偽造することもできます。
`
./scripts/reign.shUTM.xcarchiveout put Path
`
## これがAppStoreになぜないのか？
アップルは、コードを解釈したか、生成したどんなアプリケーションも許可しません、したがって、UTMが決して許されないでしょう。しかし、インターネット上の人々が脱獄を必要とせずにサイドローブのアプリに来ている様々な方法があります。我々は、これらのメソッドのどれかを容認しないか、支持しません。
## 許可する
UTMは許容Apache 2.0ライセンスの下で配布されます。しかし、いくつかの（L）GPLコンポーネントを使用します。ほとんどが動的にリンクされますが、gstreamerプラグインは静的にリンクされ、コードの一部はqemuから取得されます。あなたがこのアプリケーションを再配布するつもりならば、これに注意してください。

[1]: https://github.com/utmapp/UTM/actions?query=event%3Arelease+workflow%3ABuild
[2]: https://dantheman827.github.io/ios-app-signer/
[3]: https://github.com/utmapp/UTM/releases
[4]: screen.png
[5]: https://github.com/utmapp/UTM/actions?query=workflow%3ABuild+event%3Arelease+is%3Asuccess
