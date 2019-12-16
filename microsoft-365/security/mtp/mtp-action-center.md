---
title: アクション センターに移動して、自動化された調査および修復タスクを表示および承認する
description: アクション センターを使用して、自動化された調査の詳細を表示し、保留中のアクションを承認する
keywords: アクション センター、脅威の防止、調査、アラート、保留、自動化、検出
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 950dec4c0b0a2de2bdc60a73a12f6c7895189ea4
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911385"
---
# <a name="go-to-the-action-center-to-view-remediation-actions"></a><span data-ttu-id="5a994-104">アクション センターに移動して修復アクションを表示する</span><span class="sxs-lookup"><span data-stu-id="5a994-104">Go to the Action center to view remediation actions</span></span>

<span data-ttu-id="5a994-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5a994-105">**Applies to:**</span></span>
- <span data-ttu-id="5a994-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5a994-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="5a994-107">「単一画面」エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="5a994-107">A "single pane of glass" experience</span></span>

![アクション センター](../images/air-actioncenter.png)

<span data-ttu-id="5a994-109">アクション センターを使用して、組織のデバイスおよびメールボックス全体の現在および過去の調査結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a994-109">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="5a994-110">脅威の種類および[出された判定](mtp-autoir-results.md#remediation-actions-following-automated-investigation)に応じて、修復アクションが自動的に、または組織のセキュリティ運用チームの承認を受けて実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a994-110">Depending on the type of threat and [resulting verdict](mtp-autoir-results.md#remediation-actions-following-automated-investigation), remediation actions occur automatically or upon approval by your organization’s security operations team.</span></span> <span data-ttu-id="5a994-111">すべての修復アクションは、承認待ちか既に承認済みかにかかわらず、アクションセンターに統合されます。</span><span class="sxs-lookup"><span data-stu-id="5a994-111">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

<span data-ttu-id="5a994-112">アクション センターは、次のようなタスクに「単一画面」エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a994-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="5a994-113">保留中の修復アクションを承認する。</span><span class="sxs-lookup"><span data-stu-id="5a994-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="5a994-114">承認済みの修復アクションの監査ログを表示する。</span><span class="sxs-lookup"><span data-stu-id="5a994-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="5a994-115">完了した修復アクションを確認する。</span><span class="sxs-lookup"><span data-stu-id="5a994-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="5a994-116">アクション センターは、職場で Microsoft Threat Protection の包括的なビューを提供するため、セキュリティ運用チームはより効果的かつ効率的に運用できます。</span><span class="sxs-lookup"><span data-stu-id="5a994-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft Threat Protection at work.</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="5a994-117">修復アクション</span><span class="sxs-lookup"><span data-stu-id="5a994-117">Remediation actions</span></span>

<span data-ttu-id="5a994-118">次の表に、現在アクション センターでサポートされている修復アクションを示します。</span><span class="sxs-lookup"><span data-stu-id="5a994-118">The following table lists remediation actions that are currently supported in the Action center:</span></span> 

|<span data-ttu-id="5a994-119">エンドポイントの修復アクション</span><span class="sxs-lookup"><span data-stu-id="5a994-119">Endpoints remediation actions</span></span>  |<span data-ttu-id="5a994-120">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="5a994-120">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="5a994-121">ファイルの検疫</span><span class="sxs-lookup"><span data-stu-id="5a994-121">Quarantine file</span></span><br/><span data-ttu-id="5a994-122">レジストリ キーの削除</span><span class="sxs-lookup"><span data-stu-id="5a994-122">Remove registry key</span></span><br/><span data-ttu-id="5a994-123">プロセスの強制終了</span><span class="sxs-lookup"><span data-stu-id="5a994-123">Kill process</span></span> <br/><span data-ttu-id="5a994-124">サービスの停止</span><span class="sxs-lookup"><span data-stu-id="5a994-124">Stop the service application</span></span> <br/><span data-ttu-id="5a994-125">レジストリ キーの削除</span><span class="sxs-lookup"><span data-stu-id="5a994-125">Remove registry key</span></span> <br/><span data-ttu-id="5a994-126">ドライバーの無効化</span><span class="sxs-lookup"><span data-stu-id="5a994-126">Disable driver</span></span> <br/><span data-ttu-id="5a994-127">スケジュールされたタスクの実行</span><span class="sxs-lookup"><span data-stu-id="5a994-127">Remove scheduled task</span></span>      |<span data-ttu-id="5a994-128">メール メッセージまたはクラスターの論理的な削除</span><span class="sxs-lookup"><span data-stu-id="5a994-128">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="5a994-129">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="5a994-129">Block URL (time-of-click)</span></span><br/><span data-ttu-id="5a994-130">外部メール転送の無効化</span><span class="sxs-lookup"><span data-stu-id="5a994-130">Turn off external mail forwarding</span></span>          |

## <a name="go-to-the-action-center"></a><span data-ttu-id="5a994-131">アクション センターに移動する</span><span class="sxs-lookup"><span data-stu-id="5a994-131">Go to the admin center.</span></span>

1. <span data-ttu-id="5a994-132">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="5a994-132">Go to https://security.microsoft.com and sign in.</span></span> 

2. <span data-ttu-id="5a994-133">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a994-133">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="5a994-134">[アクション センター] には、[**保留中**] と [**履歴**] の 2 つのタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a994-134">In the Action center, you’ll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="5a994-135">[**保留中**] タブには、続行するにはセキュリティ運用チームの誰かによる確認および承認が必要な調査のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a994-135">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="5a994-136">ここに表示されている保留中のアイテムを確認し、実行してください。</span><span class="sxs-lookup"><span data-stu-id="5a994-136">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="5a994-137">[**履歴**] タブには、過去の調査や、自動的に実行された修復アクションのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a994-137">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="5a994-138">過去 1 日、1 週間、1 か月、または 6 か月のデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5a994-138">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="5a994-139">表示する列のみを表示するには、[**列のカスタマイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a994-139">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="5a994-140">![Microsoft Threat Protection のアクション センター](../images/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="5a994-140">![Action Center in Microsoft Threat Protection](../images/mtp-action-center.png)</span></span>

5. <span data-ttu-id="5a994-141">調査の詳細を表示するには、リストから項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a994-141">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="5a994-142">調査の詳細ビューが開きます。</span><span class="sxs-lookup"><span data-stu-id="5a994-142">The investigation details view opens.</span></span><br/>![調査の詳細](../images/mtp-air-investdetails.png)

    - <span data-ttu-id="5a994-144">調査がメール コンテンツ (エンティティがメールボックスなど) に関連する場合は、調査の詳細は Office 365 セキュリティ/コンプライアンス センター に表示されます ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation))。</span><span class="sxs-lookup"><span data-stu-id="5a994-144">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Office 365 Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="5a994-145">調査にデバイスが含まれる場合は、調査の詳細がセキュリティ センター で開きます ([https://security.microsoft.com](https://security.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="5a994-145">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="5a994-146">アクション センター タスクに必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5a994-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="5a994-147">アクション センターで保留中のアクションを承認または拒否するには、次の表に示すアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a994-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="5a994-148">修復アクション</span><span class="sxs-lookup"><span data-stu-id="5a994-148">Remediation action</span></span> |<span data-ttu-id="5a994-149">必要な役割と権限</span><span class="sxs-lookup"><span data-stu-id="5a994-149">Required licenses and permissions</span></span> |
|--|----|
|<span data-ttu-id="5a994-150">Microsoft Defender ATP の修復 (デバイス)</span><span class="sxs-lookup"><span data-stu-id="5a994-150">Microsoft Defender ATP remediation (devices)</span></span> |<span data-ttu-id="5a994-151">Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられた**セキュリティ管理者**の役割</span><span class="sxs-lookup"><span data-stu-id="5a994-151">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="5a994-152">--- または ---</span><span class="sxs-lookup"><span data-stu-id="5a994-152">() or []</span></span><br/><span data-ttu-id="5a994-153">Microsoft Defender ATP で割り当てられた**有効な修復アクション**の役割</span><span class="sxs-lookup"><span data-stu-id="5a994-153">**Active remediation actions** role assigned in Microsoft Defender ATP</span></span> <br/> <br/> <span data-ttu-id="5a994-154">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a994-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="5a994-155">- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="5a994-155">Administrator role permissions in Azure Active Directory</span></span><br/><span data-ttu-id="5a994-156">- [役割ベースのアクセス制御のための役割の作成と管理 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="5a994-156">- [Create and manage roles for role-based access control (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="5a994-157">Office 365 ATP の修復 (Office コンテンツおよびメール)</span><span class="sxs-lookup"><span data-stu-id="5a994-157">Office 365 ATP remediation (Office content and email)</span></span>  |<span data-ttu-id="5a994-158">Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられた**セキュリティ管理者**の役割</span><span class="sxs-lookup"><span data-stu-id="5a994-158">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="5a994-159">--- さらに ---</span><span class="sxs-lookup"><span data-stu-id="5a994-159">( and )</span></span> <br/><span data-ttu-id="5a994-160">Office 365 セキュリティ/コンプライアンス センターに割り当てられた**検索と消去**の役割 [https://protection.office.com](https://protection.office.com))</span><span class="sxs-lookup"><span data-stu-id="5a994-160">Search and Purge (this is assigned only in the Office 365 Security & Compliance Center)</span></span> <br/><br/><span data-ttu-id="5a994-161">**重要**: Office 365 セキュリティ/コンプライアンス センターにのみセキュリティ管理者の役割が割り当てられている場合は、アクション センターまたは Microsoft Threat Protection の機能にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5a994-161">**IMPORTANT**: If you have the Security Administrator role assigned only in the Office 365 Security & Compliance Center, you will not be able to access the Action center or Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="5a994-162">Azure Active Directory または Microsoft 365 管理センターでセキュリティ管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a994-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="5a994-163">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a994-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="5a994-164">- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="5a994-164">Administrator role permissions in Azure Active Directory</span></span><br/><span data-ttu-id="5a994-165">- [Office 365 セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="5a994-165">Permissions in the Office 365 Security  Compliance Center</span></span> |

> [!NOTE]
> <span data-ttu-id="5a994-166">Azure Active Directory で**グローバル管理者**の役割が割り当てられているユーザーは、アクション センターで保留中のアクションを承認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="5a994-166">Users who have the **Global Administrator** role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="5a994-167">ただし、ベスト プラクティスとして、グローバル管理者の役割が割り当てられているユーザーの数を制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a994-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="5a994-168">アクション センターのアクセス許可については、上記の**セキュリティ管理者**、**有効な修復アクション**、および**検索と消去**の役割を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a994-168">We recommend using the **Security Administrator**, **Active remediation actions**, and **Search and Purge** roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a994-169">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5a994-169">Next steps</span></span> 

- [<span data-ttu-id="5a994-170">Microsoft Threat Protection のインシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="5a994-170">Learn more about incidents in Microsoft Threat Protection</span></span>](incidents-overview.md)
- [<span data-ttu-id="5a994-171">自動化された調査の結果を表示する</span><span class="sxs-lookup"><span data-stu-id="5a994-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="5a994-172">Microsoft Threat Protection の捜索の詳細</span><span class="sxs-lookup"><span data-stu-id="5a994-172">Learn about hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)

