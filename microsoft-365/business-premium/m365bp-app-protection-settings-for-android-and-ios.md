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
ms.localizationpriority: high
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
description: アプリ管理ポリシーを作成、編集、または削除し、Android または iOS デバイス上の作業ファイルを保護する方法について説明します。
ms.openlocfilehash: 263c85ed8b3ac236e4fdefa333fecccdc328a0b7
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65622186"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Android または iOS デバイスのアプリ保護設定を設定する

この記事は Microsoft 365 Business Premium に適用されます。

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../business-premium/m365bp-app-protection-settings-for-android-and-ios.md)。

## <a name="watch-secure-office-apps-on-ios"></a>ウォッチ: iOS 上の Office アプリをセキュリティで保護する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

モバイル端末を使用するユーザーがサインインする場合に、暗証番号 (PIN) または指紋の入力を必須にし、デバイスに保存されている作業ファイルの暗号化も行う、ユーザー アクセス ポリシーを設定できます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>にサインインします。

1. [**ポリシー**] で [**ポリシーの追加**] を選択します。

1. [**ポリシーの追加**] ウィンドウで、[**ポリシー名**] に名前を入力し、[**ポリシーの種類**] から目的のポリシーの種類を選択します。

1. [**デバイスの紛失または盗難時の作業ファイルの保護**] をオンにし、次の 3 つの設定がオンになっていることを確認します。
 
    - **すべての仕事用ファイルを OneDrive for Business に保存するようユーザーに強制する**
  
    - **仕事用ファイルを暗号化する**

1. [**ユーザーによるモバイル デバイスでの Office ファイルのアクセス方法の管理**] をオンにし、設定がオンになっているか、各アイテムに設定されていることを確認します。

1. [**次のアプリのファイルが保護されます**] で、モバイル デバイス上の保護する Office アプリを選択します。

1. [**これらの設定の該当ユーザー**] では、すべてのユーザーが既定で選択されていますが、[**変更**] を選択して、作成したセキュリティ グループを選択することもできます。

1. ポリシーの作成を完了するには、[**追加**] を選択します。

1. [**ポリシーの追加**] ページで [**閉じる**] を選択します。

1. 管理センターのホーム ページで、[**ポリシー**] を選択して [**ポリシー**] ページのポリシーを表示し、新しいポリシーが追加されたことを確認します。

## <a name="create-an-app-management-policy"></a>アプリの管理ポリシーを作成する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

1. 左側のナビゲーションで、**[デバイス]** \> **[ポリシー]**\>**[追加]** を選択します。
  
1. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。

1. [**ポリシーの種類**] で、作成するポリシーのセットに応じて、[**Android アプリケーション管理**] または [**iOS アプリケーション管理**] を選びます。

1. [**デバイスの紛失または盗難時の作業ファイルの保護**]、[**ユーザーによるモバイル デバイスでの Office ファイルへのアクセス方法の管理**] の順に展開し、好みの設定を構成します。[**ユーザーによるモバイル デバイスでの Office ファイルのアクセス方法の管理**] は既定で **オフ** になっていますが、**オン** にして既定値を受け入れることをお勧めします。詳細については、「[利用可能な設定](#available-settings)」をご覧ください。

    [**既定の設定の復元**] リンクを使用すれば、既定の設定にいつでも戻すことができます。

:::image type="content" source="Media/m365bp-add-policy.png" alt-text="アプリケーション管理を使用してポリシーを作成します。":::
  
1. 次に、**これらの設定を適用するユーザー** を決めます。 既定の **All Users** セキュリティ グループを使用しない場合は、[**変更**] を選び、これらの設定を適用するセキュリティ グループを選択し \> **[選択]** を選びます。

1. 最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。

## <a name="edit-an-app-management-policy"></a>アプリの管理ポリシーを編集する

1. **ポリシー** カードで、[**ポリシーの編集**] を選びます。

1. [**ポリシーの編集**] ウィンドウで、変更するポリシーを選択します。

1. 各設定の横にある [**編集**] を選び、ポリシーの値を変更します。値を変更すると、その値がポリシーに自動的に保存されます。

1. 完了したら、[**ポリシーを編集**] ペインを閉じます。

## <a name="delete-an-app-management-policy"></a>アプリの管理ポリシーを削除する

1. **[ポリシー]** ページでポリシーを選択し、**[削除]** をクリックします。

1. [**ポリシーの削除**] ペインで、[**確認**] を選び、選択したポリシー (複数可) を削除します。 

## <a name="available-settings"></a>利用可能な設定

次の表は、デバイス上の作業ファイルを保護するために利用可能な設定と、ユーザーが自分のモバイル デバイスから Office ファイルにアクセスする方法を制御する設定に関する詳細情報を示しています。
  
 詳細については、「[Microsoft 365 Business Premium の保護機能を Intune の設定に対応付ける方法](m365bp-map-protection-features-to-intune-settings.md)」をご覧ください。 
  
### <a name="settings-that-protect-work-files"></a>作業ファイルを保護する設定

次の設定は、ユーザーのデバイスが紛失したり盗難された場合に、作業ファイルを保護するために使用できます。


|Setting  |説明  |
|:-----|:-----|
|この日数後、非アクティブなデバイスから作業ファイルを削除する  |ここで指定した日数の間デバイスが使用されていない場合、デバイスに保存されているすべての作業ファイルは自動的に削除されます。  |
|ユーザーにすべての作業ファイルを OneDrive for Business に強制的に保存させる  |この設定を **オン** にすると、作業ファイルの使用可能な保存場所は OneDrive for Business のみになります。  |
|作業ファイルの暗号化  |作業ファイルが暗号化によって保護されるように、この設定は常に **オン** にします。デバイスが紛失したり盗難された場合でも、企業データが読まれることはありません。    |

### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定

次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。

|Setting  |説明  |
|:-----|:-----|
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  |この設定が **オン** の場合、ユーザーは、ユーザー名とパスワードの他に、別の認証フォームを提供しないと、モバイル デバイスで Office アプリを使用できません。|
|ログインに指定の回数失敗した場合に PIN をリセットする  |承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。  |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある  |この設定は、もう一度サインインを求められるまで、どのくらいユーザーをアイドル状態にできるかを指定します。  |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  |賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。これは、ユーザーがオペレーティング システムを変更できるため、デバイスがマルウェアの危険にさらされる可能性が高くなることを意味します。この設定を **オン** にすると、これらのデバイスはブロックされます。    |
|Office アプリのコンテンツを個人のアプリにコピーすることをユーザーに許可しない  |これは既定で許可していますが、設定が **オン** の場合、ユーザーは作業ファイル内の情報を個人のファイルにコピーできます。この設定が **オフ** の場合、ユーザーは職場アカウントから個人用アプリまたは個人のアカウントに情報をコピーすることはできません。    |

## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)