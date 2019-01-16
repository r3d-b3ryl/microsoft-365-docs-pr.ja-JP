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
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: アプリケーション管理ポリシーを作成し、10 の Windows デバイス上の作業ファイルを保護する方法について説明します。
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869201"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Windows 10 デバイスのアプリケーション保護設定を設定する

## <a name="create-an-app-management-policy-for-windows-10"></a>Windows 10 用のアプリの管理ポリシーを作成する

ユーザーが作業タスクを実行する個人の Windows 10 デバイスを持っている場合、それらのデバイスでもデータを保護することができます。
  
1. グローバル管理者の資格情報を使用して、[Microsoft 365 Business](https://portal.office.com) にサインインします。[ **管理者** ] タイルを選び、管理センターに移動します。 
    
2. 管理ポータルの [ **デバイス ポリシー**] カードで、[ **ポリシーの追加**] を選びます。
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 
    
4. [ **ポリシーの種類**] で、[ **Windows 10 のアプリケーション管理**] を選びます。
    
5. [* * デバイス ・ タイプ * *、または**会社が所有する****個人**のいずれかを選択します。
    
6. [ **作業ファイルを暗号化する**] が自動的にオンになります。 
    
7. 作業ファイルをユーザーの PC に保存させたくない場合は、[ **ユーザーが会社のデータを個人用のファイルにコピーすることを防止し、作業ファイルを OneDrive for Business に保存するようユーザーに強制します**] を **オン**に設定します。 
    
8. **ユーザーがデバイス上の Office ファイルにアクセスする方法の管理**を展開し\>どのようにしたい設定を構成します。既定で**オフ**になって**ユーザーがモバイル デバイスでの Office のデバイスにアクセスする方法を管理**するが、有効**に**して既定値を受け入れることをお勧めします。詳細については、[利用可能な設定](protection-settings-for-windows-10-devices.md#bkmk_settings)を参照してください。 
    
    [ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。 
    
9. [ **Windows デバイスでデータを回復します**] を展開し、 **オン**にすることをお勧めします。
    
    データ回復エージェント証明書を先に作成してから、その場所を参照します。手順については、「[暗号化ファイル システム (EFS) データ回復エージェント (DRA) 証明書の作成と検証](https://go.microsoft.com/fwlink/p/?linkid=853700)」を参照してください。
    
    既定では、デバイスに保存されていてユーザーのプロファイルに関連付けられている秘密キーを使用して、作業ファイルの暗号化が行われます。該当するユーザーのみがファイル開き、暗号化を解除することができます。ただし、デバイスが失われたり、ユーザーが削除されたりした場合、ファイルを暗号化された状態に留めておくことができます。管理者は、ファイルの暗号化を解除するために、データ回復エージェント (DRA) 証明書を使用できます。
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. その他のドメインまたは SharePoint Online の場所を追加してリストに表示されているアプリ内のすべてのファイルが確実に保護されるようにする場合は、[ **その他のネットワークとクラウドの場所の保護**] を展開します。いずれかのフィールドに複数の項目を入力する必要がある場合は、項目間にセミコロン (;) を使用します。 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. 次に**にこれらの設定が表示されますか?****変更**を選択して、これらの設定が表示されますユーザー セキュリティ グループを選択の既定の**すべてのユーザー**セキュリティ グループを使用しない場合は、 \> **を選択**します。
    
12. 最後に、[ **追加**] を選択してポリシーを保存し、それをデバイスに割り当てます。 
    
## <a name="available-settings"></a>利用可能な設定

次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。
  
詳細については、「[Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法](map-protection-features-to-intune-settings.md)」をご覧ください。
  
|**設定**|**説明**|
|:-----|:-----|
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  <br/> |この設定を **オン**にすると、ユーザーは、ユーザー名とパスワードの他に、別の認証フォームを提供しないと、モバイル デバイスで Office アプリを使用できません。  <br/> |
|ログインに指定の回数失敗した場合に PIN をリセットする  <br/> |承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。  <br/> |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある  <br/> |この設定は、もう一度サインインを求められるまで、どのくらいユーザーをアイドル状態にできるかを指定します。  <br/> |
   

