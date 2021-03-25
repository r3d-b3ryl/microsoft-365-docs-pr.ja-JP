---
title: Microsoft Cloud App Security の統合の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint は、すべてのクラウド アプリのネットワーク アクティビティを転送することで、クラウド アプリ セキュリティと統合します。
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
ms.openlocfilehash: 6ea885c17cf506ef6f9a4a7138630aed671f0ce8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066291"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Defender for Endpoint の Microsoft Cloud App Security の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) は、クラウド アプリへのアクセスを制御および制限しながら、クラウドに保存されているデータに対するコンプライアンス要件を適用することで、クラウド アプリとサービスを可視化する包括的なソリューションです。 詳細については [、「Cloud App Security」を参照してください](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。

>[!NOTE]
>この機能は、Windows 10 バージョン 1809 以降を実行しているデバイスのエンタープライズ モビリティ [+](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) セキュリティの E5 ライセンスで使用できます。

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender for Endpoint and Cloud App Security の統合 

Cloud App Security の検出は、エンタープライズ ファイアウォールおよびプロキシ サーバーからクラウド トラフィック ログに転送されるログに依存します。 Microsoft Defender for Endpoint は、すべてのクラウド アプリ のネットワーク アクティビティを収集および転送することで、クラウド アプリのセキュリティと統合し、クラウド アプリの使用状況を比類のない可視性を提供します。 監視機能はデバイスに組み込み、ネットワーク アクティビティを完全にカバーします。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


この統合は、既存のクラウド アプリ セキュリティ検出に次のような大きな改善点を提供します。 

- すべての場所で利用できる - ネットワーク アクティビティはエンドポイントから直接収集されます。企業ネットワークのオンとオフのデバイスは、エンタープライズ ファイアウォールまたはプロキシ サーバー経由でルーティングされるトラフィックに依存しなくなったので、デバイスがオンまたはオフの場所で利用できます。 

- クラウド トラフィック ログを Cloud App Security に転送するには、ファイアウォールとプロキシ サーバーの構成が必要です。 Defender for Endpoint と Cloud App Security の統合により、構成は不要です。 Microsoft Defender セキュリティ センターの設定でオンにし、行くのが良いです。 

- デバイス コンテキスト - クラウド トラフィック ログにデバイス コンテキストが不足しています。 Defender for Endpoint ネットワーク アクティビティは、デバイス コンテキスト (クラウド アプリにアクセスしたデバイス) で報告されます。そのため、ネットワーク アクティビティが行われた場所 (デバイス) と、ネットワーク アクティビティを実行したユーザー (ユーザー) を正確に理解できます。 

クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

## <a name="related-topic"></a>関連トピック

- [Microsoft Cloud App Security の統合を構成する](microsoft-cloud-app-security-config.md)
