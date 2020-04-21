---
title: アクション センターに移動して、自動化された調査および修復タスクを表示および承認する
description: アクション センターを使用して、自動化された調査の詳細を表示し、保留中のアクションを承認する
keywords: アクション センター、脅威の防止、調査、アラート、保留、自動化、検出
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: c3406ebf5962d6f0ac08c1ee280bab725cf1c3bd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626960"
---
# <a name="the-action-center"></a><span data-ttu-id="41188-104">アクション センター</span><span class="sxs-lookup"><span data-stu-id="41188-104">The Action center</span></span>

<span data-ttu-id="41188-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="41188-105">**Applies to:**</span></span>
- <span data-ttu-id="41188-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="41188-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="41188-107">アクション センターを使用して、組織のデバイスおよびメールボックス全体の現在および過去の調査結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="41188-107">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="41188-108">脅威の種類および結果の verdict に応じて、[修復アクション](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)は自動的に、または組織のセキュリティ運用チームによる承認時に発生します。</span><span class="sxs-lookup"><span data-stu-id="41188-108">Depending on the type of threat and resulting verdict, [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="41188-109">すべての修復アクションは、承認待ちか既に承認済みかにかかわらず、アクションセンターに統合されます。</span><span class="sxs-lookup"><span data-stu-id="41188-109">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

![アクション センター](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="41188-111">「単一画面」エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="41188-111">A "single pane of glass" experience</span></span>

<span data-ttu-id="41188-112">アクション センターは、次のようなタスクに「単一画面」エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="41188-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="41188-113">保留中の修復アクションを承認する。</span><span class="sxs-lookup"><span data-stu-id="41188-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="41188-114">承認済みの修復アクションの監査ログを表示する。</span><span class="sxs-lookup"><span data-stu-id="41188-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="41188-115">完了した修復アクションを確認する。</span><span class="sxs-lookup"><span data-stu-id="41188-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="41188-116">アクション センターは、職場で Microsoft Threat Protection の包括的なビューを提供するため、セキュリティ運用チームはより効果的かつ効率的に運用できます。</span><span class="sxs-lookup"><span data-stu-id="41188-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft Threat Protection at work.</span></span>

## <a name="go-to-the-action-center"></a><span data-ttu-id="41188-117">アクション センターに移動する</span><span class="sxs-lookup"><span data-stu-id="41188-117">Go to the Action center</span></span>

1. <span data-ttu-id="41188-118">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="41188-118">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="41188-119">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41188-119">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="41188-120">アクションセンターに、[**保留中**] と [**履歴**] という2つのタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41188-120">In the Action center, you'll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="41188-121">[**保留中**] タブには、続行するにはセキュリティ運用チームの誰かによる確認および承認が必要な調査のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41188-121">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="41188-122">ここに表示されている保留中のアイテムを確認し、実行してください。</span><span class="sxs-lookup"><span data-stu-id="41188-122">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="41188-123">[**履歴**] タブには、過去の調査や、自動的に実行された修復アクションのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41188-123">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="41188-124">過去 1 日、1 週間、1 か月、または 6 か月のデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="41188-124">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="41188-125">表示する列のみを表示するには、[**列のカスタマイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41188-125">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="41188-126">![Microsoft Threat Protection のアクション センター](../../media/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="41188-126">![Action Center in Microsoft Threat Protection](../../media/mtp-action-center.png)</span></span>

5. <span data-ttu-id="41188-127">調査の詳細を表示するには、リストから項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="41188-127">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="41188-128">調査の詳細ビューが開きます。</span><span class="sxs-lookup"><span data-stu-id="41188-128">The investigation details view opens.</span></span><br/>![調査の詳細](../../media/mtp-air-investdetails.png)

    - <span data-ttu-id="41188-130">調査が電子メールコンテンツ (たとえば、エンティティがメールボックスなど) に関係している場合は、セキュリティ & コンプライアンスセンター ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) で調査の詳細を開きます。</span><span class="sxs-lookup"><span data-stu-id="41188-130">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="41188-131">調査にデバイスが含まれる場合は、調査の詳細がセキュリティ センター で開きます ([https://security.microsoft.com](https://security.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="41188-131">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

> [!TIP]
> <span data-ttu-id="41188-132">Microsoft の脅威保護の自動化された調査と応答機能によって何かが失敗したか、誤って検出されたと思われる場合は、お知らせください。</span><span class="sxs-lookup"><span data-stu-id="41188-132">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="41188-133">[Microsoft の脅威保護で自動調査と応答 (AIR) 機能の誤検知/ネガを報告する方法を](mtp-autoir-report-false-positives-negatives.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="41188-133">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="41188-134">アクション センター タスクに必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="41188-134">Required permissions for Action center tasks</span></span>

<span data-ttu-id="41188-135">アクション センターで保留中のアクションを承認または拒否するには、次の表に示すアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="41188-135">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="41188-136">修復アクション</span><span class="sxs-lookup"><span data-stu-id="41188-136">Remediation action</span></span> |<span data-ttu-id="41188-137">必要な役割と権限</span><span class="sxs-lookup"><span data-stu-id="41188-137">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="41188-138">Microsoft Defender ATP の修復 (デバイス)</span><span class="sxs-lookup"><span data-stu-id="41188-138">Microsoft Defender ATP remediation (devices)</span></span> |<span data-ttu-id="41188-139">Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられたセキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="41188-139">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="41188-140">--- または ---</span><span class="sxs-lookup"><span data-stu-id="41188-140">--- or ---</span></span><br/><span data-ttu-id="41188-141">Microsoft Defender ATP で割り当てられた有効な修復アクションの役割</span><span class="sxs-lookup"><span data-stu-id="41188-141">Active remediation actions role assigned in Microsoft Defender ATP</span></span> <br/> <br/> <span data-ttu-id="41188-142">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41188-142">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="41188-143">- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="41188-143">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="41188-144">- [役割ベースのアクセス制御のための役割の作成と管理 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="41188-144">- [Create and manage roles for role-based access control (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="41188-145">Office 365 ATP の修復 (Office コンテンツおよびメール)</span><span class="sxs-lookup"><span data-stu-id="41188-145">Office 365 ATP remediation (Office content and email)</span></span>  |<span data-ttu-id="41188-146">Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられたセキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="41188-146">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="41188-147">--- さらに ---</span><span class="sxs-lookup"><span data-stu-id="41188-147">--- and ---</span></span> <br/><span data-ttu-id="41188-148">セキュリティ & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に割り当てられた検索および削除の役割</span><span class="sxs-lookup"><span data-stu-id="41188-148">Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="41188-149">**重要**: セキュリティ管理者の役割がセキュリティ & コンプライアンスセンターのみに割り当てられている場合は、アクションセンターまたは Microsoft の脅威保護機能にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="41188-149">**IMPORTANT**: If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="41188-150">Azure Active Directory または Microsoft 365 管理センターでセキュリティ管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="41188-150">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="41188-151">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41188-151">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="41188-152">- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="41188-152">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="41188-153">- [セキュリティ & コンプライアンスセンターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="41188-153">- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="41188-154">Azure Active Directory でグローバル管理者の役割が割り当てられているユーザーは、アクション センターで保留中のアクションを承認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="41188-154">Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="41188-155">ただし、ベスト プラクティスとして、グローバル管理者の役割が割り当てられているユーザーの数を制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41188-155">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="41188-156">アクション センターのアクセス許可については、上記のセキュリティ管理者、有効な修復アクション、および検索と消去の役割を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41188-156">We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="41188-157">次のステップ</span><span class="sxs-lookup"><span data-stu-id="41188-157">Next steps</span></span> 

- [<span data-ttu-id="41188-158">Microsoft Threat Protection のインシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="41188-158">Learn more about incidents in Microsoft Threat Protection</span></span>](incidents-overview.md)

- [<span data-ttu-id="41188-159">自動化された調査の結果を表示する</span><span class="sxs-lookup"><span data-stu-id="41188-159">View the results of an automated investigation</span></span>](mtp-autoir-results.md)

- [<span data-ttu-id="41188-160">Microsoft Threat Protection の捜索の詳細</span><span class="sxs-lookup"><span data-stu-id="41188-160">Learn about hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)

