---
layout: contents
language: ja
title: Developer
short_desc: K2Hdkc based Resource and Roles and policy Rules
lang_opp_file: developer.html
lang_opp_word: To English
prev_url: setupja.html
prev_string: Setup
top_url: indexja.html
top_string: TOP
next_url: environmentsja.html
next_string: Environments/Settings
---

# 開発者

このページは、K2HR3 システムの変更・機能追加するための情報を説明しています。

## リポジトリの構成

ここでは、githubのk2hr3リポジトリについて説明しています。

k2hr3リポジトリは、次のサブモジュールから構成されています。

- k2hr3_app
  - Web Application リポジトリ
- k2hr3_api
  - REST API リポジトリ
- k2hr3_osnl
  - OpenStack通知リスナー用リポジトリ
- k2hr3_sidecar
  - kubernetesからの自動登録・削除用Sidecar Containerのためのdockerイメージリポジトリ
- k2hr3_utils
  - 運用/開発ツールなど各種ツール用リポジトリ
- k2hr3_get_resource 
  - リソース（RESOURCE）取得のための Systemdサービス 用リポジトリ
- k2hr3_cli
  - Command Line Interface(CLI) 用のリポジトリ
- k2hr3_helm_chart
  - Helm Chart 用のリポジトリ


後段では、各リポジトリについて説明しています。

## k2hr3_appリポジトリ

この章では、k2hr3_appリポジトリの内容とソースコードのビルド＆テスト方法を説明しています。

k2hr3_appリポジトリは、APPサーバ用リポジトリです。

1. Github上で [https://github.com/yahoojapan/k2hr3_app](https://github.com/yahoojapan/k2hr3_app)をforkします

2. リポジトリをcloneします

    ```
    $ git clone https://github.com/YOUR-USERNAME/k2hr3_app.git
    ```

3. ローカル環境に必要なパッケージをインストールします

    ```
    $ cd k2hr3_app/
    $ npm install
    ```
    
4. ブランチを作り、必要でしたら、コード変更して見てください

    ```
    $ git checkout -b my-first-contribution
    ```

5. コードの書式チェックとプログラムのテストをします

    ```
    $ npm run build
    $ npm run test
    ```

6. コード変更があれば、commitして、push します

    ```
    $ git add .
    $ git commit -m "Short description of your changes."
    $ git push origin my-first-contribution
    ```
    
7. コード変更があれば、ぜひプルリクエストを投げてみてください！

## k2hr3_apiリポジトリ

この章では、k2hr3_apiリポジトリの内容とソースコードのビルド＆テスト方法を説明しています。

k2hr3_apiリポジトリは、APIサーバー用リポジトリです。

1. Github上で [https://github.com/yahoojapan/k2hr3_api](https://github.com/yahoojapan/k2hr3_api)をforkします

2. リポジトリをcloneします

    ```
    $ git clone https://github.com/YOUR-USERNAME/k2hr3_api.git
    ```

3. ローカル環境に必要なパッケージをインストールします。
    パッケージのビルドには、**k2hdkc** のライブラリとヘッダファイルが必要となります。
   
    最近のDebianベースLinuxの利用者は、以下の手順に従ってください。
    ```
    $ sudo apt-get update -y
    $ sudo apt-get install curl -y
    $ curl -s https://packagecloud.io/install/repositories/antpickax/stable/script.deb.sh | sudo bash
    $ sudo apt-get install k2hdkc-dev
    ```

    CentOSでビルドする場合には、SoftwareCollectionsから[devtoolsetパッケージ](https://www.softwarecollections.org/en/scls/rhscl/devtoolset-7/)をインストールしてください。やり方は次のとおりです。
    ```
    $ sudo yum install centos-release-scl
    $ sudo yum install devtoolset-7
    $ scl enable devtoolset-7 bash
    ```

    Fedoraの利用者は、以下の手順に従ってください。
    ```
    $ sudo dnf makecache
    $ sudo dnf install curl -y
    $ curl -s https://packagecloud.io/install/repositories/antpickax/stable/script.rpm.sh | sudo bash
    $ sudo dnf install k2hdkc-devel
    ```

    その他最近のRPMベースのLinuxの場合は、以下の手順に従ってください。
    ```
    $ sudo yum makecache
    $ sudo yum install curl -y
    $ curl -s https://packagecloud.io/install/repositories/antpickax/stable/script.rpm.sh | sudo bash
    $ sudo yum install k2hdkc-devel
    ```

    それ以外のOSをお使いの場合は、[K2HDKCのソースコード](https://github.com/yahoojapan/k2hdkc)をビルドしてインストールしてください。ビルド方法は、[こちら](https://k2hdkc.antpick.ax/build.html)を見てください。

    
    **k2hdkc** のライブラリとヘッダファイルのインストールが終わったら、npmパッケージをインストールします。
    ```
    $ cd k2hr3_api/
    $ npm install
    ```

4. ブランチを作り、必要でしたら、コード変更して見てください
    ```
    $ git checkout -b my-first-contribution
    ```

5. コードの書式チェックとプログラムのテストをします
    ```
    $ npm run test
    ```

6. コード変更があれば、commitして、push します
    ```
    $ git add .
    $ git commit -m "Short description of your changes."
    $ git push origin my-first-contribution
    ```
    
7. コード変更があれば、ぜひプルリクエストを投げてみてください！

## k2hr3_osnlリポジトリ

この章では、k2hr3_osnlリポジトリの内容とソースコードのビルド＆テスト方法を説明しています。

k2hr3_osnlリポジトリは、OpenStack通知リスナー用のリポジトリです。

1. Github上で [https://github.com/yahoojapan/k2hr3_osnl](https://github.com/yahoojapan/k2hr3_osnl)をforkします

2. リポジトリをcloneします

    ```
    $ git clone https://github.com/YOUR-USERNAME/k2hr3_osnl.git
    ```

3. ローカル環境に必要なパッケージをインストールします

    ```
    $ cd k2hr3_osnl/
    $ pip3 install pipenv
    $ python3 -m pipenv install -dev --python /path/to/python3
    $ pipenv shell
    ```
    
4. ブランチを作り、必要でしたら、コード変更して見てください

    ```
    (k2hr3_osnl) $ git checkout -b my-first-contribution
    ```

5. コードの書式チェックとプログラムのテストをします

    ```
    (k2hr3_osnl) $ make lint test
    ```

6. コード変更があれば、commitして、push します

    ```
    (k2hr3_osnl) $ git add .
    (k2hr3_osnl) $ git commit -m "Short description of your changes."
    (k2hr3_osnl) $ git push origin my-first-contribution
    ```
    
7. コード変更があれば、ぜひプルリクエストを投げてみてください！

## k2hr3_sidecarリポジトリ

この章では、k2hr3_sidecarリポジトリの内容を説明します。

k2hr3_sidecarリポジトリは、kubernetesからPods（Conatainers）を自動登録・削除をするために必要となるSidecar dockerイメージを管理するリポジトリです。

1. Github上で [https://github.com/yahoojapan/k2hr3_sidecar](https://github.com/yahoojapan/k2hr3_sidecar)をforkします

2. リポジトリをcloneします

    ```
    $ git clone https://github.com/YOUR-USERNAME/k2hr3_sidecar.git
    ```

3. ローカル環境にdockerを以下の方法などでインストールします  
- [Get Docker Engine - Community for Debian](https://docs.docker.com/install/linux/docker-ce/debian/)
- [Install Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/)
- [Install Docker Desktop on Windows](https://docs.docker.com/docker-for-windows/install/)

4. ブランチを作り、必要でしたら、コード変更して見てください

    ```
    (k2hr3_sidecar) $ git checkout -b my-first-contribution
    ```

5. dockerイメージを作成し、中身を確認します

    ```
    (k2hr3_sidecar) $ sudo docker build --tag antpickax/k2hr3.sidecar:0.1 .
    (k2hr3_sidecar) $ sudo docker run -i -t antpickax/k2hr3.sidecar:0.1 /bin/sh
    ```

6. コード変更があれば、commitして、push します

    ```
    (k2hr3_sidecar) $ git add .
    (k2hr3_sidecar) $ git commit -m "Short description of your changes."
    (k2hr3_sidecar) $ git push origin my-first-contribution
    ```
    
7. コード変更があれば、ぜひプルリクエストを投げてみてください！

## k2hr3_utilsリポジトリ

この章では、k2hr3_utilsリポジトリの内容とソースコードのビルド＆テスト方法を説明しています。

このリポジトリは、運用/開発ツールなど各種ツール用のリポジトリです。ここでは、`devcluster`を例にして説明します。

1. Github上で [https://github.com/yahoojapan/k2hr3_utils](https://github.com/yahoojapan/k2hr3_utils)をforkします

2. リポジトリをcloneします

    ```
    $ git clone https://github.com/YOUR-USERNAME/k2hr3_utils.git
    ```
    
3. ブランチを作ります。必要でしたら、コード変更して見てください

    ```
    $ cd k2hr3_utils/devcluster
    $ git checkout -b my-first-contribution
    ```

4. cluster.shをデバッグモードで起動して、自分の環境にエラーなしでデプロイできることを確認します。

    ```
    $ sh cluster.sh -d
    ```

5. コード変更があれば、commitして、push します

    ```
    (k2hr3_osnl) $ git add .
    (k2hr3_osnl) $ git commit -m "Short description of your changes."
    (k2hr3_osnl) $ git push origin my-first-contribution
    ```
    
6. コード変更があれば、ぜひプルリクエストを投げてみてください！

## k2hr3_get_resource リポジトリ

この章では、k2hr3_get_resource リポジトリの内容とソースコードのビルド＆テスト方法を説明しています。

k2hr3_get_resource リポジトリは、ロール（ROLE）に登録されているホスト（HOST）から、リソース（RESOURCE）データを定期的に取得するための **Systemdサービス** です。

1. Github上で [https://github.com/yahoojapan/k2hr3_get_resource](https://github.com/yahoojapan/k2hr3_get_resource)をforkします

2. リポジトリをcloneします

    ```
    $ git clone https://github.com/YOUR-USERNAME/k2hr3_get_resource.git
    ```

3. ブランチを作り、必要でしたら、コード変更して見てください

    ```
    $ cd k2hr3_get_resource
    $ git checkout -b my-first-contribution
    ```

4. ローカル環境に必要なパッケージをインストールします

    ```
    [Ubuntu/Debian]
    $ sudo apt-get install git autoconf autotools-dev make dh-make dh-systemd fakeroot dpkg-dev devscripts pkg-config ruby-dev rubygems rubygems-integration procps
    
    [CentOS/Fedora]
    $ sudo yum install autoconf automake gcc-c++ make pkgconfig redhat-rpm-config rpm-build procps
    ```

5. ビルドし、パッケージを作成します。

    ```
    $ ./autogen.sh
    $ ./configure
    $ make
    $ make check
    
    [Ubuntu/Debian]
    $ ./buildutil/debian_build.sh
    
    [CentOS/Fedora]
    $ ./buildutil/rpm_build.sh
    ```

6. コード変更があれば、commitして、push します

    ```
    $ git add .
    $ git commit -m "Short description of your changes."
    $ git push origin my-first-contribution
    ```
    
7. コード変更があれば、ぜひプルリクエストを投げてみてください！

## k2hr3_cli リポジトリ

この章では、k2hr3_cli リポジトリの内容とソースコードのビルド＆テスト方法を説明しています。

k2hr3_cli リポジトリは、K2HR3 REST APIを使う Command Line Interface(CLI) プログラムです。  
ユーザは、このK2HR3 Command Line Interface(CLI)を使い、K2HR3 Web Applicationと同じ操作をコマンドラインから実行できます。  

1. Github上で [https://github.com/yahoojapan/k2hr3_cli](https://github.com/yahoojapan/k2hr3_cli)をforkします

2. リポジトリをcloneします

    ```
    $ git clone https://github.com/YOUR-USERNAME/k2hr3_cli.git
    ```

3. ブランチを作り、必要でしたら、コード変更して見てください

    ```
    $ cd k2hr3_cli
    $ git checkout -b my-first-contribution
    ```

4. ローカル環境に必要なパッケージをインストールします

    ```
    [Ubuntu/Debian]
    $ sudo apt-get install git autoconf autotools-dev make dh-make fakeroot dpkg-dev devscripts pkg-config ruby-dev rubygems rubygems-integration procps shellcheck
    
    [CentOS/Fedora]
    $ sudo yum install git autoconf automake gcc-c++ make pkgconfig redhat-rpm-config rpm-build ruby-devel rubygems procps
    ```

5. ビルドし、パッケージを作成します。

    ```
    $ ./autogen.sh
    $ ./configure
    $ make build
    $ make check
    
    [Ubuntu/Debian]
    $ ./buildutil/debian_build.sh
    
    [CentOS/Fedora]
    $ ./buildutil/rpm_build.sh
    ```

6. コード変更があれば、commitして、push します

    ```
    $ git add .
    $ git commit -m "Short description of your changes."
    $ git push origin my-first-contribution
    ```
    
7. コード変更があれば、ぜひプルリクエストを投げてみてください！

## k2hr3_helm_chart リポジトリ

この章では、k2hr3_helm_chart リポジトリの内容とソースコードのテスト方法を説明しています。

k2hr3_helm_chart は、K2HR3 Helm Chartのリポジトリです。  
ユーザは、このK2HR3 Helm Chartを使い、kubernetes環境にK2HR3システムをインストール（構築）できます。  

1. Github上で [https://github.com/yahoojapan/k2hr3_helm_chart](https://github.com/yahoojapan/k2hr3_helm_chart)をforkします

2. リポジトリをcloneします

    ```
    $ git clone https://github.com/YOUR-USERNAME/k2hr3_helm_chart.git
    ```

3. ブランチを作り、必要でしたら、コード変更して見てください

    ```
    $ cd k2hr3_helm_chart
    $ git checkout -b my-first-contribution
    ```

4. ローカル環境にHelmをインストールします

    ```
    $ curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
    ```

5. Helm Chartをテスト、疑似インストールを実行して、確認できます。

    ```
    $ cd ..
    $ helm template my-k2hr3 ./k2hr3_helm_chart <options...>
    
    $ helm install my-k2hr3 ./k2hr3_helm_chart <options...> --debug --dry-run
    ```

6. コード変更があれば、commitして、push します

    ```
    $ git add .
    $ git commit -m "Short description of your changes."
    $ git push origin my-first-contribution
    ```
    
7. コード変更があれば、ぜひプルリクエストを投げてみてください！