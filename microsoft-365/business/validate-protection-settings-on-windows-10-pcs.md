---
title: Windows 10 PC でアプリの保護設定を検証する
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Microsoft 365 Business Premium app protection 設定を Windows 10 デバイスで検証し、ユーザーが会社のデータを個人ファイルや非管理アプリにコピーできないことを確認します。
ms.openlocfilehash: 20b2e43ae53486c046440ff1066d241ec9661888
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635746"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="e4038-103">Windows 10 PC でアプリの保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="e4038-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="e4038-104">ユーザーが会社データを企業のデバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="e4038-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="e4038-105">[アプリの保護ポリシーを設定](protection-settings-for-windows-10-devices.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4038-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="e4038-106">**[** ユーザーが会社の**データを個人用ファイルにコピーできないよう**にする] をオンにして、会社が所有しているデバイスの OneDrive for business の設定に対して作業ファイルの保存を強制する場合は、Azure AD に接続してサインインした後、ユーザーのデバイス上でこれを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e4038-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="e4038-107">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="e4038-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="e4038-108">Microsoft 365 business premium の資格情報を使用してサインインし、「 [microsoft 365 Business premium ユーザーの windows デバイス](set-up-windows-devices.md)をセットアップする」の説明に従って Azure AD に接続した後、[ **windows の設定** \> ] の [**アカウント** \> **アクセスの職場または学校**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e4038-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="e4038-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span><span class="sxs-lookup"><span data-stu-id="e4038-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="e4038-111">[ \<テナント\>名**で管理**] ページで、次の図に示すような**管理サーバーのアドレス**を含む**接続情報**を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e4038-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="e4038-113">**非管理対象アプリに会社のデータを貼り付けることができないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="e4038-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="e4038-114">Microsoft 365 Business Premium によってインストールされた Outlook 2016 を開きます。</span><span class="sxs-lookup"><span data-stu-id="e4038-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="e4038-115">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e4038-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="e4038-116">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="e4038-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="e4038-117">アプリがコンテンツにアクセスできないことを示すエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4038-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="e4038-119">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e4038-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="e4038-120">ユーザーが会社データを個人用デバイスの個人用ファイルにコピーできないことを確認する</span><span class="sxs-lookup"><span data-stu-id="e4038-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="e4038-121">**接続の設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="e4038-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="e4038-122">ローカルユーザーとしてログインしている windows 10 個人用デバイスで、[windows の**設定**] に移動して、[**アカウント** \> **アクセスの職場または学校**] をクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="e4038-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="e4038-123">[ **職場または学校にアクセスする**] の下で [ **接続**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e4038-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="e4038-124">Microsoft 365 Business Premium 資格情報を [**職場または学校のアカウントの設定] ダイアログボックス** \>に**入力します。**</span><span class="sxs-lookup"><span data-stu-id="e4038-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="e4038-125">[ **職場または学校にアクセスする**] ページで、[ **職場または学校アカウント**] を選んで、[ **情報**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e4038-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![[職場または学校のアカウント] ダイアログの [情報] をクリックまたはタップします。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="e4038-127">Access の**職場または学校**のページには、次の図に示すよう**な管理サーバーのアドレス**を含む**接続情報**が表示され、その中に「 *wip* and *mam* 」という単語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4038-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="e4038-129">**非管理対象アプリに会社のデータを貼り付けることができないことを確認する**</span><span class="sxs-lookup"><span data-stu-id="e4038-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="e4038-130">Outlook 2016 を開き、必要に応じて Microsoft 365 Business Premium アカウントを追加して、Microsoft 365 Business Premium の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="e4038-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="e4038-131">メールを開き、そこから一部のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e4038-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="e4038-132">メモ帳を開き、そこにコンテンツを貼り付けようとします。</span><span class="sxs-lookup"><span data-stu-id="e4038-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="e4038-133">アプリがコンテンツにアクセスできないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4038-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="e4038-135">ただし、同じコンテンツを Word 2016 には貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e4038-135">You can, however, paste the same content into Word 2016.</span></span>
    

