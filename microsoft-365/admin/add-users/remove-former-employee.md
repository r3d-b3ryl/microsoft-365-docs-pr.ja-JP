---
title: 元従業員を削除する
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'このチェックリストに従って、Microsoft 365 およびセキュリティで保護されたデータから従業員を削除します。 '
ms.openlocfilehash: adf5c683828b30a978199145fa2c54f17d1b6b37
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780579"
---
# <a name="remove-a-former-employee"></a>元従業員を削除する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end
  
## <a name="sign-out-now"></a>今すぐサインアウトする

::: moniker range="o365-worldwide"

従業員の削除に関する短いビデオを見ることができます。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

従業員を削除するには、次のようにします。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. ユーザー名の横にあるボックスを選択し、[**パスワードのリセット**] を選択します。

3. 新しいパスワードを入力し、[**リセット**] を選択します。 (送信しないでください)。
    
4. ユーザーの名前を選択して [プロパティ] ウィンドウに移動し、[ **OneDrive** ] タブで [**サインアウトの開始**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. ユーザーを選択し、[**パスワードのリセット**] を選択します。

3. 新しいパスワードを入力し、[**リセット**] を選択します。 (送信しないでください)。

4. ユーザーをもう一度選択し、[ **OneDrive の設定**] を展開してから、[**サインアウト**] の横にある [**開始**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. ユーザーを選択し、[**パスワードのリセット**] を選択します。

3. 新しいパスワードを入力し、[**リセット**] を選択します。 (送信しないでください)。

4. ユーザーをもう一度選択し、[ **OneDrive の設定**] を展開してから、[**サインアウト**] の横にある [**開始**] を選択します。

::: moniker-end

    
1時間以内に、または現在の Microsoft 365 ページから出た後、もう一度サインインするように求めるメッセージが表示されます。 (アクセストークンは1時間にとって適切なので、タイムラインはそのトークンの残り時間と現在の web ページから移動するかどうかによって決まります)。
  
 **注意点**: ユーザーが Outlook on the web を使用している場合は、メールボックス内をクリックするだけでは、すぐに退去させることができない可能性があります。 OneDrive などの別のタイルを選択するか、ブラウザーを更新するとすぐに、サインアウトが開始されます。 
  
PowerShell を使用してユーザーをすぐにサインアウトさせるには、[Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) コマンドレットを参照してください。 
  
ユーザーのメールの使用を終了するのにどれくらいかかるかの詳細については、「[従業員のメール セッションの終了について知っておく必要があること](#what-you-need-to-know-about-terminating-an-employees-email-session)」を参照してください。
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>従業員の削除とデータの保護を行うすべての手順の概要
<a name="bkmk_now"> </a>

「従業員が組織を離れたときにデータを保護するにはどうすればよいですか?」という質問がよくあります。 この記事では、Microsoft 365 へのアクセスをブロックする方法と、データを保護するために実行する必要のある手順について説明します。
  
> [!NOTE]
> グローバル管理者の場合は、従業員を削除し、電子メールを転送して、新しいガイド付きの操作を使用して OneDrive コンテンツに対する処理を選択することができます。 詳細については、「[グローバル管理者: ユーザーを削除する](remove-former-employee.md)」を参照してください。 ただし、従業員が会社のデータにアクセスできないようにするには、ここに記載されている追加の手順をすべて完了することをお勧めします。 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**手順** <br/> |**理由** <br/> |
|1. [元従業員のメールボックスの内容を保存する](#save-the-contents-of-a-former-employees-mailbox) <br/> |これは、従業員の仕事を引き継ぐユーザー、または訴訟が発生した場合に便利です。  <br/> |
|2. [元従業員のメールを別の従業員に転送するか、または元従業員のメールボックスを共有メールボックスに変換する](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [元従業員のモバイル デバイスをワイプし、ブロックする](#wipe-and-block-a-former-employees-mobile-device) <br/> |携帯電話またはタブレットからビジネス データを削除します。  <br/> |
|4.[以前の従業員の Microsoft 365 データへのアクセスをブロックする](#block-a-former-employees-access-to-microsoft-365-data)<br/> |これにより、ユーザーは古い Microsoft 365 メールボックスおよびデータにアクセスできなくなります。  <br/><br/> **ヒント**: ユーザーのアクセスをブロックすると、ライセンスの支払いが続行されます。 支払いを停止するには、サブスクリプションからそのライセンスを削除する必要があります (手順 5)。           |
|5. [従業員の OneDrive のコンテンツを移動する](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |ユーザーのライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |ユーザーが、会社が発行したコンピューターではなく、個人のコンピューターを使用して OneDrive や SharePoint からファイルをダウンロードした場合は、保存されたそれらのファイルを削除する方法はありません。  <br/><br/> ユーザーは自分のコンピューターに同期されたファイルに引き続きアクセスできます。  <br/> |
|6.[以前の従業員から Microsoft 365 ライセンスを削除して削除し](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)ます。<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [元従業員のユーザー アカウントを削除する](#delete-a-former-employees-user-account)<br/> |これにより、管理センターからアカウントが削除されます。 これできれいになります。  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>元従業員のメールボックスの内容を保存する
<a name="bkmk_preserve"> </a>

元従業員のメールボックスの内容を保存するには、2 つの方法があります。
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    または
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    メールボックスを "非アクティブのメールボックス" に変えると、管理者、法令遵守責任者、またはレコード マネージャーは、Exchange Online のインプレース電子情報開示を使用して、コンテンツにアクセスし、検索できます。
    
    非アクティブなメールボックスはメールを受信することができず、組織の共有アドレス帳にもその他のリストにも表示されません。
    
    メールボックスにホールドを設定する方法については、「 [Exchange Online の非アクティブなメールボックスを管理](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)する」を参照してください。
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>元従業員のメールを別の従業員に転送するか、または元従業員のメールボックスを共有メールボックスに変換する
<a name="bkmk_forward"> </a>

この手順で、他の従業員に元従業員のメール アドレスを割り当てるか、または作成した[共有メールボックスにユーザーのメールボックスを変換します](../email/convert-user-mailbox-to-shared-mailbox.md)。 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- メールの転送を設定した場合、元従業員宛の *新しい*  メールのみが、現在の従業員に送信されるようになります。 
    
- メールの転送を設定する場合、元従業員のアカウントにライセンスが付与されている必要があります。
    
 > [!IMPORTANT] 
 > メール転送または共有メールボックスを設定している場合は、最後に、元従業員のアカウントを削除しないでください。 メール転送や共有メールボックスを固定するには、アカウントを残しておく必要があります。 

::: moniker range="o365-worldwide"  

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員の名前を選択し、[**メール**] タブを選択します。

3. [**電子メールの転送**] で、[**メール転送の管理**] を選択します。

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. **[保存]** を選択します。 
    
6. 元従業員のアカウントを削除しないよう注意してください。
 
::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. ブロックする従業員を選択し、[メールの**設定**] を展開します。

3. [**電子メール転送**] の横にある [**編集**] を選択します。

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. **[保存]** を選択します。 
    
6. 元従業員のアカウントを削除しないよう注意してください。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. ブロックする従業員を選択し、[メールの**設定**] を展開します。

3. [**電子メール転送**] の横にある [**編集**] を選択します。

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. **[保存]** を選択します。 
    
6. 元従業員のアカウントを削除しないよう注意してください。

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>元従業員のモバイル デバイスをワイプし、ブロックする
<a name="bkmk_mobile"> </a>

元従業員が組織の電話を持っていた場合は、Exchange 管理センター でその電話をワイプおよびブロックしてすべての組織データを削除し、その電話から Office 365 に接続できないようにします。
  

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

3. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**. 
    
4. ユーザーを選択し、[**モバイルデバイス**] で [**詳細の表示**] を選択します。 
    
5. [**モバイルデバイスの詳細**] ページの [**モバイルデバイス**] で、モバイルデバイスを選択し、[データワイプデバイスの**ワイプ**] を選択して、[ ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **ブロック**] を選択します。 
    
6. **[保存]** を選択します。 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>以前の従業員の Microsoft 365 データへのアクセスをブロックする
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > アカウントをブロックすると、有効になるまで最大24時間かかる場合があります。 ユーザーのサインインアクセスをすぐに阻止する必要がある場合は、[パスワードをリセット](reset-passwords.md)してから、すべてのデバイスで Microsoft 365 セッションからサインアウトするワンタイムイベントを開始する必要があります。 「[今すぐサインアウトする](#sign-out-now)」を参照してください。
 

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員の名前を選択し、ユーザーの名前の下で [**このユーザーをブロック**する] の記号を選択します。

3. [**ユーザーによるサインインをブロックする**] を選択し、[**保存**] を選択します。 

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員を選択し、[**サインインをブロック**する] を選択します。

3. [**ユーザーによるサインインをブロックする**] を選択し、[**保存**] を選択します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員を選択し、[**サインインをブロック**する] を選択します。

3. [**ユーザーによるサインインをブロックする**] を選択し、[**保存**] を選択します。 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>元従業員の電子メール (Exchange Online) へのアクセスをブロックする
<a name="bkmk_block_email"> </a>

Microsoft 365 サブスクリプションの一部として電子メールを所有している場合は、次の手順に従って Exchange 管理センターにログインし、元の従業員が自分のメールにアクセスするのをブロックする必要があります。
  

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。
     
2. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**. 
    
3. ユーザーをダブルクリックして、[**メールボックスの機能**] ページに移動します。 [**モバイルデバイス**] で、[ **Exchange ActiveSync を無効**にし、**デバイス用 OWA を無効**にする] を選択し、メッセージが表示されたら両方に **[はい]** と答えます。 
    
4. メッセージが表示されたら、[**電子メール接続**] で [**無効に**する **]** を選択します。 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>以前の従業員から Microsoft 365 ライセンスを削除して削除する
<a name="bkmk_remove"> </a>

そのため、ユーザーが組織を離れた後にライセンスの支払いを続行しない場合は、Microsoft 365 ライセンスを削除してから、サブスクリプションから削除する必要があります。 サブスクリプションからライセンスを削除しない場合、そのライセンスを他のユーザーに割り当てることができます。
  
ライセンスの削除後、そのユーザーのすべてのデータが 30 日間保持されます。 データに[アクセス](get-access-to-and-back-up-a-former-user-s-data.md)したり、ユーザーが復帰した場合にアカウントを[復元](restore-user.md)したりすることができます。 30日後、ユーザーのすべてのデータ (SharePoint Online に保存されているドキュメントを除く) は、Microsoft 365 から完全に削除され、回復することはできません。 

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員の名前を選択し、[**ライセンスとアプリ**] タブを選択します。

4. 削除するライセンスのチェックボックスをオフにし、[**変更の保存**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員を選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。

3. [**製品ライセンス**] ページで、削除するライセンスを切り替えて、[**保存**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員を選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。

3. [**製品ライセンス**] ページで、削除するライセンスを切り替えて、[**保存**] を選択します。

::: moniker-end


他のユーザーを採用するまで **ライセンスの数を減らすには** 、次の操作を行います。 

::: moniker range="o365-worldwide"



1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。


::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。

::: moniker-end
    
2. 他のユーザーを採用するまで支払いないように、[**ライセンスの追加/削除**] を選択してライセンスを削除します。

別のユーザーをビジネスに[追加](add-users.md)すると、1つの手順でライセンスを同時に購入するように求めるメッセージが表示されます。
    
Microsoft 365 for business のユーザーライセンスの管理の詳細については、「365 Microsoft の一般法人向け[ユーザーへのライセンスの割り当て](../manage/assign-licenses-to-users.md)」と「ユーザーからライセンスを削除する ( [microsoft 365 for business](../manage/remove-licenses-from-users.md))」を参照してください。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>削除した従業員のアカウントが Skype for Business に与える影響
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>元従業員のユーザー アカウントを削除する
<a name="bkmk_delete"> </a>

元従業員のすべてのユーザー データにアクセスして保存したら、元従業員のアカウントを削除できます。
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 削除する従業員の名前を選択します。

3. ユーザー名の下で、[**ユーザーの削除**] の記号を選択します。 このユーザーに対して必要なオプションを選択し、[**ユーザーの削除**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 削除する従業員の名前を選択します。

3. ページの上部で、[ユーザーの**削除**] を選択します。 このユーザーに対して必要なオプションを選択し、[**ユーザーの削除**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 削除する従業員の名前を選択します。

3. ページの上部で、[ユーザーの**削除**] を選択します。 このユーザーに対して必要なオプションを選択し、[**ユーザーの削除**] を選択します。

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>組織では Active Directory を使用していますか。

ローカル Active Directory 環境からユーザーアカウントを Microsoft 365 に同期させる場合は、ローカルの Active Directory サービスでユーザーアカウントを削除および復元する必要があります。 ユーザー アカウントを Office 365 で削除または復元することはできません。
  
手順については、「[ユーザーアカウントを削除する](https://go.microsoft.com/fwlink/?linkid=841808)」を参照してください。
  
Azure Active Directory を使用している場合は、[Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell コマンドレットを参照してください。 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>従業員のメール セッションの終了について知っておく必要があること
<a name="bkmk_session"> </a>

ここでは、従業員のメールの使用を終了する方法について説明します (Exchange)。
  
|||
|:-----|:-----|
|**可能な操作** <br/> |**方法** <br/> |
|セッション (Outlook on the web、Outlook、Exchange Active Sync など) を終了し、新しいセッションを強制的に開く  <br/> |パスワードを再設定する  <br/> |
|(すべてのプロトコルの) セッションを終了し、今後のセッションに対するアクセスをブロックする  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|特定のプロトコル (ActiveSync など) のセッションを終了する  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
上記の操作は、次の 3 か所で実行できます。
  
|||
|:-----|:-----|
|**セッションを終了する場所** <br/> |**所要時間** <br/> |
|Exchange 管理センターまたは PowerShell を使用する場合  <br/> |予想される遅延が 30 分以内  <br/> |
|Azure Active Directory 管理センター  <br/> |予想される遅延が 60 分以内  <br/> |
|オンプレミス環境  <br/> |予想される遅延が 3 時間以上  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>アカウントの終了に対して最も迅速な応答を取得する方法

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>関連記事

[ユーザーを復元する](restore-user.md)
  
