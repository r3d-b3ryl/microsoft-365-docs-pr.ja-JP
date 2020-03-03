---
title: Office 365 から元従業員を削除する
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'このチェックリストに従って、Office 365 およびセキュリティで保護されたデータから従業員を削除します。 '
ms.openlocfilehash: f29f24e0f9cf583e768000cff2d6081eb9df6d87
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353118"
---
# <a name="remove-a-former-employee-from-office-365"></a>Office 365 から元従業員を削除する
  
## <a name="sign-out-now"></a>今すぐサインアウトする

::: moniker range="o365-worldwide"

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

従業員の削除に関する短いビデオを見ることができます。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

従業員を削除するには、次のようにします。

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ユーザー名の横にあるボックスを選択し、[**パスワードのリセット**] を選択します。

3. 新しいパスワードを入力し、[**リセット**] を選択します。 (送信しないでください)。
    
4. ユーザーの名前を選択して [プロパティ] ウィンドウに移動し、[ **OneDrive** ] タブで [**サインアウトの開始**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ユーザーを選択し、[**パスワードのリセット**] を選択します。

3. 新しいパスワードを入力し、[**リセット**] を選択します。 (送信しないでください)。

4. ユーザーをもう一度選択し、[ **OneDrive の設定**] を展開してから、[**サインアウト**] の横にある [**開始**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ユーザーを選択し、[**パスワードのリセット**] を選択します。

3. 新しいパスワードを入力し、[**リセット**] を選択します。 (送信しないでください)。

4. ユーザーをもう一度選択し、[ **OneDrive の設定**] を展開してから、[**サインアウト**] の横にある [**開始**] を選択します。

::: moniker-end

    
1時間以内、または現在の Office 365 ページから離れた後、もう一度サインインするように求めるメッセージが表示されます。 (アクセストークンは1時間にとって適切なので、タイムラインはそのトークンの残り時間と現在の web ページから移動するかどうかによって決まります)。
  
 **注意点**: ユーザーが Outlook on the web を使用している場合は、メールボックス内をクリックするだけでは、すぐに退去させることができない可能性があります。 OneDrive などの別のタイルを選択するか、ブラウザーを更新するとすぐに、サインアウトが開始されます。 
  
PowerShell を使用してユーザーをすぐにサインアウトさせるには、[Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) コマンドレットを参照してください。 
  
ユーザーのメールの使用を終了するのにどれくらいかかるかの詳細については、「[従業員のメール セッションの終了について知っておく必要があること](#what-you-need-to-know-about-terminating-an-employees-email-session)」を参照してください。
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>従業員の削除とデータの保護を行うすべての手順の概要
<a name="bkmk_now"> </a>

"社員が退職したとき、どのような方法でデータを保護しますか。" というご質問を頻繁にお寄せいただいております。この記事では、Office 365 へのアクセスをブロックする方法とデータを守るために行う必要のある措置について説明します。
  
> [!NOTE]
> グローバル管理者の場合は、従業員を削除し、電子メールを転送して、新しいガイド付きの操作を使用して OneDrive コンテンツに対する処理を選択することができます。 詳細については、「[グローバル管理者: ユーザーを削除する](remove-former-employee.md)」を参照してください。 ただし、従業員が会社のデータにアクセスできないようにするには、ここに記載されている追加の手順をすべて完了することをお勧めします。 
  
簡単な概要を示します。各手順については、この記事で詳しく説明します。
  
|||
|:-----|:-----|
|**手順** <br/> |**理由** <br/> |
|1. [元従業員のメールボックスの内容を保存する](#save-the-contents-of-a-former-employees-mailbox) <br/> |これは、従業員の仕事を引き継ぐユーザー、または訴訟が発生した場合に便利です。  <br/> |
|2. [元従業員のメールを別の従業員に転送するか、または元従業員のメールボックスを共有メールボックスに変換する](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |この操作を行うと、元従業員のメール アドレスはアクティブなままとなります。顧客やパートナーが元従業員のアドレスにメールを引き続き送信する場合は、この手順を行うと、仕事を引き継ぐユーザーに転送されます。  <br/> |
|3. [元従業員のモバイル デバイスをワイプし、ブロックする](#wipe-and-block-a-former-employees-mobile-device) <br/> |携帯電話またはタブレットからビジネス データを削除します。  <br/> |
|4. [元従業員の Office 365 データへのアクセスをブロックする](#block-a-former-employees-access-to-office-365-data)<br/> |ユーザーが、古い Office 365 のメールボックスとデータにアクセスすることを防ぎます。  <br/><br/> **ヒント**: ユーザーのアクセスをブロックすると、ライセンスの支払いが続行されます。 支払いを停止するには、サブスクリプションからそのライセンスを削除する必要があります (手順 5)。           |
|5. [従業員の OneDrive のコンテンツを移動する](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |ユーザーのライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  <br/><br/> アカウントを削除する前に、OneDrive のコンテンツをアクセスしやすい別の場所に移動する必要があります。従業員のアカウントを削除すると、OneDrive のコンテンツは **30** 日間保持されます。その 30 日間であれば、ユーザーのアカウントを復元し、OneDrive のコンテンツにアクセスすることができます。ユーザーのアカウントを復元した場合、30 日後でも OneDrive のコンテンツにアクセスできます。  <br/> |
|5a. ユーザーが個人のコンピューターを使用して OneDrive や SharePoint にアクセスした場合はどうなりますか?  <br/> |ユーザーが、会社が発行したコンピューターではなく、個人のコンピューターを使用して OneDrive や SharePoint からファイルをダウンロードした場合は、保存されたそれらのファイルを削除する方法はありません。  <br/><br/> ユーザーは自分のコンピューターに同期されたファイルに引き続きアクセスできます。  <br/> |
|6. [元従業員から Office 365 のライセンスを削除する](#remove-and-delete-the-office-365-license-from-a-former-employee)<br/> |ライセンスを削除すると、別のユーザーに割り当てることができます。または、他のユーザーを採用するまで支払うことがないように、ライセンスを削除することもできます。  <br/><br/> ライセンスを削除すると、ユーザーの古いメール、連絡先、および予定表は **30 日間** 保持され、その後、完全に削除されます。 ライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  <br/> |
|7. [元従業員のユーザー アカウントを削除する](#delete-a-former-employees-user-account)<br/> |これにより、管理センターからアカウントが削除されます。 これできれいになります。  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>元従業員のメールボックスの内容を保存する
<a name="bkmk_preserve"> </a>

元従業員のメールボックスの内容を保存するには、2 つの方法があります。
  
1. 使用しているバージョンの Outlook 2013 または 2016 に元従業員のメール アドレスを追加し, .pst ファイルにデータをエクスポートします。必要に応じて、別のメール アカウントにデータをインポートすることができます。方法については、「[元ユーザーのデータにアクセスしてバックアップを作成する](get-access-to-and-back-up-a-former-user-s-data.md)」を参照してください。
    
    または
    
2. ユーザー アカウントを削除する前に、メールボックスに訴訟ホールドまたはインプレース ホールドを配置します。これは 1 つ目のオプションよりも複雑ですが、企業計画にアーカイブと訴訟ホールドが含まれている場合、訴訟の可能性がある場合、および技術力の高い IT 部門がある場合は、行う価値があります。
    
    メールボックスを "非アクティブのメールボックス" に変えると、管理者、法令遵守責任者、またはレコード マネージャーは、Exchange Online のインプレース電子情報開示を使用して、コンテンツにアクセスし、検索できます。
    
    非アクティブなメールボックスはメールを受信することができず、組織の共有アドレス帳にもその他のリストにも表示されません。
    
    メールボックスにホールドを設定する方法については、「 [Exchange Online の非アクティブなメールボックスを管理](https://docs.microsoft.com/office365/securitycompliance/create-and-manage-inactive-mailboxes)する」を参照してください。
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>元従業員のメールを別の従業員に転送するか、または元従業員のメールボックスを共有メールボックスに変換する
<a name="bkmk_forward"> </a>

この手順で、他の従業員に元従業員のメール アドレスを割り当てるか、または作成した[共有メールボックスにユーザーのメールボックスを変換します](../email/convert-user-mailbox-to-shared-mailbox.md)。 
  
- 共有メールボックスを作成すると、コストを低く抑えることができます。これは、 **メールボックスのサイズが 50 GB より小さい限り** 、ライセンスの料金を支払う必要がないからです。50 GB を超えると、メールボックスにライセンスを割り当てる必要があります。 
    
- メールボックスを共有メールボックスに変換すると、以前のすべてのメールを入手できるようになります。この処理を行うと、占有する領域が大きくなる可能性があります。
    
- メールの転送を設定した場合、元従業員宛の *新しい*  メールのみが、現在の従業員に送信されるようになります。 
    
- メールの転送を設定する場合、元従業員のアカウントにライセンスが付与されている必要があります。
    
 > [!IMPORTANT] 
 > メール転送または共有メールボックスを設定している場合は、最後に、元従業員のアカウントを削除しないでください。 メール転送や共有メールボックスを固定するには、アカウントを残しておく必要があります。 

::: moniker range="o365-worldwide"  

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員の名前を選択し、[**メール**] タブを選択します。

3. [**電子メールの転送**] で、[**メール転送の管理**] を選択します。

4. [ **このメールボックスに送信されたすべてのメールを転送する** ] をオンにします。[ **転送先アドレス** ] ボックスに、メールを受け取る現在の従業員 (または共有メールボックス) のメール アドレスを入力します。 
  
5. [**保存**] を選択します。 
    
6. 元従業員のアカウントを削除しないよう注意してください。
 
::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ブロックする従業員を選択し、[メールの**設定**] を展開します。

3. [**電子メール転送**] の横にある [**編集**] を選択します。

4. [ **このメールボックスに送信されたすべてのメールを転送する** ] をオンにします。[ **転送先アドレス** ] ボックスに、メールを受け取る現在の従業員 (または共有メールボックス) のメール アドレスを入力します。 
  
5. [**保存**] を選択します。 
    
6. 元従業員のアカウントを削除しないよう注意してください。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ブロックする従業員を選択し、[メールの**設定**] を展開します。

3. [**電子メール転送**] の横にある [**編集**] を選択します。

4. [ **このメールボックスに送信されたすべてのメールを転送する** ] をオンにします。[ **転送先アドレス** ] ボックスに、メールを受け取る現在の従業員 (または共有メールボックス) のメール アドレスを入力します。 
  
5. [**保存**] を選択します。 
    
6. 元従業員のアカウントを削除しないよう注意してください。

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>元従業員のモバイル デバイスをワイプし、ブロックする
<a name="bkmk_mobile"> </a>

元従業員が組織の電話を持っていた場合は、Exchange 管理センター でその電話をワイプおよびブロックしてすべての組織データを削除し、その電話から Office 365 に接続できないようにします。
  

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

3. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**. 
    
4. ユーザーを選択し、[**モバイルデバイス**] で [**詳細の表示**] を選択します。 
    
5. [**モバイルデバイスの詳細**] ページの **[モバイルデバイス**] で、モバイルデバイスを選択し、[](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png)**データ**![ワイプデバイスのワイプ] を選択して、[**ブロック**] を選択します。 
    
6. [**保存**] を選択します。 
    
    **ヒント**: オンプレミスの Blackberry Enterprise Service からも、そのユーザーを削除するか無効にするかします。さらに、そのユーザーのすべての Blackberry デバイスを無効にする必要もあります。ユーザーを無効にする具体的な手順については、「Blackberry Business Cloud Services Administration Guide」 (Blackberry Business Cloud Services 管理ガイド) を参照してください。 
    
## <a name="block-a-former-employees-access-to-office-365-data"></a>元従業員の Office 365 データへのアクセスをブロックする
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > アカウントをブロックすると、有効になるまで最大24時間かかる場合があります。 すぐにユーザーのサインイン アクセスを防ぐ必要がある場合は、 [パスワードをリセット](reset-passwords.md)して、すべてのデバイスの Office 365 セッションからサインアウトする 1 回限りのイベントを開始する必要があります。 「[今すぐサインアウトする](#sign-out-now)」を参照してください。
 

::: moniker range="o365-worldwide"

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員の名前を選択し、ユーザーの名前の下で [**このユーザーをブロック**する] の記号を選択します。

3. [**ユーザーによるサインインをブロックする**] を選択し、[**保存**] を選択します。 

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 禁止する従業員を選択し、[**サインインをブロック**する] を選択します。

3. [**ユーザーによるサインインをブロックする**] を選択し、[**保存**] を選択します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 禁止する従業員を選択し、[**サインインをブロック**する] を選択します。

3. [**ユーザーによるサインインをブロックする**] を選択し、[**保存**] を選択します。 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>元従業員の電子メール (Exchange Online) へのアクセスをブロックする
<a name="bkmk_block_email"> </a>

Office 365 サブスクリプションに Office 365 のメールが含まれている場合は、Exchange 管理センター にログインし、次の手順を実行して、元従業員がメールにアクセスできないようにする必要があります。
  

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。
     
2. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**. 
    
3. ユーザーをダブルクリックして、[**メールボックスの機能**] ページに移動します。 [**モバイルデバイス**] で、[ **Exchange ActiveSync を無効**にし、**デバイス用 OWA を無効**にする] を選択し、メッセージが表示されたら両方に **[はい]** と答えます。 
    
4. メッセージが表示されたら、[**電子メール接続**] で [**無効に**する **]** を選択します。 
    
## <a name="remove-and-delete-the-office-365-license-from-a-former-employee"></a>元従業員から Office 365 のライセンスを削除する
<a name="bkmk_remove"> </a>

ユーザーが組織を離れた後、ライセンスの料金支払いを続行しない場合、そのユーザーの Office 365 のライセンスを削除して、サブスクリプションから削除する必要があります。サブスクリプションからライセンスを削除しない場合、そのライセンスを他のユーザーに割り当てることができます。
  
ライセンスの削除後、そのユーザーのすべてのデータが 30 日間保持されます。データに[アクセス](get-access-to-and-back-up-a-former-user-s-data.md)したり、ユーザーが復帰した場合にアカウントを[復元](restore-user.md)したりすることができます。30 日経過すると、ユーザーのすべてのデータ (SharePoint Online に保存されているドキュメントを除く) が、Office 365 から永久に削除され、復元することはできません。 

::: moniker range="o365-worldwide"

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 禁止する従業員の名前を選択し、[**ライセンスとアプリ**] タブを選択します。

4. 削除するライセンスのチェックボックスをオフにし、[**変更の保存**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 禁止する従業員を選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。

3. [**製品ライセンス**] ページで、削除するライセンスを切り替えて、[**保存**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 禁止する従業員を選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。

3. [**製品ライセンス**] ページで、削除するライセンスを切り替えて、[**保存**] を選択します。

::: moniker-end


他のユーザーを採用するまで **ライセンスの数を減らすには** 、次の操作を行います。 

::: moniker range="o365-worldwide"



1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。


::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。

::: moniker-end
    
2. 他のユーザーを採用するまで支払いないように、[**ライセンスの追加/削除**] を選択してライセンスを削除します。

別のユーザーをビジネスに[追加](add-users.md)すると、1つの手順でライセンスを同時に購入するように求めるメッセージが表示されます。
    
一般法人向け Office 365 のユーザー ライセンス管理の詳細については、「[一般法人向け Office 365 ライセンスをユーザーに割り当てる](../manage/assign-licenses-to-users.md)」および「[一般法人向け Office 365 のユーザーからライセンスを削除する](../manage/remove-licenses-from-users.md)」をご覧ください。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>削除した従業員のアカウントが Skype for Business に与える影響
<a name="bkmk_remove"> </a>

Office 365 からユーザーのライセンスを削除すると、ユーザーに関連付けられている PSTN 通話番号が解放されます。この番号を別のユーザーに割り当てることができます。
  
ユーザーがキュー グループに属している場合、ユーザーは呼び出しキューのエージェントの実行可能な対象にならなくなります。そのため、呼び出しキューに関連付けられているグループからもユーザーを削除することをお勧めします。 
  
## <a name="delete-a-former-employees-user-account"></a>元従業員のユーザー アカウントを削除する
<a name="bkmk_delete"> </a>

元従業員のすべてのユーザー データにアクセスして保存したら、元従業員のアカウントを削除できます。
  
メールの転送を設定した場合や、アカウントを共有メールボックスに変換した場合、アカウントを削除しないでください。いずれの場合も、メール転送および共有メールボックスを固定するには、アカウントが必要です。

::: moniker range="o365-worldwide"

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 削除する従業員の名前を選択します。

3. ユーザー名の下で、[**ユーザーの削除**] の記号を選択します。 このユーザーに対して必要なオプションを選択し、[**ユーザーの削除**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 削除する従業員の名前を選択します。

3. ページの上部で、[ユーザーの**削除**] を選択します。 このユーザーに対して必要なオプションを選択し、[**ユーザーの削除**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 削除する従業員の名前を選択します。

3. ページの上部で、[ユーザーの**削除**] を選択します。 このユーザーに対して必要なオプションを選択し、[**ユーザーの削除**] を選択します。

::: moniker-end

ユーザーを削除するとき、約 30 日間アカウントが無効になります。30 日後に永久に削除されるまではアカウントを復元できます。
  
### <a name="does-your-organization-use-active-directory"></a>組織では Active Directory を使用していますか。

ユーザー アカウントがローカルな Active Directory 環境から Office 365 に同期されている場合、ローカルな Active Directory サービス内でユーザー アカウントを削除および復元する必要があります。ユーザー アカウントを Office 365 で削除または復元することはできません。
  
手順については、「[ユーザーアカウントを削除する](https://go.microsoft.com/fwlink/?linkid=841808)」を参照してください。
  
Azure Active Directory を使用している場合は、[Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell コマンドレットを参照してください。 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>従業員のメール セッションの終了について知っておく必要があること
<a name="bkmk_session"> </a>

ここでは、従業員のメールの使用を終了する方法について説明します (Exchange)。
  
|||
|:-----|:-----|
|**可能な操作** <br/> |**方法** <br/> |
|セッション (Outlook on the web、Outlook、Exchange Active Sync など) を終了し、新しいセッションを強制的に開く  <br/> |パスワードを再設定する  <br/> |
|(すべてのプロトコルの) セッションを終了し、今後のセッションに対するアクセスをブロックする  <br/> |アカウントを無効にする。例 (Exchange 管理センターまたは PowerShell を使用する場合):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|特定のプロトコル (ActiveSync など) のセッションを終了する  <br/> |プロトコルを無効にする。例 (Exchange 管理センターまたは PowerShell を使用する場合):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
上記の操作は、次の 3 か所で実行できます。
  
|||
|:-----|:-----|
|**セッションを終了する場所** <br/> |**所要時間** <br/> |
|Exchange 管理センターまたは PowerShell を使用する場合  <br/> |予想される遅延が 30 分以内  <br/> |
|Azure Active Directory 管理センター  <br/> |予想される遅延が 60 分以内  <br/> |
|オンプレミス環境  <br/> |予想される遅延が 3 時間以上  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>アカウントの終了に対して最も迅速な応答を取得する方法

 **最も迅速な応答**: Exchange 管理センターを使用 (PowerShell を使用) するか、または Azure Active Directory 管理センターを使用します。オンプレミスの環境では、DirSync を介して変更を同期するのに数時間かかる場合があります。 
  
 **オンプレミスおよび Exchange データ センターにプレゼンスがあるユーザーの場合、迅速な応答**: Azure Active Directory 管理センター/Exchange 管理センターを使用してセッションを終了し、オンプレミスの環境でも変更を加えます。そうしないと、Azure Active Directory 管理センター/Exchange 管理センターでの変更は、DirSync によって上書きされます。 
  
## <a name="related-articles"></a>関連記事

[ユーザーを復元する](restore-user.md)
  
