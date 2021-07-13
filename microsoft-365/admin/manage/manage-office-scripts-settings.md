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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: 組織内のユーザーのスクリプトOffice設定を管理する方法について学習します。
ms.openlocfilehash: fea50838cf1089b73a6af5bbf86d490293831085
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392673"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="3237b-103">Office スクリプトの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="3237b-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="3237b-104">[Officeスクリプトを使用](/office/dev/scripts)すると、ユーザーは Web 上でスクリプトを記録、編集、実行することでExcel自動化できます。</span><span class="sxs-lookup"><span data-stu-id="3237b-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="3237b-105">Officeスクリプトは、Power Automateと機能し、ユーザーはオンライン (Business) コネクタを使用してブックExcelスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="3237b-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="3237b-106">Microsoft 365管理者は、Officeスクリプトの設定を管理Microsoft 365 管理センター。</span><span class="sxs-lookup"><span data-stu-id="3237b-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3237b-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="3237b-107">Before you begin</span></span>

- <span data-ttu-id="3237b-108">スクリプト設定Office管理するには、グローバル管理者である必要があります。詳細については、「管理者ロール[について」を参照してください](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="3237b-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="3237b-109">組織内のユーザーが、Microsoft 365 または Office 365 の商用プランまたは EDU プランに対して有効なライセンスを持ち、Office デスクトップ アプリ (以下のいずれかのプランなど) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3237b-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="3237b-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="3237b-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="3237b-111">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="3237b-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="3237b-112">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="3237b-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="3237b-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="3237b-113">Office 365 E3</span></span>
    - <span data-ttu-id="3237b-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="3237b-114">Office 365 E5</span></span>
    - <span data-ttu-id="3237b-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="3237b-115">Office 365 A3</span></span>
    - <span data-ttu-id="3237b-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="3237b-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="3237b-117">スクリプトの可用性Officeスクリプトの共有を管理する</span><span class="sxs-lookup"><span data-stu-id="3237b-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="3237b-118">[組織のMicrosoft 365 管理センター] タブの [組織 \> **設定] タブ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="3237b-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="3237b-119">[スクリプト **Office選択します**。</span><span class="sxs-lookup"><span data-stu-id="3237b-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="3237b-120">Office既定ではスクリプトが有効になっているので、組織のすべてのユーザーが機能にアクセスして使用し、スクリプトを共有できます。</span><span class="sxs-lookup"><span data-stu-id="3237b-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="3237b-121">組織のスクリプトOfficeをオフにする場合は、[ユーザーが組織のタスクを自動化 **Excel on the webオフにします**。</span><span class="sxs-lookup"><span data-stu-id="3237b-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="3237b-122">以前に組織の Office スクリプトをオフにし、そのスクリプトを有効に戻す場合は **、[Excel on the web** でユーザーがタスクを自動化する] を選択し、この機能にアクセスして使用できるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3237b-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="3237b-123">組織内のすべてのユーザーがスクリプトにアクセスして使用Officeするには、[すべてのユーザー] **(既定**) を選択のままにします。</span><span class="sxs-lookup"><span data-stu-id="3237b-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="3237b-124">特定のグループのメンバーだけが Office スクリプトにアクセスして使用するには、[特定のグループ] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="3237b-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="3237b-125">許可リストに追加できるグループは 1 つのみであり、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3237b-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="3237b-126">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="3237b-127">配布グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-127">Distribution group</span></span>
        - <span data-ttu-id="3237b-128">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-128">Security group</span></span>
        - <span data-ttu-id="3237b-129">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="3237b-130">さまざまな種類のグループの詳細については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="3237b-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="3237b-131">Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有するには **、[Office スクリプト** にアクセスできるユーザーが組織内の他のユーザーとスクリプトを共有する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3237b-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="3237b-132">組織外でのスクリプトの共有は許可されません。</span><span class="sxs-lookup"><span data-stu-id="3237b-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="3237b-133">後で組織のスクリプト共有をオフにした場合でも、ユーザーは以前に共有したスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3237b-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="3237b-134">スクリプトでスクリプトを共有できるユーザー Officeを指定します。</span><span class="sxs-lookup"><span data-stu-id="3237b-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="3237b-135">スクリプトへのアクセス権を持つすべてのOfficeスクリプトを共有するには、[すべての **ユーザー]** (既定) を選択のままにします。</span><span class="sxs-lookup"><span data-stu-id="3237b-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="3237b-136">Office スクリプトへのアクセス権を持つ特定のグループのメンバーだけがスクリプトを共有するには、[特定のグループ] を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="3237b-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="3237b-137">許可リストに追加できるグループは 1 つのみであり、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3237b-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="3237b-138">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="3237b-139">配布グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-139">Distribution group</span></span>
        - <span data-ttu-id="3237b-140">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-140">Security group</span></span>
        - <span data-ttu-id="3237b-141">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="3237b-142">さまざまな種類のグループの詳細については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="3237b-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="3237b-143">ユーザーが Power Automate フロー内で Office スクリプトを実行するには、[Office スクリプトへのアクセス権を持つユーザーにスクリプトを実行 **Power Automate。**</span><span class="sxs-lookup"><span data-stu-id="3237b-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="3237b-144">これにより、ユーザーは[オンライン] ([ビジネス) コネクタExcel実行](/connectors/excelonlinebusiness)スクリプト オプションを使用してフロー ステップ **を追加** できます。</span><span class="sxs-lookup"><span data-stu-id="3237b-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="3237b-145">スクリプトにアクセスできるすべてのユーザー Officeフローでスクリプトを使用するには、[すべての **ユーザー]** (既定) を選択したままにしてください。</span><span class="sxs-lookup"><span data-stu-id="3237b-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="3237b-146">Office スクリプトにアクセスできる特定のグループのメンバーだけがフローでスクリプトを使用するには、[特定のグループ]を選択し、グループの名前または電子メール エイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="3237b-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="3237b-147">許可リストに追加できるグループは 1 つのみであり、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3237b-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="3237b-148">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="3237b-149">配布グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-149">Distribution group</span></span>
        - <span data-ttu-id="3237b-150">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-150">Security group</span></span>
        - <span data-ttu-id="3237b-151">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="3237b-151">Mail-enabled security group</span></span>

        <span data-ttu-id="3237b-152">さまざまな種類のグループの詳細については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="3237b-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="3237b-153">スクリプトを使用してスクリプトを使用Office詳細Power Automate、「スクリプトを使用してスクリプトOffice[実行する」を参照Power Automate。](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="3237b-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="3237b-154">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3237b-154">Select **Save**.</span></span>

    <span data-ttu-id="3237b-155">Office スクリプトの設定の変更が有効になるまで、最大で 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3237b-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3237b-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="3237b-156">Next steps</span></span>

<span data-ttu-id="3237b-157">Office スクリプトは Power Automate で動作しますので、ユーザーが Office スクリプトを使用している間に組織のデータが保護されたままになるために、既存のデータ損失防止 (DLP) ポリシーを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3237b-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="3237b-158">詳細については、「[データ損失防止 (DLP) ポリシー](/power-automate/prevent-data-loss)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3237b-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="3237b-159">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="3237b-159">Related content</span></span>

<span data-ttu-id="3237b-160">[Officeスクリプトの技術ドキュメント](/office/dev/scripts/)(リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="3237b-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="3237b-161">[[スクリプトOfficeの概要 (](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a)記事Excel)</span><span class="sxs-lookup"><span data-stu-id="3237b-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="3237b-162">[Web OfficeスクリプトExcel共有](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)する (記事)</span><span class="sxs-lookup"><span data-stu-id="3237b-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="3237b-163">[スクリプトを記録、編集、およびOfficeする (Excel on the web)](/office/dev/scripts/tutorials/excel-tutorial)</span><span class="sxs-lookup"><span data-stu-id="3237b-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
