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
ms.openlocfilehash: 2fd9b958cdbdaf22346f8171c789f2ca9a8336d1
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957609"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="051dc-104">Microsoft 365 セキュリティ センターでユーザーを分析する</span><span class="sxs-lookup"><span data-stu-id="051dc-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="051dc-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="051dc-105">**Applies to:**</span></span>

- <span data-ttu-id="051dc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="051dc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="051dc-107">インシデント分析の一部には、ユーザー アカウントを含めできます。</span><span class="sxs-lookup"><span data-stu-id="051dc-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="051dc-108">[インシデント]**からインシデント** の [ユーザー] タブから開始し、&**ユーザー** >\*通知>\***します**。</span><span class="sxs-lookup"><span data-stu-id="051dc-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例":::

<span data-ttu-id="051dc-110">インシデントのユーザー アカウントの概要を簡単に取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。</span><span class="sxs-lookup"><span data-stu-id="051dc-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="051dc-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="051dc-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウント概要ウィンドウの例":::

> [!NOTE]
> <span data-ttu-id="051dc-113">[ユーザー] ページには、Azure Active Directory (AD) 組織とグループが表示され、ユーザーに関連付けられているグループとアクセス許可を理解できます。</span><span class="sxs-lookup"><span data-stu-id="051dc-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="051dc-114">このフライアウト ページでは、現在のインシデント、アクティブなアラート、リスク レベル、ユーザーの露出、アカウント、デバイスなど、ユーザーの脅威情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="051dc-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="051dc-115">さらに、Microsoft 365 セキュリティ センターで直接アクションを実行して、侵害されたユーザーに対処し、ユーザーが侵害されたか、再度サインインする必要が生じか確認できます。</span><span class="sxs-lookup"><span data-stu-id="051dc-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="051dc-116">ここから、[ユーザー に移動] **ページを選択して** 、ユーザー アカウントの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="051dc-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="051dc-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="051dc-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウント ページの例":::

<span data-ttu-id="051dc-119">[ユーザー] ページの一覧からユーザー アカウントの名前を選択すると、このページを **確認** することもできます。</span><span class="sxs-lookup"><span data-stu-id="051dc-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="051dc-120">Microsoft 365 セキュリティ センターのユーザー ページでは、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Cloud App Security の情報を組み合わせたもの (ライセンスに応じて異なる)。</span><span class="sxs-lookup"><span data-stu-id="051dc-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="051dc-121">このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="051dc-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="051dc-122">これには、ユーザーの全体的なリスクに寄与したリスクと最近のイベントやアラートを評価するのに役立つスコアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="051dc-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="051dc-123">このページでは、次の追加アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="051dc-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="051dc-124">ユーザー アカウントを侵害済みとしてマークする</span><span class="sxs-lookup"><span data-stu-id="051dc-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="051dc-125">ユーザーにもう一度サインインを要求する</span><span class="sxs-lookup"><span data-stu-id="051dc-125">Require the user to sign in again</span></span>
- <span data-ttu-id="051dc-126">ユーザー アカウントを中断する</span><span class="sxs-lookup"><span data-stu-id="051dc-126">Suspend the user account</span></span>
- <span data-ttu-id="051dc-127">Azure Active Directory (Azure AD) ユーザー アカウントの設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="051dc-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="051dc-128">ユーザー アカウントが所有するファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="051dc-128">View the files owned by the user account</span></span>
- <span data-ttu-id="051dc-129">このユーザーと共有されているファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="051dc-129">View files shared with this user.</span></span> 

<span data-ttu-id="051dc-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="051dc-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 セキュリティ センターのインシデントに対するユーザー アカウントでのアクションの例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="051dc-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="051dc-132">Related topics</span></span>

- [<span data-ttu-id="051dc-133">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="051dc-133">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="051dc-134">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="051dc-134">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="051dc-135">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="051dc-135">Manage incidents</span></span>](manage-incidents.md)