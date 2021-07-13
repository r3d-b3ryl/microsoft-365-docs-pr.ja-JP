---
title: Microsoft 365 Lighthouseリストの概要
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
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseの一覧について説明します。
ms.openlocfilehash: 05c6bf6c1b9529d05fac04c2d5c43802280cfbc9
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395336"
---
# <a name="microsoft-365-lighthouse-tenant-list-overview"></a><span data-ttu-id="08660-103">Microsoft 365 Lighthouseリストの概要</span><span class="sxs-lookup"><span data-stu-id="08660-103">Microsoft 365 Lighthouse tenant list overview</span></span>

> [!NOTE]
> <span data-ttu-id="08660-104">この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08660-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="08660-105">組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="08660-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="08660-106">テナントMicrosoft 365 Lighthouseリストには、契約している異なるテナントに関する分析情報が表示されます(テナントのオンボーディング状態は、Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="08660-106">The Microsoft 365 Lighthouse tenant list provides insights into the different tenants you have a contract with, including tenant onboarding status relative to Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="08660-107">テナントリストでは、テナントにタグを付け、Microsoft 365 Lighthouse 全体でさまざまなフィルターを提供し、特定のテナントとその展開計画の状態について詳しくは、ドリルダウンしてください。</span><span class="sxs-lookup"><span data-stu-id="08660-107">The tenant list also lets you tag tenants to provide different filters throughout Microsoft 365 Lighthouse, and drill down to learn more about a given tenant and the status of their deployment plan.</span></span>

<span data-ttu-id="08660-108">テナントがオンボーディング要件Microsoft 365 Lighthouse [を](m365-lighthouse-requirements.md)満たした後、テナントの一覧に状態が **[アクティブ**] として表示されます。</span><span class="sxs-lookup"><span data-stu-id="08660-108">After your tenants meet the [Microsoft 365 Lighthouse onboarding requirements](m365-lighthouse-requirements.md), their status will show as **Active** in the tenant list.</span></span>

<span data-ttu-id="08660-109">[テナント] ウィンドウでテナントMicrosoft 365 Lighthouseアクセスするには、左側のナビゲーション ウィンドウで [テナント] を選択して [テナント] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="08660-109">To access the tenant list in Microsoft 365 Lighthouse, select **Tenants** in the left navigation pane to open the Tenants page.</span></span>

## <a name="tenant-status"></a><span data-ttu-id="08660-110">テナントの状態</span><span class="sxs-lookup"><span data-stu-id="08660-110">Tenant status</span></span>

<span data-ttu-id="08660-111">次の表に、さまざまな状態メッセージとその意味を示します。</span><span class="sxs-lookup"><span data-stu-id="08660-111">The following table shows the different status messages and their meaning.</span></span><br><br>

| <span data-ttu-id="08660-112">ステータス メッセージ</span><span class="sxs-lookup"><span data-stu-id="08660-112">Status message</span></span> | <span data-ttu-id="08660-113">説明</span><span class="sxs-lookup"><span data-stu-id="08660-113">Description</span></span> |
|--|--|
| <span data-ttu-id="08660-114">Active</span><span class="sxs-lookup"><span data-stu-id="08660-114">Active</span></span> | <span data-ttu-id="08660-115">オンボーディングとデータ フローが開始されました。</span><span class="sxs-lookup"><span data-stu-id="08660-115">Onboarding and data flow has started.</span></span> |
| <span data-ttu-id="08660-116">プロセス中</span><span class="sxs-lookup"><span data-stu-id="08660-116">In process</span></span> | <span data-ttu-id="08660-117">テナントが検出されましたが、完全にはオンボードされません。</span><span class="sxs-lookup"><span data-stu-id="08660-117">Tenant discovered, but not fully onboarded.</span></span> |
| <span data-ttu-id="08660-118">不適格、DAP</span><span class="sxs-lookup"><span data-stu-id="08660-118">Ineligible, DAP</span></span> | <span data-ttu-id="08660-119">委任された管理者特権 (DAP) のセットアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="08660-119">Delegated Admin Privileges (DAP) setup is required.</span></span> |
| <span data-ttu-id="08660-120">不適格、ユーザー数</span><span class="sxs-lookup"><span data-stu-id="08660-120">Ineligible, user count</span></span> | <span data-ttu-id="08660-121">テナントには、許可されているユーザーよりも多くのユーザーがあります。</span><span class="sxs-lookup"><span data-stu-id="08660-121">Tenant has more users than allowed.</span></span> |
| <span data-ttu-id="08660-122">不適格、ライセンス</span><span class="sxs-lookup"><span data-stu-id="08660-122">Ineligible, license</span></span> | <span data-ttu-id="08660-123">テナントに必要なライセンスはありません。</span><span class="sxs-lookup"><span data-stu-id="08660-123">Tenant does not have required license.</span></span> |
| <span data-ttu-id="08660-124">非アクティブ</span><span class="sxs-lookup"><span data-stu-id="08660-124">Inactive</span></span> | <span data-ttu-id="08660-125">テナントがアクティブではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="08660-125">Tenant is no longer active.</span></span> |

<span data-ttu-id="08660-126">テナントを非アクティブ化すると、ユーザーが非アクティブ化プロセスを完了Microsoft 365 Lighthouseに対してアクションを実行できません。</span><span class="sxs-lookup"><span data-stu-id="08660-126">Once you inactivate a tenant, you can't take action on the tenant while Microsoft 365 Lighthouse completes the inactivation process.</span></span> <span data-ttu-id="08660-127">非アクティブ化が完了するために最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08660-127">It may take up to 48 hours for inactivation to complete.</span></span>

<span data-ttu-id="08660-128">テナントを再アクティブ化する場合、データが再び表示されるには最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08660-128">If you decide to reactivate a tenant, it may take up to 48 hours for data to reappear.</span></span>

## <a name="tenant-tags"></a><span data-ttu-id="08660-129">テナント タグ</span><span class="sxs-lookup"><span data-stu-id="08660-129">Tenant tags</span></span>

<span data-ttu-id="08660-130">顧客テナントにカスタム ラベルをタグ付けMicrosoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="08660-130">You can tag your customer tenants with a custom label within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="08660-131">これらのタグは、テナントを整理するために使用できます。また、関連する顧客テナントのセットで使用できる既存のビューと分析情報を簡単にフィルター処理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="08660-131">These tags can be used to organize your tenants and can also help you easily filter the existing views and insights available to relevant sets of customer tenants.</span></span> <span data-ttu-id="08660-132">[テナント] ページから、タグと割り当てられているテナントを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="08660-132">You can also manage your tags and which tenants they're assigned to from the Tenants page.</span></span>

## <a name="related-content"></a><span data-ttu-id="08660-133">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="08660-133">Related content</span></span>

<span data-ttu-id="08660-134">[ユーザーのMicrosoft 365 Lighthouse](m365-lighthouse-requirements.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="08660-134">[Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (article)</span></span>\
<span data-ttu-id="08660-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="08660-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>