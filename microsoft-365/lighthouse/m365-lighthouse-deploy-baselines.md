---
title: ベースラインMicrosoft 365 Lighthouse展開する
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
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseベースラインを展開する方法Microsoft 365 Lighthouseします。
ms.openlocfilehash: f329993443b4bd3003a3e8460d77f9b73ac10fc6
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409106"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a><span data-ttu-id="6f470-103">ベースラインMicrosoft 365 Lighthouse展開する</span><span class="sxs-lookup"><span data-stu-id="6f470-103">Deploy Microsoft 365 Lighthouse baselines</span></span> 

> [!NOTE]
> <span data-ttu-id="6f470-104">この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6f470-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="6f470-105">組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="6f470-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="6f470-106">Microsoft 365 Lighthouse基準を使用すると、テナント ユーザー、デバイス、およびデータをセキュリティで保護するための標準的な管理テナント構成を展開できます。</span><span class="sxs-lookup"><span data-stu-id="6f470-106">Microsoft 365 Lighthouse baselines let you deploy standard managed tenant configurations to secure tenant users, devices, and data.</span></span> <span data-ttu-id="6f470-107">次の 6 つの既定の基準構成が標準でMicrosoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="6f470-107">There are six default baseline configurations that come standard with Microsoft 365 Lighthouse:</span></span>

- <span data-ttu-id="6f470-108">管理者に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="6f470-108">Require MFA for admins</span></span>
- <span data-ttu-id="6f470-109">エンド ユーザーに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="6f470-109">Require MFA for end users</span></span>
- <span data-ttu-id="6f470-110">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="6f470-110">Block Legacy Authentication</span></span>
- <span data-ttu-id="6f470-111">[デバイス登録の設定] Microsoft エンドポイント マネージャー – Azure AD参加</span><span class="sxs-lookup"><span data-stu-id="6f470-111">Set up Device Enrollment in Microsoft Endpoint Manager – Azure AD Join</span></span>
- <span data-ttu-id="6f470-112">デバイスの Defender ウイルス対策ポリシーをWindowsする</span><span class="sxs-lookup"><span data-stu-id="6f470-112">Configure Defender Anti-virus policy for Windows devices</span></span>
- <span data-ttu-id="6f470-113">デバイスのコンプライアンス ポリシーをWindowsする</span><span class="sxs-lookup"><span data-stu-id="6f470-113">Configure Compliance Policy for Windows devices</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6f470-114">はじめに</span><span class="sxs-lookup"><span data-stu-id="6f470-114">Before you begin</span></span>

<span data-ttu-id="6f470-115">ユーザーと顧客テナントが「要件」に記載されている要件を満[た](m365-lighthouse-requirements.md)していることを確認Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="6f470-115">Make sure you and your customer tenants meet the requirements listed in [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span></span>

## <a name="learn-more-about-the-default-baseline"></a><span data-ttu-id="6f470-116">既定の基準計画の詳細</span><span class="sxs-lookup"><span data-stu-id="6f470-116">Learn more about the default baseline</span></span>

<span data-ttu-id="6f470-117">左側 **のナビゲーション ウィンドウから** [基準計画] を選択して、[基準計画] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f470-117">Select **Baselines** from the left navigation pane to open the Baselines page.</span></span> <span data-ttu-id="6f470-118">既定の基準計画が既定のテナント グループ (すべてのテナント) に既に追加されているのが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f470-118">You'll see that the default baseline has already been added to the Default tenant group (all tenants).</span></span> <span data-ttu-id="6f470-119">既定の基準計画構成を表示するには、[基準計画の表示] を **選択して** [既定の基準計画] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f470-119">To view the default baseline configurations, select **View baseline** to open the Default baseline page.</span></span> <span data-ttu-id="6f470-120">構成は展開手順として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f470-120">The configurations are listed as deployment steps.</span></span> <span data-ttu-id="6f470-121">展開の詳細とユーザーへの影響を表示するには、展開手順を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f470-121">Select any of the deployment steps to view deployment details and user impact.</span></span>

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="[既定の基準計画] ページのスクリーンショット。>。":::

## <a name="deploy-a-baseline-configuration"></a><span data-ttu-id="6f470-123">ベースライン構成の展開</span><span class="sxs-lookup"><span data-stu-id="6f470-123">Deploy a baseline configuration</span></span>  

1. <span data-ttu-id="6f470-124">左側のナビゲーション ページで、[ **テナント** ] を選択して、オンボードテナントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="6f470-124">In the left navigation page, select **Tenants** to view a list of your onboarded tenants.</span></span>

2. <span data-ttu-id="6f470-125">ベースライン構成を展開するテナントを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f470-125">Select the tenant you want to deploy the baseline configuration to.</span></span>

3. <span data-ttu-id="6f470-126">[展開 **計画] タブを** 選択すると、テナントの展開計画に追加されたベースラインのすべての展開手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f470-126">Select the **Deployment plan** tab to see all the deployment steps from the baseline that have been added to the tenant's deployment plan.</span></span>

4. <span data-ttu-id="6f470-127">展開手順を選択して、展開手順ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f470-127">Select a deployment step to open the deployment step page.</span></span>

5. <span data-ttu-id="6f470-128">[ **適用] を** 選択して、選択した展開手順をテナントに適用します。</span><span class="sxs-lookup"><span data-stu-id="6f470-128">Select **Apply** to apply the selected deployment step to the tenant.</span></span> <span data-ttu-id="6f470-129">展開手順に 「このアクションには手動の手順が必要です」と示されている場合は、展開手順が正しく適用されるように手動手順を完了してください。</span><span class="sxs-lookup"><span data-stu-id="6f470-129">If the deployment step indicates "This action requires a manual step", make sure to complete the manual step so the deployment step is applied correctly.</span></span>

## <a name="related-content"></a><span data-ttu-id="6f470-130">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="6f470-130">Related content</span></span>

<span data-ttu-id="6f470-131">[基準計画を使用して標準テナント構成を](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 展開する概要 (記事)</span><span class="sxs-lookup"><span data-stu-id="6f470-131">[Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (article)</span></span>\
<span data-ttu-id="6f470-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="6f470-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>