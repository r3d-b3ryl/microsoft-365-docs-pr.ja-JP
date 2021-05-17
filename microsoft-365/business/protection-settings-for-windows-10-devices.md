---
title: デバイスのアプリケーション保護設定を編集またはWindows 10する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: アプリ管理ポリシーを作成または編集し、ユーザーの個人用デバイスで作業ファイルを保護するWindows 10します。
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580016"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="fc211-103">デバイスのアプリケーション保護設定を設定またはWindows 10する</span><span class="sxs-lookup"><span data-stu-id="fc211-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="fc211-104">この記事は、このMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="fc211-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="fc211-105">アプリの管理ポリシーを編集Windows 10</span><span class="sxs-lookup"><span data-stu-id="fc211-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="fc211-106"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fc211-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="fc211-107">左側のナビゲーションで、[デバイス ポリシー **]** \> **を選択します** 。</span><span class="sxs-lookup"><span data-stu-id="fc211-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="fc211-108">既存のアプリ ポリシーをWindowsし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="fc211-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="fc211-109">変更 **する設定** の横にある [編集] を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fc211-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="fc211-110">Windows 10 用のアプリの管理ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fc211-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="fc211-111">ユーザーが作業タスクを実行する個人の Windows 10 デバイスを持っている場合、それらのデバイスでもデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="fc211-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="fc211-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fc211-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="fc211-113">左側のナビゲーションで、[デバイス ポリシー **の** \> **追加] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fc211-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="fc211-114">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc211-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="fc211-115">[ **ポリシーの種類**] で、[ **Windows 10 のアプリケーション管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fc211-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="fc211-116">[**デバイスの種類] で**、[個人]**または [会社\*\*\*\*所有] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fc211-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="fc211-117">[ **作業ファイルを暗号化する**] が自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="fc211-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="fc211-118">作業ファイルをユーザーの PC に保存させたくない場合は、[ **ユーザーが会社のデータを個人用のファイルにコピーすることを防止し、作業ファイルを OneDrive for Business に保存するようユーザーに強制します**] を **オン** に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc211-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="fc211-119">[デバイス **上のデータの回復Windows展開します**。</span><span class="sxs-lookup"><span data-stu-id="fc211-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="fc211-120">オンにすることをお **勧めします**。</span><span class="sxs-lookup"><span data-stu-id="fc211-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="fc211-121">データ回復エージェント証明書を先に作成してから、その場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="fc211-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="fc211-122">手順については、「暗号化ファイル システム (EFS) データ復旧エージェント (DRA) 証明書を作成して [確認する」を参照してください](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)。</span><span class="sxs-lookup"><span data-stu-id="fc211-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span></span>
    
    <span data-ttu-id="fc211-123">既定では、デバイスに保存されていてユーザーのプロファイルに関連付けられている秘密キーを使用して、作業ファイルの暗号化が行われます。</span><span class="sxs-lookup"><span data-stu-id="fc211-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="fc211-124">該当するユーザーのみがファイル開き、暗号化を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="fc211-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="fc211-125">ただし、デバイスが失われたり、ユーザーが削除されたりした場合、ファイルを暗号化された状態に留めておくことができます。</span><span class="sxs-lookup"><span data-stu-id="fc211-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="fc211-126">管理者は、データ復旧エージェント (DRA) 証明書を使用してファイルを復号化できます。</span><span class="sxs-lookup"><span data-stu-id="fc211-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="fc211-128">[**追加のドメインまたは** SharePoint Online の場所を追加する場合は、[追加のネットワークとクラウドの場所を保護する] を展開して、一覧に表示されているアプリのファイルが確実に保護されます。</span><span class="sxs-lookup"><span data-stu-id="fc211-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="fc211-129">いずれかのフィールドに複数の項目を入力する必要がある場合は、項目間にセミコロン (;) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fc211-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="fc211-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="fc211-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="fc211-133">最後に、[ **追加**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fc211-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span>