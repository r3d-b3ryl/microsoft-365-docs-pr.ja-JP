---
title: メール転送を構成する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: メール転送を使用すると、ユーザー メールボックスに送信Microsoft 365メール メッセージを組織の内部または外部の別のメールボックスに転送できます。
ms.openlocfilehash: 77f374623244708c0b2bf1ecdae1af0cbebc9812
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176560"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>メール転送の構成 (Microsoft 365

組織の管理者として、ユーザーのメールボックスのメール転送をセットアップする会社の要件がある場合があります。 メール転送を利用すれば、あるユーザーのメールボックスに送信されたメール メッセージを組織内外の別のユーザーのメールボックスに転送できます。

> [!IMPORTANT]
> 送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。 詳細については、「Control automatic external email forwarding in Microsoft 365 」[を参照してください](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。

## <a name="configure-email-forwarding"></a>メール転送を構成する

メール転送を設定する前に、次の点に注意してください。

- リモート ドメイン上のユーザーに自動的に転送されたメッセージの送信を許可します。 詳細については [、「リモート ドメインの管理」](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) を参照してください。

- メール転送を設定すると **、受信メールボックス** に送信された新しいメールだけが転送されます。

- メール転送では、From アカウント  *に*  ライセンスが必要です。 ユーザーが組織を去ったことによりメール転送を設定する場合には、別の方法として[そのユーザーのメールボックスを共有メールボックス変換](convert-user-mailbox-to-shared-mailbox.md)することです。 こうすることで、複数のユーザーがそのメールボックスにアクセスできます。 ただし、共有メールボックスは 50 GB 以下にする必要があります。

これらの手順を実行するには、Exchange管理者またはグローバル管理者Microsoft 365必要があります。 詳細については、「管理役割について [」を参照してください](../add-users/about-admin-roles.md)。

::: moniker range="o365-worldwide"

1. 管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=834822)** します。

2. メールを転送するユーザーの名前を選択し、[プロパティ] ページを開きます。

3. [メール] **タブで** 、[メール転送の **管理] を選択します**。

4. [電子メールの転送]ページで、[このメールボックスに送信されたメールを転送する] を選択し、転送先のアドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 [**変更の保存**] を選択します。

    **複数の電子メール アドレスに転送するには**、ユーザーに対して、アドレスに転送するルールを設定Outlookを設定できます。 
    
    1.  Outlook **ホーム** > **ルールを** > **開く >** **[ルールの管理] &アラート**  
    1. [ **新しいルール** > **] [適用するルール] を選択して** 、リストの下部近くに表示されるメッセージにルールを適用し、[次へ] を **クリックします**。
    1. [ **はい** ] をクリックします。このルールは、受信したメッセージに適用されます。 
    1. 次のリストで、ユーザーまたはパブリック グループにリダイレクトするアクションを選択 **し** 、その他 **のルールの処理を停止する**
    1. ウィンドウの下部にある下 **線付き語句の** ユーザーまたはパブリック グループをクリックします。
    1. [転送先 **] フィールドに** メールを転送するメール アドレスを入力し **、[OK] をクリックします**。
    1. [完了] **の選択**
    

     または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。

5. 自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない!  この操作を行った場合、メール転送は停止します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=847686)** します。

2. メールを転送してプロパティ ページを開くユーザーの名前を選択します。

3. [メール **の設定]** を展開し、[メール転送] セクション **で** [編集] を **選択します**。

4. [メール転送] ページで、トグルを **[オン**] に設定し、転送先アドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 **[保存]** を選択します。

   **複数の電子メール アドレスに転送するには**、ユーザーに対して、アドレスに転送するルールを設定Outlookを設定できます。 詳細については、「ルールを使用して [メッセージを自動的に転送する」を参照してください](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。

5. 自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない!  この操作を行った場合、メール転送は停止します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=850628)** します。

2. メールを転送してプロパティ ページを開くユーザーの名前を選択します。

3. [メール **の設定]** を展開し、[メール転送] セクション **で** [編集] を **選択します**。

4. [メール転送] ページで、トグルを **[オン**] に設定し、転送先アドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 **[保存]** を選択します。

   **複数の電子メール アドレスに転送するには**、ユーザーに対して、アドレスに転送するルールを設定Outlookを設定できます。 詳細については、「ルールを使用して [メッセージを自動的に転送する」を参照してください](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。

5. 自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない! この操作を行った場合、メール転送は停止します。

::: moniker-end

## <a name="related-content"></a>関連コンテンツ 

[共有メールボックスの作成](../email/create-a-shared-mailbox.md) (記事)\
[別のアドレスからメールを送信](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) する (記事)\
[外部メールの自動転送を制御Microsoft 365](/security/office-365-security/external-email-forwarding?view=o365-worldwide) (記事)\
[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (記事)
