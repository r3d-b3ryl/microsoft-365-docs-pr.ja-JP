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
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278182"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="2c1ab-103">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="2c1ab-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="2c1ab-104">Windows 10 用のアプリの管理ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2c1ab-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="2c1ab-105">ユーザーが作業タスクを実行する個人の Windows 10 デバイスを持っている場合、それらのデバイスでもデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="2c1ab-106">グローバル管理者の資格情報を使用して、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=837890)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-106">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> <span data-ttu-id="2c1ab-107">[ **管理者**] タイルを選び、管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-107">Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="2c1ab-108">左側のナビゲーションで、[**デバイス** \> **ポリシー** \>の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="2c1ab-109">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="2c1ab-110">[ **ポリシーの種類**] で、[ **Windows 10 のアプリケーション管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="2c1ab-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="2c1ab-112">[ **作業ファイルを暗号化する**] が自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="2c1ab-113">作業ファイルをユーザーの PC に保存させたくない場合は、[ **ユーザーが会社のデータを個人用のファイルにコピーすることを防止し、作業ファイルを OneDrive for Business に保存するようユーザーに強制します**] を **オン**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="2c1ab-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="2c1ab-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="2c1ab-116">詳細については、「[利用可能な設定](#available-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-116">See [Available settings](#available-settings)for more information.</span></span> 
    
    <span data-ttu-id="2c1ab-117">[ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-117">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="2c1ab-118">[ **Windows デバイスでデータを回復します**] を展開し、 **オン**にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-118">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="2c1ab-p103">データ回復エージェント証明書を先に作成してから、その場所を参照します。手順については、「[暗号化ファイル システム (EFS) データ回復エージェント (DRA) 証明書の作成と検証](https://go.microsoft.com/fwlink/p/?linkid=853700)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="2c1ab-p104">既定では、デバイスに保存されていてユーザーのプロファイルに関連付けられている秘密キーを使用して、作業ファイルの暗号化が行われます。該当するユーザーのみがファイル開き、暗号化を解除することができます。ただし、デバイスが失われたり、ユーザーが削除されたりした場合、ファイルを暗号化された状態に留めておくことができます。管理者は、ファイルの暗号化を解除するために、データ回復エージェント (DRA) 証明書を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="2c1ab-p105">その他のドメインまたは SharePoint Online の場所を追加してリストに表示されているアプリ内のすべてのファイルが確実に保護されるようにする場合は、[ **その他のネットワークとクラウドの場所の保護**] を展開します。いずれかのフィールドに複数の項目を入力する必要がある場合は、項目間にセミコロン (;) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="2c1ab-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="2c1ab-131">最後に、[ **追加**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-131">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="2c1ab-132">利用可能な設定</span><span class="sxs-lookup"><span data-stu-id="2c1ab-132">Available settings</span></span>

<span data-ttu-id="2c1ab-133">次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-133">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="2c1ab-134">詳細については、「[Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法](map-protection-features-to-intune-settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-134">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="2c1ab-135">**設定**</span><span class="sxs-lookup"><span data-stu-id="2c1ab-135">**Setting**</span></span>|<span data-ttu-id="2c1ab-136">**説明**</span><span class="sxs-lookup"><span data-stu-id="2c1ab-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2c1ab-137">Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="2c1ab-137">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="2c1ab-138">この設定を **オン**にすると、ユーザーは、ユーザー名とパスワードの他に、別の認証フォームを提供しないと、モバイル デバイスで Office アプリを使用できません。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-138">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="2c1ab-139">ログインに指定の回数失敗した場合に PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="2c1ab-139">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="2c1ab-140">承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-140">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="2c1ab-141">次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある</span><span class="sxs-lookup"><span data-stu-id="2c1ab-141">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="2c1ab-142">この設定は、もう一度サインインを求められるまで、どのくらいユーザーをアイドル状態にできるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c1ab-142">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

