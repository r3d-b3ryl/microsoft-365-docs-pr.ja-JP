---
title: Android または iOS デバイスのアプリ保護設定を検証する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 'Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.  '
ms.openlocfilehash: 5ab16d481bd11ec31a1387a7e94d8b08bb3e0abe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287352"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="8562d-103">Android または iOS デバイスのアプリ保護設定を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="8562d-104">タブの指示に従って、Android または iOS デバイスのアプリ保護設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="8562d-104">Follow the instructions in the tabs to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="androidtab"></a>[<span data-ttu-id="8562d-105">Android</span><span class="sxs-lookup"><span data-stu-id="8562d-105">Android</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="8562d-106">ユーザーのデバイスでアプリ保護設定が機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="8562d-106">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="8562d-107">[Android デバイス用のアプリの構成を設定](app-protection-settings-for-android-and-ios.md) し、アプリを保護したら、次の手順に従って、選択した設定が機能することを検証できます。</span><span class="sxs-lookup"><span data-stu-id="8562d-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="8562d-108">最初に、ポリシーが検証するアプリに適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-108">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="8562d-109">In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.</span><span class="sxs-lookup"><span data-stu-id="8562d-109">In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="8562d-110">セットアップ時に作成した設定の **Android 用のアプリケーション ポリシー**、または作成した別のポリシーを選び、Outlook などにそのポリシーが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="8562d-112">Office アプリにアクセスするのに必要な PIN または指紋認証を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="8562d-113">[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**] が **オン**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="8562d-115">ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="8562d-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="8562d-116">PIN の入力または指紋認証も求められます。</span><span class="sxs-lookup"><span data-stu-id="8562d-116">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="8562d-118">[PIN をリセットする試行の失敗回数] を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="8562d-119">[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **PIN をリセットする試行の失敗回数**] に何らかの回数が設定されていることを確認します。既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="8562d-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="8562d-120">ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="8562d-120">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="8562d-p101">ポリシーで指定された回数だけ不正な PIN を入力します。PIN をリセットする [ **PIN の試行回数の上限に達しました**] というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8562d-p101">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="8562d-p102">[ **PIN のリセット**] を押します。ユーザーの Microsoft 365 Business 資格情報を使用してサインインするように求められ、次に新しい PIN の設定を求められます。</span><span class="sxs-lookup"><span data-stu-id="8562d-p102">Press **Reset PIN**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="8562d-126">[OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する] を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-126">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="8562d-127">[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オン**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-127">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="8562d-129">ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8562d-129">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="8562d-130">添付ファイルを含むメールを開き、添付ファイルの情報の横にある下矢印アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="8562d-130">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="8562d-132">画面の下部に [ **デバイスに保存できません**] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8562d-132">You will see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="8562d-134">この時点では、OneDrive for Business への保存は Android に有効になっていないため、ローカルに保存がブロックされていることだけが確認できます。</span><span class="sxs-lookup"><span data-stu-id="8562d-134">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="8562d-135">[Office アプリがアイドルになってからユーザーにもう一度サインインを求める時間] を確認する</span><span class="sxs-lookup"><span data-stu-id="8562d-135">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="8562d-136">[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある**] に何らかの分数が設定されていることを確認します。既定値は 30 分です。</span><span class="sxs-lookup"><span data-stu-id="8562d-136">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="8562d-137">ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8562d-137">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="8562d-p103">Outlook の受信トレイが表示されます。Android デバイスを少なくとも 30 分間 (またはポリシーに設定した時間よりも長い時間) 触れずにアイドル状態にします。多くの場合、デバイスが暗くなります。</span><span class="sxs-lookup"><span data-stu-id="8562d-p103">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="8562d-141">Android デバイスで Outlook に再アクセスします。</span><span class="sxs-lookup"><span data-stu-id="8562d-141">Re-access Outlook on the Android device.</span></span>
    
4. <span data-ttu-id="8562d-142">Outlook をもう一度アクセスする前に、PIN を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8562d-142">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="8562d-143">暗号化で作業ファイルの保護を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-143">Validate Protect work files with encryption</span></span>

<span data-ttu-id="8562d-144">[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **暗号化を使用して作業ファイルを保護する**] が **オン**、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オフ**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-144">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="8562d-145">ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8562d-145">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="8562d-146">いくつかの画像の添付ファイルを含むメールを開きます。</span><span class="sxs-lookup"><span data-stu-id="8562d-146">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="8562d-147">添付ファイルの情報の横にある下矢印アイコンをタップして、添付ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="8562d-147">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="8562d-p104">Outlook にデバイス上の写真、メディア、ファイルへのアクセスを許可するように求められる場合があります。[ **許可**] をタップします。</span><span class="sxs-lookup"><span data-stu-id="8562d-p104">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="8562d-151">画面の下部で、[ **デバイスに保存する**] を選び、 **ギャラリー** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="8562d-151">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="8562d-p105">リストに暗号化された写真 (複数の画像の添付ファイルを保存した場合は複数の写真) が表示されます。これは、白い感嘆符が入った白い円が中心にある灰色の四角形として写真リストに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8562d-p105">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="iostab"></a>[<span data-ttu-id="8562d-155">iOS</span><span class="sxs-lookup"><span data-stu-id="8562d-155">iOS</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="8562d-156">ユーザーのデバイスでアプリ保護設定が機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="8562d-156">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="8562d-157">[iOS デバイス用のアプリの構成を設定](app-protection-settings-for-android-and-ios.md) し、アプリを保護したら、次の手順に従って、選択した設定が機能することを検証できます。</span><span class="sxs-lookup"><span data-stu-id="8562d-157">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="8562d-158">最初に、ポリシーが検証するアプリに適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-158">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="8562d-159">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span><span class="sxs-lookup"><span data-stu-id="8562d-159">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="8562d-160">セットアップ時に作成した設定に **iOS アプリケーション ポリシー**または独自に作成した別のポリシーを選び、Outlook などにそれが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-160">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="8562d-162">Office アプリにアクセスするのに必要な PIN を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-162">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="8562d-163">[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**] が **オン**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-163">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="8562d-165">ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="8562d-165">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="8562d-166">PIN の入力または指紋認証も求められます。</span><span class="sxs-lookup"><span data-stu-id="8562d-166">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="8562d-168">[PIN をリセットする試行の失敗回数] を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-168">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="8562d-169">[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **PIN をリセットする試行の失敗回数**] に何らかの回数が設定されていることを確認します。既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="8562d-169">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="8562d-170">ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="8562d-170">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="8562d-p106">ポリシーで指定された回数だけ不正な PIN を入力します。PIN をリセットする [ **PIN の試行回数の上限に達しました**] というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8562d-p106">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="8562d-p107">[ **OK**] を押します。ユーザーの Microsoft 365 Business 資格情報を使用してサインインするように求められ、次に新しい PIN の設定を求められます。</span><span class="sxs-lookup"><span data-stu-id="8562d-p107">Press **OK**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="8562d-176">[OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する] を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-176">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="8562d-177">[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オン**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-177">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="8562d-179">ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8562d-179">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="8562d-180">添付ファイルを含むメールを開き、添付ファイルを開き、画面の下部で [ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8562d-180">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="8562d-p108">OneDrive for Business のオプションのみが表示されます。表示されない場合は、[ **アカウントの追加**] をタップして、[ **ストレージ アカウントの追加**] 画面から [ **OneDrive for Business**] を選びます。求められたら、エンド ユーザーの Microsoft 365 Business を入力してサインインします。</span><span class="sxs-lookup"><span data-stu-id="8562d-p108">You should only see an option for OneDrive for Business. If not If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen. Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="8562d-185">[ **保存**] をタップして、[ **OneDrive for Business**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8562d-185">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="8562d-186">[Office アプリがアイドルになってからユーザーにもう一度サインインを求める時間] を確認する</span><span class="sxs-lookup"><span data-stu-id="8562d-186">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="8562d-187">[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある**] に何らかの分数が設定されていることを確認します。既定値は 30 分です。</span><span class="sxs-lookup"><span data-stu-id="8562d-187">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="8562d-188">ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8562d-188">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="8562d-p109">Outlook の受信トレイが表示されます。iOS デバイスを少なくとも 30 分間 (またはポリシーに設定した時間よりも長い時間) 触れずに放置します。多くの場合、デバイスが暗くなります。</span><span class="sxs-lookup"><span data-stu-id="8562d-p109">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="8562d-192">iOS デバイスで Outlook に再アクセスします。</span><span class="sxs-lookup"><span data-stu-id="8562d-192">Re-access Outlook on the iOS device.</span></span>
    
4. <span data-ttu-id="8562d-193">Outlook をもう一度アクセスする前に、PIN を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8562d-193">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="8562d-194">暗号化で作業ファイルの保護を検証する</span><span class="sxs-lookup"><span data-stu-id="8562d-194">Validate Protect work files with encryption</span></span>

<span data-ttu-id="8562d-195">[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **暗号化を使用して作業ファイルを保護する**] が **オン**、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オフ**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8562d-195">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="8562d-196">ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8562d-196">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="8562d-197">いくつかの画像の添付ファイルを含むメールを開きます。</span><span class="sxs-lookup"><span data-stu-id="8562d-197">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="8562d-198">添付ファイルをタップし、その下にある [ **保存**] オプションをタップします。</span><span class="sxs-lookup"><span data-stu-id="8562d-198">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="8562d-p110">ホーム画面から **写真**アプリを開きます。保存され暗号化された写真 (複数の画像の添付ファイルを保存した場合は複数の写真) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8562d-p110">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

