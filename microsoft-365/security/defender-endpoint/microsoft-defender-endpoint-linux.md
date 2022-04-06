---
title: Linux 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Linux にMicrosoft Defender for Endpointをインストールして使用する方法について説明します。
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
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dcc4ed070e900f9df892abb58cd05cdad2dca619
ms.sourcegitcommit: 2f6a0096038d09f0e43e1231b01c19e0b40fb358
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64687013"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Linux でMicrosoft Defender for Endpointをインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Linux 上でMicrosoft Defender for Endpointと共に他のサード パーティのエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しない副作用が発生する可能性があります。 Microsoft 以外のエンドポイント保護が環境の絶対的な要件である場合でも、[パッシブ モード](linux-preferences.md#enforcement-level-for-antivirus-engine)で実行するようにウイルス対策機能を構成した後でも、Defender for Endpoint on Linux EDR機能を安全に利用できます。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Linux にMicrosoft Defender for Endpointをインストールする方法

Linux のMicrosoft Defender for Endpointには、マルウェア対策とエンドポイントでの検出と対応 (EDR) 機能が含まれています。 


### <a name="prerequisites"></a>前提条件

- Microsoft 365 Defender ポータルへのアクセス
- [systemd](https://systemd.io/) システム マネージャーを使用した Linux ディストリビューション
- Linux および BASH スクリプトの初心者レベルのエクスペリエンス
- デバイスに対する管理者特権 (手動展開の場合)

> [!NOTE]
> Linux エージェント上のMicrosoft Defender for Endpointは[、OMS エージェント](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)から独立しています。 Microsoft Defender for Endpoint独自の独立したテレメトリ パイプラインに依存しています。


### <a name="installation-instructions"></a>インストール手順

Linux にMicrosoft Defender for Endpointをインストールおよび構成するために使用できるいくつかの方法とデプロイ ツールがあります。

一般に、次の手順を実行する必要があります。

- Microsoft Defender for Endpoint サブスクリプションがあることを確認します。
- 次のいずれかのデプロイ方法を使用して Linux にMicrosoft Defender for Endpointをデプロイします。
  - コマンド ライン ツール:
    - [手動展開](linux-install-manually.md)
  - サード パーティの管理ツール:
    - [Puppet 構成管理ツールを使用してデプロイする](linux-install-with-puppet.md)
    - [Ansible 構成管理ツールを使用してデプロイする](linux-install-with-ansible.md)
    - [Chef 構成管理ツールを使用してデプロイする](linux-deploy-defender-for-endpoint-with-chef.md)

インストールエラーが発生した場合は、「[Linux 上のMicrosoft Defender for Endpointでのインストールエラーのトラブルシューティング」を](linux-support-install.md)参照してください。

> [!NOTE]
> 既定のインストール パス以外の場所にMicrosoft Defender for Endpointをインストールすることはサポートされていません。 

### <a name="system-requirements"></a>システム要件

- サポートされている Linux サーバーディストリビューションと x64 (AMD64/EM64T) とx86_64バージョン:

  - Red Hat Enterprise Linux 6.7 以降
  - Red Hat Enterprise Linux 7.2 以降
  - Red Hat Enterprise Linux 8.x
  - CentOS 6.7 以降 
  - CentOS 7.2 以降
  - Ubuntu 16.04 LTS 以上の LTS
  - Debian 9 以降
  - SUSE Linux Enterprise Server 12 以降
  - Oracle Linux 7.2 以降
  - Oracle Linux 8.x
  - Amazon Linux 2
  - Fedora 33 以降

    > [!NOTE]
    > 明示的に一覧表示されていないディストリビューションとバージョンはサポートされていません (公式にサポートされているディストリビューションから派生した場合でも)。

- サポートされているカーネル バージョンの一覧
  - 最小カーネル バージョン 3.10.0-327 (Red Hat Enterprise Linux 6 および CentOS 6 を除く、上記でサポートされているすべての Linux ディストリビューションの場合)
  - カーネル オプションを `fanotify` 有効にする必要があります
  - Red Hat Enterprise Linux 6 および CentOS 6:
    - 6.7 の場合: 2.6.32-573.*
    - 6.8 の場合: 2.6.32-642.*
    - 6.9 の場合:2.6.32-696.* (2.6.32-696.el6.x86_64を除く)
    - 6.10 の場合:2.6.32-754.43.1 に2.6.32.754.2.1.el6.x86_64:
    
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
       - 2.6.32-754.43.1.el6.x86_64
       - 2.6.32-754.6.3.el6.x86_64
       - 2.6.32-754.9.1.el6.x86_64

 > [!NOTE]
 > 新しいパッケージ バージョンがリリースされると、以前の 2 つのバージョンのサポートはテクニカル サポートのみに縮小されます。 このセクションに記載されているバージョンより古いバージョンは、技術的なアップグレード サポートでのみ提供されます。


  > [!CAUTION]
  > 他 `fanotify`のベースのセキュリティ ソリューションと並行して Linux 上で Defender for Endpoint を実行することはサポートされていません。 オペレーティング システムのハングなど、予期しない結果につながる可能性があります。

- ディスク領域: 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon には実行可能なアクセス許可が必要です。 詳細については、「[Linux でのMicrosoft Defender for Endpointのインストールに関する問題のトラブルシューティング](/microsoft-365/security/defender-endpoint/linux-support-install)」の「デーモンに実行可能なアクセス許可があることを確認する」を参照してください。

- コア: 最小 2 個、優先 4 個

- メモリ: 最小 1 GB、優先 4

    > [!NOTE]
    > /var に空きディスク領域があることを確認してください。

- このソリューションは現在、次のファイル システムの種類に対してリアルタイム保護を提供しています。

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

サービスを有効にした後、ネットワークまたはファイアウォールを構成して、サービスとエンドポイント間の送信接続を許可することが必要になる場合があります。

- 監査フレームワーク (`auditd`) を有効にする必要があります。

  > [!NOTE]
  > 追加 `/etc/audit/rules.d/` されたルールによってキャプチャされたシステム イベントは追加 `audit.log`され、ホストの監査とアップストリームの収集に影響を与える可能性があります。 Linux でMicrosoft Defender for Endpointによって追加されたイベントには、キーがタグ付`mdatp`けされます。

### <a name="configuring-exclusions"></a>除外の構成

Microsoft Defender ウイルス対策に除外を追加する場合は、Microsoft Defender ウイルス対策の[一般的な除外ミス](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)に注意する必要があります

### <a name="network-connections"></a>ネットワーク接続

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスとその関連 URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター規則がないことを確認する必要があります。 存在する場合は、それらに対して特別に *許可* ルールを作成する必要がある場合があります。

<br>

****

|ドメイン リストのスプレッドシート| 説明|
|---|---|
|商用顧客向けの Microsoft Defender for Endpoint の URL リスト| 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Gov/GCC/DoD 向けの Microsoft Defender for Endpoint の URL リスト | Gov/GCC/DoD のお客様向けのサービスの場所、地理的な場所、OS の特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

> [!NOTE]
> より具体的な URL の一覧については、「 [プロキシとインターネット接続の設定を構成する](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)」を参照してください。

Defender for Endpoint は、次の検出方法を使用してプロキシ サーバーを検出できます。

- 透過プロキシ
- 手動の静的プロキシ構成

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、前述の URL で匿名トラフィックが許可されていることを確認します。 透過的プロキシの場合、Defender for Endpoint には追加の構成は必要ありません。 静的プロキシの場合は、「 [手動静的プロキシ構成](linux-static-proxy-configuration.md)」の手順に従います。

> [!WARNING]
> PAC、WPAD、および認証されたプロキシはサポートされていません。 静的プロキシまたは透過プロキシのみが使用されていることを確認します。
>
> セキュリティ上の理由から、SSL 検査とインターセプト プロキシもサポートされていません。 SSL 検査とプロキシ サーバーの例外を構成して、Defender for Endpoint on Linux から関連する URL にデータをインターセプトせずに直接渡すようにします。 インターセプト証明書をグローバル ストアに追加すると、インターセプトは許可されません。

トラブルシューティングの手順については、「[Linux でのMicrosoft Defender for Endpointに関するクラウド接続の問題のトラブルシューティング」を](linux-support-connectivity.md)参照してください。

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Linux でMicrosoft Defender for Endpointを更新する方法

Microsoft は、パフォーマンス、セキュリティ、新機能を提供するために、ソフトウェア更新プログラムを定期的に発行しています。 Linux でMicrosoft Defender for Endpointを更新するには、「[Linux でのMicrosoft Defender for Endpointの更新プログラムのデプロイ](linux-updates.md)」を参照してください。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint の構成方法

エンタープライズ環境で製品を構成する方法のガイダンスについては、「[Linux でのMicrosoft Defender for Endpointの基本設定の設定」を](linux-preferences.md)参照してください。

## <a name="common-applications-to-microsoft-defender-for-endpoint-can-impact"></a>Microsoft Defender for Endpointする一般的なアプリケーションは影響を受ける可能性があります

特定のアプリケーションからの高い I/O ワークロードでは、Microsoft Defender for Endpointインストール時にパフォーマンスの問題が発生する可能性があります。 これには、Jenkins や Jira などの開発者シナリオ用のアプリケーションや、OracleDB や Postgres などのデータベース ワークロードが含まれます。 パフォーマンスの低下が発生する場合は、信頼されたアプリケーションの除外を設定することを検討し、[Microsoft Defender ウイルス対策の一般的な除外ミス](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)を考慮してください。 その他のガイダンスについては、サード パーティ製アプリケーションからのウイルス対策の除外に関するドキュメントを参照することを検討してください。

## <a name="resources"></a>リソース

- ログ、アンインストール、またはその他のトピックの詳細については、「 [リソース](linux-resources.md)」を参照してください。
