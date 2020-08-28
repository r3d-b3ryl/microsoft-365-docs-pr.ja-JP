---
title: Windows 10 デバイスのアプリケーション保護設定を編集または設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: アプリ管理ポリシーを作成または編集し、ユーザーの個人用 Windows 10 デバイス上の作業ファイルを保護する方法について説明します。
ms.openlocfilehash: f85a59649e43c141b62091337b842a490d411833
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289201"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="0c589-103">Windows 10 デバイスのアプリケーション保護設定を設定または編集する</span><span class="sxs-lookup"><span data-stu-id="0c589-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="0c589-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c589-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="0c589-105">Windows 10 のアプリ管理ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="0c589-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="0c589-106"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0c589-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="0c589-107">左側のナビゲーションで、[**デバイス**ポリシー] を選択し \> **Policies**ます。</span><span class="sxs-lookup"><span data-stu-id="0c589-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="0c589-108">既存の Windows アプリポリシーを選択し、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c589-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="0c589-109">変更する設定の横にある [ **編集** ] を選択してから、 **保存**します。</span><span class="sxs-lookup"><span data-stu-id="0c589-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="0c589-110">Windows 10 用のアプリの管理ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0c589-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="0c589-111">ユーザーが作業タスクを実行する個人の Windows 10 デバイスを持っている場合、それらのデバイスでもデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="0c589-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="0c589-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0c589-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="0c589-113">左側のナビゲーションで、[**デバイス**ポリシーの追加] を選択し \> **Policies** \> **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="0c589-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="0c589-114">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c589-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="0c589-115">[ **ポリシーの種類**] で、[ **Windows 10 のアプリケーション管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0c589-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="0c589-116">[ **デバイスの種類**] で、[ **個人** ] または [ **会社所有**] のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c589-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="0c589-117">[ **作業ファイルを暗号化する**] が自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="0c589-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="0c589-118">作業ファイルをユーザーの PC に保存させたくない場合は、[ **ユーザーが会社のデータを個人用のファイルにコピーすることを防止し、作業ファイルを OneDrive for Business に保存するようユーザーに強制します**] を **オン**に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c589-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="0c589-119">**[Windows デバイス上のデータの回復] を**展開します。</span><span class="sxs-lookup"><span data-stu-id="0c589-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="0c589-120">これをオンにすることをお勧め**します。**</span><span class="sxs-lookup"><span data-stu-id="0c589-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="0c589-121">データ回復エージェント証明書を先に作成してから、その場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="0c589-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="0c589-122">手順については、「 [暗号化ファイルシステム (EFS) データ回復エージェント (DRA) 証明書を作成および検証する](https://go.microsoft.com/fwlink/p/?linkid=853700)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c589-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="0c589-123">既定では、デバイスに保存されていてユーザーのプロファイルに関連付けられている秘密キーを使用して、作業ファイルの暗号化が行われます。</span><span class="sxs-lookup"><span data-stu-id="0c589-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="0c589-124">該当するユーザーのみがファイル開き、暗号化を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="0c589-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="0c589-125">ただし、デバイスが失われたり、ユーザーが削除されたりした場合、ファイルを暗号化された状態に留めておくことができます。</span><span class="sxs-lookup"><span data-stu-id="0c589-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="0c589-126">管理者は、データ回復エージェント (DRA) 証明書を使用して、ファイルの暗号化を解除できます。</span><span class="sxs-lookup"><span data-stu-id="0c589-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="0c589-128">追加のドメインまたは SharePoint Online の場所を追加して、一覧表示されているすべてのアプリのファイルが保護されるようにする場合は、 **[追加のネットワークとクラウドの場所を保護** する] を展開します。</span><span class="sxs-lookup"><span data-stu-id="0c589-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="0c589-129">いずれかのフィールドに複数の項目を入力する必要がある場合は、項目間にセミコロン (;) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c589-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="0c589-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="0c589-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="0c589-133">最後に、[ **追加**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0c589-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
