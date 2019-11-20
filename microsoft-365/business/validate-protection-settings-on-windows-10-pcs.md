---
title: Windows 10 PC でアプリの保護設定を検証する
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Windows 10 デバイスで Microsoft 365 Business app protection の設定を検証する方法について説明します。
ms.openlocfilehash: c54b053c1f6efbca8fd02431c416793a044c6821
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721862"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="e26f5-103">Windows 10 PC でアプリの保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="e26f5-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="e26f5-104">ユーザーが会社データを企業のデバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="e26f5-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="e26f5-105">[アプリの保護ポリシーを設定](protection-settings-for-windows-10-devices.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e26f5-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="e26f5-106">**[** ユーザーが会社の**データを個人用ファイルにコピーできないよう**にする] をオンにして、会社が所有しているデバイスの OneDrive for business の設定に対して作業ファイルの保存を強制する場合は、Azure AD に接続してサインインした後、ユーザーのデバイス上でこれを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="e26f5-107">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="e26f5-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="e26f5-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span><span class="sxs-lookup"><span data-stu-id="e26f5-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="e26f5-111">[ \<テナント\>名**で管理**] ページで、次の図に示すような**管理サーバーのアドレス**を含む**接続情報**を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="e26f5-113">**非管理対象アプリに会社のデータを貼り付けることができないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="e26f5-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="e26f5-114">Microsoft 365 Business によってインストールされた Outlook 2016 を開きます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="e26f5-115">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e26f5-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="e26f5-116">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="e26f5-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="e26f5-117">アプリがコンテンツにアクセスできないことを示すエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="e26f5-119">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="e26f5-120">ユーザーが会社データを個人用デバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="e26f5-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="e26f5-121">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="e26f5-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="e26f5-122">ローカルユーザーとしてログインしている windows 10 個人用デバイスで、[windows の**設定**] に移動して、[**アカウント** \> **アクセスの職場または学校**] をクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="e26f5-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="e26f5-123">[ **職場または学校にアクセスする**] の下で [ **接続**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="e26f5-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="e26f5-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="e26f5-125">[ **職場または学校にアクセスする**] ページで、[ **職場または学校アカウント**] を選んで、[ **情報**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![[職場または学校のアカウント] ダイアログの [情報] をクリックまたはタップします。](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="e26f5-127">Access の**職場または学校**のページには、次の図に示すよう**な管理サーバーのアドレス**を含む**接続情報**が表示され、その中に「 *wip* and *mam* 」という単語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e26f5-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="e26f5-129">**非管理対象アプリに会社のデータを貼り付けることができないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="e26f5-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="e26f5-130">Outlook 2016 を開いて、必要に応じて Microsoft 365 Business アカウントを追加し、Microsoft 365 Business の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="e26f5-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="e26f5-131">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e26f5-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="e26f5-132">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="e26f5-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="e26f5-133">アプリがコンテンツにアクセスできないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="e26f5-135">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e26f5-135">You can, however, paste the same content into Word 2016.</span></span>
    

