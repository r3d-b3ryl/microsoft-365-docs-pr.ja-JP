---
title: GoDaddy で DNS レコードをMicrosoft 365にConnectする
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: ドメインを確認し、GoDaddy for Microsoft で電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 6cf110b55c76ce6c857f13dcd5b0075b309b654f
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780349"
---
# <a name="connect-your-dns-records-at-godaddy-to-microsoft-365"></a>GoDaddy で DNS レコードをMicrosoft 365にConnectする

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。

使用している DNS ホスティング プロバイダーが GoDaddy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。

## <a name="before-you-begin"></a>開始する前に

ドメインの DNS レコードを設定するには、次の 2 つのオプションがあります。

- [**ドメイン Connectを使用する**](#use-domain-connect-to-verify-and-set-up-your-domain) 別のメール サービス プロバイダーでドメインを設定していない場合は、ドメイン Connect手順を使用して、Microsoft 365で使用する新しいドメインを自動的に確認して設定します。

   または

- [**手動の手順を使用する**](#create-dns-records-with-manual-setup) 次の手動手順を使用してドメインを確認し、ドメイン レジストラーに追加するレコードをいつ、どのレコードにするかを選択します。 これにより、たとえば便宜上、新しい MX (メール) レコードを設定できます。

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>ドメイン Connectを使用してドメインを確認して設定する

次の手順に従って、Microsoft 365を使用して GoDaddy ドメインを自動的に確認して設定します。

1. Microsoft 365 管理センターで **設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a> を選択し、設定するドメインを選択します。

1. 3 つのドット (その他のアクション) を選択>、[ **セットアップの開始]** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. [ドメインの接続方法] でページで、[ **続行**] を選択します。

1. [DNS レコードの追加] ページで、[ **DNS レコードの追加**] を選択します。

1. GoDaddy ログイン ページで、アカウントにサインインし、[承認] を選択 **します**。

   これで、Microsoft 365のドメイン設定が完了します。

## <a name="create-dns-records-with-manual-setup"></a>手動セットアップを使用して DNS レコードを作成する

GoDaddy でこれらのレコードを追加すると、Microsoft サービスで動作するようにドメインが設定されます。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。

   ログインを求めるメッセージが表示されたら、ログイン資格情報を使用し、右上にあるログイン名を選択して、[ **マイ 製品**] を選択します。

1. [ **ドメイン]** で、確認するドメインの横にある 3 つのドットを選択し、[DNS の **管理**] を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **レコード**] で [ **追加** ] を選択します (下にスクロールする必要がある場合があります)。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

1. ドロップダウン リストから **TXT を** 選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="[種類] ドロップダウン リストから [TXT] を選択します。":::

1. 新しいレコードのボックスに、テーブルの値を入力またはコピーして貼り付けます。

   |種類|ホスト|TXT Value|TTL|
   |---|---|---|---|
   |TXT|@|MS=ms *XXXXXXXX*<br>**注**: これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|1 hour  <br>|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXT-values.png" alt-text="TXT レコードのテーブルの値を入力します。":::

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXTSave.png" alt-text="[保存] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
Microsoft 365でレコードを確認するには:
  
1. 管理センターで、**設定** \> ドメインに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。

1. [ドメイン] ページで、確認するドメインを選択し、[ **セットアップの開始]** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。
  
1. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。

   ログインを求めるメッセージが表示されたら、ログイン資格情報を使用し、右上にあるログイン名を選択して、[ **マイ 製品**] を選択します。

2. [ **ドメイン]** で、確認するドメインの横にある 3 つのドットを選択し、[DNS の **管理**] を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

3. [ **レコード**] で [ **追加**] を選択します。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

4. ドロップダウン リストから **MX** を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="[種類] ドロップダウン リストから [MX] を選択します。":::

5. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   (ドロップダウン リストから **[種類]** と [ **TTL** ] の値を選択します)。

   |種類|ホスト|Points to |Priority|TTL|
   |---|---|---|---|---|
   |MX|@| *\<domain-key\>*.mail.protection.outlook.com  <br/> **メモ：** Microsoft アカウントから取得します *\<domain-key\>* 。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|10  <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。|1 hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="MX レコードのテーブルの値を入力します。":::

6. **[保存]** を選択します。

### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。

   ログインを求めるメッセージが表示されたら、ログイン資格情報を使用し、右上にあるログイン名を選択して、[ **マイ 製品**] を選択します。

2. [ **ドメイン]** で、確認するドメインの横にある 3 つのドットを選択し、[DNS の **管理**] を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

3. [ **レコード**] で [ **追加**] を選択します。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

4. ドロップダウン リストから **CNAME を** 選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="[種類] ドロップダウン リストから CNAME を選択します。":::

5. CNAME レコードを作成します。

   新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

   (ドロップダウン リストから **TTL** 値を選択します)。

   |種類|ホスト|Points to |TTL|
   |---|---|---|---|
   |CNAME|autodiscover|autodiscover.outlook.com|1 hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="CNAME レコードのテーブルの値を入力します。":::

6. **[保存]** を選択します。

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1 つの*  SPF レコードを作成します。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。

   ログインを求めるメッセージが表示されたら、ログイン資格情報を使用し、右上にあるログイン名を選択して、[ **マイ 製品**] を選択します。

2. [ **ドメイン]** で、確認するドメインの横にある 3 つのドットを選択し、[DNS の **管理**] を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

3. [ **レコード**] で [ **追加**] を選択します。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

4. ドロップダウン リストから **TXT を** 選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="[種類] ドロップダウン リストから [TXT] を選択します。":::

5. In the boxes for the new record, type or copy and paste the following values.

   (ドロップダウン リストから **TTL** 値を選択します)。

   |種類|ホスト|TXT Value|TTL|
   |---|---|---|---|
   |TXT|@|v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|1 時間|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXT-values.png" alt-text="TXT レコードのテーブルの値を入力します。":::

6. **[保存]** を選択します。

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

Microsoft Teamsに加えて、組織がチャット、電話会議、ビデオ通話などのオンラインコミュニケーション サービスにSkype for Businessを使用している場合にのみ、このオプションを選択します。 Skypeには、ユーザー間通信用の 2 つの SRV レコードと、ユーザーをサインインしてサービスに接続するための 2 つの CNAME レコードの 4 つのレコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。

   ログインを求めるメッセージが表示されたら、ログイン資格情報を使用し、右上にあるログイン名を選択して、[ **マイ 製品**] を選択します。

1. [ **ドメイン]** で、確認するドメインの横にある 3 つのドットを選択し、[DNS の **管理**] を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **レコード**] で [ **追加**] を選択します。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

1. ドロップダウン リストから **SRV** を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="[種類] ドロップダウン リストから [SRV] を選択します。":::

1. 1 番目の SRV レコードを作成します。

   新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

   (ドロップダウン リストから **[種類]** と [ **TTL** ] の値を選択します)。

   |種類|サービス|プロトコル|名前|Target|優先度|太さ|ポート|TTL|
   |---|---|---|---|---|---|---|---|---|
   |SRV|_sip|_tls|@|sipdir.online.lync.com|100| 1|443|1 Hour|
   |SRV|_sipfederationtls|_tcp|@| sipfed.online.lync.com| 100|1|5061|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-SRV-values.png" alt-text="SRV レコードのテーブルの値を入力します。":::

1. **[保存]** を選択します。

1. テーブルの 2 行目から値を選択して、他の SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Skype for Businessに必要な 2 つの CNAME レコードを追加する
  
1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。

   ログインを求めるメッセージが表示されたら、ログイン資格情報を使用し、右上にあるログイン名を選択して、[ **マイ 製品**] を選択します。

1. [ **ドメイン]** で、確認するドメインの横にある 3 つのドットを選択し、[DNS の **管理**] を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **レコード**] で [ **追加**] を選択します。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

1. ドロップダウン リストから **CNAME を** 選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="[種類] ドロップダウン リストから CNAME を選択します。":::

1. 新規レコードの空のボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

   |種類|ホスト|Points to |TTL|
   |---|---|---|---|
   |CNAME|sip|sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|
   |CNAME|lyncdiscover|webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="CNAME レコードのテーブルの値を入力します。":::
  
1. **[保存]** を選択します。
  
1. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>詳細オプション: Microsoft 365のIntuneとモバイル デバイス管理

このサービスは、ドメインに接続するモバイル デバイスをセキュリティで保護し、リモートで管理するのに役立ちます。 モバイル デバイス管理では、ユーザーがデバイスをサービスに登録できるように、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records-mobile-device-management"></a>モバイル デバイス管理で必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。

   ログインを求めるメッセージが表示されたら、ログイン資格情報を使用し、右上にあるログイン名を選択して、[ **マイ 製品**] を選択します。

1. [ **ドメイン]** で、確認するドメインの横にある 3 つのドットを選択し、[DNS の **管理**] を選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **レコード**] で [ **追加**] を選択します。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

1. ドロップダウン リストから **CNAME を** 選択します。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="[種類] ドロップダウン リストから CNAME を選択します。":::

1. 新規レコードの空のボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

   |種類|ホスト|Points to |TTL|
   |---|---|---|---|
   |CNAME|enterpriseregistration|enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|
   |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="CNAME レコードのテーブルの値を入力します。":::
  
1. **[保存]** を選択します。
  
1. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
