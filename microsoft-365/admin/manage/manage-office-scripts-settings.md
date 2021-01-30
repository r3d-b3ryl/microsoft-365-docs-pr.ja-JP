---
title: Office スクリプトの設定を管理する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 組織内のユーザーの Office設定を管理する方法について学習します。
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058425"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="49e9d-103">Office スクリプトの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="49e9d-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="49e9d-104">Officeスクリプトを使用すると、Excel on the web でスクリプトを記録、編集、および実行することにより、タスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="49e9d-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="49e9d-105">Officeスクリプトは Power Automate で動作し、ユーザーは Excel Online (Business) コネクタを使用してブック上でスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="49e9d-106">Microsoft 365 管理者は、Microsoft 365 Officeスクリプトの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="49e9d-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="49e9d-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="49e9d-107">Before you begin</span></span>

- <span data-ttu-id="49e9d-108">スクリプトのOffice管理するには、グローバル管理者である必要があります。詳細については、「管理者ロール [について」を参照してください](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="49e9d-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="49e9d-109">組織内のユーザーが、次のいずれかのプランなど、Office デスクトップ アプリへのアクセスを含む Microsoft 365 または Office 365 の商用または EDU プランの有効なライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49e9d-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="49e9d-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="49e9d-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="49e9d-111">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="49e9d-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="49e9d-112">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="49e9d-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="49e9d-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="49e9d-113">Office 365 E3</span></span>
    - <span data-ttu-id="49e9d-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="49e9d-114">Office 365 E5</span></span>
    - <span data-ttu-id="49e9d-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="49e9d-115">Office 365 A3</span></span>
    - <span data-ttu-id="49e9d-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="49e9d-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="49e9d-117">スクリプトとスクリプトOfficeの可用性を管理する</span><span class="sxs-lookup"><span data-stu-id="49e9d-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="49e9d-118">Microsoft 365 管理センターで **、[Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services]</a> タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="49e9d-119">[スクリプト **Office選択します**。</span><span class="sxs-lookup"><span data-stu-id="49e9d-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="49e9d-120">Officeスクリプトは既定でオンにされ、組織内のすべてのユーザーが機能にアクセスして使用し、スクリプトを共有できます。</span><span class="sxs-lookup"><span data-stu-id="49e9d-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="49e9d-121">組織のスクリプトOfficeオフにする場合は、[ユーザーが Excel **on the web** でタスクを自動化する] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="49e9d-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="49e9d-122">以前に組織の Office スクリプトをオフにし、再び有効にする場合は、[ユーザーが **Excel on the web** でタスクを自動化する] を選択し、この機能にアクセスして使用できるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="49e9d-123">組織内のすべてのユーザーがスクリプトにアクセスして使用Officeするには、[すべての **ユーザー]** (既定) を選択したままにします。</span><span class="sxs-lookup"><span data-stu-id="49e9d-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="49e9d-124">特定のグループのメンバーにのみ Office Scripts へのアクセスと使用を許可するには、[特定のグループ] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="49e9d-125">許可リストに追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="49e9d-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="49e9d-126">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="49e9d-127">配布グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-127">Distribution group</span></span>
        - <span data-ttu-id="49e9d-128">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-128">Security group</span></span>
        - <span data-ttu-id="49e9d-129">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="49e9d-130">さまざまな種類のグループの詳細については、「グループの比較」を [参照してください](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="49e9d-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="49e9d-131">Office スクリプトにアクセスできるユーザーが組織内の他のユーザーとスクリプトを共有するには **、[Office スクリプト** にアクセスできるユーザーが組織内の他のユーザーとスクリプトを共有する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="49e9d-132">組織外でのスクリプトの共有は許可されません。</span><span class="sxs-lookup"><span data-stu-id="49e9d-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="49e9d-133">後で組織のスクリプト共有をオフにした場合でも、ユーザーは以前に共有したスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="49e9d-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="49e9d-134">スクリプトにアクセスできるユーザーを指定Officeスクリプトを共有できます。</span><span class="sxs-lookup"><span data-stu-id="49e9d-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="49e9d-135">スクリプトへのアクセス権を持Officeスクリプトを共有するには、[すべての **ユーザー]** (既定) を選択したままにしてください。</span><span class="sxs-lookup"><span data-stu-id="49e9d-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="49e9d-136">Office Scripts にアクセスできる特定のグループのメンバーだけがスクリプトを共有するには、[特定のグループ]を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="49e9d-137">許可リストに追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="49e9d-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="49e9d-138">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="49e9d-139">配布グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-139">Distribution group</span></span>
        - <span data-ttu-id="49e9d-140">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-140">Security group</span></span>
        - <span data-ttu-id="49e9d-141">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="49e9d-142">さまざまな種類のグループの詳細については、「グループの比較」を [参照してください](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="49e9d-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="49e9d-143">ユーザーが Power Automate フロー内で Office スクリプトを実行するには **、[Office スクリプト** にアクセスできるユーザーが Power Automate でスクリプトを実行する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="49e9d-144">これにより、ユーザーは Excel Online [(Business) Connector](/connectors/excelonlinebusiness)の実行スクリプト オプションを使用してフロー **ステップを追加** できます。</span><span class="sxs-lookup"><span data-stu-id="49e9d-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="49e9d-145">すべてのユーザーが Office スクリプトをフローで使用するには、[すべての **ユーザー]** (既定) を選択したままにしてください。</span><span class="sxs-lookup"><span data-stu-id="49e9d-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="49e9d-146">Office スクリプトにアクセスできる特定のグループのメンバーだけがフロー内でスクリプトを使用するには、[特定のグループ]を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="49e9d-147">許可リストに追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="49e9d-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="49e9d-148">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="49e9d-149">配布グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-149">Distribution group</span></span>
        - <span data-ttu-id="49e9d-150">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-150">Security group</span></span>
        - <span data-ttu-id="49e9d-151">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="49e9d-151">Mail-enabled security group</span></span>

        <span data-ttu-id="49e9d-152">さまざまな種類のグループの詳細については、「グループの比較」を [参照してください](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="49e9d-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="49e9d-153">データ損失防止ポリシーへの影響を含め、Power Automate で Office スクリプトを使用する方法の詳細については [、「Power Automate](/office/dev/scripts/develop/power-automate-integration)を使用して Office スクリプトを実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49e9d-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="49e9d-154">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49e9d-154">Select **Save**.</span></span>

    <span data-ttu-id="49e9d-155">スクリプト設定の変更が有効Office、最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="49e9d-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="49e9d-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="49e9d-156">Next steps</span></span>

<span data-ttu-id="49e9d-157">Office スクリプトは Power Automate と組み合わせるために、既存のデータ損失防止 (DLP) ポリシーを確認して、ユーザーが Office スクリプトを使用している間も組織のデータが保護されたままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49e9d-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="49e9d-158">詳細については、「データ損失 [防止 (DLP) ポリシー」を参照してください](/power-automate/prevent-data-loss)。</span><span class="sxs-lookup"><span data-stu-id="49e9d-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="49e9d-159">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="49e9d-159">Related content</span></span>

<span data-ttu-id="49e9d-160">[Office スクリプトの技術ドキュメント](/office/dev/scripts/) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="49e9d-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="49e9d-161">[Excel Office スクリプトの概要](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (記事)</span><span class="sxs-lookup"><span data-stu-id="49e9d-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="49e9d-162">[Excel Officeスクリプトを共有する](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (記事)</span><span class="sxs-lookup"><span data-stu-id="49e9d-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="49e9d-163">[Excel on the web でスクリプトをOffice、編集、および作成する](/office/dev/scripts/tutorials/excel-tutorial) (記事)</span><span class="sxs-lookup"><span data-stu-id="49e9d-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
