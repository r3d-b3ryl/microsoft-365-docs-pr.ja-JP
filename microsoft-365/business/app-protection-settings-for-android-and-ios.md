---
title: Android または iOS デバイスのアプリ保護設定を設定する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 作成、編集、または、アプリケーション管理のポリシーを削除および Android や iOS のデバイス上の作業ファイルを保護する方法について説明します。
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869569"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="2b7c6-103">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="2b7c6-104">アプリの管理ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-104">Create an app management policy</span></span>

1. <span data-ttu-id="2b7c6-105">グローバル管理者の資格情報を使用して、[Microsoft 365 Business](https://portal.office.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-105">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="2b7c6-106">管理センターの [ **デバイス ポリシー**] カードで、[ **ポリシーの追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-106">In the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="2b7c6-108">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="2b7c6-109">[ **ポリシーの種類**] で、作成するポリシーのセットに応じて、[ **Android アプリケーション管理**] または [ **iOS アプリケーション管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="2b7c6-p101">**デバイスの紛失や盗難時の保護の作業ファイル**と**ユーザーがモバイル デバイス上の Office ファイルにアクセスする方法を管理**] を展開\>どのようにしたい設定を構成します。既定で**オフ**になって**ユーザーがモバイル デバイス上の Office ファイルにアクセスする方法を管理**するが、有効**に**して既定値を受け入れることをお勧めします。詳細については、[利用可能な設定](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-p101">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="2b7c6-113">[ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="2b7c6-p102">次に**にこれらの設定が表示されますか?\*\*\*\*変更**を選択して、これらの設定が表示されますユーザー セキュリティ グループを選択の既定の**すべてのユーザー**セキュリティ グループを使用しない場合は、 \> **を選択**します。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="2b7c6-117">最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="2b7c6-118">アプリの管理ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-118">Edit an app management policy</span></span>

1. <span data-ttu-id="2b7c6-119">**ポリシー**カード上には、**ポリシーの編集**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="2b7c6-120">[ **ポリシーの編集**] ウィンドウで、変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="2b7c6-p103">各設定の横にある [ **編集**] を選び、ポリシーの値を変更します。値を変更すると、その値がポリシーに自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="2b7c6-123">完了したら、[ **ポリシーを編集**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="2b7c6-124">アプリの管理ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-124">Delete an app management policy</span></span>

1. <span data-ttu-id="2b7c6-125">**ポリシー** カードで、[ **ポリシーの削除**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-125">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="2b7c6-126">[ウィンドウ]**のポリシーを削除**削除するポリシーを選択して\>**を選択**し、[**確認**または複数の選択したポリシーを削除するのには。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-126">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="2b7c6-127">利用可能な設定</span><span class="sxs-lookup"><span data-stu-id="2b7c6-127">Available settings</span></span>

<span data-ttu-id="2b7c6-128">次の表は、デバイス上の作業ファイルを保護するために利用可能な設定と、ユーザーが自分のモバイル デバイスから Office ファイルにアクセスする方法を制御する設定に関する詳細情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="2b7c6-129">詳細については、「 [Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法](map-protection-features-to-intune-settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="2b7c6-130">作業ファイルを保護する設定</span><span class="sxs-lookup"><span data-stu-id="2b7c6-130">Settings that protect work files</span></span>

<span data-ttu-id="2b7c6-131">次の設定は、ユーザーのデバイスが紛失したり盗難された場合に、作業ファイルを保護するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2b7c6-132">設定</span><span class="sxs-lookup"><span data-stu-id="2b7c6-132">Setting</span></span>  <br/> |<span data-ttu-id="2b7c6-133">説明</span><span class="sxs-lookup"><span data-stu-id="2b7c6-133">Description</span></span>  <br/> |
|<span data-ttu-id="2b7c6-134">アクティブでない状態が指定の日数続いたデバイスから作業ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="2b7c6-135">ここで指定した日数の間デバイスが使用されなかった場合、デバイスに保存されているすべての作業ファイルは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="2b7c6-136">OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="2b7c6-137">この設定を **オン**にすると、作業ファイルの使用可能な保存場所は OneDrive for Business のみになります。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="2b7c6-138">作業ファイルを暗号化する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="2b7c6-p104">作業ファイルが暗号化によって保護されるように、この設定は常に **オン**にします。デバイスが紛失したり盗難された場合でも、企業データが読まれることはありません。  </span><span class="sxs-lookup"><span data-stu-id="2b7c6-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="2b7c6-141">ユーザーによるモバイル デバイスでの Office ファイルへのアクセスを制御する設定</span><span class="sxs-lookup"><span data-stu-id="2b7c6-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="2b7c6-142">次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2b7c6-143">設定</span><span class="sxs-lookup"><span data-stu-id="2b7c6-143">Setting</span></span>  <br/> |<span data-ttu-id="2b7c6-144">説明</span><span class="sxs-lookup"><span data-stu-id="2b7c6-144">Description</span></span>  <br/> |
|<span data-ttu-id="2b7c6-145">Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="2b7c6-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="2b7c6-146">この設定を **オン**にすると、ユーザーは、ユーザー名とパスワードの他に、別の認証フォームを提供しないと、モバイル デバイスで Office アプリを使用できません。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="2b7c6-147">ログインに指定の回数失敗した場合に PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="2b7c6-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="2b7c6-148">承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="2b7c6-149">次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある</span><span class="sxs-lookup"><span data-stu-id="2b7c6-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="2b7c6-150">この設定は、もう一度サインインを求められるまで、どのくらいユーザーをアイドル状態にできるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="2b7c6-151">脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="2b7c6-p105">賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。これは、ユーザーがオペレーティング システムを変更できるため、デバイスがマルウェアの危険にさらされる可能性が高くなることを意味します。この設定を **オン** にすると、これらのデバイスはブロックされます。  </span><span class="sxs-lookup"><span data-stu-id="2b7c6-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="2b7c6-155">Office アプリのコンテンツを個人のアプリにコピーすることをユーザーに許可する</span><span class="sxs-lookup"><span data-stu-id="2b7c6-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="2b7c6-p106">既定では、このできるように操作を行いますが、ユーザーが個人用ファイルに、作業ファイルの情報をコピー可能性があります**に**設定する場合は。設定が**オフ**の場合、ユーザーはアプリケーションの個人または個人のアカウントに、勤務先のアカウントから情報をコピーすることができません。</span><span class="sxs-lookup"><span data-stu-id="2b7c6-p106">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file. If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.  </span></span><br/> |
   

  

