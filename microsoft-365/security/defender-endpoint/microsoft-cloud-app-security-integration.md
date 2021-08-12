---
title: Microsoft Cloud App Security 統合の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint は、すべてのクラウド Cloud App Securityアクティビティを転送することで、ユーザーと統合します。
keywords: クラウド、アプリ、ネットワーク、可視性、使用状況
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 2e55070cfc8f5ee138f93ca7ae254655fabcdc9867ba3fd2056f9bbc35f3d099
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53800080"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security Defender for Endpoint の概要の詳細

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) は、クラウド アプリへのアクセスを制御および制限しながら、クラウドに保存されているデータに対するコンプライアンス要件を適用することで、クラウド アプリとサービスを可視化する包括的なソリューションです。 詳細については、「Cloud App Security」[を参照してください](/cloud-app-security/what-is-cloud-app-security)。

> [!NOTE]
> この機能は、バージョン 1809 以降で実行Enterprise Mobility + SecurityデバイスWindows 10 E5 ライセンスで使用できます。 [](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender for Endpoint and Cloud App Security統合

Cloud App Security検出は、エンタープライズ ファイアウォールおよびプロキシ サーバーから転送されるクラウド トラフィック ログに依存します。 Microsoft Defender for Endpoint は、すべてのクラウド Cloud App Securityアクティビティを収集して転送することで、クラウド アプリの使用状況を他に類を見ない可視性を提供することで、クラウド アプリと統合します。 監視機能はデバイスに組み込み、ネットワーク アクティビティを完全にカバーします。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4yQ]

この統合により、既存の検出に対して次の主なCloud App Security提供されます。

- すべての場所で利用できる - ネットワーク アクティビティはエンドポイントから直接収集されます。企業ネットワークのオンとオフのデバイスは、エンタープライズ ファイアウォールまたはプロキシ サーバー経由でルーティングされるトラフィックに依存しなくなったので、デバイスがオンまたはオフの場所で利用できます。

- 構成は不要です。クラウド トラフィック ログをファイアウォールとプロキシ サーバーの構成が必要Cloud App Securityクラウド トラフィック ログを転送します。 Defender for Endpoint and Cloud App Security統合により、構成は不要です。 設定でオンにMicrosoft Defender セキュリティ センターし、行くのが良いです。\

- デバイス コンテキスト - クラウド トラフィック ログにデバイス コンテキストが不足しています。 Defender for Endpoint ネットワーク アクティビティは、デバイス コンテキスト (クラウド アプリにアクセスしたデバイス) で報告されます。そのため、ネットワーク アクティビティが行われた場所 (デバイス) と、ネットワーク アクティビティを実行したユーザー (ユーザー) を正確に理解できます。

クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](/cloud-app-security/discovered-apps)。

## <a name="related-topic"></a>関連トピック

- [Microsoft Cloud App Security との統合を構成する](microsoft-cloud-app-security-config.md)
