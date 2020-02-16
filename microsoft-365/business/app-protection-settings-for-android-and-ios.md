---
title: Android または iOS デバイスのアプリ保護設定を設定する
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: アプリの管理ポリシーを作成、編集、または削除する方法と、Android または iOS デバイスで作業ファイルを保護する方法について説明します。
ms.openlocfilehash: f4366230805c50fe82183431e3bd2bdfa9fddd68
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068651"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Android または iOS デバイスのアプリ保護設定を設定する

![をhttps://aka.ms/aboutM365preview指すバナー。](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a>アプリの管理ポリシーを作成する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。 
    
2. 左側のナビゲーションで、[**デバイス** \> **ポリシー** \>の**追加**] を選択します。
  
3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 
    
4. 作成するポリシーのセットに応じて、[**ポリシーの種類**] で [ **Android 用のアプリケーション管理**] または [ **iOS 用アプリケーション管理**] を選択します。 
    
5. **デバイスが紛失または盗難にあったときに [作業ファイルの保護**] を展開し、**ユーザーがモバイルデバイスで Office ファイルにアクセスする方法を管理**します。 設定を構成してください。 **ユーザーがモバイルデバイスで Office ファイルにアクセスする方法を管理**する既定の設定は**無効**になっていますが、オン**に**して既定値をそのまま使用することをお勧めします。 詳細については、「[使用可能な設定](#available-settings)」を参照してください。 
    
    [ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Next decide **Who will get these settings?** 既定の [**すべてのユーザー** ] セキュリティグループを使用しない場合は、[**変更**] を選択し、これら\> **の設定を**取得するセキュリティグループを選択します。
    
7. 最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。 
    
## <a name="edit-an-app-management-policy"></a>アプリの管理ポリシーを編集する

1. [**ポリシー** ] カードで、[**ポリシーの編集**] を選択します。
    
2. [ **ポリシーの編集**] ウィンドウで、変更するポリシーを選択します。 
    
3. 各設定の横にある [ **編集**] を選び、ポリシーの値を変更します。 値を変更すると、ポリシーに自動的に保存されます。
    
4. 完了したら、[ポリシーの**編集**] ウィンドウを閉じます。 
    
## <a name="delete-an-app-management-policy"></a>アプリの管理ポリシーを削除する

1. [**ポリシー** ] ページで、ポリシーを選択してから**削除**します。
    
2. [**ポリシーの削除**] ウィンドウで、[**確認**] を選択して、選択したポリシーまたはポリシーを削除します。 
    
## <a name="available-settings"></a>利用可能な設定

次の表では、デバイス上の作業ファイルを保護するために使用できる設定に関する詳細情報と、ユーザーがモバイルデバイスから Office ファイルにアクセスする方法を制御する設定について詳しく説明します。
  
 詳細については、「[Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法](map-protection-features-to-intune-settings.md)」をご覧ください。 
  
### <a name="settings-that-protect-work-files"></a>作業ファイルを保護する設定

次の設定は、ユーザーのデバイスが紛失したり盗難された場合に、作業ファイルを保護するために使用できます。
  
|||
|:-----|:-----|
|設定  <br/> |説明  <br/> |
|この日数後、非アクティブなデバイスから作業ファイルを削除する  <br/> |指定した日数にデバイスを使用しない場合は、デバイスに保存されているすべての作業ファイルが自動的に削除されます。  <br/> |
|ユーザーにすべての作業ファイルを OneDrive for Business に強制的に保存させる  <br/> |この設定が**オンに**なっている場合、作業ファイルの保存場所として使用できるのは、OneDrive for business のみです。  <br/> |
|作業ファイルの暗号化  <br/> |作業ファイルが暗号化によって保護されるように、この設定は常に **オン**にします。 デバイスが紛失または盗難にあった場合でも、会社のデータを読み取ることはできません。  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定

次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。
  
|||
|:-----|:-----|
|設定  <br/> |説明  <br/> |
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  <br/> |この設定が**オンになって**いる場合、ユーザーのモバイルデバイスで Office アプリを使用できるようにするには、ユーザー名とパスワードに加えて、別の形式の認証を提供する必要があります。<br/> |
|ログインに指定の回数失敗した場合に PIN をリセットする  <br/> |承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。  <br/> |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある  <br/> |この設定により、ユーザーがもう一度サインインするように求めるメッセージが表示されるまでの待機時間を指定できます。  <br/> |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  <br/> |賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。これは、ユーザーがオペレーティング システムを変更できるため、デバイスがマルウェアの危険にさらされる可能性が高くなることを意味します。この設定を **オン**にすると、これらのデバイスはブロックされます。  <br/> |
|Office アプリのコンテンツを個人のアプリにコピーすることをユーザーに許可する  <br/> |これは既定で許可していますが、設定が **オン**の場合、ユーザーは作業ファイル内の情報を個人のファイルにコピーできます。 この設定が **オフ** の場合、ユーザーは職場アカウントから個人用アプリまたは個人のアカウントに情報をコピーすることはできません。  <br/> |
