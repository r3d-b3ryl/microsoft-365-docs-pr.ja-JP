---
title: Insider リスク管理ユーザー (プレビュー)
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
ms.openlocfilehash: a9ff7e38a99a5fe5bd8da5301bec5e19bc015cf3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072791"
---
# <a name="insider-risk-management-users-preview"></a><span data-ttu-id="2cc11-104">Insider リスク管理ユーザー (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2cc11-104">Insider risk management users (preview)</span></span>

<span data-ttu-id="2cc11-105">Insider リスク管理ユーザーは、1つ以上の insider リスク管理ポリシーに含まれている組織内の従業員です。</span><span class="sxs-lookup"><span data-stu-id="2cc11-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="2cc11-106">**ユーザーダッシュボード**を使用して、従業員に関するリスク情報をすばやく確認し、従業員を既存の insider リスク管理ポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="2cc11-107">Insider リスク管理ポリシーに含まれる各ユーザーには、次の情報が**ユーザーダッシュボード**に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cc11-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="2cc11-108">**Users**: ユーザーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="2cc11-108">**Users**: The user name for a user.</span></span>
- <span data-ttu-id="2cc11-109">**リスクレベル**:</span><span class="sxs-lookup"><span data-stu-id="2cc11-109">**Risk level**:</span></span> 
- <span data-ttu-id="2cc11-110">**Active alerts**: すべてのポリシーのアクティブなアラートの数。</span><span class="sxs-lookup"><span data-stu-id="2cc11-110">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="2cc11-111">**確認**された違反: ユーザーの*確認ポリシー違反*として解決されたケースの数。</span><span class="sxs-lookup"><span data-stu-id="2cc11-111">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="2cc11-112">**ケース**: ユーザーの現在のアクティブなケース。</span><span class="sxs-lookup"><span data-stu-id="2cc11-112">**Case**: The current active case for the user.</span></span>

![Insider リスク管理ユーザーダッシュボード](../media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="2cc11-114">ユーザーの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="2cc11-114">View user details</span></span>

<span data-ttu-id="2cc11-115">ユーザーのリスクアクティビティの詳細を表示するには、ユーザー**ダッシュボード**でユーザーをダブルクリックして、ユーザーの詳細ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="2cc11-115">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="2cc11-116">詳細ウィンドウで、次の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2cc11-116">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="2cc11-117">[**ユーザープロファイル**] タブ</span><span class="sxs-lookup"><span data-stu-id="2cc11-117">**User profile** tab</span></span>
    - <span data-ttu-id="2cc11-118">[**名前と役職**]: ユーザーの名前と役職を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-118">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="2cc11-119">**ユーザーの電子メール**: ユーザーの電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="2cc11-119">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="2cc11-120">**エイリアス**: ユーザーのネットワークエイリアス。</span><span class="sxs-lookup"><span data-stu-id="2cc11-120">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="2cc11-121">**組織または部署**: ユーザーの組織または部署。</span><span class="sxs-lookup"><span data-stu-id="2cc11-121">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="2cc11-122">[**ユーザーアクティビティ**] タブ</span><span class="sxs-lookup"><span data-stu-id="2cc11-122">**User activity** tab</span></span>
    - <span data-ttu-id="2cc11-123">[**最近のユーザーアクティビティの履歴**]: イベントと、ユーザーアクティビティのリスク指標の両方のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cc11-123">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="2cc11-124">トリガーイベントは、resignation 日付または従業員の最後にスケジュールされた日付の承諾の場合があります。</span><span class="sxs-lookup"><span data-stu-id="2cc11-124">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="2cc11-125">リスクインジケーターとは、リスクの要素があると判断され、ユーザーが含まれるポリシーと一致するアクティビティのことです。</span><span class="sxs-lookup"><span data-stu-id="2cc11-125">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="2cc11-126">イベントとリスクアクティビティは、最新のアイテムが最初に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cc11-126">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="2cc11-127">ポリシーにユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="2cc11-127">Add a user to a policy</span></span>

<span data-ttu-id="2cc11-128">Insider リスク管理ポリシーにユーザーを追加するには、Microsoft 365 コンプライアンスセンターの**insider リスク管理**ソリューションの [新しいポリシーウィザード] または [**ユーザー** ] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-128">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="2cc11-129">既存の insider リスクポリシーにユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-129">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="2cc11-130">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**ユーザー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-130">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="2cc11-131">ツールバーの [**ポリシーにユーザーを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-131">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="2cc11-132">[**新しいユーザーの追加**] ダイアログで、[**ユーザー** ] フィールドにユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-132">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="2cc11-133">ポリシーに追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-133">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="2cc11-134">[**ポリシー** ] フィールドのドロップダウン矢印を選択して、構成済みの insider リスク管理ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-134">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="2cc11-135">ユーザーを追加するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-135">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="2cc11-136">[**監視] ウィンドウ**スライダーコントロールを使用して、......監視ウィンドウの範囲は、5から30日です。</span><span class="sxs-lookup"><span data-stu-id="2cc11-136">Use the **Monitoring window** slider control to define the...... The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="2cc11-137">[**追加**] を選択し、ポリシーにユーザーを追加する**ことを確認**します。</span><span class="sxs-lookup"><span data-stu-id="2cc11-137">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
