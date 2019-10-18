---
title: Android または iOS デバイスのアプリ保護設定を設定する
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
ms.openlocfilehash: a829cfbcb3209313a53e0a1406f5252d3d5580d8
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574740"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Android または iOS デバイスのアプリ保護設定を設定する

![をhttps://aka.ms/aboutM365preview指すバナー。](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a>アプリの管理ポリシーを作成する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。 
    
2. 左側のナビゲーションで、[**デバイス** \> **ポリシー** \>の**追加**] を選択します。
  
3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 
    
4. [ **ポリシーの種類**] で、作成するポリシーのセットに応じて、[ **Android アプリケーション管理**] または [ **iOS アプリケーション管理**] を選びます。 
    
5. Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. 詳細については、「[利用可能な設定](#available-settings)」を参照してください。 
    
    [ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
    
7. 最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。 
    
## <a name="edit-an-app-management-policy"></a>アプリの管理ポリシーを編集する

1. [**ポリシー** ] カードで、[**ポリシーの編集**] を選択します。
    
2. [ **ポリシーの編集**] ウィンドウで、変更するポリシーを選択します。 
    
3. 各設定の横にある [ **編集**] を選び、ポリシーの値を変更します。値を変更すると、その値がポリシーに自動的に保存されます。 
    
4. 完了したら、[ **ポリシーを編集**] ウィンドウを閉じます。 
    
## <a name="delete-an-app-management-policy"></a>アプリの管理ポリシーを削除する

1. [**ポリシー** ] ページで、ポリシーを選択してから**削除**します。
    
2. [**ポリシーの削除**] ウィンドウで、[**確認**] を選択して、選択したポリシーまたはポリシーを削除します。 
    
## <a name="available-settings"></a>利用可能な設定

次の表は、デバイス上の作業ファイルを保護するために利用可能な設定と、ユーザーが自分のモバイル デバイスから Office ファイルにアクセスする方法を制御する設定に関する詳細情報を示しています。
  
 詳細については、「 [Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法](map-protection-features-to-intune-settings.md)」をご覧ください。 
  
### <a name="settings-that-protect-work-files"></a>作業ファイルを保護する設定

次の設定は、ユーザーのデバイスが紛失したり盗難された場合に、作業ファイルを保護するために使用できます。
  
|||
|:-----|:-----|
|Setting  <br/> |説明  <br/> |
|この日数後、非アクティブなデバイスから作業ファイルを削除する  <br/> |ここで指定した日数の間デバイスが使用されなかった場合、デバイスに保存されているすべての作業ファイルは自動的に削除されます。  <br/> |
|ユーザーにすべての作業ファイルを OneDrive for Business に強制的に保存させる  <br/> |この設定を **オン**にすると、作業ファイルの使用可能な保存場所は OneDrive for Business のみになります。  <br/> |
|作業ファイルの暗号化  <br/> |作業ファイルが暗号化によって保護されるように、この設定は常に **オン**にします。デバイスが紛失したり盗難された場合でも、企業データが読まれることはありません。  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>ユーザーによるモバイル デバイスでの Office ファイルへのアクセスを制御する設定

次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。
  
|||
|:-----|:-----|
|Setting  <br/> |説明  <br/> |
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  <br/> |この設定を **オン**にすると、ユーザーは、ユーザー名とパスワードの他に、別の認証フォームを提供しないと、モバイル デバイスで Office アプリを使用できません。  <br/> |
|ログインに指定の回数失敗した場合に PIN をリセットする  <br/> |承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。  <br/> |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある  <br/> |この設定は、もう一度サインインを求められるまで、どのくらいユーザーをアイドル状態にできるかを指定します。  <br/> |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  <br/> |賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。これは、ユーザーがオペレーティング システムを変更できるため、デバイスがマルウェアの危険にさらされる可能性が高くなることを意味します。この設定を **オン**にすると、これらのデバイスはブロックされます。  <br/> |
|Office アプリのコンテンツを個人のアプリにコピーすることをユーザーに許可する  <br/> |これは既定で許可していますが、設定が **オン**の場合、ユーザーは作業ファイル内の情報を個人のファイルにコピーできます。 この設定が **オフ** の場合、ユーザーは職場アカウントから個人用アプリまたは個人のアカウントに情報をコピーすることはできません。  <br/> |
   

  

