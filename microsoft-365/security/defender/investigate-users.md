---
title: Microsoft 365 Defender でユーザーを調査する
description: Microsoft 365 セキュリティ センターでのインシデントのユーザーを調査します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティセンター, モニター, レポート, ID, データ, デバイス, アプリ, インシデント, 分析, 応答
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572803"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="907cf-104">Microsoft 365 Defender でユーザーを調査する</span><span class="sxs-lookup"><span data-stu-id="907cf-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="907cf-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="907cf-105">**Applies to:**</span></span>

- <span data-ttu-id="907cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="907cf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="907cf-107">インシデント調査の一部には、ユーザー アカウントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="907cf-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="907cf-108">& インシデントの警告>インシデント>**ユーザー**]**のインシデント** の [**ユーザー** ] タブから開始します。</span><span class="sxs-lookup"><span data-stu-id="907cf-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントのユーザー ページの例":::

<span data-ttu-id="907cf-110">インシデントのユーザー アカウントの概要を簡単に取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。</span><span class="sxs-lookup"><span data-stu-id="907cf-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="907cf-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="907cf-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウントの概要ウィンドウの例":::

> [!NOTE]
> <span data-ttu-id="907cf-113">[ユーザー] ページには、グループとAzure Active Directory (Azure AD) 組織が表示され、ユーザーに関連付けられているグループとアクセス許可を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="907cf-113">The User page shows Azure Active Directory (Azure AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="907cf-114">このフライアウト ページでは、現在のインシデント、アクティブなアラート、およびリスク レベル、ユーザーの露出、アカウント、デバイスなど、ユーザーの脅威情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="907cf-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="907cf-115">さらに、侵害されたユーザーに対処するために、Microsoft 365 セキュリティ センターで直接アクションを実行したり、ユーザーが侵害されたことを確認したり、再度サインインを要求したりできます。</span><span class="sxs-lookup"><span data-stu-id="907cf-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="907cf-116">ここから[ **ユーザー ページへ移動** ]を選択すると、ユーザー アカウントの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="907cf-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="907cf-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="907cf-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウント ページの例":::

<span data-ttu-id="907cf-119">このページは、[ユーザー] ページの一覧からユーザー アカウントの名前を **選択** して表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="907cf-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="907cf-120">Microsoft 365 セキュリティ センターのユーザー ページは、エンドポイントの Microsoft Defender、Id 用 Microsoft Defender、およびMicrosoft Cloud App Security (お持ちのライセンスに応じて) からの情報を組み合わせています。</span><span class="sxs-lookup"><span data-stu-id="907cf-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="907cf-121">このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="907cf-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="907cf-122">これには、リスクと、ユーザーの全体的なリスクに寄与した最近のイベントとアラートを評価するのに役立つスコアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="907cf-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="907cf-123">このページから、次の追加アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="907cf-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="907cf-124">ユーザー アカウントを侵害済みとしてマークする</span><span class="sxs-lookup"><span data-stu-id="907cf-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="907cf-125">ユーザーに再びサインインを要求する</span><span class="sxs-lookup"><span data-stu-id="907cf-125">Require the user to sign in again</span></span>
- <span data-ttu-id="907cf-126">ユーザー アカウントを中断する</span><span class="sxs-lookup"><span data-stu-id="907cf-126">Suspend the user account</span></span>
- <span data-ttu-id="907cf-127">Azure Active Directory (Azure AD) ユーザー アカウント設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="907cf-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="907cf-128">ユーザー アカウントが所有するファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="907cf-128">View the files owned by the user account</span></span>
- <span data-ttu-id="907cf-129">このユーザーと共有されているファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="907cf-129">View files shared with this user.</span></span> 

<span data-ttu-id="907cf-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="907cf-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 セキュリティ センターでのインシデントに対するユーザー アカウントのアクションの例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="907cf-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="907cf-132">Next steps</span></span>

<span data-ttu-id="907cf-133">インプロセス インシデントの必要に応じて、 [調査](investigate-incidents.md)を続行します。</span><span class="sxs-lookup"><span data-stu-id="907cf-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="907cf-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="907cf-134">See also</span></span>

- [<span data-ttu-id="907cf-135">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="907cf-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="907cf-136">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="907cf-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="907cf-137">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="907cf-137">Manage incidents</span></span>](manage-incidents.md)