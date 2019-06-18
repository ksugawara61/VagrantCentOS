# CentOSを活用したVagrant環境

## 概要

Vagrant上でDockerの検証可能なサンプル環境です。<br>
OSはCentOSを採用しています。

## 設定パラメータ

Vagrantfileファイル内の以下の変数を変更することでサーバ（ノード）の設定変更が可能です。

| 項目 |変数名 | 説明 |
| :--- | :--- | :--- |
| ノードのIP | $node_ip | ノードに設定するIPアドレス |
| ノードのホスト名 | $node_hostname | ノードのホスト名 |
| ノードのメモリー | $node_vm_memory | Masterノードで利用可能なメモリー数 |
| ノードのCPU | $node_vm_cpu | Masterノードで利用可能なCPU数 |

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
| git | latest | バージョン管理ツール |
| Docker | 18.06.3-ce | コンテナツール |
| Docker Compose | 1.24.0 | 複数のコンテナを定義・実行するツール |

### 共有ディレクトリ

ホストOSの **./dev** ディレクトリ配下で編集したファイルはゲストOS上にも共有されるように設定しています。

| ホストOSのディレクトリパス | ゲストOSのディレクトリパス |
| :---: | :---: |
| ./dev | /home/vagrant/dev |

## 参考文献

1. Index of linux_centos_, https://download.docker.com/linux/centos/, Online; accessed 18-June-2019.
