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
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984918"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="7e748-103">クラウド ソリューション プロバイダーの追加情報</span><span class="sxs-lookup"><span data-stu-id="7e748-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="7e748-104">お客様をサポートするクラウド ソリューション プロバイダー (CSP) は、Microsoft Cloud Deutschland から新しいドイツのデータセンター地域への移行中に追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e748-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="7e748-105">パートナー テナントの移行</span><span class="sxs-lookup"><span data-stu-id="7e748-105">Partner tenant migration</span></span>

<span data-ttu-id="7e748-106">パートナーの Microsoft Cloud Deutschland テナントは移行されません。</span><span class="sxs-lookup"><span data-stu-id="7e748-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="7e748-107">代わりに、新しいOffice 365サービス テナントが、新しいドイツのデータセンター領域の Microsoft パートナーごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="7e748-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="7e748-108">CSP 顧客テナントは、新しいドイツのデータセンター地域に移行され、同じパートナーの新Office 365サービス テナントにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="7e748-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="7e748-109">顧客移行後、パートナーはドイツのデータセンター地域の新しいサービス Office 365テナントを使用して顧客を管理できます。</span><span class="sxs-lookup"><span data-stu-id="7e748-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="7e748-110">Azure でサブスクリプションが見つからない</span><span class="sxs-lookup"><span data-stu-id="7e748-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="7e748-111">サブスクリプション [とライセンス移行 (フェーズ 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) が完了すると、クラウド ソリューション プロバイダーは Azure サブスクリプションにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="7e748-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="7e748-112">アクセスを回復するには、次の手順に従って、すべての Azure サブスクリプションと管理グループを管理するためのアクセス [を昇格します](/azure/role-based-access-control/elevate-access-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="7e748-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
