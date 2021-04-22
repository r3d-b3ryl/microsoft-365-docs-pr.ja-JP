---
title: Microsoft 365 セキュリティ センターでユーザーを分析する
description: Microsoft 365 セキュリティ センターのユーザーを分析する
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、監視、レポート、ID、データ、デバイス、アプリ、インシデント、分析、応答
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939732"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="b75f8-104">Microsoft 365 セキュリティ センターでユーザーを分析する</span><span class="sxs-lookup"><span data-stu-id="b75f8-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b75f8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b75f8-105">**Applies to:**</span></span>

- <span data-ttu-id="b75f8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b75f8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b75f8-107">インシデント分析の一部には、ユーザー アカウントを含めできます。</span><span class="sxs-lookup"><span data-stu-id="b75f8-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="b75f8-108">[インシデント]**からインシデント** の [ユーザー] タブから開始し、&**ユーザー** >\*通知>\***します**。</span><span class="sxs-lookup"><span data-stu-id="b75f8-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例":::

<span data-ttu-id="b75f8-110">インシデントのユーザー アカウントの概要を簡単に取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。</span><span class="sxs-lookup"><span data-stu-id="b75f8-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="b75f8-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b75f8-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウント概要ウィンドウの例":::

<span data-ttu-id="b75f8-113">ここから、[ユーザー に移動] **ページを選択して** 、ユーザー アカウントの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b75f8-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="b75f8-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b75f8-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウント ページの例":::

<span data-ttu-id="b75f8-116">[ユーザー] ページの一覧からユーザー アカウントの名前を選択すると、このページを **確認** することもできます。</span><span class="sxs-lookup"><span data-stu-id="b75f8-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="b75f8-117">Microsoft 365 セキュリティ センターのユーザー ページでは、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Cloud App Security の情報を組み合わせたもの (ライセンスに応じて異なる)。</span><span class="sxs-lookup"><span data-stu-id="b75f8-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="b75f8-118">このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b75f8-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="b75f8-119">これには、ユーザーの全体的なリスクに寄与したリスクと最近のイベントやアラートを評価するのに役立つスコアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b75f8-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="b75f8-120">このページでは、次の追加アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b75f8-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="b75f8-121">ユーザー アカウントを侵害済みとしてマークする</span><span class="sxs-lookup"><span data-stu-id="b75f8-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="b75f8-122">ユーザーにもう一度サインインを要求する</span><span class="sxs-lookup"><span data-stu-id="b75f8-122">Require the user to sign in again</span></span>
- <span data-ttu-id="b75f8-123">ユーザー アカウントを中断する</span><span class="sxs-lookup"><span data-stu-id="b75f8-123">Suspend the user account</span></span>
- <span data-ttu-id="b75f8-124">Azure Active Directory (Azure AD) ユーザー アカウントの設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b75f8-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="b75f8-125">ユーザー アカウントが所有するファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="b75f8-125">View the files owned by the user account</span></span>
- <span data-ttu-id="b75f8-126">このユーザーと共有されているファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="b75f8-126">View files shared with this user.</span></span> 

<span data-ttu-id="b75f8-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b75f8-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 セキュリティ センターのインシデントに対するユーザー アカウントでのアクションの例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="b75f8-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b75f8-129">Related topics</span></span>

- [<span data-ttu-id="b75f8-130">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="b75f8-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b75f8-131">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="b75f8-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="b75f8-132">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="b75f8-132">Manage incidents</span></span>](manage-incidents.md)