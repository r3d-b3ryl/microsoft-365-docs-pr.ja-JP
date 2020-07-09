---
title: ユーザー名とメール アドレスを変更する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: 'グローバル管理者によって行われる、ユーザーのメール アドレスと表示名の変更方法について説明します。 '
ms.openlocfilehash: fedc1532bfec246392180d386a6960dbb08bd137
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079715"
---
# <a name="change-a-user-name-and-email-address"></a>ユーザー名とメール アドレスを変更する

ユーザーが結婚し、姓が変わった場合など、メール アドレスと表示名を変更する必要が生じることがあります。

ユーザーのメール アドレスの変更に関する短いビデオをご覧ください。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

このビデオがお役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

## <a name="change-a-users-email-address"></a>ユーザーの電子メール アドレスを変更する

次の手順を実行するには、[グローバル管理者](about-admin-roles.md)である必要があります。 

::: moniker range="o365-worldwide"
 
1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。
    
2. ユーザー名を選択し、 [**アカウント**] タブで、[**ユーザー名の管理**] を選択します。
    
3. 最初のボックスに、新しいメールアドレスの最初の部分を入力します。 独自のドメインを Microsoft 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択します。 

4. [**変更の保存**] を選択します。

   
::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。  

2. ユーザーを選択します。 ポップアップ ウィンドウで、[**ユーザー名 / メール**] の隣にある [**編集**]を選択します。

3. 最初のボックスに、新しいメールアドレスの最初の部分を入力します。 独自のドメインを Microsoft 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。

4. [**保存**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。 

2. ユーザーを選択します。 ポップアップ ウィンドウで、[**ユーザー名 / メール**] の隣にある [**編集**]を選択します。

3. 最初のボックスに、新しいメールアドレスの最初の部分を入力します。 独自のドメインを Microsoft 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。

4. [**保存**] を選択します。

::: moniker-end

**重要**: エラー メッセージが表示された場合は、「[エラー メッセージを解決する](#resolve-error-messages)」を参照してください。

## <a name="set-the-primary-email-address"></a>プライマリ メール アドレスを設定する

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
    
2. ユーザー名を選択し、 [**アカウント**] タブで [**メール エイリアスの管理**] を選択します。

3. そのユーザーのプライマリ メール アドレスとして設定するメール アドレスで [**プライマリとして設定**] を選択します。 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Microsoft 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    また、グローバル管理者である場合にのみ、このオプションが表示されます。このオプションが表示されない場合は、ユーザーの名前とプライマリ メール アドレスを変更するアクセス許可がありません。
  
4. ユーザーのサインイン情報を変更しようとしているという大きな黄色の警告が表示されます。 [**保存**]、[**閉じる**] の順に選びます。
    
5. ユーザーに次の情報を伝えます。
 
  - この変更は、しばらく時間がかかる場合があります。
  
  - Their new username. They'll need it to sign in to Microsoft 365.
    
  - ユーザーが Skype for Business Online を使っている場合は、ユーザーが計画している Skype for Business Online 会議のスケジュールを変更する必要があることと、外部の取引先担当者に連絡先情報の更新を依頼する必要があることを伝えます。

  - ユーザーが OneDrive を使用している場合は、現在の場所への URL が変更されています。 ユーザーの OneDrive に OneNote ノートブックがある場合は、OneNote でノートブックを閉じてから再度開く必要がある場合があります。 OneDrive で共有したファイルがあるユーザーの場合は、ファイルへのリンクが機能しなくても、再共有できる場合があります。    
  
  - パスワードも変更した場合は、モバイル デバイスにアクセスしたときに、新しいパスワードの入力を求められます。入力しなければ、モバイル デバイスは同期されません。
  
::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。  

2. ユーザーを選択します。 ポップアップ ウィンドウで、[**ユーザー名 / メール**] の隣にある [**編集**]を選択します。

3. そのユーザーのプライマリ メール アドレスとして設定するメール アドレスで [**プライマリとして設定**] を選択します。 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Microsoft 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    また、グローバル管理者である場合にのみ、このオプションが表示されます。このオプションが表示されない場合は、ユーザーの名前とプライマリ メール アドレスを変更するアクセス許可がありません。
  
4. ユーザーのサインイン情報を変更しようとしているという大きな黄色の警告が表示されます。 [**保存**]、[**閉じる**] の順に選びます。
    
5. ユーザーに次の情報を伝えます。
 
  - この変更が反映されるまで、しばらくお待ちいただく場合があります。
  
  - What their new username is. They'll need it to sign in to Microsoft 365.
    
  - ユーザーが Skype for Business Online を使っている場合は、ユーザーが計画している Skype for Business Online 会議のスケジュールを変更する必要があることと、外部の取引先担当者に古い連絡先情報の更新を依頼する必要があることを伝えます。

  - ユーザーが OneDrive を使用している場合は、現在の場所への URL が変更されたことを伝えます。 ユーザーの OneDrive に OneNote ノートブックがある場合は、OneNote でノートブックを閉じてから再度開く必要がある場合があります。 OneDrive で共有したファイルがあるユーザーの場合は、ファイルへのリンクが機能しなくても、再共有できる場合があります。    
  
  - パスワードも変更した場合は、モバイル デバイスにアクセスしたときに、新しいパスワードの入力を求められることを伝えます。入力しなければ、モバイル デバイスは同期されません。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。 

2. ユーザーを選択します。 ポップアップ ウィンドウで、[**ユーザー名 / メール**] の隣にある [**編集**]を選択します。

3. そのユーザーのプライマリ メール アドレスとして設定するメール アドレスで [**プライマリとして設定**] を選択します。 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Microsoft 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    また、グローバル管理者である場合にのみ、このオプションが表示されます。このオプションが表示されない場合は、ユーザーの名前とプライマリ メール アドレスを変更するアクセス許可がありません。
  
4. ユーザーのサインイン情報を変更しようとしているという大きな黄色の警告が表示されます。 [**保存**]、[**閉じる**] の順に選びます。
    
5. ユーザーに次の情報を伝えます。
 
  - この変更が反映されるまで、しばらくお待ちいただく場合があります。
  
  - What their new username is. They'll need it to sign in to Microsoft 365.
    
  - ユーザーが Skype for Business Online を使っている場合は、ユーザーが計画している Skype for Business Online 会議のスケジュールを変更する必要があることと、外部の取引先担当者に古い連絡先情報の更新を依頼する必要があることを伝えます。

  - ユーザーが OneDrive を使用している場合は、現在の場所への URL が変更されたことを伝えます。 ユーザーの OneDrive に OneNote ノートブックがある場合は、OneNote でノートブックを閉じてから再度開く必要がある場合があります。 OneDrive で共有したファイルがあるユーザーの場合は、ファイルへのリンクが機能しなくても、再共有できる場合があります。    
  
  - パスワードも変更した場合は、モバイル デバイスにアクセスしたときに、新しいパスワードの入力を求められることを伝えます。入力しなければ、モバイル デバイスは同期されません。

::: moniker-end
  
## <a name="change-a-users-display-name"></a>ユーザーの表示名を変更する

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. ユーザー名を選択し、[**アカウント**] タブで [**連絡先情報の管理**] を選択します。

3. [**表示名**] ボックスに、ユーザーの新しい名前を入力し、[**保存**] を選択します。 

    「**申し訳ございません。ユーザーを編集できませんでした。情報を確認して、もう一度やり直してください。**」というエラー メッセージが表示された場合、「[エラー メッセージを解決する](#resolve-error-messages)」を参照してください。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username.

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。  

2. ユーザーを選択します。 ポップアップ ウィンドウで、[**連絡先情報**] の隣にある [**編集**] を選択します。

3. [**表示名**] ボックスに、ユーザーの新しい名前を入力し、[**保存**] を選択します。 

    「**申し訳ございません。ユーザーを編集できませんでした。情報を確認して、もう一度やり直してください。**」というエラー メッセージが表示された場合、「[エラー メッセージを解決する](#resolve-error-messages)」を参照してください。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。 

2. ユーザーを選択します。 ポップアップ ウィンドウで、[**連絡先情報**] の隣にある [**編集**] を選択します。

3. [**表示名**] ボックスに、ユーザーの新しい名前を入力し、[**保存**] を選択します。 

    「**申し訳ございません。ユーザーを編集できませんでした。情報を確認して、もう一度やり直してください。**」というエラー メッセージが表示された場合、「[エラー メッセージを解決する](#resolve-error-messages)」を参照してください。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

## <a name="resolve-error-messages"></a>エラー メッセージを解決する

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>「パラメーター名 'EmailAddresses' に一致するパラメーターが見つかりません」

If you get the error message " **A parameter cannot be found that matches parameter name 'EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call [support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) and ask them to do a full sync for you.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>「申し訳ございません。ユーザーを編集できませんでした。 ユーザー情報を確認して、もう一度やり直してください」

" **申し訳ございません。ユーザーを編集できませんでした。情報を確認して、もう一度やり直してください**。 " というエラー メッセージが表示された場合、お客様はグローバル管理者ではなく、ユーザー名を変更するアクセス許可がないことを意味します。 会社の全体管理者に連絡をとり、変更するように依頼してください。


## <a name="what-to-do-with-old-email-addresses"></a>古いメール アドレスの使用方法

A person's previous primary email address is retained as an additional email address. **We strongly recommend that you don't remove the old email address.**
  
Some people might continue to send email to the person's old email address and deleting it may result in NDR failures. Microsoft automatically routes it to the new one. Also, do not reuse old SMTP email addresses and apply them to new accounts. This can also cause NDR failures or delivery to an unintended mailbox.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>ユーザーのオフライン アドレス帳がグローバル アドレス一覧と同期しない

If they are using Exchange Online or if their account is linked with your organization's on-premises Exchange environment, you might see this error when you try to change a username and email address: "This user is synchronized with your local Active Directory. Some details can be edited only through your local Active Directory."
  
This is due to the Microsoft Online Email Routing Address (MOERA). The MOERA is constructed from the person's  _userPrincipalName_ attribute in Active Directory and is automatically assigned to the cloud account during the initial sync and once created, it cannot be modified or removed in Microsoft 365. You can subsequently change the username in the Active Directory, but it doesn't change the MOERA and you may run into issues displaying the newly changed name in the Global Address List. 
  
この問題を解決するには、Microsoft 365 管理者の認証情報を使って [PowerShell 用 Azure Active Directory モジュール]( https://go.microsoft.com/fwlink/?LinkId=823193)にログインし、 次の構文を使用します。 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> This changes the person's **userPrincipalName** attribute and has no bearing on their Microsoft Online Email Routing Address (MOERA) email address. It is best practice, however, to have the person's logon UPN match their primary SMTP address. 
  
Windows Server 2003 以前のバージョンで Active Directory を使用して他のユーザーのユーザー名を変更する方法については、[ユーザー アカウントの名前の変更](https://go.microsoft.com/fwlink/?LinkId=809091)に関するページを参照してください。
  
## <a name="related-articles"></a>関連記事

[管理者: 1 人または複数のユーザーのパスワードを再設定する](reset-passwords.md)
  
[ユーザーに別のメール アドレスを追加する](../email/add-another-email-alias-for-a-user.md)
