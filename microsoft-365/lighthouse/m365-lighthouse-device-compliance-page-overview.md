---
title: Microsoft 365 Lighthouseデバイス コンプライアンス ページの概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouseデバイスコンプライアンス ページについて説明します。
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395226"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="37f5c-103">Microsoft 365 Lighthouseデバイス コンプライアンス ページの概要</span><span class="sxs-lookup"><span data-stu-id="37f5c-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="37f5c-104">この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37f5c-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="37f5c-105">組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="37f5c-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="37f5c-106">Microsoft 365 Lighthouse左側のナビゲーション ウィンドウで [デバイス] を選択して [デバイスコンプライアンス] ページを開き、すべてのテナントの Intune デバイスコンプライアンスに関連するインサイトと情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="37f5c-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="37f5c-107">このページでは、テナント全体のコンプライアンス状態の概要を取得し、テナントごとにデバイスの一覧を表示し、コンプライアンス ポリシーと設定に関する状態レポートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="37f5c-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="37f5c-108">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="37f5c-108">Overview tab</span></span>  
  
<span data-ttu-id="37f5c-109">[概要] タブで、テナント全体のデバイス コンプライアンスの状態を表示し、毎月のデバイス コンプライアンスの傾向を確認し、デバイスにコンプライアンス ポリシーが割り当てられているかどうかを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="37f5c-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="37f5c-110">条件付きアクセス ポリシーに基づいて、テナントデバイスのコンプライアンスアクションと要件に関する情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="37f5c-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="[概要] タブのスクリーンショット。":::

## <a name="devices-tab"></a><span data-ttu-id="37f5c-112">[デバイス] タブ</span><span class="sxs-lookup"><span data-stu-id="37f5c-112">Devices tab</span></span>

<span data-ttu-id="37f5c-113">[デバイス] タブで、すべてのテナント デバイスの一覧を表示し、コンプライアンスの状態 (準拠、非準拠、猶予期間、および評価されない) に基づいて一覧をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="37f5c-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="37f5c-114">さまざまなコンプライアンス状態の詳細については [、「Monitor Intune Device compliance policies」を参照してください](/mem/intune/protect/compliance-policy-monitor)。</span><span class="sxs-lookup"><span data-stu-id="37f5c-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="37f5c-115">デバイスが現在のコンプライアンス状態にある理由の詳細を表示するには、任意のデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="37f5c-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="37f5c-116">デバイスでアクションを実行する必要がある場合は、デバイスをデバイスに表示するオプションMicrosoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="37f5c-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="[デバイス] タブのスクリーンショット。":::

## <a name="policies-tab"></a><span data-ttu-id="37f5c-118">[ポリシー] タブ</span><span class="sxs-lookup"><span data-stu-id="37f5c-118">Policies tab</span></span>

<span data-ttu-id="37f5c-119">[ポリシー] タブでは、ツールバーの比較機能を使用して、テナント全体のコンプライアンス ポリシーを表示し、同じプラットフォームタイプの 2 つまたは 3 つのポリシーを比較できます。</span><span class="sxs-lookup"><span data-stu-id="37f5c-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="37f5c-120">また、ポリシーを選択して詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="37f5c-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="[ポリシー] タブのスクリーンショット。":::

## <a name="settings-tab"></a><span data-ttu-id="37f5c-122">設定タブ</span><span class="sxs-lookup"><span data-stu-id="37f5c-122">Settings tab</span></span>

<span data-ttu-id="37f5c-123">[設定] タブには、テナント デバイス間の非準拠設定の集計レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37f5c-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="37f5c-124">レポート行を選択して、非準拠デバイスが属するテナントを含む詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="37f5c-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="[ページ] タブ設定スクリーンショット。":::

## <a name="related-content"></a><span data-ttu-id="37f5c-126">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="37f5c-126">Related content</span></span>

<span data-ttu-id="37f5c-127">[Microsoft 365 Lighthouse ユーザー ページの概要](m365-lighthouse-users-page-overview.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="37f5c-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="37f5c-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="37f5c-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
