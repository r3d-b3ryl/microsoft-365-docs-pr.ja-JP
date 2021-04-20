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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Microsoft 365 for business アカウントに関連付けられたメール エイリアスと呼ばれる複数の電子メール アドレスを持つ方法について説明します。 '
ms.openlocfilehash: 4003dcfca29a722ccdf9b86cca5aa1141fbdb367
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892807"
---
# <a name="add-another-email-alias-for-a-user"></a>ユーザーに別のメール エイリアスを追加する
  
この記事は、ビジネス サブスクリプションを持つ Microsoft 365 管理者向けです。 ホーム ユーザー向けではありません。
  
Microsoft 365 のプライマリ メール アドレスは、通常、アカウントの作成時にユーザーが割り当てられた電子メール アドレスです。 ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。 また、複数の電子メール アドレスを Microsoft 365 for business アカウントに関連付けすることもできます。 これらの追加アドレスをエイリアスと呼びます。 
  
たとえば、Jenna が電子メール アドレス jenna@contosoco.com を持っているが、jen@contosoco.com でメールを受け取りたい場合は、その名前で彼女を参照する人もいたとします。 両方のメール アドレスが Jenna の受信トレイに移動できるよう、エイリアスを作成できます。
<br><br>  
  
ユーザーあたり最大 400 個のエイリアスを作成できます。 追加の料金やライセンスは必要ありません。
  
> [!Tip]
> 複数のユーザーが 1 つの電子メール アドレスに送信されるメールを管理する場合 (info@NodPublishers.com、sales@NodPublishers.com メールボックスを作成します。 詳細については、「共有メールボックスの [作成」を参照してください](create-a-shared-mailbox.md)。
  
## <a name="add-email-aliases-to-a-user"></a>ユーザーにメール エイリアスを追加する
<a name="AddEmailPreview"> </a>

これを行うには [、管理者のアクセス許可](../add-users/about-admin-roles.md) が必要です。 

  
::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. [アクティブ ユーザー **] ページ** で、[メール エイリアスの管理] > **ユーザーを選択します**。 ユーザーにライセンスが割り当てられていない場合、このオプションは表示しません。 
    
3. [+ **エイリアスの追加] を選択** し、ユーザーの新しいエイリアスを入力します。   
    
    > [!Important] 
    > エラー メッセージが表示された場合は、パラメーター名 **'EmailAddresses,"** と一致するパラメーターが見つかりません。これは、テナントのセットアップを終了するにはもう少し時間がかかるか、最近追加した場合はカスタム ドメインを使用します。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
    
  
    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 リストに別のドメイン名を追加するには [、「Add a domain to Microsoft 365」を参照してください](../setup/add-domain.md)。 
  
     
5. 完了したら、[変更の保存] **を選択します**。
    
6. Microsoft 365 全体で新しいエイリアスが設定されるのを 24 時間待ちます。
    
    これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。 たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。
    
  
7. **ユーザーが返信すると *、From* アドレスは Outlook クライアントに依存します。Outlook on the web では、電子メールが受信されたエイリアスが使用されます (これを ping-pong の原則と呼ぶ)。Outlook デスクトップは、メインのメール エイリアスを使用します。** たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。 Eliza が Outlook デスクトップを使用してメッセージに返信すると、メインの電子メール アドレスは、Eliza@NodPublishers.com として表示 Sales@NodPublishers.com。
    
::: moniker-end

::: moniker range="o365-germany"
    
1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。 
    
    
2. [**アクティブなユーザー**] ページで、編集するユーザー名を選びます。

3. [ユーザー名 **/ メール エイリアス] の横にある [** 編集] を **選択します**。

    > [!Important] 
    > エラー メッセージが表示された場合は、パラメーター名 **'EmailAddresses,"** と一致するパラメーターが見つかりません。これは、テナントのセットアップを終了するにはもう少し時間がかかるか、最近追加した場合はカスタム ドメインを使用します。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。

4. [エイリアス] の下 **のテキスト ボックス** に、新しいメール エイリアスの最初の部分を入力します。 独自のドメインを Microsoft 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。 次に **[追加]** を選択します。

    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 リストに別のドメイン名を追加するには [、「Add a domain to Microsoft 365」を参照してください](../setup/add-domain.md)。 

5. 完了したら、[**保存**] を選択します。

6. Microsoft 365 全体で新しいエイリアスが設定されるのを 24 時間待ちます。 
    
    これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。 たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。
    
  
7. **ユーザーが返信すると *、From* アドレスは Outlook クライアントに依存します。Outlook on the web では、電子メールが受信されたエイリアスが使用されます (これを ping-pong の原則と呼ぶ)。Outlook デスクトップは、メインのメール エイリアスを使用します。** たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。 Eliza が Outlook デスクトップを使用してメッセージに返信すると、メインの電子メール アドレスは、Eliza@NodPublishers.com として表示 Sales@NodPublishers.com。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。 

    
2. [**アクティブなユーザー**] ページで、編集するユーザー名を選びます。

3. [ユーザー名 **/ メール エイリアス] の横にある [** 編集] を **選択します**。

    > [!Important] 
    > エラー メッセージが表示された場合は、パラメーター名 **'EmailAddresses,"** と一致するパラメーターが見つかりません。これは、テナントのセットアップを終了するにはもう少し時間がかかるか、最近追加した場合はカスタム ドメインを使用します。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。

4. [エイリアス] の下 **のテキスト ボックス** に、新しいメール エイリアスの最初の部分を入力します。 独自のドメインを Microsoft 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。 次に **[追加]** を選択します。

    > [!IMPORTANT]
    > GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。 
  
    > [!TIP]
    > メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。 リストに別のドメイン名を追加するには [、「Add a domain to Microsoft 365」を参照してください](../setup/add-domain.md)。 

5. 完了したら、[**保存**] を選択します。

6. Microsoft 365 全体で新しいエイリアスが設定されるのを 24 時間待ちます。 
    
    これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。 たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。
    
  
7. **ユーザーが返信すると *、From* アドレスは Outlook クライアントに依存します。Outlook on the web では、電子メールが受信されたエイリアスが使用されます (これを ping-pong の原則と呼ぶ)。Outlook デスクトップは、メインのメール エイリアスを使用します。** たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。 Eliza が Outlook デスクトップを使用してメッセージに返信すると、メインの電子メール アドレスは、Eliza@NodPublishers.com として表示 Sales@NodPublishers.com。

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"パラメーター名 EmailAddresses に一致するパラメーターが見つかりません" を取得しましたか?


"パラメーター名 **EmailAddresses** に一致するパラメーターが見つかりません" というエラー メッセージが表示された場合は、テナントのセットアップを完了するにはもう少し時間がかかっています。最近追加した場合は、カスタム ドメインが表示されます。 セットアップ プロセスが完了するには、最大 4 時間かかります。 しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。 問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy または別のパートナーからサブスクリプションを購入した場合


GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。

## <a name="sending-email-from-the-proxy-address-easily"></a>プロキシ アドレスからメールを簡単に送信する

2021 年 4 月に新しい機能が展開され、Outlook on the web を使用すると、ユーザーはエイリアスから簡単に送信できます。 テナント管理者がコマンドレットを使用するテナントに機能がロールアウトすると、テナント内のユーザーは、各エントリが Outlook 設定のエイリアスに対応するチェック ボックスの一覧にアクセスできます。 `Set-OrganizationConfig -SendFromAliasEnabled $true` エイリアスを選択すると、[新規作成] フォームの [From] ドロップダウンにエイリアスが表示されます。
  
## <a name="related-articles"></a>関連記事

[別のアドレスからメールを送信する](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md)
