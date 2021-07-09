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
description: Android デバイスまたは iOS デバイスMicrosoft 365 Business Premiumアプリ保護設定を検証する方法について説明します。
ms.openlocfilehash: 43e74b548711550090021c39096b1647cee9e039
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339332"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Android デバイスまたは iOS デバイスのアプリ保護設定を検証する

Android または iOS デバイスのアプリ保護設定を検証するには、次のセクションの手順に従います。
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>アプリの保護設定がユーザー デバイスで動作しているのを確認する

[Android デバイス用のアプリの構成を設定](app-protection-settings-for-android-and-ios.md) し、アプリを保護したら、次の手順に従って、選択した設定が機能することを検証できます。 
  
まず、ポリシーを検証するアプリにポリシーが適用されます。
  
1. 管理センターで [Microsoft 365 Business Premiumポリシーの](https://admin.microsoft.com)**編集に** \> **移動します**。
    
2. セットアップ **時に作成した設定**、または作成した別のポリシーに対して [Android 用のアプリケーション ポリシー] を選択し、たとえば、Outlook適用されているを確認します。 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Office アプリにアクセスするのに必要な PIN または指紋認証を検証する

[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**] が **オン** に設定されていることを確認します。
  
![[アプリにアクセスするために PIN または指紋を要求Office] が [オン] に設定されている必要があります。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. ユーザーの Android デバイスで、ユーザーのOutlook資格情報を使用してサインインMicrosoft 365 Business Premiumします。
    
2. PIN を入力するか、指紋を使用するように求めるメッセージも表示されます。
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>[PIN をリセットする試行の失敗回数] を検証する

[ポリシーの編集] ウィンドウで **、[Office** ドキュメント のアクセス制御] の横にある [編集] を選択し、[ユーザーがモバイル デバイス上の **Office** ファイルにアクセスする方法を管理する] を展開し、失敗した試行回数が一部の数に設定された後に **PIN** をリセットするを確認します。 これは既定で 5 です。 
  
1. ユーザーの Android デバイスで、ユーザーのOutlook資格情報を使用してサインインMicrosoft 365 Business Premiumします。
    
2. ポリシーで指定された回数だけ不正な PIN を入力します。 PIN をリセットするために PIN の試行制限に達した **というメッセージ** が表示されます。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. [ **PIN のリセット**] を押します。 ユーザーの資格情報を使用してサインインするように求Microsoft 365 Business Premium、新しい PIN を設定する必要があります。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>[OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する] を検証する

[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オン** に設定されていることを確認します。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. ユーザーの Android デバイスで、Outlookを開き、ユーザーの資格情報を使用Microsoft 365 Business Premiumサインインし、必要に応じて PIN を入力します。
    
2. 添付ファイルを含むメールを開き、添付ファイルの情報の横にある下矢印アイコンをタップします。
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    画面の下部 **に [デバイスに保存できません** ] が表示されます。 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > この時点では、OneDrive for Business への保存は Android に有効になっていないため、ローカルに保存がブロックされていることだけが確認できます。 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>[Office アプリがアイドルになってからユーザーにもう一度サインインを求める時間] を確認する

[ポリシーの編集] ウィンドウで **、[Office** ドキュメント アクセス制御] の横にある [編集] を選択し、[ユーザーがモバイル デバイス上の **Office** ファイルにアクセスする方法を管理する] を展開し **、[Office** アプリのアイドル状態が発生した後にユーザーに再度サインインを要求する] が数分間に設定されている必要があります。 これは既定で 30 分です。 
  
1. ユーザーの Android デバイスで、Outlookを開き、ユーザーの資格情報を使用Microsoft 365 Business Premiumサインインし、必要に応じて PIN を入力します。
    
2. Outlook の受信トレイが表示されます。Android デバイスを少なくとも 30 分間 (またはポリシーに設定した時間よりも長い時間) 触れずにアイドル状態にします。多くの場合、デバイスが暗くなります。
    
3. Android Outlookにアクセスします。
    
4. もう一度アクセスする前に、PIN の入力を求Outlookされます。
    
### <a name="validate-protect-work-files-with-encryption"></a>暗号化で作業ファイルの保護を検証する

[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **暗号化を使用して作業ファイルを保護する**] が **オン**、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オフ** に設定されていることを確認します。
  
1. ユーザーの Android デバイスで、Outlookを開き、ユーザーの資格情報を使用Microsoft 365 Business Premiumサインインし、必要に応じて PIN を入力します。
    
2. いくつかの画像ファイルの添付ファイルを含む電子メールを開きます。
    
3. 添付ファイルの情報の横にある下矢印アイコンをタップして、添付ファイルを保存します。
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Outlook にデバイス上の写真、メディア、ファイルへのアクセスを許可するように求められる場合があります。[ **許可**] をタップします。
    
5. 画面の下部で、[ **デバイスに保存する**] を選び、 **ギャラリー** アプリを開きます。 
    
6. リストに暗号化された写真 (複数の画像の添付ファイルを保存した場合は複数の写真) が表示されます。これは、白い感嘆符が入った白い円が中心にある灰色の四角形として写真リストに表示される場合があります。
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>ユーザーのデバイスでアプリ保護設定が機能していることを確認する

[iOS デバイス用のアプリの構成を設定](app-protection-settings-for-android-and-ios.md) し、アプリを保護したら、次の手順に従って、選択した設定が機能することを検証できます。 
  
まず、ポリシーを検証するアプリにポリシーが適用されます。
  
1. 管理センターで [Microsoft 365 Business Premiumポリシーの](https://admin.microsoft.com)**編集に** \> **移動します**。
    
2. セットアップ **時に作成した設定**、または作成した別のポリシーに対して iOS 用のアプリケーション ポリシーを選択し、たとえば、iOS に適用Outlookします。 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Office アプリにアクセスするのに必要な PIN を検証する

[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**] が **オン** に設定されていることを確認します。
  
![[アプリにアクセスするために PIN または指紋を要求Office] が [オン] に設定されている必要があります。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. ユーザーの iOS デバイスで、Outlookを開き、ユーザーの資格情報でサインインMicrosoft 365 Business Premiumします。
    
2. PIN を入力するか、指紋を使用するように求めるメッセージも表示されます。
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>[PIN をリセットする試行の失敗回数] を検証する

[ポリシーの編集] ウィンドウで **、[Office** ドキュメント のアクセス制御] の横にある [編集] を選択し、[ユーザーがモバイル デバイス上の **Office** ファイルにアクセスする方法を管理する] を展開し、失敗した試行回数が一部の数に設定された後に **PIN** をリセットするを確認します。 これは既定で 5 です。 
  
1. ユーザーの iOS デバイスで、Outlookを開き、ユーザーの資格情報でサインインMicrosoft 365 Business Premiumします。
    
2. ポリシーで指定された回数だけ不正な PIN を入力します。 PIN をリセットするために PIN の試行制限に達した **というメッセージ** が表示されます。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. [ **OK**] を押します。 ユーザーの資格情報を使用してサインインするように求Microsoft 365 Business Premium、新しい PIN を設定する必要があります。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>[OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する] を検証する

[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オン** に設定されていることを確認します。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. ユーザーの iOS デバイスで、Outlookを開き、ユーザーの資格情報を使用Microsoft 365 Business Premiumサインインし、要求された場合は PIN を入力します。
    
2. 添付ファイルを含むメールを開き、添付ファイルを開き、画面の下部で [ **保存**] を選びます。 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. OneDrive for Business のオプションのみが表示されます。 アカウントを追加しない場合は、[アカウントの **追加]** をタップOneDrive for Business **[アカウント** の追加] 画面Storage **選択** します。 プロンプトが表示されたら、エンド ユーザー Microsoft 365 Business Premiumにサインインするように指定します。 
    
    [ **保存**] をタップして、[ **OneDrive for Business**] を選びます。
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>[Office アプリがアイドルになってからユーザーにもう一度サインインを求める時間] を確認する

[ポリシーの編集] ウィンドウで **、[Office** ドキュメント アクセス制御] の横にある [編集] を選択し、[ユーザーがモバイル デバイス上の **Office** ファイルにアクセスする方法を管理する] を展開し **、[Office** アプリのアイドル状態が発生した後にユーザーに再度サインインを要求する] が数分間に設定されている必要があります。 これは既定で 30 分です。 
  
1. ユーザーの iOS デバイスで、Outlookを開き、ユーザーの資格情報を使用Microsoft 365 Business Premiumサインインし、要求された場合は PIN を入力します。
    
2. Outlook の受信トレイが表示されます。iOS デバイスを少なくとも 30 分間 (またはポリシーに設定した時間よりも長い時間) 触れずに放置します。多くの場合、デバイスが暗くなります。
    
3. iOS Outlookにアクセスします。
    
4. もう一度アクセスする前に、PIN の入力を求Outlookされます。
    
### <a name="validate-protect-work-files-with-encryption"></a>暗号化で作業ファイルの保護を検証する

[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **暗号化を使用して作業ファイルを保護する**] が **オン**、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オフ** に設定されていることを確認します。
  
1. ユーザーの iOS デバイスで、Outlookを開き、ユーザーの資格情報を使用Microsoft 365 Business Premiumサインインし、要求された場合は PIN を入力します。
    
2. いくつかの画像ファイルの添付ファイルを含む電子メールを開きます。
    
3. 添付ファイルをタップし、その下にある [ **保存**] オプションをタップします。 
    
4. ホーム画面から **写真** アプリを開きます。保存され暗号化された写真 (複数の画像の添付ファイルを保存した場合は複数の写真) が表示されます。 
    
---

