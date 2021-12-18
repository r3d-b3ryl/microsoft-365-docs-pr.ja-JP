---
title: Microsoft Defender for Cloud Apps 統合の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint は、すべてのクラウド アプリのネットワーク アクティビティを転送することで、Defender for Cloud Apps と統合します。
keywords: クラウド、アプリ、ネットワーク、可視性、使用状況
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 8260903ba8031bae76f420a7b010ed73df1c833d
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560386"
---
# <a name="microsoft-defender-for-cloud-apps-in-defender-for-endpoint-overview"></a>エンドポイント用 Defender の Microsoft Defender for Cloud Apps の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Cloud Apps は、クラウド アプリへのアクセスを制御および制限しながら、クラウドに保存されたデータに対するコンプライアンス要件を適用することで、クラウド アプリとサービスを可視化する包括的なソリューションです。 詳細については [、「Defender for Cloud Apps」を参照してください](/cloud-app-security/what-is-cloud-app-security)。

> [!NOTE]
> この機能は、バージョン 1809 以降Enterprise Mobility + Security 11 以降Windows 10デバイスの E5 ライセンスWindows使用できます。 [](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

## <a name="microsoft-defender-for-endpoint-and-defender-for-cloud-apps-integration"></a>Microsoft Defender for Endpoint and Defender for Cloud Apps の統合

Defender for Cloud Apps discovery は、エンタープライズ ファイアウォールおよびプロキシ サーバーからクラウド トラフィック ログに転送されるログに依存します。 Microsoft Defender for Endpoint は、すべてのクラウド アプリ のネットワーク アクティビティを収集および転送することで、Defender for Cloud Apps と統合し、クラウド アプリの使用状況を比類のない可視性を提供します。 監視機能はデバイスに組み込み、ネットワーク アクティビティを完全にカバーします。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4yQ]

この統合により、既存の Defender for Cloud Apps 検出に次のような大きな改善点が提供されます。

- すべての場所で利用できる - ネットワーク アクティビティはエンドポイントから直接収集されます。企業ネットワークのオンとオフのデバイスは、エンタープライズ ファイアウォールまたはプロキシ サーバー経由でルーティングされるトラフィックに依存しなくなったので、デバイスがオンまたはオフの場所で利用できます。

- 構成は不要です。クラウド トラフィック ログを Defender for Cloud Apps に転送するには、ファイアウォールとプロキシ サーバーの構成が必要です。 Defender for Endpoint と Defender for Cloud Apps の統合により、構成は必要ありません。 設定でオンにMicrosoft Defender セキュリティ センターし、行くのが良いです。\

- デバイス コンテキスト - クラウド トラフィック ログにデバイス コンテキストが不足しています。 Defender for Endpoint ネットワーク アクティビティは、デバイス コンテキスト (クラウド アプリにアクセスしたデバイス) で報告されます。そのため、ネットワーク アクティビティが行われた場所 (デバイス) と、ネットワーク アクティビティを実行したユーザー (ユーザー) を正確に理解できます。

クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](/cloud-app-security/discovered-apps)。

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Cloud Apps を統合のために構成する](microsoft-cloud-app-security-config.md)
