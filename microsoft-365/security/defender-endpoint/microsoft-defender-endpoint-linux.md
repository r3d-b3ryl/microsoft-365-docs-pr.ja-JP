---
title: Linux 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Linux で Microsoft Defender for Endpoint をインストールして使用する方法について説明します。
keywords: Microsoft、Defender、Microsoft Defender for Endpoint、Linux、インストール、展開、アンインストール、puppet、ansible、linux、redhat、ubuntu、debian、sles、suse、centos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a0c013b6b99ad9b8da6a3cedeb93df036de4e257
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464071"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Linux 上で Microsoft Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> 他のサード パーティ製エンドポイント保護製品を Microsoft Defender for Endpoint on Linux で実行すると、パフォーマンスの問題や予期しない副作用につながる可能性があります。 Microsoft 以外のエンドポイント保護が環境の絶対的な要件である場合でも、パッシブ モードで実行するウイルス対策機能を構成した後も、Linux EDR の Defender for Endpoint 機能を安全に利用できます。[](linux-preferences.md#enforcement-level-for-antivirus-engine)

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Linux に Microsoft Defender for Endpoint をインストールする方法

### <a name="prerequisites"></a>前提条件

- ポータルへのMicrosoft 365 Defenderアクセス
- systemd システム マネージャー [を使用した](https://systemd.io/) Linux 配布
- Linux および BASH スクリプトでの初心者レベルのエクスペリエンス
- デバイスの管理特権 (手動展開の場合)

> [!NOTE]
> Microsoft Defender for Endpoint on Linux エージェントは [、OMS エージェントから独立しています](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)。 Microsoft Defender for Endpoint は、独自の独立したテレメトリ パイプラインに依存しています。


### <a name="installation-instructions"></a>インストール手順

Linux での Microsoft Defender for Endpoint のインストールと構成に使用できる方法と展開ツールがいくつかあります。

一般に、次の手順を実行する必要があります。

- Microsoft Defender for Endpoint サブスクリプションを持っている必要があります。
- 次のいずれかの展開方法を使用して、Microsoft Defender for Endpoint on Linux を展開します。
  - コマンド ライン ツール:
    - [手動展開](linux-install-manually.md)
  - サードパーティの管理ツール:
    - [Puppet 構成管理ツールを使用した展開](linux-install-with-puppet.md)
    - [Ansible 構成管理ツールを使用した展開](linux-install-with-ansible.md)
    - [Chef 構成管理ツールを使用した展開](linux-deploy-defender-for-endpoint-with-chef.md)

インストールエラーが発生した場合は、「 [Microsoft Defender for Endpoint on Linux](linux-support-install.md)」の「インストールエラーのトラブルシューティング」を参照してください。

> [!NOTE]
> 既定のインストール パス以外の場所に Microsoft Defender for Endpoint をインストールする場合はサポートされていません。 

### <a name="system-requirements"></a>システム要件

- サポートされる Linux サーバー配布と x64 (AMD64/EM64T) バージョン:

  - Red Hat Enterprise Linux 6.7 以上
  - Red Hat Enterprise Linux 7.2 以上
  - Red Hat Enterprise Linux 8.x
  - CentOS 6.7 以上 
  - CentOS 7.2 以上
  - Ubuntu 16.04 LTS 以上の LTS
  - Debian 9 以上
  - SUSE Linux Enterprise サーバー 12 以上
  - Oracle Linux 7.2 以上
  - Amazon Linux 2
  - Fedora 33 以上

    > [!NOTE]
    > 明示的にリストされていない配布とバージョンはサポートされていません (正式にサポートされている配布から派生している場合でも)。

- サポートされているカーネル バージョンの一覧
  - Red Hat Enterprise Linux 6 および CentOS 6:
    - 6.7 の場合: 2.6.32-573.*
    - 6.8 の場合: 2.6.32-642.*
    - 6.9 の場合: 2.6.32-696.*
    - 6.10: 2.6.32.754.2.1.el6.x86_64 2.6.32-754.41.2:
    
       - 2.6.32-754.10.1.el6.x86_64
       - 2.6.32-754.11.1.el6.x86_64
       - 2.6.32-754.12.1.el6.x86_64
       - 2.6.32-754.14.2.el6.x86_64
       - 2.6.32-754.15.3.el6.x86_64
       - 2.6.32-754.17.1.el6.x86_64
       - 2.6.32-754.18.2.el6.x86_64
       - 2.6.32-754.2.1.el6.x86_64
       - 2.6.32-754.22.1.el6.x86_64
       - 2.6.32-754.23.1.el6.x86_64
       - 2.6.32-754.24.2.el6.x86_64
       - 2.6.32-754.24.3.el6.x86_64
       - 2.6.32-754.25.1.el6.x86_64
       - 2.6.32-754.27.1.el6.x86_64
       - 2.6.32-754.28.1.el6.x86_64
       - 2.6.32-754.29.1.el6.x86_64
       - 2.6.32-754.29.2.el6.x86_64
       - 2.6.32-754.3.5.el6.x86_64
       - 2.6.32-754.30.2.el6.x86_64
       - 2.6.32-754.33.1.el6.x86_64
       - 2.6.32-754.35.1.el6.x86_64
       - 2.6.32-754.39.1.el6.x86_64
       - 2.6.32-754.41.2.el6.x86_64
       - 2.6.32-754.6.3.el6.x86_64
       - 2.6.32-754.9.1.el6.x86_64


    > [!NOTE]
    > 新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートにのみ縮小されます。 このセクションに記載されているバージョンより古いバージョンは、技術的なアップグレードのサポートのためにのみ提供されます。

  - サポートされている配布の残りの部分では、必要な最小カーネル バージョンは 3.10.0-327 です。

- イベント プロバイダーのメカニズム
  - Red Hat Enterprise Linux 6 および CentOS 6: `Talpa` カーネル モジュール ベースのソリューション
  - サポートされている配布の残りの部分については、次の条件を使用します。 `Fanotify`
    - カーネル `fanotify` オプションを有効にする必要があります

      > [!CAUTION]
      > Linux で Defender for Endpoint を他のベースのセキュリティ ソリューション `fanotify`と並べて実行する方法はサポートされていません。 オペレーティング システムのハングを含む予期しない結果につながる可能性があります。

- ディスク領域: 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon には実行可能なアクセス許可が必要です。 詳細については、「 [Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install) のインストールに関する問題のトラブルシューティング」の「デーモンに実行可能なアクセス許可が付与されている」を参照してください。

- コア: 最小 2、4 優先

- メモリ: 最小 1 GB、4 優先

    > [!NOTE]
    > /var に空きディスク領域が含まれます。

- ソリューションは現在、次のファイル システムの種類に対してリアルタイム保護を提供します。

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の送信接続を許可する必要がある場合があります。

- 監査フレームワーク (`auditd`) を有効にする必要があります。

  > [!NOTE]
  > 追加されたルールによってキャプチャ`/etc/audit/rules.d/``audit.log`されたシステム イベントは (s) に追加され、ホストの監査とアップストリーム コレクションに影響を与える可能性があります。 Microsoft Defender for Endpoint on Linux で追加されたイベントには、キーがタグ付け `mdatp` されます。

### <a name="configuring-exclusions"></a>除外の構成

ユーザーに除外を追加Microsoft Defender ウイルス対策、ユーザーの一般的な除外の間違いを[念頭に置Microsoft Defender ウイルス対策](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)

### <a name="network-connections"></a>ネットワーク接続

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しなかっている必要があります。 ある場合は、許可ルール *の作成が* 必要な場合があります。

<br>

****


|ドメインリストのスプレッドシート| 説明|
|---|---|
|商用顧客向け Microsoft Defender for Endpoint URL リスト | 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Gov/GCC/DoD のお客様向け Microsoft Defender for Endpoint URL リスト| Gov/GCC/DoD のお客様向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)
|


> [!NOTE]
> より具体的な URL リストについては、「 [Configure proxy and internet connectivity settings」を参照してください](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

Defender for Endpoint では、次の検出方法を使用してプロキシ サーバーを検出できます。

- 透過プロキシ
- 静的プロキシの手動構成

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。 透過プロキシの場合、Defender for Endpoint の追加構成は不要です。 静的プロキシの場合は、「手動静的プロキシ構成 [」の手順に従います](linux-static-proxy-configuration.md)。

> [!WARNING]
> PAC、WPAD、および認証されたプロキシはサポートされていません。 静的プロキシまたは透過プロキシのみを使用してください。
>
> SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。 SSL インスペクションとプロキシ サーバーの例外を構成して、Defender for Endpoint on Linux のデータを、インターセプトなしで関連する URL に直接渡します。 インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。

トラブルシューティング手順については、「 [Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md) のクラウド接続の問題のトラブルシューティング」を参照してください。

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Linux 上のエンドポイント用 Microsoft Defender を更新する方法

Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。 Microsoft Defender for Endpoint on Linux を更新するには、「 [Deploy updates for Microsoft Defender for Endpoint on Linux」を参照してください](linux-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint の構成方法

エンタープライズ環境で製品を構成する方法については、「 [Linux での Microsoft Defender for Endpoint の基本設定の設定」を参照してください](linux-preferences.md)。

## <a name="common-applications-to-microsoft-defender-for-endpoint-can-impact"></a>エンドポイント向け Microsoft Defender への一般的なアプリケーションは、影響を与える可能性があります

特定のアプリケーションの高い I/O ワークロードでは、Microsoft Defender for Endpoint のインストール時にパフォーマンスの問題が発生する可能性があります。 これには、Jenkins や Jira などの開発者シナリオ用のアプリケーションや、OracleDB や Postgres などのデータベース ワークロードが含まれます。 パフォーマンスの低下が発生した場合は、信頼できるアプリケーションの除外を設定し、一般的な除外の間違いを念頭に置[Microsoft Defender ウイルス対策検討してください](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)。 その他のガイダンスについては、サード パーティ製アプリケーションからのウイルス対策の除外に関するコンサルティング ドキュメントを検討してください。

## <a name="resources"></a>リソース

- ログ記録、アンインストール、その他のトピックの詳細については、「Resources」を参照 [してください](linux-resources.md)。
