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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365 を使用して 1 つ以上のメール アカウントへのメール転送を設定します。
ms.openlocfilehash: d7c9a37a066bd53e541cf623c1953fb572827b61
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197865"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Microsoft 365 でのメール転送の構成

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。

::: moniker-end

組織の管理者として、ユーザーのメールボックスのメール転送をセットアップする会社の要件がある場合があります。 メール転送を利用すれば、あるユーザーのメールボックスに送信されたメール メッセージを組織内外の別のユーザーのメールボックスに転送できます。

> [!IMPORTANT]
> 送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。 詳細については [、「Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)で外部メールの自動転送を制御する」を参照してください。

## <a name="configure-email-forwarding"></a>メール転送を構成する

メール転送を設定する前に、次の点に注意してください。

- メール転送を設定すると **、受信メールボックス** に送信された新しいメールだけが転送されます。

- メール転送では、From アカウント  *に*  ライセンスが必要です。 ユーザーが組織を去ったことによりメール転送を設定する場合には、別の方法として[そのユーザーのメールボックスを共有メールボックス変換](convert-user-mailbox-to-shared-mailbox.md)することです。 こうすることで、複数のユーザーがそのメールボックスにアクセスできます。 ただし、共有メールボックスは 50 GB 以下にする必要があります。

これらの手順を実行するには、Microsoft 365 の Exchange 管理者またはグローバル管理者である必要があります。 詳細については、「管理役割について [」を参照してください](../add-users/about-admin-roles.md)。

::: moniker range="o365-worldwide"

1. 管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=834822)** します。

2. メールを転送してプロパティ ページを開くユーザーの名前を選択します。

3. [メール] **タブで** 、[メール転送の **管理] を選択します**。

4. [電子メールの転送]ページで、[このメールボックスに送信されたメールを転送する] を選択し、転送先のアドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 [**変更の保存**] を選択します。

    **複数の電子メール アドレスに転送するには**、ユーザーに Outlook でアドレスに転送するルールを設定する必要があります。 詳細については、「ルールを使用して [メッセージを自動的に転送する」を参照してください](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

     または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。

5. 自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない!  この操作を行った場合、メール転送は停止します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=847686)** します。

2. メールを転送してプロパティ ページを開くユーザーの名前を選択します。

3. [メール **の設定]** を展開し、[メール転送] セクション **で** [編集] を **選択します**。

4. [メール転送] ページで、トグルを **[オン**] に設定し、転送先アドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 **[保存]** を選択します。

   **複数の電子メール アドレスに転送するには**、ユーザーに Outlook でアドレスに転送するルールを設定する必要があります。 詳細については、「ルールを使用して [メッセージを自動的に転送する」を参照してください](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。

5. 自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない!  この操作を行った場合、メール転送は停止します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=850628)** します。

2. メールを転送してプロパティ ページを開くユーザーの名前を選択します。

3. [メール **の設定]** を展開し、[メール転送] セクション **で** [編集] を **選択します**。

4. [メール転送] ページで、トグルを **[オン**] に設定し、転送先アドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 **[保存]** を選択します。

   **複数の電子メール アドレスに転送するには**、ユーザーに Outlook でアドレスに転送するルールを設定する必要があります。 詳細については、「ルールを使用して [メッセージを自動的に転送する」を参照してください](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。

5. 自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない!  この操作を行った場合、メール転送は停止します。

::: moniker-end