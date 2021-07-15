---
title: アプリ ポリシーを管理する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アプリ ガバナンス ポリシーを管理します。
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420399"
---
# <a name="manage-app-policies"></a><span data-ttu-id="0cfad-103">アプリ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="0cfad-103">Manage app policies</span></span>

><span data-ttu-id="0cfad-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="0cfad-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0cfad-105">組織が使用している最新のアプリに対応し、新しいアプリベースの攻撃や、アプリ コンプライアンス ニーズの継続的な変更に対応するには、次の方法でアプリ ポリシーを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cfad-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="0cfad-106">新しいアプリを対象とした新しいポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0cfad-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="0cfad-107">既存のポリシーの状態を変更する (アクティブ、非アクティブ、監査モード)</span><span class="sxs-lookup"><span data-stu-id="0cfad-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="0cfad-108">既存のポリシーの条件を変更する</span><span class="sxs-lookup"><span data-stu-id="0cfad-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="0cfad-109">アラートの自動修復に関する既存のポリシーのアクションを変更する</span><span class="sxs-lookup"><span data-stu-id="0cfad-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="0cfad-110">既存のポリシーを管理するプロセスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="0cfad-111">ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-111">Edit the policy:</span></span>

  - <span data-ttu-id="0cfad-112">ポリシーの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="0cfad-113">必要に応じて、テストのために状態を **[監査モード]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="0cfad-114">生成されたアラートなど、期待される動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="0cfad-115">予期しない動作が発生する場合は、手順 1 に戻ります。</span><span class="sxs-lookup"><span data-stu-id="0cfad-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="0cfad-116">想定どおりの動作であれば、ポリシーを編集して、状態を [アクティブ] に変更します (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="0cfad-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![アプリ ポリシー ワークフローの管理](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="0cfad-118">アプリ ポリシー構成の編集</span><span class="sxs-lookup"><span data-stu-id="0cfad-118">Editing an app policy configuration</span></span>

<span data-ttu-id="0cfad-119">既存のアプリ ポリシーの構成を変更するには:</span><span class="sxs-lookup"><span data-stu-id="0cfad-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="0cfad-120">ポリシー リストでポリシーを選択し、アプリ ポリシー ウィンドウで **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="0cfad-121">リストでポリシーの縦の省略記号を選択し、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="0cfad-122">**[ポリシーの編集]** ページで、ページをステップ実行し、適切な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="0cfad-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="0cfad-123">**説明**: ポリシーの目的を理解しやすくするために、説明を変更します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="0cfad-124">**重大度**</span><span class="sxs-lookup"><span data-stu-id="0cfad-124">**Severity**</span></span>
- <span data-ttu-id="0cfad-125">**ポリシー設定**: ポリシーが適用されるアプリのセットを変更します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="0cfad-126">既存の条件を使用するか、条件を変更するかを選択することもできます</span><span class="sxs-lookup"><span data-stu-id="0cfad-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="0cfad-127">**アクション**: ポリシーによって生成されたアラートの自動修復アクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="0cfad-128">**状態**: ポリシーの状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="0cfad-129">アプリ ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="0cfad-129">Deleting an app policy</span></span>

<span data-ttu-id="0cfad-130">アプリ ポリシーを削除するには、次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="0cfad-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="0cfad-131">ポリシー リストでポリシーを選択し、アプリ ポリシー ウィンドウで **[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="0cfad-132">リストでポリシーの縦の省略記号を選択し、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="0cfad-133">アプリ ポリシーを削除する代わりに、状態を非アクティブに変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0cfad-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="0cfad-134">非アクティブになると、アラートは生成されません。</span><span class="sxs-lookup"><span data-stu-id="0cfad-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="0cfad-135">たとえば、将来のポリシーに役立つ特定の条件セットを持つアプリのアプリ ポリシーを削除するのではなく、アプリ ポリシーの名前を変更してその有用性を示し、状態を非アクティブに設定します。</span><span class="sxs-lookup"><span data-stu-id="0cfad-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="0cfad-136">後でポリシーに戻り、類似したアプリ用にポリシーを変更して、状態を監査モードまたは非アクティブに設定できます。</span><span class="sxs-lookup"><span data-stu-id="0cfad-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
