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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: メール転送を使用すると、Microsoft 365 ユーザー メールボックスに送信された電子メール メッセージを組織内または外部の別のメールボックスに転送できます。
ms.openlocfilehash: 5522d9202732ca54d1a395a83e99ae2442b68eb9
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766574"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Microsoft 365でメール転送を構成する

組織の管理者として、ユーザーのメールボックスの電子メール転送を設定するための会社の要件がある場合があります。 メール転送を利用すれば、あるユーザーのメールボックスに送信されたメール メッセージを組織内外の別のユーザーのメールボックスに転送できます。

> [!IMPORTANT]
> 送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。 詳細については、「[Microsoft 365での自動外部メール転送を制御する](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)」を参照してください。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="configure-email-forwarding"></a>メール転送を構成する

メール転送を設定する前に、次の点に注意してください:

- リモート ドメイン上のユーザーにメッセージが自動的に転送されることを許可または禁止します。 詳細については、「 [リモート ドメインの管理](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) 」を参照してください。

- メール転送を設定すると、*メールボックスから* 送信された **新しい** メールのみが転送されます。

- メール転送では、  *from*  アカウントにライセンスが必要です。 ユーザーが組織を去ったことによりメール転送を設定する場合には、別の方法として[そのユーザーのメールボックスを共有メールボックス変換](convert-user-mailbox-to-shared-mailbox.md)することです。 こうすることで、複数のユーザーがそのメールボックスにアクセスできます。 ただし、共有メールボックスは 50 GB 以下にする必要があります。

これらの手順を実行するには、Microsoft 365のExchange管理者またはグローバル管理者である必要があります。 詳細については、「 [管理者ロールについて](../add-users/about-admin-roles.md)」のトピックを参照してください。

::: moniker range="o365-worldwide"

1. 管理センターで、[ **ユーザー** \> **[アクティブ ユーザー](https://go.microsoft.com/fwlink/p/?linkid=834822)** ] ページに移動します。

2. 電子メールを転送するユーザーの名前を選択し、プロパティ ページを開きます。

3. [ **メール** ] タブで、[ **メール転送の管理**] を選択します。

4. [電子メール転送] ページで、[ **このメールボックスに送信されたすべてのメールを転送する**] を選択し、転送先のアドレスを入力して、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 **[変更の保存]** を選択します。

    **複数の電子メール アドレスに転送するには、ユーザー** に、アドレスに転送するルールをOutlookに設定するように求めることができます。 
    
    1.  **outlook** > **Home** >**Rules を** 開>ルール **の管理&アラートを** 選択する  
    1. 受信したメッセージの **[新しい規則** > **の選択の適用規則** ] を一覧の一番下付近で選択し、[ **次へ**] をクリックします。
    1. [ **はい** ] をクリックすると、受信したすべてのメッセージにこのルールが適用されます。 
    1. 次の一覧で、アクションを **ユーザーまたはパブリック グループにリダイレクト** し、**その他のルールの処理を停止** するアクションを選択します
    1. ウィンドウの下部にある下線付きフレーズ **のユーザーまたはパブリック グループ** をクリックします。
    1. [宛先] フィールドにメールを転送する **メール アドレス** を入力し、[ **OK**] をクリックします。
    1. **[完了]** を選択する
    

     または、管理センターで [配布グループを作成](../setup/create-distribution-lists.md)し、 [アドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順を使用して DL を指すように転送を設定します。

5. 転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。  その場合、メール転送は停止します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[ **ユーザー** \> **[アクティブ ユーザー](https://go.microsoft.com/fwlink/p/?linkid=850628)** ] ページに移動します。

2. メールを転送してプロパティ ページを開くユーザーの名前を選択します。

3. [ **メール設定]** を展開し、[ **電子メール転送** ] セクションで **[編集]** を選択します。

4. メール転送ページで、トグルを **[オン]** に設定し、転送先アドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 **[保存]** を選択します。

   **複数の電子メール アドレスに転送するには、ユーザー** に、アドレスに転送するルールをOutlookに設定するように求めることができます。 詳細については、「 [ルールを使用してメッセージを自動的に転送する](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。

   または、管理センターで [配布グループを作成](../setup/create-distribution-lists.md)し、 [アドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順を使用して DL を指すように転送を設定します。

5. 転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。 その場合、メール転送は停止します。

::: moniker-end

## <a name="related-content"></a>関連コンテンツ 

[共有メールボックス GWT を作成する](../email/create-a-shared-mailbox.md) (記事)\
[別のアドレスからメールを送信する](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (記事)\
[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (記事)\
[Microsoft 365の自動外部メール転送を制御する](/microsoft-365/security/office-365-security/external-email-forwarding) (記事)


