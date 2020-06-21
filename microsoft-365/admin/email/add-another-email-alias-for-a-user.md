---
title: ユーザーに別のメール エイリアスを追加する
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Microsoft 365 for business アカウントに関連付けられている電子メールエイリアスと呼ばれる複数の電子メールアドレスを設定する方法について説明します。 '
ms.openlocfilehash: c0e71ef150ccf592ea4f808a5e6609e1675767a4
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780291"
---
# <a name="add-another-email-alias-for-a-user"></a>ユーザーに別のメール エイリアスを追加する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end
  
この記事は、ビジネスサブスクリプションを所有する Microsoft 365 管理者を対象としています。 ホーム ユーザー向けではありません。
  
Microsoft 365 のプライマリ電子メールアドレスは、通常、アカウントの作成時にユーザーが割り当てられた電子メールアドレスです。 ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。 また、Microsoft 365 for business アカウントに関連付けられている電子メールアドレスを複数持つこともできます。 これらの追加アドレスをエイリアスと呼びます。 
  
たとえば、Jenna が電子メールアドレス jenna@contosoco.com を持っているとしますが、ユーザーがその名前で自分を参照している場合は、jen@contosoco.com で電子メールを受信したいと考えています。 両方の電子メールアドレスが Jenna の受信トレイに送られるように、のエイリアスを作成することができます。
<br><br>  
  
ユーザーあたり最大 400 個のエイリアスを作成できます。 追加の料金やライセンスは必要ありません。
  
> [!Tip]
> Info@NodPublishers.com や sales@NodPublishers.com などの1つの電子メールアドレスに送信された電子メールを複数のユーザーが管理できるようにする場合は、共有メールボックスを作成します。 詳細については、「[共有メールボックスを作成](create-a-shared-mailbox.md)する」を参照してください。
  
## <a name="add-email-aliases-to-a-user"></a>ユーザーにメール エイリアスを追加する
<a name="AddEmailPreview"> </a>

これを行うには、[管理者のアクセス許可](../add-users/about-admin-roles.md)が必要です。 

  
::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. [**アクティブなユーザー** ] ページで、[ユーザー >**メールエイリアスの管理**] を選択します。 ユーザーにライセンスが割り当てられていない場合、このオプションは表示されません。 
    
3. [ **+ エイリアスの追加**] を選択し、ユーザーの新しい別名を入力します。   
    
    > [!Important] 
    > "**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
    
  
    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。 
  
     
5. 完了したら、[**変更の保存**] を選択します。
    
6. Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。
    
    これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。 たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。
    
  
7. **ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。** たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。 Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。 
    
    
2. [ **アクティブなユーザー**] ページで、編集するユーザー名を選びます。

3. [**ユーザー名/メールエイリアス**] の横にある [**編集**] を選択します。

    > [!Important] 
    > "**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。

4. [**エイリアス**] の下のテキストボックスに、新しい電子メールエイリアスの最初の部分を入力します。 独自のドメインを Office 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。 次に **[追加]** を選択します。

    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。 

5. 完了したら、[**保存**] を選択します。

6. Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。 
    
    これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。 たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。
    
  
7. **ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。** たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。 Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。 

    
2. [ **アクティブなユーザー**] ページで、編集するユーザー名を選びます。

3. [**ユーザー名/メールエイリアス**] の横にある [**編集**] を選択します。

    > [!Important] 
    > "**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。

4. [**エイリアス**] の下のテキストボックスに、新しい電子メールエイリアスの最初の部分を入力します。 独自のドメインを Office 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。 次に **[追加]** を選択します。

    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。 

5. 完了したら、[**保存**] を選択します。

6. Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。 
    
    これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。 たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。
    
  
7. **ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。** たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。 Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"パラメーター名 EmailAddresses に一致するパラメーターが見つかりません" が表示されましたか?


"**パラメーター名が電子メールアドレスに一致するパラメーターが見つかりません**" というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかっていること、または、ユーザーが最近追加された場合はカスタムドメインを使用していることを意味します。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy または別のパートナーからサブスクリプションを購入した場合


GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。
  
## <a name="related-articles"></a>関連記事

[別のアドレスからメールを送信する](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md)
  

