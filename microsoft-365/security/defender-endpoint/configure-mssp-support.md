---
title: マネージ セキュリティ サービス プロバイダーのサポートを構成する
description: エンドポイント用 Microsoft Defender との MSSP 統合を構成するために必要な手順を実行する
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8f4b63c2c4d1f0205e3a97eec6273c878d866f0d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213747"
---
# <a name="configure-managed-security-service-provider-integration"></a>マネージド セキュリティ サービス プロバイダーの統合を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

管理セキュリティ サービス プロバイダー (MSSP) の統合を有効にするには、次の構成手順を実行する必要があります。

> [!NOTE]
> この記事では、サービス プロバイダーとサービス コンシューマーを区別するために、次の用語を使用します。
>
> - MSSP: 組織のセキュリティ デバイスの監視と管理を提供するセキュリティ組織。
> - MSSP のお客様: MSSP のサービスを利用する組織。

統合により、MSSP は次のアクションを実行できます。

- MSSP 顧客のポータルへのアクセスMicrosoft 365 Defenderする
- 電子メール通知を取得し、
- セキュリティ情報とイベント管理 (SIEM) ツールを使用してアラートを取得する

MSSP がこれらのアクションを実行する前に、MSSP のお客様は、MSSP がポータルにアクセスできるよう、Defender for Endpoint テナントへのアクセスを許可する必要があります。

通常、MSSP のお客様は初期構成手順を実行して、MSSP にセキュリティ セントラル テナントへのアクセス権Windows Defender付与します。 アクセスが許可された後、他の構成手順は、MSSP カスタマーまたは MSSP によって実行できます。

一般に、次の構成手順を実行する必要があります。

- **MSSP にアクセス権を付与Microsoft 365 Defender**

  このアクションは、MSSP のお客様が行う必要があります。 MSSP のお客様の Defender for Endpoint テナントへの MSSP アクセスを許可します。

- **MSSP に送信されるアラート通知を構成する**

  このアクションは、MSSP カスタマーまたは MSSP によって実行できます。 これにより、MSSP は、MSSP のお客様に対処する必要があるアラートを知る必要があります。

- **MSSP 顧客のテナントから SIEM システムへのアラートの取得**

  このアクションは MSSP によって実行されます。 これにより、MSSP は SIEM ツールでアラートをフェッチできます。

- **API を使用して MSSP 顧客のテナントからアラートを取得する**

  このアクションは MSSP によって実行されます。 これにより、MSSP は API を使用してアラートをフェッチできます。

## <a name="multi-tenant-access-for-mssps"></a>MSSP のマルチテナント アクセス

マルチテナント委任アクセスを実装する方法については [、「Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)のマルチテナント アクセス」を参照してください。

## <a name="related-topics"></a>関連トピック

- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [MSSP カスタマー ポータルにアクセスする](access-mssp-portal.md)
- [アラート通知を構成する](configure-mssp-notifications.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
