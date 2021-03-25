---
title: Microsoft Defender ATP for Linux
ms.reviewer: ''
description: Microsoft Defender ATP for Linux をインストールして使用する方法について説明します。
keywords: microsoft、 defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: ce7b15a727ddfa9b0d2bc68b7901f2e79aaf0721
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064963"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender for Endpoint for Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Microsoft Defender for Endpoint for Linux をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Microsoft Defender for Endpoint for Linux と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender for Endpoint for Linux をインストールする方法

### <a name="prerequisites"></a>前提条件

- Microsoft Defender セキュリティ センター ポータルへのアクセス
- systemd システム マネージャー [を使用した](https://systemd.io/) Linux 配布
- Linux および BASH スクリプトでの初心者レベルのエクスペリエンス
- デバイスの管理特権 (手動展開の場合)

### <a name="installation-instructions"></a>インストール手順

Microsoft Defender for Endpoint for Linux のインストールと構成に使用できる方法と展開ツールがいくつかあります。

一般に、次の手順を実行する必要があります。

- Microsoft Defender for Endpoint サブスクリプションを持ち、Microsoft Defender for Endpoint ポータルへのアクセス権を持 [っている必要があります](microsoft-defender-security-center.md)。
- 次のいずれかの展開方法を使用して、Microsoft Defender for Endpoint for Linux を展開します。
  - コマンド ライン ツール:
    - [手動展開](linux-install-manually.md)
  - サードパーティの管理ツール:
    - [Puppet 構成管理ツールを使用した展開](linux-install-with-puppet.md)
    - [Ansible 構成管理ツールを使用した展開](linux-install-with-ansible.md)

インストールエラーが発生した場合は、「Microsoft Defender for Endpoint for Linux でのインストールエラーのトラブルシューティング [」を参照してください](linux-support-install.md)。

### <a name="system-requirements"></a>システム要件

- サポートされている Linux サーバーの配布とバージョン:

  - Red Hat Enterprise Linux 7.2 以上
  - CentOS 7.2 以上
  - Ubuntu 16.04 LTS 以上の LTS
  - Debian 9 以上
  - SUSE Linux Enterprise Server 12 以上
  - Oracle Linux 7.2 以上

- 最小カーネル バージョン 3.10.0-327
- カーネル `fanotify` オプションを有効にする必要があります
  > [!CAUTION]
  > Defender for Endpoint for Linux を他のベースのセキュリティ ソリューションと並べて実行する `fanotify` 方法はサポートされていません。 オペレーティング システムのハングを含む予期しない結果につながる可能性があります。

- ディスク領域: 1 GB
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
  >[!NOTE]
  > 追加されたルールによってキャプチャされたシステム イベントは監査ログに追加され、ホストの監査とアップストリーム コレクション `audit.logs` に影響を与える可能性があります。 Microsoft Defender for Endopoint for Linux で追加されたイベントには、キーがタグ付け `mdatp` されます。

### <a name="network-connections"></a>ネットワーク接続

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しなかっている必要があります。 ある場合は、許可ルール *の作成が* 必要な場合があります。

|**ドメインリストのスプレッドシート**|**説明**|
|:-----|:-----|
|![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)<br/>  | サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。 <br><br>[ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> より具体的な URL リストについては [、「Configure proxy and internet connectivity settings」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

Defender for Endpoint では、次の検出方法を使用してプロキシ サーバーを検出できます。
- 透過プロキシ
- 静的プロキシの手動構成

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。 透過プロキシの場合、Defender for Endpoint の追加構成は不要です。 静的プロキシの場合は、「手動静的プロキシ構成 [」の手順に従います](linux-static-proxy-configuration.md)。

> [!WARNING]
> PAC、WPAD、および認証されたプロキシはサポートされていません。 静的プロキシまたは透過プロキシのみを使用してください。
>
> SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。 SSL インスペクションとプロキシ サーバーが、Defender for Endpoint for Linux からインターセプトなしで関連する URL にデータを直接渡す例外を構成します。 インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。

トラブルシューティング手順については、「Microsoft Defender for Endpoint for Linux のクラウド接続の問題のトラブルシューティング [」を参照してください](linux-support-connectivity.md)。

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender for Endpoint for Linux を更新する方法

Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。 Microsoft Defender for Endpoint for Linux を更新するには [、「Deploy updates for Microsoft Defender for Endpoint for Linux」を参照してください](linux-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender for Endpoint for Linux を構成する方法

エンタープライズ環境で製品を構成する方法のガイダンスについては、「Linux 用 Microsoft Defender for Endpoint の基本設定の [設定」を参照してください](linux-preferences.md)。

## <a name="resources"></a>リソース

- ログ記録、アンインストール、その他のトピックの詳細については [、「Resources」を参照してください](linux-resources.md)。
