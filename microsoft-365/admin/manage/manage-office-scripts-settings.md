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
description: 組織内のユーザーのOfficeスクリプト設定を管理する方法について説明します。
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572311"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="8aa5c-103">Office スクリプトの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="8aa5c-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="8aa5c-104">[Officeスクリプト](/office/dev/scripts)を使用すると、ユーザーは Web 上のExcelでスクリプトを記録、編集、実行することでタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="8aa5c-105">OfficeスクリプトはPower Automateと連携し、ユーザーはオンライン (ビジネス) コネクタを使用してワークブックでスクリプトを実行Excel。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="8aa5c-106">Microsoft 365管理者は、Microsoft 365管理センターからOfficeスクリプト設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8aa5c-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="8aa5c-107">Before you begin</span></span>

- <span data-ttu-id="8aa5c-108">Officeスクリプト設定を管理するには、グローバル管理者である必要があります。詳細については、「[管理者ロールについて](../add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="8aa5c-109">組織内のユーザーが、次のいずれかのプランなど、Office デスクトップ アプリへのアクセスを含む、Microsoft 365またはOffice 365の商用または EDU プランの有効なライセンスを持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="8aa5c-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="8aa5c-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="8aa5c-111">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="8aa5c-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="8aa5c-112">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="8aa5c-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="8aa5c-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="8aa5c-113">Office 365 E3</span></span>
    - <span data-ttu-id="8aa5c-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="8aa5c-114">Office 365 E5</span></span>
    - <span data-ttu-id="8aa5c-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="8aa5c-115">Office 365 A3</span></span>
    - <span data-ttu-id="8aa5c-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="8aa5c-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="8aa5c-117">Officeスクリプトの可用性とスクリプトの共有を管理する</span><span class="sxs-lookup"><span data-stu-id="8aa5c-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="8aa5c-118">Microsoft 365管理センターで、[組織設定のサービス **] タブ設定** \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a>します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="8aa5c-119">[**スクリプトOffice] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="8aa5c-120">Officeスクリプトは既定で有効になっており、組織内の全員が機能にアクセスして使用したり、スクリプトを共有したりできます。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="8aa5c-121">組織のOfficeスクリプトをオフにするには、[**ユーザーがExcel on the webでタスクを自動化できるようにする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="8aa5c-122">以前に組織のスクリプトOfficeをオフにして、それをオンに戻す場合は、[**ユーザーがExcel on the webでタスクを自動化できるようにする**] をオンにし、その機能にアクセスして使用できるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="8aa5c-123">組織内のすべてのユーザーが Officeスクリプトにアクセスして使用できるようにするには、[**すべてのユーザー** ](既定値)を選択したままにします。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="8aa5c-124">特定のグループのメンバーのみがOfficeスクリプトにアクセスして使用できるようにするには、[特定の **グループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="8aa5c-125">許可一覧に追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="8aa5c-126">Microsoft 365グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="8aa5c-127">配送グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-127">Distribution group</span></span>
        - <span data-ttu-id="8aa5c-128">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-128">Security group</span></span>
        - <span data-ttu-id="8aa5c-129">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="8aa5c-130">さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="8aa5c-131">Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有できるようにするには **、[Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有できるようにする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="8aa5c-132">組織外でのスクリプトの共有は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="8aa5c-133">後で組織のスクリプト共有を無効にしても、ユーザーは以前に共有されたスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="8aa5c-134">スクリプトを共有できるOfficeスクリプトにアクセスできるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="8aa5c-135">Officeスクリプトへのアクセス権を持つすべてのユーザーがスクリプトを共有できるようにするには、[**すべてのユーザー** ](デフォルト)を選択したままにします。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="8aa5c-136">Officeスクリプトへのアクセス権を持つ特定のグループのメンバーのみがスクリプトを共有できるようにするには、[**特定のグループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="8aa5c-137">許可一覧に追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="8aa5c-138">Microsoft 365グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="8aa5c-139">配送グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-139">Distribution group</span></span>
        - <span data-ttu-id="8aa5c-140">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-140">Security group</span></span>
        - <span data-ttu-id="8aa5c-141">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="8aa5c-142">さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="8aa5c-143">ユーザーがPower Automateフロー内でOfficeスクリプトを実行できるようにするには **、[OfficeスクリプトにアクセスできるユーザーがPower Automateでスクリプトを実行できるようにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="8aa5c-144">これにより、ユーザーは [、オンライン (ビジネス) コネクタ](/connectors/excelonlinebusiness)の **スクリプトの実行** オプションExcelを使用してフロー ステップを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="8aa5c-145">Officeスクリプトへのアクセス権を持つすべてのユーザーがフローでスクリプトを使用できるようにするには **、Everyone** (デフォルト) を選択したままにします。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="8aa5c-146">Officeスクリプトへのアクセス権を持つ特定のグループのメンバーのみがフローでスクリプトを使用できるようにするには、[**特定のグループ**] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="8aa5c-147">許可一覧に追加できるグループは 1 つだけで、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="8aa5c-148">Microsoft 365グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="8aa5c-149">配送グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-149">Distribution group</span></span>
        - <span data-ttu-id="8aa5c-150">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-150">Security group</span></span>
        - <span data-ttu-id="8aa5c-151">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-151">Mail-enabled security group</span></span>

        <span data-ttu-id="8aa5c-152">さまざまな種類のグループの詳細については、「グループの [比較](../create-groups/compare-groups.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="8aa5c-153">Power AutomateでOfficeスクリプトを使用する方法の詳細については[、「Power AutomateでOfficeスクリプトを実行](/office/dev/scripts/develop/power-automate-integration)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="8aa5c-154">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-154">Select **Save**.</span></span>

    <span data-ttu-id="8aa5c-155">Officeスクリプトの設定の変更が有効になるためには、最大 48 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8aa5c-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="8aa5c-156">Next steps</span></span>

<span data-ttu-id="8aa5c-157">OfficeスクリプトはPower Automateと連携するため、既存のデータ損失防止 (DLP) ポリシーを確認して、ユーザーがOffice スクリプトを使用している間も組織のデータが保護されたままであることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="8aa5c-158">詳細については、「 [データ損失防止 (DLP) ポリシー](/power-automate/prevent-data-loss)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aa5c-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="8aa5c-159">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="8aa5c-159">Related content</span></span>

<span data-ttu-id="8aa5c-160">[Office スクリプトのテクニカル ドキュメント](/office/dev/scripts/)(リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="8aa5c-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="8aa5c-161">[ExcelのOfficeスクリプトの概要](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a)(記事)</span><span class="sxs-lookup"><span data-stu-id="8aa5c-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="8aa5c-162">[Web 用ExcelでOfficeスクリプトを共有](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)する (記事)</span><span class="sxs-lookup"><span data-stu-id="8aa5c-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="8aa5c-163">[Excel on the webでOfficeスクリプトを記録、編集、作成](/office/dev/scripts/tutorials/excel-tutorial)する (記事)</span><span class="sxs-lookup"><span data-stu-id="8aa5c-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
