---
title: Windows 10 デバイスのアプリケーション保護設定を設定する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Windows 10 デバイスでアプリ管理ポリシーを作成し、作業ファイルを保護する方法について説明します。
ms.openlocfilehash: f649454417dceae05255df6b37760af99c0b8d4f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660388"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="f672d-103">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="f672d-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="f672d-104">Windows 10 用のアプリの管理ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f672d-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="f672d-105">ユーザーが作業タスクを実行する個人の Windows 10 デバイスを持っている場合、それらのデバイスでもデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="f672d-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="f672d-106">の管理センターに移動<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>します。</span><span class="sxs-lookup"><span data-stu-id="f672d-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="f672d-107">左側のナビゲーションで、[**デバイス** \> **ポリシー** \>の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f672d-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="f672d-108">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f672d-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="f672d-109">[ **ポリシーの種類**] で、[ **Windows 10 のアプリケーション管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f672d-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="f672d-110">[**デバイスの種類**] で、[**個人**] または [**会社所有**] のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f672d-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="f672d-111">[ **作業ファイルを暗号化する**] が自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="f672d-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="f672d-112">作業ファイルをユーザーの PC に保存させたくない場合は、[ **ユーザーが会社のデータを個人用のファイルにコピーすることを防止し、作業ファイルを OneDrive for Business に保存するようユーザーに強制します**] を **オン**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f672d-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="f672d-113">[ **Windows デバイスでデータを回復します**] を展開し、 **オン**にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f672d-113">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="f672d-p101">データ回復エージェント証明書を先に作成してから、その場所を参照します。手順については、「[暗号化ファイル システム (EFS) データ回復エージェント (DRA) 証明書の作成と検証](https://go.microsoft.com/fwlink/p/?linkid=853700)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f672d-p101">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="f672d-p102">既定では、デバイスに保存されていてユーザーのプロファイルに関連付けられている秘密キーを使用して、作業ファイルの暗号化が行われます。該当するユーザーのみがファイル開き、暗号化を解除することができます。ただし、デバイスが失われたり、ユーザーが削除されたりした場合、ファイルを暗号化された状態に留めておくことができます。管理者は、ファイルの暗号化を解除するために、データ回復エージェント (DRA) 証明書を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f672d-p102">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="f672d-p103">その他のドメインまたは SharePoint Online の場所を追加してリストに表示されているアプリ内のすべてのファイルが確実に保護されるようにする場合は、[ **その他のネットワークとクラウドの場所の保護**] を展開します。いずれかのフィールドに複数の項目を入力する必要がある場合は、項目間にセミコロン (;) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f672d-p103">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="f672d-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="f672d-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="f672d-126">最後に、[ **追加**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f672d-126">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 