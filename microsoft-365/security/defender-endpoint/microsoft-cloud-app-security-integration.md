---
title: Microsoft Defender for Cloud Apps 統合の概要
ms.reviewer: ''
description: Microsoft Defender for Endpointは、すべてのクラウド アプリ ネットワーク アクティビティを転送することで、Defender for Cloud アプリと統合されます。
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
ms.openlocfilehash: d3cf5259aeb070175d5d2a4a95154974c6cd4d56
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61867831"
---
# <a name="microsoft-defender-for-cloud-apps-in-defender-for-endpoint-overview"></a>Defender for Endpoint のMicrosoft Defender for Cloud Appsの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Cloud Appsは、クラウド アプリへのアクセスを制御および制限し、クラウドに格納されているデータに対するコンプライアンス要件を適用することで、クラウド アプリとサービスを可視化する包括的なソリューションです。 詳細については、「[Defender for Cloud アプリ](/cloud-app-security/what-is-cloud-app-security)」を参照してください。

> [!NOTE]
> この機能は、Windows 10 バージョン 1809 以降、または[Windows 11](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)を実行しているデバイスのEnterprise Mobility + Securityに対する E5 ライセンスで使用できます。

## <a name="microsoft-defender-for-endpoint-and-defender-for-cloud-apps-integration"></a>Microsoft Defender for EndpointとDefender for Cloudアプリの統合

Defender for Cloud Apps の検出は、エンタープライズ ファイアウォールとプロキシ サーバーからクラウド トラフィック ログが転送されることに依存しています。 Microsoft Defender for Endpointは、すべてのクラウド アプリ ネットワーク アクティビティを収集して転送することで、Defender for Cloud アプリと統合し、クラウド アプリの使用状況を比類のない可視性で提供します。 監視機能はデバイスに組み込まれており、ネットワーク アクティビティの完全なカバレッジを提供します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4yQ]

この統合により、既存のDefender for Cloud アプリの検出に次の大きな機能強化が提供されます。

- すべての場所で使用可能 - ネットワーク アクティビティはエンドポイントから直接収集されるため、デバイスが企業ネットワーク上または企業ネットワーク外の場所であればどこでも使用できます。これは、エンタープライズ ファイアウォールまたはプロキシ サーバー経由でルーティングされるトラフィックに依存しなくなったためです。

- すぐに機能し、構成は不要です。クラウド トラフィック ログを Defender for Cloud Apps に転送するには、ファイアウォールとプロキシ サーバーの構成が必要です。 Defender for Endpoint と Defender for Cloud Apps の統合では、構成は必要ありません。 Microsoft 365 Defender設定でオンにするだけで、問題ありません。

- デバイス コンテキスト - クラウド トラフィック ログにデバイス コンテキストが不足しています。 Defender for Endpoint ネットワーク アクティビティは、デバイス コンテキスト (どのデバイスがクラウド アプリにアクセスしたか) で報告されるため、ネットワーク アクティビティが行われた場所 (デバイス) と、それを実行したユーザーを正確に把握できます。

クラウド検出の詳細については、「検出 [されたアプリの操作](/cloud-app-security/discovered-apps)」を参照してください。

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Cloud Apps を統合のために構成する](microsoft-cloud-app-security-config.md)
