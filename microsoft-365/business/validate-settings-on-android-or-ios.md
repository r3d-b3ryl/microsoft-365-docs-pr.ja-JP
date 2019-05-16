---
title: Android または iOS デバイスのアプリ保護設定を検証する
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
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 'Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.  '
ms.openlocfilehash: d4ed70290b21b40ca9ecd5601954c429a27dc528
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072372"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Android または iOS デバイスのアプリ保護設定を検証する

タブの指示に従って、Android または iOS デバイスのアプリ保護設定を検証します。
  
## <a name="androidtab"></a>[Android](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>ユーザーのデバイスでアプリ保護設定が機能していることを確認する

[Android デバイス用のアプリの構成を設定](app-protection-settings-for-android-and-ios.md) し、アプリを保護したら、次の手順に従って、選択した設定が機能することを検証できます。 
  
最初に、ポリシーが検証するアプリに適用されていることを確認します。
  
1. In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.
    
2. セットアップ時に作成した設定の **Android 用のアプリケーション ポリシー**、または作成した別のポリシーを選び、Outlook などにそのポリシーが適用されていることを確認します。 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Office アプリにアクセスするのに必要な PIN または指紋認証を検証する

[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**] が **オン**に設定されていることを確認します。
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインします。
    
2. PIN の入力または指紋認証も求められます。
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>[PIN をリセットする試行の失敗回数] を検証する

[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **PIN をリセットする試行の失敗回数**] に何らかの回数が設定されていることを確認します。既定値は 5 です。 
  
1. ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインします。
    
2. ポリシーで指定された回数だけ不正な PIN を入力します。PIN をリセットする [ **PIN の試行回数の上限に達しました**] というメッセージが表示されます。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. [ **PIN のリセット**] を押します。ユーザーの Microsoft 365 Business 資格情報を使用してサインインするように求められ、次に新しい PIN の設定を求められます。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>[OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する] を検証する

[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オン**に設定されていることを確認します。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。
    
2. 添付ファイルを含むメールを開き、添付ファイルの情報の横にある下矢印アイコンをタップします。
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    画面の下部に [ **デバイスに保存できません**] が表示されます。 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > この時点では、OneDrive for Business への保存は Android に有効になっていないため、ローカルに保存がブロックされていることだけが確認できます。 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>[Office アプリがアイドルになってからユーザーにもう一度サインインを求める時間] を確認する

[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある**] に何らかの分数が設定されていることを確認します。既定値は 30 分です。 
  
1. ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。
    
2. Outlook の受信トレイが表示されます。Android デバイスを少なくとも 30 分間 (またはポリシーに設定した時間よりも長い時間) 触れずにアイドル状態にします。多くの場合、デバイスが暗くなります。
    
3. Android デバイスで Outlook に再アクセスします。
    
4. Outlook をもう一度アクセスする前に、PIN を入力するように求められます。
    
### <a name="validate-protect-work-files-with-encryption"></a>暗号化で作業ファイルの保護を検証する

[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **暗号化を使用して作業ファイルを保護する**] が **オン**、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オフ**に設定されていることを確認します。
  
1. ユーザーの Android デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。
    
2. いくつかの画像の添付ファイルを含むメールを開きます。
    
3. 添付ファイルの情報の横にある下矢印アイコンをタップして、添付ファイルを保存します。
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Outlook にデバイス上の写真、メディア、ファイルへのアクセスを許可するように求められる場合があります。[ **許可**] をタップします。
    
5. 画面の下部で、[ **デバイスに保存する**] を選び、 **ギャラリー** アプリを開きます。 
    
6. リストに暗号化された写真 (複数の画像の添付ファイルを保存した場合は複数の写真) が表示されます。これは、白い感嘆符が入った白い円が中心にある灰色の四角形として写真リストに表示される場合があります。
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="iostab"></a>[iOS](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>ユーザーのデバイスでアプリ保護設定が機能していることを確認する

[iOS デバイス用のアプリの構成を設定](app-protection-settings-for-android-and-ios.md) し、アプリを保護したら、次の手順に従って、選択した設定が機能することを検証できます。 
  
最初に、ポリシーが検証するアプリに適用されていることを確認します。
  
1. In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.
    
2. セットアップ時に作成した設定に **iOS アプリケーション ポリシー**または独自に作成した別のポリシーを選び、Outlook などにそれが適用されていることを確認します。 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Office アプリにアクセスするのに必要な PIN を検証する

[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**] が **オン**に設定されていることを確認します。
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインします。
    
2. PIN の入力または指紋認証も求められます。
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>[PIN をリセットする試行の失敗回数] を検証する

[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **PIN をリセットする試行の失敗回数**] に何らかの回数が設定されていることを確認します。既定値は 5 です。 
  
1. ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインします。
    
2. ポリシーで指定された回数だけ不正な PIN を入力します。PIN をリセットする [ **PIN の試行回数の上限に達しました**] というメッセージが表示されます。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. [ **OK**] を押します。ユーザーの Microsoft 365 Business 資格情報を使用してサインインするように求められ、次に新しい PIN の設定を求められます。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>[OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する] を検証する

[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オン**に設定されていることを確認します。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。
    
2. 添付ファイルを含むメールを開き、添付ファイルを開き、画面の下部で [ **保存**] を選びます。 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. OneDrive for Business のオプションのみが表示されます。表示されない場合は、[ **アカウントの追加**] をタップして、[ **ストレージ アカウントの追加**] 画面から [ **OneDrive for Business**] を選びます。求められたら、エンド ユーザーの Microsoft 365 Business を入力してサインインします。 
    
    [ **保存**] をタップして、[ **OneDrive for Business**] を選びます。
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>[Office アプリがアイドルになってからユーザーにもう一度サインインを求める時間] を確認する

[ **ポリシーの編集**] ウィンドウで、[ **Office ドキュメントのアクセス制御**] の横の [ **編集**] を選び、[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] を展開し、[ **次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある**] に何らかの分数が設定されていることを確認します。既定値は 30 分です。 
  
1. ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。
    
2. Outlook の受信トレイが表示されます。iOS デバイスを少なくとも 30 分間 (またはポリシーに設定した時間よりも長い時間) 触れずに放置します。多くの場合、デバイスが暗くなります。
    
3. iOS デバイスで Outlook に再アクセスします。
    
4. Outlook をもう一度アクセスする前に、PIN を入力するように求められます。
    
### <a name="validate-protect-work-files-with-encryption"></a>暗号化で作業ファイルの保護を検証する

[ **ポリシーの編集**] ウィンドウで、[ **デバイスの紛失または盗難に対する保護**] の横の [ **編集**] を選び、[ **デバイスの紛失または盗難時の作業ファイルの保護**] を展開し、[ **暗号化を使用して作業ファイルを保護する**] が **オン**、[ **OneDrive for Business へすべての作業ファイルを保存するようユーザーに強制する**] が **オフ**に設定されていることを確認します。
  
1. ユーザーの iOS デバイスで、Outlook を開き、ユーザーの Microsoft 365 Business 資格情報を使ってサインインし、求められたら PIN を入力します。
    
2. いくつかの画像の添付ファイルを含むメールを開きます。
    
3. 添付ファイルをタップし、その下にある [ **保存**] オプションをタップします。 
    
4. ホーム画面から **写真**アプリを開きます。保存され暗号化された写真 (複数の画像の添付ファイルを保存した場合は複数の写真) が表示されます。 
    
---

