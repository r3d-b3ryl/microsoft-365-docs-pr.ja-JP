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
description: 組織内のユーザーの Office スクリプト設定を管理する方法について説明します。
ms.openlocfilehash: 44e2a5c0e0577db344fdbb00a110674df3e71bdc
ms.sourcegitcommit: 04f196528a7a91b404478553433af3fa94d7eee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "47317495"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="5fae5-103">Office スクリプトの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="5fae5-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="5fae5-104">Office スクリプトを使用すると、ユーザーは web 上の Excel でスクリプトを記録、編集、および実行することによってタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="5fae5-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="5fae5-105">Office スクリプトは電源自動化と共に動作し、ユーザーは Excel Online (Business) コネクタを使用してブックのスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="5fae5-106">Microsoft 365 管理者は、Microsoft 365 管理センターから Office スクリプトの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="5fae5-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5fae5-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="5fae5-107">Before you begin</span></span>

- <span data-ttu-id="5fae5-108">Office スクリプトの設定を管理するには、グローバル管理者である必要があります。詳細については、「 [管理者の役割につい](../add-users/about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fae5-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="5fae5-109">組織内のユーザーが、次のプランのいずれかのような Office デスクトップアプリへのアクセスを含む、Microsoft 365 または Office 365 コマーシャルまたは EDU プランの有効なライセンスを所有していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="5fae5-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="5fae5-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="5fae5-111">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="5fae5-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="5fae5-112">エンタープライズ向け Microsoft  365 アプリ</span><span class="sxs-lookup"><span data-stu-id="5fae5-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="5fae5-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="5fae5-113">Office 365 E3</span></span>
    - <span data-ttu-id="5fae5-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="5fae5-114">Office 365 E5</span></span>
    - <span data-ttu-id="5fae5-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="5fae5-115">Office 365 A3</span></span>
    - <span data-ttu-id="5fae5-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="5fae5-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="5fae5-117">Office スクリプトの可用性およびスクリプトの共有を管理する</span><span class="sxs-lookup"><span data-stu-id="5fae5-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="5fae5-118">Microsoft 365 管理センターで、[設定] [ **Settings** \> **組織設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">サービス</a>] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="5fae5-119">[ **Office スクリプト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="5fae5-120">Office スクリプトは既定で有効になっており、組織内のすべてのユーザーが機能にアクセスして使用し、スクリプトを共有できます。</span><span class="sxs-lookup"><span data-stu-id="5fae5-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="5fae5-121">組織の Office スクリプトを無効にするには、[ **ユーザーが web 上の Excel でタスクを自動化できる** ようにする] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5fae5-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="5fae5-122">以前に組織の Office スクリプトをオフにしていて、再度有効にする場合は、[ **ユーザーに web 上の Excel でのタスクの自動化を許可**する] を選択し、機能にアクセスして使用できるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="5fae5-123">組織内のすべてのユーザーが Office スクリプトにアクセスして使用できるようにするには、 **[すべてのユーザー] (既定** 値) を選択したままにします。</span><span class="sxs-lookup"><span data-stu-id="5fae5-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span> 

    - <span data-ttu-id="5fae5-124">特定のグループのメンバーのみが Office スクリプトにアクセスして使用できるようにするには、[ **特定のグループ**] を選択し、グループの名前または電子メールエイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="5fae5-125">許可リストには、グループを1つだけ追加できます。また、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fae5-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="5fae5-126">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="5fae5-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="5fae5-127">配布グループ</span><span class="sxs-lookup"><span data-stu-id="5fae5-127">Distribution group</span></span>
        - <span data-ttu-id="5fae5-128">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="5fae5-128">Security group</span></span>
        - <span data-ttu-id="5fae5-129">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="5fae5-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="5fae5-130">さまざまな種類のグループの詳細については、「 [グループを比較](../create-groups/compare-groups.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fae5-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="5fae5-131">Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有できるようにするには、[ **Office スクリプトへのアクセス権を持つユーザーが組織内の他のユーザーとスクリプトを共有**できるようにする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="5fae5-132">組織外のスクリプトの共有は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="5fae5-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="5fae5-133">後で組織のスクリプト共有を無効にした場合でも、ユーザーは以前に共有されたスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5fae5-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="5fae5-134">Office スクリプトにアクセスできるユーザーを指定して、スクリプトを共有できます。</span><span class="sxs-lookup"><span data-stu-id="5fae5-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="5fae5-135">Office スクリプトへのアクセス権を持つすべてのユーザーがスクリプトを共有できるようにするには、 **[すべてのユーザー (既定** )] を選択したままにします。</span><span class="sxs-lookup"><span data-stu-id="5fae5-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="5fae5-136">Office スクリプトへのアクセス権を持つ特定のグループのメンバーのみがスクリプトを共有できるようにするには、[ **特定のグループ**] を選択し、グループの名前または電子メールエイリアスを入力して許可リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="5fae5-137">許可リストには、グループを1つだけ追加できます。また、次のいずれかの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fae5-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="5fae5-138">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="5fae5-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="5fae5-139">配布グループ</span><span class="sxs-lookup"><span data-stu-id="5fae5-139">Distribution group</span></span>
        - <span data-ttu-id="5fae5-140">セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="5fae5-140">Security group</span></span>
        - <span data-ttu-id="5fae5-141">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="5fae5-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="5fae5-142">さまざまな種類のグループの詳細については、「 [グループを比較](../create-groups/compare-groups.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fae5-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="5fae5-143">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae5-143">Select **Save**.</span></span>

    <span data-ttu-id="5fae5-144">Office スクリプトの設定の変更が有効になるまで、最大48時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fae5-144">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5fae5-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="5fae5-145">Next steps</span></span>

<span data-ttu-id="5fae5-146">Office スクリプトはパワー自動処理に対応しているため、既存のデータ損失防止 (DLP) ポリシーを確認して、ユーザーが Office スクリプトを使用している間も、組織のデータが保護されたままになるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5fae5-146">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="5fae5-147">詳細については、「 [データ損失防止 (DLP) ポリシー](/power-automate/prevent-data-loss)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fae5-147">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="5fae5-148">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="5fae5-148">Related content</span></span>

<span data-ttu-id="5fae5-149">[Office スクリプトの技術ドキュメント](/office/dev/scripts/) (リンクページ) </span><span class="sxs-lookup"><span data-stu-id="5fae5-149">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="5fae5-150">[Excel での Office スクリプトの概要](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (記事) </span><span class="sxs-lookup"><span data-stu-id="5fae5-150">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="5fae5-151">[Web 用の Excel で Office スクリプトを共有](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) する (記事) </span><span class="sxs-lookup"><span data-stu-id="5fae5-151">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="5fae5-152">[Excel on the web で Office スクリプトを記録、編集、および作成する](/office/dev/scripts/tutorials/excel-tutorial) (記事)</span><span class="sxs-lookup"><span data-stu-id="5fae5-152">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>