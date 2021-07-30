---
title: Linux 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Linux で Microsoft Defender for Endpoint をインストールして使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, Linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34c8ff79ebfb1325fa4c649ef246396c4dc54297
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656357"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Linux 上で Microsoft Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> 他のサード パーティ製エンドポイント保護製品を Microsoft Defender for Endpoint on Linux で実行すると、パフォーマンスの問題や予期しない副作用につながる可能性があります。 Microsoft 以外のエンドポイント保護が環境の絶対的な要件である場合でも、パッシブ モードで実行するウイルス対策機能を構成した後でも、Linux EDR の Defender for Endpoint[](linux-preferences.md#enable--disable-passive-mode)機能を安全に利用できます。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Linux に Microsoft Defender for Endpoint をインストールする方法

### <a name="prerequisites"></a>前提条件

- ポータルへのMicrosoft 365 Defenderアクセス
- systemd システム マネージャー [を使用した](https://systemd.io/) Linux 配布
- Linux および BASH スクリプトでの初心者レベルのエクスペリエンス
- デバイスの管理特権 (手動展開の場合)

> [!NOTE]
>  Microsoft Defender for Endpoint on Linux エージェントは [OMS エージェントから独立しています](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)。 Microsoft Defender for Endpoint は、独自の独立したテレメトリ パイプラインに依存しています。
> 
> Microsoft Defender for Endpoint on Linux はまだ Azure Security Center に統合されていません。

### <a name="installation-instructions"></a>インストール手順

Linux での Microsoft Defender for Endpoint のインストールと構成に使用できる方法と展開ツールがいくつかあります。

一般に、次の手順を実行する必要があります。

- Microsoft Defender for Endpoint サブスクリプションを持ち、Microsoft Defender for Endpoint ポータルへのアクセス権を持 [っている必要があります](microsoft-defender-security-center.md)。
- 次のいずれかの展開方法を使用して、Microsoft Defender for Endpoint on Linux を展開します。
  - コマンド ライン ツール:
    - [手動展開](linux-install-manually.md)
  - サードパーティの管理ツール:
    - [Puppet 構成管理ツールを使用した展開](linux-install-with-puppet.md)
    - [Ansible 構成管理ツールを使用した展開](linux-install-with-ansible.md)
    - [Chef 構成管理ツールを使用した展開](linux-deploy-defender-for-endpoint-with-chef.md)
    
インストールエラーが発生した場合は、「Microsoft Defender for Endpoint on Linux でのインストールエラーのトラブルシューティング [」を参照してください](linux-support-install.md)。



### <a name="system-requirements"></a>システム要件

- サポートされる Linux サーバー配布と x64 (AMD64/EM64T) バージョン:

  - Red Hat Enterprise Linux 7.2 以上
  - CentOS 7.2 以上
  - Ubuntu 16.04 LTS 以上の LTS
  - Debian 9 以上
  - SUSE Linux Enterprise サーバー 12 以上
  - Oracle Linux 7.2 以上

    > [!NOTE]
    > 明示的にリストされていない配布とバージョンはサポートされていません (正式にサポートされている配布から派生している場合でも)。


- 最小カーネル バージョン 3.10.0-327

- カーネル `fanotify` オプションを有効にする必要があります

  > [!CAUTION]
  > Linux で Defender for Endpoint を他のベースのセキュリティ ソリューションと並べて実行する `fanotify` 方法はサポートされていません。 オペレーティング システムのハングを含む予期しない結果につながる可能性があります。

- ディスク領域: 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon には実行可能なアクセス許可が必要です。 詳細については、「Microsoft Defender for Endpoint on Linux のインストールに関する問題のトラブルシューティング」の「デーモンに実行可能なアクセス許可が付与されている」 [を参照してください](/microsoft-365/security/defender-endpoint/linux-support-install)。

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

- 監査フレームワーク ( `auditd` ) を有効にする必要があります。
  > [!NOTE]
  > 追加されたルールによってキャプチャされたシステム イベントは (s) に追加され、ホストの監査とアップストリーム コレクション `/etc/audit/rules.d/` `audit.log` に影響を与える可能性があります。 Microsoft Defender for Endpoint on Linux で追加されたイベントには、キーがタグ付け `mdatp` されます。

### <a name="network-connections"></a>ネットワーク接続

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しなかっている必要があります。 ある場合は、許可ルール *の作成が* 必要な場合があります。

| ドメインリストのスプレッドシート | 説明 |
|:-----|:-----|
|![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)<br/>  | サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。 <br><br>[ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> より具体的な URL リストについては [、「Configure proxy and internet connectivity settings」を参照してください](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

Defender for Endpoint では、次の検出方法を使用してプロキシ サーバーを検出できます。
- 透過プロキシ
- 静的プロキシの手動構成

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。 透過プロキシの場合、Defender for Endpoint の追加構成は不要です。 静的プロキシの場合は、「手動静的プロキシ構成 [」の手順に従います](linux-static-proxy-configuration.md)。

> [!WARNING]
> PAC、WPAD、および認証されたプロキシはサポートされていません。 静的プロキシまたは透過プロキシのみを使用してください。
>
> SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。 SSL インスペクションとプロキシ サーバーの例外を構成して、Defender for Endpoint on Linux のデータを、インターセプトなしで関連する URL に直接渡します。 インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。

トラブルシューティング手順については、「Microsoft Defender for Endpoint on Linux のクラウド接続の問題のトラブルシューティング [」を参照してください](linux-support-connectivity.md)。

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Linux 上のエンドポイント用 Microsoft Defender を更新する方法

Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。 Microsoft Defender for Endpoint on Linux を更新するには、「Linux での Microsoft Defender for Endpoint の [更新プログラムの展開」を参照してください](linux-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint の構成方法

エンタープライズ環境で製品を構成する方法については、「Linux での Microsoft Defender for Endpoint の基本設定の設定 [」を参照してください](linux-preferences.md)。

## <a name="resources"></a>リソース

- ログ記録、アンインストール、その他のトピックの詳細については [、「Resources」を参照してください](linux-resources.md)。
