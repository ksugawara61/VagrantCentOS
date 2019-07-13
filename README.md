# CentOSを活用したVagrant環境

## 概要

Vagrant上でDockerの検証可能なサンプル環境です。<br>
OSはCentOSを採用しています。

## 設定パラメータ

Vagrantfileファイル内の以下の変数を変更することでサーバ（ノード）の設定変更が可能です。

| 項目 |変数名 | 説明 |
| :--- | :--- | :--- |
| ノードのIP | node_ip | ノードに設定するIPアドレス |
| ノードのホスト名 | node_hostname | ノードのホスト名 |
| ノードのメモリー | node_vm_memory | Masterノードで利用可能なメモリー数 |
| ノードのCPU | node_vm_cpu | Masterノードで利用可能なCPU数 |
| ノードのポート | node_port_array | ノードで利用するポート |

## サーバ環境

| 項目 | バージョン |
| :--- | :--- |
| CentOS | 7.6.1810 |

### ミドルウェア

CentOS上に以下のミドルウェアをインストールしています。

| 項目 | バージョン | 説明 |
| :--- | :--- | :--- |
| Vim | latest | エディタ |
| wget | latest | ダウンローダ |
| htop | latest | タスクマネージャ |
| git | 2.22.0 | バージョン管理ツール |
| Docker | 18.06.3-ce | コンテナツール |
| Docker Compose | 1.24.0 | 複数のコンテナを定義・実行するツール |
| rbenv | latest | rubyパッケージ管理 |
| nvm | latest | nodeパッケージ管理 |
| node | latest(LTS) | nodeパッケージ管理 |
| MySQL | 5.7 | Relational Database |
| Postgresql | latest | Relational Database |
| Redis | 5.0.5 | KVS |
| Memcached | 1.5.16 | KVS |
| Elasticsearch | 7.2.0 | 検索エンジン |

#### Elasticsearch

elasticsearchには、以下のanalyzerをインストールしています。

* Analyzerの種類

| 項目 | analyzer名 | 説明 |
| :--- | :--- | :--- |
| icu | analysis-icu | 国際的に規約されている文字の解析器 |
| kuromoji | analysis-kuromoji | 日本語の形態素解析器 |
| kuromoji-ipadic-neologd | analysis-kuromoji-ipadic-neologd | Elasticsearch用システム辞書(NEologd and ipadic) |

### 共有ディレクトリ

ホストOSの **./dev** ディレクトリ配下で編集したファイルはゲストOSのノード上にも共有されるように設定しています。

| ホストOSのディレクトリパス | ゲストOSのディレクトリパス |
| :---: | :---: |
| ./dev | /home/vagrant/dev |

## コマンド

* ノードの起動

```
$ vagrant up
```

* ノードの停止

```
$ vagrant halt
```

* ノードの再起動

```
$ vagrant destroy
```

* ノードの破棄

```
$ vagrant destroy
```

## 参考文献

1. Index of linux_centos_, https://download.docker.com/linux/centos/, Online; accessed 18-June-2019.
2. 【Linux】タイムゾーン(Timezone)の変更 - Qiita, https://qiita.com/azusanakano/items/b39bd22504313884a7c3, Online; accessed 18-June-2019.
3. Ansible Documentation, https://docs.ansible.com/, Online; accessed 18-June-2019.
4. git_git_ Git Source Code Mirror - This is a publish-only repository and all pull requests are ignored. Please follow Documentation_SubmittingPatches procedure for any of your improvements., https://github.com/git/git, Online; accessed 18-June-2019.
5. Elasticsearch6.3に日本語analyzerをインストール - 30代SEのメモ, https://techblog.hatenadiary.com/entry/2018/08/06/230717, Online; accessed 13-Jul-2019.
6. codelibs_elasticsearch-analysis-kuromoji-ipadic-neologd_ Elasticsearch's Analyzer for Kuromoji with Neologd, https://github.com/codelibs/elasticsearch-analysis-kuromoji-ipadic-neologd, Online; accessed 13-Jul-2019.
