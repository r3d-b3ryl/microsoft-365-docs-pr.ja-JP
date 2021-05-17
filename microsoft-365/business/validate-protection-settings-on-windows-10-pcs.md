---
title: Windows 10 PC でアプリの保護設定を検証する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: デバイスMicrosoft 365 Business Premiumアプリ保護設定Windows 10検証し、ユーザーが会社のデータを個人用ファイルまたは管理されていないアプリにコピーできないことを確認します。
ms.openlocfilehash: e319ffa5149f055b5de45078facc8899acffc223
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579864"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="79554-103">Windows 10 PC でアプリの保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="79554-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="79554-104">ユーザーが会社データを企業のデバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="79554-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="79554-105">[アプリの保護ポリシーを設定](protection-settings-for-windows-10-devices.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="79554-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="79554-106">[ユーザーが会社のデータを個人用ファイルにコピーし、会社所有のデバイスの作業ファイルを **OneDrive for Business** に保存するように強制する] 設定をオンにした場合は、Azure AD に接続してサインインした後、ユーザーのデバイスでこれを確認できます。</span><span class="sxs-lookup"><span data-stu-id="79554-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="79554-107">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="79554-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="79554-108">Microsoft 365 Business Premium 資格情報を使用してサインインし、「Microsoft 365 Business Premium ユーザー用 [の Windows](set-up-windows-devices.md)デバイスのセットアップ」の説明に従って Azure AD に接続した後、[Windows 設定アカウント アクセスの仕事または学校] に \>  \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="79554-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="79554-109">[Azure **に接続] \<tenant name\> をAD** し、[情報] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="79554-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="79554-111">[**管理] ページで**、次の図に示すように、管理サーバー アドレスを含む接続 \<tenant name\> 情報を確認できます。  </span><span class="sxs-lookup"><span data-stu-id="79554-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="79554-113">**管理されていないアプリに会社のデータを貼り付けできないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="79554-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="79554-114">ユーザー Outlook 2016によってインストールされたファイルを開Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="79554-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="79554-115">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="79554-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="79554-116">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="79554-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="79554-117">アプリがコンテンツにアクセスできないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79554-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="79554-119">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="79554-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="79554-120">ユーザーが会社データを個人用デバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="79554-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="79554-121">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="79554-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="79554-122">ローカル ユーザー Windows 10ログインしている個人用デバイスで、[Windows 設定] に移動し、[アカウントアクセスの仕事または学校] をクリックまたは \> **タップします**。</span><span class="sxs-lookup"><span data-stu-id="79554-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="79554-123">[ **職場または学校にアクセスする**] の下で [ **接続**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="79554-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="79554-124">[仕事Microsoft 365 Business Premiumアカウントの設定] ダイアログに資格情報を入力 **します** \> 。サインイン **します**。</span><span class="sxs-lookup"><span data-stu-id="79554-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="79554-125">[ **職場または学校にアクセスする**] ページで、[ **職場または学校アカウント**] を選んで、[ **情報**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="79554-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![[仕事または学校のアカウント] ダイアログで [情報] をクリックまたはタップします。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="79554-127">[アクセス **の作業時間または** 学校] ページで、次の図に示すような管理サーバー アドレスを含む接続情報を確認できます。その中に wip と *mam* という単語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79554-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="79554-129">**管理されていないアプリに会社のデータを貼り付けできないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="79554-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="79554-130">アカウントOutlook 2016開き、必要に応Microsoft 365 Business Premiumアカウントを追加し、資格情報を使用Microsoft 365 Business Premiumします。</span><span class="sxs-lookup"><span data-stu-id="79554-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="79554-131">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="79554-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="79554-132">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="79554-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="79554-133">アプリがコンテンツにアクセスできないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79554-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="79554-135">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="79554-135">You can, however, paste the same content into Word 2016.</span></span>
    

