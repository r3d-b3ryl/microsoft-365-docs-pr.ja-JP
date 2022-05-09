---
title: マネージド セキュリティ サービス プロバイダーのサポートを構成する
description: MSSP と Microsoft Defender for Endpointの統合を構成するために必要な手順を実行します。
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
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
ms.openlocfilehash: 1a9a7e24bc08338549a78fcf9e9b2756701cd83f
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074584"
---
# <a name="configure-managed-security-service-provider-integration"></a>マネージド セキュリティ サービス プロバイダーの統合を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

マネージド セキュリティ サービス プロバイダー (MSSP) の統合を有効にするには、次の構成手順を実行する必要があります。

> [!NOTE]
> この記事では、サービス プロバイダーとサービス コンシューマーを区別するために、次の用語を使用します。
>
> - MSSP: 組織のセキュリティ デバイスの監視と管理を提供するセキュリティ組織。
> - MSSP のお客様: MSSP のサービスに関与する組織。

この統合により、MSSP は次のアクションを実行できるようになります。

- MSSP 顧客のMicrosoft 365 Defender ポータルにアクセスする
- 電子メール通知を取得し、
- セキュリティ情報とイベント管理 (SIEM) ツールを使用してアラートをフェッチする

MSSP がこれらのアクションを実行する前に、MSSP のお客様は、MSSP がポータルにアクセスできるように、Defender for Endpoint テナントへのアクセスを許可する必要があります。

通常、MSSP のお客様は初期構成手順を実行して、MSSP にWindows Defender Security Central テナントへのアクセスを許可します。 アクセスが許可された後は、MSSP の顧客または MSSP によって他の構成手順を実行できます。

一般に、次の構成手順を実行する必要があります。

- **Microsoft 365 Defenderへの MSSP アクセス権を付与する**

  このアクションは、MSSP のお客様が行う必要があります。 MSSP 顧客の Defender for Endpoint テナントへの MSSP アクセス権が付与されます。

- **MSSP に送信されるアラート通知を構成する**

  このアクションは、MSSP のお客様または MSSP によって実行できます。 これにより、MSSP のお客様に対処するために必要なアラートが MSSP に認識されます。

- **MSSP 顧客のテナントから SIEM システムにアラートをフェッチする**

  このアクションは、MSSP によって実行されます。 これにより、MSSP は SIEM ツールでアラートをフェッチできます。

- **API を使用して MSSP 顧客のテナントからアラートをフェッチする**

  このアクションは、MSSP によって実行されます。 これにより、MSSP は API を使用してアラートをフェッチできます。

## <a name="multi-tenant-access-for-mssps"></a>MSSP のマルチテナント アクセス

マルチテナント委任アクセスを実装する方法については、「 [Managed Security Service Providers のマルチテナント アクセス](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)」を参照してください。

## <a name="related-topics"></a>関連項目

- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [MSSP カスタマー ポータルにアクセスする](access-mssp-portal.md)
- [アラート通知を構成する](configure-mssp-notifications.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
