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
ms.openlocfilehash: 7710accf9a3cd1db788dd5215ab6d7bbb97e48a6
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074382"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="315a8-103">Windows 10 PC でアプリの保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="315a8-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="315a8-104">ユーザーが会社データを企業のデバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="315a8-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="315a8-p101">[アプリの保護ポリシーを設定](protection-settings-for-windows-10-devices.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。会社所有のデバイスの [ **ユーザーが会社のデータを個人用ファイルにコピーできないようにして、強制的に作業ファイルを OneDrive for Business に保存させる**] 設定を **オン**にした場合、Azure AD に接続してサインインした後に、ユーザーのデバイスでこの設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="315a8-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="315a8-107">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="315a8-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="315a8-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span><span class="sxs-lookup"><span data-stu-id="315a8-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="315a8-111">[ \<テナント\>名**で管理**] ページで、次の図に示すような**管理サーバーのアドレス**を含む**接続情報**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="315a8-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="315a8-113">**会社のデータを管理されていないアプリに貼り付けることができないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="315a8-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="315a8-114">Microsoft 365 Business によってインストールされた Outlook 2016 を開きます。</span><span class="sxs-lookup"><span data-stu-id="315a8-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="315a8-115">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="315a8-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="315a8-116">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="315a8-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="315a8-117">アプリがコンテンツにアクセスできないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="315a8-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="315a8-119">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="315a8-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="315a8-120">ユーザーが会社データを個人用デバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="315a8-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="315a8-121">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="315a8-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="315a8-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span><span class="sxs-lookup"><span data-stu-id="315a8-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="315a8-123">[ **職場または学校にアクセスする**] の下で [ **接続**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="315a8-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="315a8-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="315a8-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="315a8-125">[ **職場または学校にアクセスする**] ページで、[ **職場または学校アカウント**] を選んで、[ **情報**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="315a8-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="315a8-127">[ **職場または学校にアクセスする**] ページで、 **wip**  および  **mam**  の単語を含む、次の図のような [ *管理サーバー アドレス*] が示された [ *接続情報*] を表示できます。</span><span class="sxs-lookup"><span data-stu-id="315a8-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="315a8-129">**会社のデータを管理されていないアプリに貼り付けることができないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="315a8-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="315a8-130">Outlook 2016 を開いて、必要に応じて Microsoft 365 Business アカウントを追加し、Microsoft 365 Business の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="315a8-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="315a8-131">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="315a8-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="315a8-132">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="315a8-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="315a8-133">アプリがコンテンツにアクセスできないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="315a8-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="315a8-135">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="315a8-135">You can, however, paste the same content into Word 2016.</span></span>
    

