---
title: Office 365 でメール転送を構成する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365 を使用して、1つまたは複数の電子メールアカウントへのメール転送を設定します。
ms.openlocfilehash: b6ad4032748c35db8e8c18b609915aef4231cb6c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255276"
---
# <a name="configure-email-forwarding-in-office-365"></a>Office 365 でメール転送を構成する
  
Office 365 を使用している組織の管理者であれば、ユーザーのメールボックスのメール転送設定に関して会社から条件が与えられていることがあります。メール転送を利用すれば、あるユーザーのメールボックスに送信されたメール メッセージを組織内外の別のユーザーのメールボックスに転送できます。

  
## <a name="configure-email-forwarding"></a>メール転送を構成する

 メール転送を設定する前に、次の点に注意してください。 

- メール転送を設定すると *、そのメール*ボックスに送信された**新しい**メールだけが表示されます。 
    
- 電子メール転送では、送信*元*アカウントにライセンスが必要です。 ユーザーが組織を去ったことによりメール転送を設定する場合には、別の方法として[そのユーザーのメールボックスを共有メールボックス変換](convert-user-mailbox-to-shared-mailbox.md)することです。 こうすることで、複数のユーザーがそのメールボックスにアクセスできます。 ただし、共有メールボックスは 50 GB 以下にする必要があります。 
    
これらの手順を実行するには、Office 365 の Exchange 管理者または全体管理者である必要があります。 詳細については、「[管理者の役割につい](../add-users/about-admin-roles.md)て」を参照してください。

::: moniker range="o365-worldwide"

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
    
2. 転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。 
 
3. [**メール**] タブで、[**メール転送の管理**] を選択します。 
  
4. [電子メールの転送] ページで、[**このメールボックスに送信されたすべてのメールを転送する**] を選択し、転送先アドレスを入力して、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 [**変更の保存**] を選択します。
    
    **複数の電子メールアドレスに転送する**場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。 詳細については、「[ルールを使用してメッセージを自動的に転送する](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。 
    
     または、管理センターで[配布グループを作成](../setup/create-distribution-lists.md)し、[そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。
    
5. 転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。  その場合、電子メールの転送は停止します。 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。 
    
2. 転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。 

3. [**メールの設定**] を展開し、[**電子メールの転送**] セクションで [**編集**] を選択します。

4. [電子メールの転送] ページで、 **[オン**] に切り替え、[転送先アドレス] を入力して、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 [**保存**] を選択します。
    
    **複数の電子メールアドレスに転送する**場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。 詳細については、「[ルールを使用してメッセージを自動的に転送する](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。 
    
     または、管理センターで[配布グループを作成](../setup/create-distribution-lists.md)し、[そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。
    
5. 転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。  その場合、電子メールの転送は停止します。    

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。 
    
2. 転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。 

3. [**メールの設定**] を展開し、[**電子メールの転送**] セクションで [**編集**] を選択します。

4. [電子メールの転送] ページで、 **[オン**] に切り替え、[転送先アドレス] を入力して、転送されたメールのコピーを保持するかどうかを選択します。 このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。 [**保存**] を選択します。
    
    **複数の電子メールアドレスに転送する**場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。 詳細については、「[ルールを使用してメッセージを自動的に転送する](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。 
    
     または、管理センターで[配布グループを作成](../setup/create-distribution-lists.md)し、[そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。
    
5. 転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。  その場合、電子メールの転送は停止します。 

::: moniker-end 
