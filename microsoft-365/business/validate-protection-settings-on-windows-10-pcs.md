---
title: Windows 10 PC でアプリの保護設定を検証する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 10 の Windows デバイスで Microsoft 365 のビジネス アプリケーションの保護設定を検証する方法について説明します。
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869406"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="f2db6-103">Windows 10 PC でアプリの保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="f2db6-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="f2db6-104">ユーザーが会社データを企業のデバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="f2db6-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="f2db6-p101">[アプリの保護ポリシーを設定](protection-settings-for-windows-10-devices.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。会社所有のデバイスの [ **ユーザーが会社のデータを個人用ファイルにコピーできないようにして、強制的に作業ファイルを OneDrive for Business に保存させる**] 設定を **オン**にした場合、Azure AD に接続してサインインした後に、ユーザーのデバイスでこの設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="f2db6-107">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="f2db6-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="f2db6-p102">365 ビジネスのマイクロソフトの資格情報を使用してサインインして[Microsoft 365 ビジネス ユーザー向けの Windows デバイスの設定](set-up-windows-devices.md)で説明したように、Azure AD に接続して後、に、 **Windows の設定** \> **アカウント** \> **アクセス職場または学校**.選択して**に接続されている\<テナント名\>Azure AD**、し、**情報**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2db6-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="f2db6-111">[ \>] ページで、次の図のような [ **管理サーバー アドレス**] を含む [ **接続情報**] を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="f2db6-113">**会社のデータを管理されていないアプリに貼り付けることができないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="f2db6-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="f2db6-114">Microsoft 365 Business によってインストールされた Outlook 2016 を開きます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="f2db6-115">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="f2db6-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="f2db6-116">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="f2db6-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="f2db6-117">アプリがコンテンツにアクセスできないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="f2db6-119">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="f2db6-120">ユーザーが会社データを個人用デバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="f2db6-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="f2db6-121">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="f2db6-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="f2db6-122">Windows 10 個人用デバイスの場所は、ローカル ユーザーとしてログインしている**Windows の設定**に移動し、クリックするか**アカウント**をタップして\>**アクセス職場または学校**。</span><span class="sxs-lookup"><span data-stu-id="f2db6-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="f2db6-123">[ **職場または学校にアクセスする**] の下で [ **接続**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="f2db6-124">Microsoft 365 ビジネスの資格情報を入力、 **、作業時間を設定または学校のアカウント] ダイアログ** \> **サインイン**します。</span><span class="sxs-lookup"><span data-stu-id="f2db6-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="f2db6-125">[ **職場または学校にアクセスする**] ページで、[ **職場または学校アカウント**] を選んで、[ **情報**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="f2db6-127">[ **職場または学校にアクセスする**] ページで、 **wip**  および  **mam**  の単語を含む、次の図のような [ *管理サーバー アドレス*] が示された [ *接続情報*] を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="f2db6-129">**会社のデータを管理されていないアプリに貼り付けることができないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="f2db6-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="f2db6-130">Outlook 2016 を開いて、必要に応じて Microsoft 365 Business アカウントを追加し、Microsoft 365 Business の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="f2db6-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="f2db6-131">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="f2db6-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="f2db6-132">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="f2db6-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="f2db6-133">アプリがコンテンツにアクセスできないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="f2db6-135">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f2db6-135">You can, however, paste the same content into Word 2016.</span></span>
    

