---
title: クラウド ソリューション プロバイダーの追加情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Deutschland からの移行に関連するクラウド ソリューション プロバイダーの追加情報。'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191271"
---
# <a name="additional-information-for-cloud-solution-providers"></a>クラウド ソリューション プロバイダーの追加情報

お客様をサポートするクラウド ソリューション プロバイダー (CSP) は、Microsoft Cloud Deutschland から新しいドイツのデータセンター地域への移行中に追加の手順を実行する必要があります。

## <a name="partner-tenant-migration"></a>パートナー テナントの移行

パートナーの Microsoft Cloud Deutschland テナントは移行されません。 代わりに、新しいOffice 365サービス テナントが、新しいドイツのデータセンター領域の Microsoft パートナーごとに作成されます。

CSP 顧客テナントは、新しいドイツのデータセンター地域に移行され、同じパートナーの新Office 365サービス テナントにリンクされます。 顧客移行後、パートナーはドイツのデータセンター地域の新しいサービス Office 365テナントを使用して顧客を管理できます。

## <a name="missing-subscriptions-in-azure"></a>Azure でサブスクリプションが見つからない

サブスクリプション [とライセンス移行 (フェーズ 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) が完了すると、クラウド ソリューション プロバイダーは Azure サブスクリプションにアクセスできなくなります。

アクセスを回復するには、次の手順に従って、すべての Azure サブスクリプションと管理グループを管理するためのアクセス [を昇格します](/azure/role-based-access-control/elevate-access-global-admin)。
