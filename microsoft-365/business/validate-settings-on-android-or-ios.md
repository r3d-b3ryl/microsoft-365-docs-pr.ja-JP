---
title: Android デバイスまたは iOS デバイスのアプリ保護設定を検証する
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Android または iOS デバイスで Microsoft 365 Business Premium アプリ保護設定を検証する方法について説明します。
ms.openlocfilehash: a0a4a6e6cff59f66a506929e97c99d361472a68b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578069"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="7e86a-103">Android デバイスまたは iOS デバイスのアプリ保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="7e86a-104">Android または iOS デバイスのアプリ保護設定を検証するには、次のセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7e86a-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="7e86a-105">Android</span><span class="sxs-lookup"><span data-stu-id="7e86a-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="7e86a-106">アプリの保護設定がユーザー デバイスで動作しているのを確認する</span><span class="sxs-lookup"><span data-stu-id="7e86a-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="7e86a-107">[Android デバイス用のアプリの構成を設定](app-protection-settings-for-android-and-ios.md) し、アプリを保護したら、次の手順に従って、選択した設定が機能することを検証できます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="7e86a-108">まず、ポリシーを検証するアプリにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="7e86a-109">Microsoft 365 Business Premium [管理センター](https://portal.office.com)で、[ポリシーの編集 **] ポリシー** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="7e86a-109">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="7e86a-110">セットアップ **時に作成した設定** 、または作成した別のポリシーに対して [Android 用のアプリケーション ポリシー] を選択し、Outlook に適用されている例を確認します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="7e86a-112">Office アプリにアクセスするのに必要な PIN または指紋認証を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="7e86a-113">[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**] が **オン** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![[アプリにアクセスするために PIN または指紋を要求する] Officeが [オン] に設定されている必要があります。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="7e86a-115">ユーザーの Android デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="7e86a-116">PIN を入力するか、指紋を使用するように求めるメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="7e86a-118">[PIN をリセットする試行の失敗回数] を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="7e86a-119">[ポリシーの編集] ウィンドウで **、[Office** ドキュメント のアクセス制御] の横にある [編集] を選択し、[ユーザーがモバイル デバイス上の **Office** ファイルにアクセスする方法を管理する] を展開し、失敗した試行回数が一部の数に設定されている場合は **、[PIN** のリセット] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="7e86a-120">これは既定で 5 です。</span><span class="sxs-lookup"><span data-stu-id="7e86a-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="7e86a-121">ユーザーの Android デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="7e86a-122">ポリシーで指定された回数だけ不正な PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="7e86a-123">PIN をリセットするために PIN の試行制限に達した **というメッセージ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="7e86a-125">[ **PIN のリセット**] を押します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-125">Press **Reset PIN**.</span></span> <span data-ttu-id="7e86a-126">ユーザーの Microsoft 365 Business Premium 資格情報でサインインするように求めるメッセージが表示され、新しい PIN を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e86a-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="7e86a-127">[OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する] を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="7e86a-128">[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オン** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="7e86a-130">ユーザーの Android デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインし、要求された場合は PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="7e86a-131">添付ファイルを含むメールを開き、添付ファイルの情報の横にある下矢印アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="7e86a-133">画面の下部 **に [デバイスに保存できません** ] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="7e86a-135">この時点では、OneDrive for Business への保存は Android に有効になっていないため、ローカルに保存がブロックされていることだけが確認できます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="7e86a-136">[Office アプリがアイドルになってからユーザーにもう一度サインインを求める時間] を確認する</span><span class="sxs-lookup"><span data-stu-id="7e86a-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="7e86a-137">[ポリシーの編集] ウィンドウで **、[Office** ドキュメント アクセス制御] の横にある [編集] を選択し、[ユーザーがモバイル デバイス上の **Office** ファイルにアクセスする方法を管理する] を展開し **、[Office** アプリのアイドル状態が発生した後にユーザーに再度サインインを要求する] が数分間に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e86a-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="7e86a-138">これは既定で 30 分です。</span><span class="sxs-lookup"><span data-stu-id="7e86a-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="7e86a-139">ユーザーの Android デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインし、要求された場合は PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="7e86a-p105">Outlook の受信トレイが表示されます。Android デバイスを少なくとも 30 分間 (またはポリシーに設定した時間よりも長い時間) 触れずにアイドル状態にします。多くの場合、デバイスが暗くなります。</span><span class="sxs-lookup"><span data-stu-id="7e86a-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="7e86a-143">Android デバイスで Outlook に再度アクセスします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="7e86a-144">Outlook に再度アクセスする前に、PIN の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="7e86a-145">暗号化で作業ファイルの保護を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="7e86a-146">[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **暗号化を使用して作業ファイルを保護する**] が **オン**、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オフ** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="7e86a-147">ユーザーの Android デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインし、要求された場合は PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="7e86a-148">いくつかの画像ファイルの添付ファイルを含む電子メールを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="7e86a-149">添付ファイルの情報の横にある下矢印アイコンをタップして、添付ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="7e86a-p106">Outlook にデバイス上の写真、メディア、ファイルへのアクセスを許可するように求められる場合があります。[ **許可**] をタップします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="7e86a-153">画面の下部で、[ **デバイスに保存する**] を選び、 **ギャラリー** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="7e86a-p107">リストに暗号化された写真 (複数の画像の添付ファイルを保存した場合は複数の写真) が表示されます。これは、白い感嘆符が入った白い円が中心にある灰色の四角形として写真リストに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e86a-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="7e86a-157">iOS</span><span class="sxs-lookup"><span data-stu-id="7e86a-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="7e86a-158">ユーザーのデバイスでアプリ保護設定が機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="7e86a-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="7e86a-159">[iOS デバイス用のアプリの構成を設定](app-protection-settings-for-android-and-ios.md) し、アプリを保護したら、次の手順に従って、選択した設定が機能することを検証できます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="7e86a-160">まず、ポリシーを検証するアプリにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="7e86a-161">Microsoft 365 Business Premium [管理センター](https://portal.office.com)で、[ポリシーの編集 **] ポリシー** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="7e86a-161">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="7e86a-162">セットアップ **時に作成した設定** 、または作成した別のポリシーの iOS 用のアプリケーション ポリシーを選択し、Outlook に適用されている例を確認します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="7e86a-164">Office アプリにアクセスするのに必要な PIN を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="7e86a-165">[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**] が **オン** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![[アプリにアクセスするために PIN または指紋を要求する] Officeが [オン] に設定されている必要があります。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="7e86a-167">ユーザーの iOS デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="7e86a-168">PIN を入力するか、指紋を使用するように求めるメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="7e86a-170">[PIN をリセットする試行の失敗回数] を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="7e86a-171">[ポリシーの編集] ウィンドウで **、[Office** ドキュメント のアクセス制御] の横にある [編集] を選択し、[ユーザーがモバイル デバイス上の **Office** ファイルにアクセスする方法を管理する] を展開し、失敗した試行回数が一部の数に設定されている場合は **、[PIN** のリセット] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="7e86a-172">これは既定で 5 です。</span><span class="sxs-lookup"><span data-stu-id="7e86a-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="7e86a-173">ユーザーの iOS デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="7e86a-174">ポリシーで指定された回数だけ不正な PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="7e86a-175">PIN をリセットするために PIN の試行制限に達した **というメッセージ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="7e86a-177">[ **OK**] を押します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-177">Press **OK**.</span></span> <span data-ttu-id="7e86a-178">ユーザーの Microsoft 365 Business Premium 資格情報でサインインするように求めるメッセージが表示され、新しい PIN を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e86a-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="7e86a-179">[OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する] を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="7e86a-180">[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オン** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="7e86a-182">ユーザーの iOS デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインし、必要に応じて PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="7e86a-183">添付ファイルを含むメールを開き、添付ファイルを開き、画面の下部で [ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="7e86a-185">OneDrive for Business のオプションのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="7e86a-186">存在しない場合は、[アカウントの **追加] をタップ** し、[ストレージ アカウントの追加] 画面から **[OneDrive for Business]** **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="7e86a-187">プロンプトが表示されたら、エンド ユーザーの Microsoft 365 Business Premium にサインインするように指定します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="7e86a-188">[ **保存**] をタップして、[ **OneDrive for Business**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="7e86a-189">[Office アプリがアイドルになってからユーザーにもう一度サインインを求める時間] を確認する</span><span class="sxs-lookup"><span data-stu-id="7e86a-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="7e86a-190">[ポリシーの編集] ウィンドウで **、[Office** ドキュメント アクセス制御] の横にある [編集] を選択し、[ユーザーがモバイル デバイス上の **Office** ファイルにアクセスする方法を管理する] を展開し **、[Office** アプリのアイドル状態が発生した後にユーザーに再度サインインを要求する] が数分間に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e86a-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="7e86a-191">これは既定で 30 分です。</span><span class="sxs-lookup"><span data-stu-id="7e86a-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="7e86a-192">ユーザーの iOS デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインし、必要に応じて PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="7e86a-p113">Outlook の受信トレイが表示されます。iOS デバイスを少なくとも 30 分間 (またはポリシーに設定した時間よりも長い時間) 触れずに放置します。多くの場合、デバイスが暗くなります。</span><span class="sxs-lookup"><span data-stu-id="7e86a-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="7e86a-196">iOS デバイスの Outlook にもう一度アクセスします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="7e86a-197">Outlook に再度アクセスする前に、PIN の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="7e86a-198">暗号化で作業ファイルの保護を検証する</span><span class="sxs-lookup"><span data-stu-id="7e86a-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="7e86a-199">[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **暗号化を使用して作業ファイルを保護する**] が **オン**、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オフ** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="7e86a-200">ユーザーの iOS デバイスで Outlook を開き、ユーザーの Microsoft 365 Business Premium 資格情報でサインインし、必要に応じて PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e86a-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="7e86a-201">いくつかの画像ファイルの添付ファイルを含む電子メールを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="7e86a-202">添付ファイルをタップし、その下にある [ **保存**] オプションをタップします。</span><span class="sxs-lookup"><span data-stu-id="7e86a-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="7e86a-p114">ホーム画面から **写真** アプリを開きます。保存され暗号化された写真 (複数の画像の添付ファイルを保存した場合は複数の写真) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e86a-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

