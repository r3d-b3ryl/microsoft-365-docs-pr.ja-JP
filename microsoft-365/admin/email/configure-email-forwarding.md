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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365 を使用して、1つまたは複数の電子メールアカウントへのメール転送を設定します。
ms.openlocfilehash: c821d4363a053b432c4376d7b4fec4926df7b568
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560794"
---
# <a name="configure-email-forwarding"></a>メール転送を構成する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end
  
組織の管理者として、ユーザーのメールボックスの電子メール転送を設定するには、会社の要件がある場合があります。 メール転送を利用すれば、あるユーザーのメールボックスに送信されたメール メッセージを組織内外の別のユーザーのメールボックスに転送できます。

> [!IMPORTANT]
> 送信スパムフィルターポリシーを使用して、外部の受信者への自動転送を制御することができます。 詳細については、「 [Microsoft 365 での自動外部電子メール転送の制御](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)」を参照してください。

  
## <a name="configure-email-forwarding"></a>メール転送を構成する

 メール転送を設定する前に、次の点に注意してください。 

- メール転送を設定すると、*差出人* メールボックスに送信された **新しい** メールだけが転送されます。 
    
- 電子メール転送では、送信  *元*  アカウントにライセンスが必要です。 ユーザーが組織を去ったことによりメール転送を設定する場合には、別の方法として[そのユーザーのメールボックスを共有メールボックス変換](convert-user-mailbox-to-shared-mailbox.md)することです。 こうすることで、複数のユーザーがそのメールボックスにアクセスできます。 ただし、共有メールボックスは 50 GB 以下にする必要があります。 
    
これらの手順を実行するには、Microsoft 365 の Exchange 管理者または全体管理者である必要があります。 詳細については、「 [管理者の役割につい](../add-users/about-admin-roles.md)て」を参照してください。

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。
    
2. 転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。 
 
3. [ **メール** ] タブで、[ **メール転送の管理**] を選択します。 
  
4. [電子メールの転送] ページで、[ **このメールボックスに送信されたすべてのメールを転送する**] を選択し、転送先アドレスを入力して、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 [**変更の保存**] を選択します。
    
    **複数の電子メールアドレスに転送する** 場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。 詳細については、「 [ルールを使用してメッセージを自動的に転送する](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。 
    
     または、管理センターで [配布グループを作成](../setup/create-distribution-lists.md)し、 [そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。
    
5. 転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。  その場合、電子メールの転送は停止します。 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。 
    
2. 転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。 

3. [ **メールの設定**] を展開し、[ **電子メールの転送** ] セクションで [ **編集**] を選択します。

4. [電子メールの転送] ページで、 **[オン**] に切り替え、[転送先アドレス] を入力して、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 **[保存]** を選択します。
    
    **複数の電子メールアドレスに転送する** 場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。 詳細については、「 [ルールを使用してメッセージを自動的に転送する](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。 
    
     または、管理センターで [配布グループを作成](../setup/create-distribution-lists.md)し、 [そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。
    
5. 転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。  その場合、電子メールの転送は停止します。    

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。 
    
2. 転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。 

3. [ **メールの設定**] を展開し、[ **電子メールの転送** ] セクションで [ **編集**] を選択します。

4. [電子メールの転送] ページで、 **[オン**] に切り替え、[転送先アドレス] を入力して、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 **[保存]** を選択します。
    
    **複数の電子メールアドレスに転送する** 場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。 詳細については、「 [ルールを使用してメッセージを自動的に転送する](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。 
    
     または、管理センターで [配布グループを作成](../setup/create-distribution-lists.md)し、 [そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。
    
5. 転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。  その場合、電子メールの転送は停止します。 


::: moniker-end 
