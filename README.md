以下は日本語訳です。

---

# Apache Roller

[Apache Roller](http://roller.apache.org) は、Java ベースのフル機能を備えたマルチユーザーおよびグループブログサーバであり、小規模から大規模なブログサイトに適しています。  
Roller は通常、Apache Tomcat と MySQL を使用して実行されます。  
Roller は次の Maven プロジェクトで構成されています:

* _roller-project_:         トップレベルプロジェクト
* _app_:                    Roller Weblogger のウェブアプリケーション、JSP ページ、Velocity テンプレート
* _assembly-release_:       Roller の公式ディストリビューションを作成するために使用
* _docs_:                   ASCII Doc 形式の Roller ドキュメント
* _it-selenium_:            Selenium を使用した Roller の統合ブラウザテスト

## ドキュメント

Roller のインストール、ユーザー、およびテンプレートガイドは、ODT 形式（OpenOffice や LibreOffice 用）で利用できます:

* <https://github.com/apache/roller/tree/master/docs>

## 詳細情報

Roller Confluence Wiki をご覧ください:

* Roller のビルドと実行方法: <https://cwiki.apache.org/confluence/x/EM4>
* Roller への貢献方法: <https://cwiki.apache.org/confluence/x/2hsB>
* Roller のリリース方法: <https://cwiki.apache.org/confluence/x/gycB>
* その他の開発者向けリソース: <https://cwiki.apache.org/confluence/x/D84>

## Roller のインストール 

本番環境で Roller を実行する場合は、最新の公式リリースをダウンロードし、インストールガイドに従ってインストールしてください。インストールガイドは以下のドキュメントリンクで確認できます: <https://github.com/apache/roller/tree/master/docs>.

## クイックスタート: Maven 経由での実行

この方法は本番環境での運用には推奨されませんが、Roller を試してみるには比較的簡単な方法です。  
UNIX シェル、Java、Maven、Git が揃っている場合:

コードを取得する:

```bash
$ git clone https://github.com/apache/roller.git
```

Roller をコンパイル・ビルドする:

```bash
$ cd roller
$ mvn -DskipTests=true install
```

埋め込みの Derby データベースを使用して Jetty 上で Roller を実行する（テスト用）:

```bash
$ mvn jetty:run
```

Jetty が起動したら、ブラウザで <http://localhost:8080/roller> にアクセスして Roller を試してください。

## クイックスタート: Docker 経由での実行

もう一つの Roller を試す方法は Docker を使用する方法です。  
この方法は Maven や Java が不要なため、Maven 経由で実行するよりも簡単です。  
Docker が用意できている場合、以下の手順でデモ目的で Roller を実行できます。

コードを取得する:

```bash
$ git clone https://github.com/apache/roller.git
```

Docker Compose を実行して、PostgreSQL データベースとともに Roller をビルド・起動する:

```bash
$ cd roller
$ docker-compose up
```
    
Docker イメージのビルドと起動にはしばらく時間がかかります。  
完了したら、ブラウザで <http://localhost:8080/roller> にアクセスして Roller を試してください。

---
