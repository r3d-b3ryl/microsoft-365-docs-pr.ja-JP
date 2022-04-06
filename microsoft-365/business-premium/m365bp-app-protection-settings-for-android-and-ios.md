---
title: Android または iOS デバイスのアプリ保護設定を設定する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: アプリ管理ポリシーを作成、編集、または削除し、Android デバイスまたは iOS デバイス上の作業ファイルを保護する方法について説明します。
ms.openlocfilehash: 8965f70a19161be24f4276b8dac20c84865d9a71
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635337"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Android または iOS デバイスのアプリ保護設定を設定する

この記事は、ユーザーにMicrosoft 365 Business Premium。

> [!NOTE]
> Microsoft Defender for Business 2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../business-premium/m365bp-app-protection-settings-for-android-and-ios.md)。

## <a name="watch-secure-office-apps-on-ios"></a>ウォッチ: iOS Officeアプリをセキュリティで保護する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

モバイル ユーザーがサインインする PIN または指紋を入力する必要があるユーザー アクセス ポリシーを設定し、デバイスに保存されている作業ファイルも暗号化できます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>にサインインします。

2. [ポリシー **] で、[** ポリシーの **追加] を選択します**。

3. [ポリシー **の追加] ウィンドウ** で、[ポリシー名] に名前を入力し、[ポリシーの種類] で必要なポリシーの種類 **を選択します**。

4. [ユーザーが **モバイル デバイス上のOfficeファイル** にアクセスする方法を管理する] をオンにし、次の 3 つの設定がオンになっていることを確認します。
 
    - **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**
 
    - **デバイスが紛失または盗まれたときに作業ファイルを保護する**
 
    - **仕事用ファイルを暗号化する**

5. [**これらのアプリのファイルが保護されます**] で、モバイル Office保護するアプリを選択します。

6. [**Who** これらの設定が表示されます。既定ではすべてのユーザーが選択されますが、[変更] を選択して、作成したセキュリティ グループを選択できます。

7. ポリシーの作成を完了するには、[追加] を **選択します**。

8. [ポリシーの **追加] ページで** 、[閉じる] を **選択します**。

9. 管理センターのホーム ページで、[ポリシー] を選択し、[ポリシー] ページでポリシーを確認して、新しいポリシーが **追加されたと確認** します。

## <a name="create-an-app-management-policy"></a>アプリの管理ポリシーを作成する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。 
    
2. 左側のナビゲーションで、[デバイス ポリシー **の追加]** \> **を選択** \> **します**。
  
3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 
    
4. [ **ポリシーの種類]** で、作成するポリシーのセットに応じて、[ **Android** 用アプリケーション管理] または [ **iOS** 用アプリケーション管理] を選択します。 
    
5. [**デバイスが紛失または盗難された** 場合に作業ファイルを保護する] を展開し、ユーザーがモバイル デバイス上Officeファイルにアクセスする **方法を管理します**。 必要な設定を構成します。 **ユーザーがモバイル デバイス上Officeファイル** にアクセスする方法を管理する方法は既定では [オフ] ですが、オンにし、既定値を受け入れすることをお勧めします。 詳細については、「使用可能な設定 [」を参照してください](#available-settings)。 
    
    [ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。 
    
    ![スクリーンショット: [Android 用アプリケーション管理を使用してポリシーを作成する] が選択されています。](/media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Next decide **Who will get these settings?** 既定の [すべてのユーザー] セキュリティ グループを使用しない場合は、[変更] を選択し、これらの設定を取得するセキュリティ グループを選択\>**します。選択します**。
    
7. 最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。 
    
## <a name="edit-an-app-management-policy"></a>アプリの管理ポリシーを編集する

1. [ポリシー] **カードで、[** ポリシーの編集] **を選択します**。
    
2. [ **ポリシーの編集**] ウィンドウで、変更するポリシーを選択します。 
    
3. 各設定の横にある [ **編集**] を選び、ポリシーの値を変更します。 値を変更すると、ポリシーに自動的に保存されます。
    
4. 完了したら、[ポリシーの編集] **ウィンドウを閉** じます。 
    
## <a name="delete-an-app-management-policy"></a>アプリの管理ポリシーを削除する

1. [ポリシー **] ページで** ポリシーを選択し、[削除] を **選択します**。
    
2. [ポリシー **の削除] ウィンドウで** 、[ **確認] を選択** して、選択したポリシーまたはポリシーを削除します。 
    
## <a name="available-settings"></a>利用可能な設定

次の表に、デバイス上の作業ファイルを保護するために使用できる設定と、ユーザーがモバイル デバイスからファイルにアクセスする方法を制御するOffice詳細な情報を示します。
  
 詳細については、「How [do protection features in Microsoft 365 Business Premium設定にマップIntuneしてください](m365bp-map-protection-features-to-intune-settings.md)。 
  
### <a name="settings-that-protect-work-files"></a>作業ファイルを保護する設定

次の設定は、ユーザーのデバイスが紛失したり盗難された場合に、作業ファイルを保護するために使用できます。


|設定  |説明  |
|:-----|:-----|
|この日数後、非アクティブなデバイスから作業ファイルを削除する  |ここで指定した日数のデバイスを使用しない場合、デバイスに保存されている作業ファイルは自動的に削除されます。  |
|ユーザーにすべての作業ファイルを OneDrive for Business に強制的に保存させる  |この設定が **[オン] の場合**、作業ファイルに使用できる保存場所は、OneDrive for Business。  |
|作業ファイルの暗号化  |作業ファイルが暗号化によって保護されるように、この設定は常に **オン** にします。 デバイスが紛失または盗まれた場合でも、誰も会社のデータを読み取ることはありません。  |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定

次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。


|設定  |説明  |
|:-----|:-----|
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  |この設定が **[オン] の** 場合、ユーザーはモバイル デバイスでアプリを使用する前に、ユーザー名とパスワードに加えて、別Officeを提供する必要があります。|
|ログインに指定の回数失敗した場合に PIN をリセットする  |承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。  |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある  |この設定は、ユーザーが再度サインインするように求めるメッセージが表示されるまでアイドル状態にできる期間を決定します。  |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  |賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。これは、ユーザーがオペレーティング システムを変更できるため、デバイスがマルウェアの危険にさらされる可能性が高くなることを意味します。この設定を **オン** にすると、これらのデバイスはブロックされます。    |
|ユーザーがアプリから個人用アプリにコンテンツをコピー Office許可しない  |これは既定で許可していますが、設定が **オン** の場合、ユーザーは作業ファイル内の情報を個人のファイルにコピーできます。 この設定が **オフ** の場合、ユーザーは職場アカウントから個人用アプリまたは個人のアカウントに情報をコピーすることはできません。  |

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)