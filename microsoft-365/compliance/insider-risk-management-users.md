---
title: Insider リスク管理ユーザー
description: Microsoft 365 での insider リスク管理のユーザーについて説明します。
keywords: Microsoft 365、insider リスク管理、リスク管理、コンプライアンス
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 322cd0aa8b72ea2c81792b36614e87d97db87d7c
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179108"
---
# <a name="insider-risk-management-users"></a><span data-ttu-id="3c713-104">Insider リスク管理ユーザー</span><span class="sxs-lookup"><span data-stu-id="3c713-104">Insider risk management users</span></span>

<span data-ttu-id="3c713-105">Insider リスク管理ユーザーは、1つ以上の insider リスク管理ポリシーに含まれている組織内の従業員です。</span><span class="sxs-lookup"><span data-stu-id="3c713-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="3c713-106">**ユーザーダッシュボード**を使用して、従業員に関するリスク情報をすばやく確認し、従業員を既存の insider リスク管理ポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3c713-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="3c713-107">Insider リスク管理ポリシーに含まれる各ユーザーには、次の情報が**ユーザーダッシュボード**に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c713-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="3c713-108">**Users**: ユーザーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="3c713-108">**Users**: The username for a user.</span></span>
- <span data-ttu-id="3c713-109">**リスクレベル**: ユーザーの現在の計算されたリスクレベル。</span><span class="sxs-lookup"><span data-stu-id="3c713-109">**Risk level**: The current calculated risk level of the user.</span></span> <span data-ttu-id="3c713-110">このスコアは24時間ごとに計算され、ユーザーに関連付けられたすべてのアクティブなアラートからアラートのリスクスコアを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c713-110">This score is calculated every 24 hours and uses the alert risk scores from all active alerts associated to the user.</span></span>
- <span data-ttu-id="3c713-111">**Active alerts**: すべてのポリシーのアクティブなアラートの数。</span><span class="sxs-lookup"><span data-stu-id="3c713-111">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="3c713-112">**確認**された違反: ユーザーの*確認ポリシー違反*として解決されたケースの数。</span><span class="sxs-lookup"><span data-stu-id="3c713-112">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="3c713-113">**ケース**: ユーザーの現在のアクティブなケース。</span><span class="sxs-lookup"><span data-stu-id="3c713-113">**Case**: The current active case for the user.</span></span>

![Insider リスク管理ユーザーダッシュボード](../media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="3c713-115">ユーザーの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="3c713-115">View user details</span></span>

<span data-ttu-id="3c713-116">ユーザーのリスクアクティビティの詳細を表示するには、ユーザー**ダッシュボード**でユーザーをダブルクリックして、ユーザーの詳細ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c713-116">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="3c713-117">詳細ウィンドウで、次の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3c713-117">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="3c713-118">[**ユーザープロファイル**] タブ</span><span class="sxs-lookup"><span data-stu-id="3c713-118">**User profile** tab</span></span>
    - <span data-ttu-id="3c713-119">[**名前と役職**]: ユーザーの名前と役職を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c713-119">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="3c713-120">**ユーザーの電子メール**: ユーザーの電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="3c713-120">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="3c713-121">**エイリアス**: ユーザーのネットワークエイリアス。</span><span class="sxs-lookup"><span data-stu-id="3c713-121">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="3c713-122">**組織または部署**: ユーザーの組織または部署。</span><span class="sxs-lookup"><span data-stu-id="3c713-122">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="3c713-123">[**ユーザーアクティビティ**] タブ</span><span class="sxs-lookup"><span data-stu-id="3c713-123">**User activity** tab</span></span>
    - <span data-ttu-id="3c713-124">[**最近のユーザーアクティビティの履歴**]: イベントと、ユーザーアクティビティのリスク指標の両方のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c713-124">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="3c713-125">トリガーイベントは、resignation 日付または従業員の最後にスケジュールされた日付の承諾の場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c713-125">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="3c713-126">リスクインジケーターとは、リスクの要素があると判断され、ユーザーが含まれるポリシーと一致するアクティビティのことです。</span><span class="sxs-lookup"><span data-stu-id="3c713-126">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="3c713-127">イベントとリスクアクティビティは、最新のアイテムが最初に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c713-127">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="3c713-128">ポリシーにユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="3c713-128">Add a user to a policy</span></span>

<span data-ttu-id="3c713-129">Insider リスク管理ポリシーにユーザーを追加するには、Microsoft 365 コンプライアンスセンターの**insider リスク管理**ソリューションの [新しいポリシーウィザード] または [**ユーザー** ] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c713-129">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="3c713-130">既存の insider リスクポリシーにユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c713-130">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="3c713-131">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**ユーザー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="3c713-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="3c713-132">ツールバーの [**ポリシーにユーザーを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c713-132">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="3c713-133">[**新しいユーザーの追加**] ダイアログで、[**ユーザー** ] フィールドにユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3c713-133">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="3c713-134">ポリシーに追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3c713-134">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="3c713-135">[**ポリシー** ] フィールドのドロップダウン矢印を選択して、構成済みの insider リスク管理ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="3c713-135">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="3c713-136">ユーザーを追加するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3c713-136">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="3c713-137">**アクティブ化のウィンドウ**スライダーコントロールを使用して、このユーザーに対してポリシーがアクティブである期間を定義します。また、このポリシーに一致する最初のアクティビティをユーザーが実行したときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="3c713-137">Use the **Activation window** slider control to define how long the policy is active for this user and is triggered when the user performs the first activity matching the policy.</span></span> <span data-ttu-id="3c713-138">監視ウィンドウの範囲は、5から30日です。</span><span class="sxs-lookup"><span data-stu-id="3c713-138">The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="3c713-139">[**追加**] を選択し、ポリシーにユーザーを追加する**ことを確認**します。</span><span class="sxs-lookup"><span data-stu-id="3c713-139">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
