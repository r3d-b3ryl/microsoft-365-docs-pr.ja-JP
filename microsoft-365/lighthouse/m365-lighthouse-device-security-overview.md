---
title: Microsoft 365 Lighthouseの [Microsoft Defender for Endpoint] ページの概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、セキュリティ リスクを表示する方法について説明します。
ms.openlocfilehash: f4c33552c71ada14d11e309cc2d7328f203e066c
ms.sourcegitcommit: 23a53b5c5e372a2a7ad5e175850224d3d464f6dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "67055968"
---
# <a name="overview-of-the-microsoft-defender-for-endpoint-page-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの [Microsoft Defender for Endpoint] ページの概要

Microsoft Defender for Endpointは、ランサムウェア、マルウェア、フィッシング、その他の脅威から顧客のデバイスを保護するためのエンドポイント セキュリティを提供します。 Microsoft 365 Lighthouseを使用すると、すべての顧客テナントのエンドポイント セキュリティ分析情報と情報を表示できます。

Microsoft 365 Lighthouseの [Microsoft Defender for Endpoint] ページには、ホーム ページの **[セキュリティ インシデント**] カードまたは左側のナビゲーション ウィンドウで [**デバイス** > **デバイス のセキュリティ**] を選択してアクセスできます。 テナントに注意が必要なセキュリティ インシデントとアラート、およびMicrosoft Defender for Endpointにオンボードされたデバイスが表示されます。

## <a name="incidents-and-alerts-tab"></a>[インシデントとアラート] タブ

[インシデントとアラート] タブには、顧客のネットワーク内のデバイスからフラグが設定されたインシデントとアラートのマルチテナント インシデント キューが表示されます。 既定では、キューには、過去 30 日間に発生したアクティブなインシデントが表示されます。 任意のインシデントまたはアラートを選択して、詳細情報を表示できます。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/microsoft-defender-endpoint-incidents.png" alt-text="インシデントとアラートをMicrosoft Defender for Endpointする":::

## <a name="devices-tab"></a>[デバイス] タブ

[デバイス] タブには、Microsoft Defender for Endpointにオンボードされている顧客テナント内のすべてのデバイスが一覧表示されます。 この一覧には、Microsoft エンドポイント マネージャーおよびMicrosoft Defender for Endpointによって管理されているデバイスが含まれます。

[デバイス] タブには、次のオプションも含まれています。

- **エクスポート**: デバイス コンプライアンス データを Excel コンマ区切り値 (.csv) ファイルにエクスポートする場合に選択します。
- **検索**: キーワードを入力して、リスト内の特定のデバイスをすばやく見つけます。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/microsoft-defender-endpoint-devices.png" alt-text="Microsoft Defender for Endpointオンボードデバイス ビュー":::

## <a name="related-content"></a>関連コンテンツ
[Microsoft Defender for Endpointインシデントの管理](../security/defender-endpoint/manage-incidents.md) (記事)\
[Microsoft Defender for Endpointのインシデントを調査する](../security/defender-endpoint/investigate-incidents.md) (記事)
