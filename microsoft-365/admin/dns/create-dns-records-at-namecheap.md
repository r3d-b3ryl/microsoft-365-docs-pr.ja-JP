---
title: Namecheap で DNS レコードを Microsoft 365 に接続する
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: ドメインを確認し、Namecheap for Microsoft で電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 8af8b88cc2bdd0c819f349e2820d637b99e6d730
ms.sourcegitcommit: 8cd230e243eba452b27f725d66152becb6aff49b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563343"
---
# <a name="connect-your-dns-records-at-namecheap-to-microsoft-365"></a>Namecheap で DNS レコードを Microsoft 365 に接続する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

使用している DNS ホスティング プロバイダーが Namecheap の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。

Namecheap でこれらのレコードを追加すると、Microsoft サービスで動作するようにドメインが設定されます。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

1. まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。 サインインして続行するように求められます。

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap にサインインします。":::

1. ランディング ページの [ **アカウント**] で、ドロップダウン **リストから [ドメイン 一覧** ] を選択します。

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="ドロップダウン リストから [ドメイン 一覧] を選択します。":::

1. [ドメイン一覧] ページで、編集するドメインを選択し、[ **管理**] を選択します。

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="[管理] を選択します。":::

1. [ **高度な DNS**] を選択します。

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="[高度な DNS] を選択します。":::

1. [ **ホスト レコード]** セクションで、[ **新しいレコードの追加**] を選択します。

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="[新しいレコードの追加] を選択します。":::

1. [ **Type**] ドロップダウンで、[ **TXT Record**] を選びます。

    > [!NOTE]
    > [**ADD NEW RECORD]\(新しいレコードの追加**\) を選択すると、[**種類**] ドロップダウンが自動的に表示されます。

     :::image type="content" source="../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png" alt-text="[TXT レコード] を選択します。":::

1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

    (ドロップダウン リストから **TTL** 値を選択します)。

    |型|ホスト|値|TTL|
    |---|---|---|---|
    |TXT|@|MS=ms *XXXXXXXX*  <br/>**注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)|30 分|

     :::image type="content" source="../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png" alt-text="テーブルの値をコピーして貼り付けます。":::

1. 変更の **保存** (チェック マーク) コントロールを選択します。

     :::image type="content" source="../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png" alt-text="[変更の保存] コントロールを選択します。":::

1. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

Microsoft 365 でレコードを確認するには、

1. 管理センターで、[ **設定ドメイン]** \> に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。

1. [ドメイン] ページで、確認するドメインを選択し、[ **セットアップの開始]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。

1. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。 サインインして続行するように求められます。

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap にサインインします。":::

1. ランディング ページの [ **アカウント**] で、ドロップダウン **リストから [ドメイン 一覧** ] を選択します。

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="ドロップダウン リストから [ドメイン 一覧] を選択します。":::

1. [ **ドメイン一覧** ] ページで、編集するドメインを選択し、[ **管理**] を選択します。

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="[管理] を選択します。":::

1. [ **高度な DNS**] を選択します。

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="[高度な DNS] を選択します。":::

1. [ **MAIL SETTINGS**] セクションで、[ **Email Forwarding**] ドロップダウン リストから [ **Custom MX**] を選びます。

    (下へスクロールしなければならないことがあります。)

     :::image type="content" source="../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png" alt-text="[カスタム MX] を選択します。":::

1. [ **新しいレコードの追加]** を選択します。

     :::image type="content" source="../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png" alt-text="新しいレコードを追加します。":::

1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます

    ([ **Priority**] ボックスは、[ **Value**] ボックスの右側にある名前のないボックスです。 ドロップダウン リストから **TTL** 値を選択します)。

    |型|ホスト|値|Priority|TTL|
    |---|---|---|---|---|
    |MX レコード|@|\<*domain-key*\>.mail.protection.outlook.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **メモ：** Microsoft アカウントから取得します *\<domain-key\>* 。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)|0  <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。|30 分|

     :::image type="content" source="../../media/f3b76d62-5022-48c1-901b-8615a8571309.png" alt-text="テーブルの値をコピーして貼り付けます。":::

1. 変更の **保存** (チェック マーク) コントロールを選択します。

     :::image type="content" source="../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png" alt-text="[変更の保存] コントロールを選択します。":::

1. これ以外の MX レコードがある場合は、次の 2 段階のプロセスに従って、それぞれのレコードを削除します。

    最初に、 **削除** するレコードの削除 (ごみ箱) を選択します。

     :::image type="content" source="../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png" alt-text="[削除] を選択します。":::

    次に、[ **はい** ] を選択して削除を確認します。

     :::image type="content" source="../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png" alt-text="[はい] を選択します。":::

    この手順の最初に追加した MX レコード以外の MX レコードをすべて削除します。

## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。 サインインして続行するように求められます。

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap にサインインします。":::

1. ランディング ページの [ **アカウント**] で、ドロップダウン **リストから [ドメイン 一覧** ] を選択します。

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="[ドメイン 一覧] を選択します。":::

1. [ **ドメイン一覧** ] ページで、編集するドメインを選択し、[ **管理**] を選択します。

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="[管理] を選択します。":::

1. [ **高度な DNS**] を選択します。

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="[高度な DNS] を選択します。":::

1. [ **ホスト レコード]** セクションで、[ **新しいレコードの追加**] を選択します。

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="[新しいレコードの追加] を選択します。":::

1. [ **Type**] ドロップダウンで、[ **CNAME Record**] を選びます。

    > [!NOTE]
    > [**ADD NEW RECORD]\(新しいレコードの追加**\) を選択すると、[**種類**] ドロップダウンが自動的に表示されます。

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="[CNAME レコード] を選択します。":::

1. 新しいレコードの空のボックスで、[ **Record Type**] に [ **CNAME**] を選び、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

    |型|ホスト|値|TTL|
    |---|---|---|---|
    |CNAME|autodiscover|autodiscover.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|自動|

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="テーブルの値をコピーして貼り付けます。":::

1. 変更の **保存** (チェック マーク) コントロールを選択します。

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="[変更の保存] コントロールを選択します。":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む *1 つの*  SPF レコードを作成します。

1. まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。 サインインして続行するように求められます。

1. ランディング ページの [ **アカウント**] で、ドロップダウン **リストから [ドメイン 一覧** ] を選択します。

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="[ドメイン 一覧] を選択します。":::

1. [ **ドメイン一覧** ] ページで、編集するドメインを選択し、[ **管理**] を選択します。

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="[管理] を選択します。":::

1. [ **高度な DNS**] を選択します。

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="[高度な DNS] を選択します。":::

1. [ **ホスト レコード]** セクションで、[ **新しいレコードの追加**] を選択します。

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="[新しいレコードの追加] を選択します。":::

1. [ **Type**] ドロップダウンで、[ **TXT Record**] を選びます。

    > [!NOTE]
    > [**ADD NEW RECORD]\(新しいレコードの追加**\) を選択すると、[**種類**] ドロップダウンが自動的に表示されます。

     :::image type="content" source="../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png" alt-text="[TXT レコード] を選択します。":::

1. 新規レコードのボックスに、次の値を入力するか、次の表から値をコピーして貼り付けます

    (ドロップダウン リストから **TTL** 値を選択します)。

    |型|ホスト|値|TTL|
    |---|---|---|---|
    |TXT|@|v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|30 分|

     :::image type="content" source="../../media/ea0829f1-990b-424b-b26e-9859468318dd.png" alt-text="テーブルの値をコピーして貼り付けます。":::

1. 変更の **保存** (チェック マーク) コントロールを選択します。

     :::image type="content" source="../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png" alt-text="[変更の保存] コントロールを選択します。":::

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

Microsoft Teams に加えて、組織がチャット、電話会議、ビデオ通話などのオンラインコミュニケーション サービスにSkype for Businessを使用している場合にのみ、このオプションを選択します。 Skype には、ユーザー間通信用の 2 つの SRV レコードと、ユーザーをサインインしてサービスに接続するための 2 つの CNAME レコードの 4 つのレコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。 サインインするように求められます。

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap にサインインします。":::

1. ランディング ページの [ **アカウント**] で、ドロップダウン **リストから [ドメイン 一覧** ] を選択します。

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="[ドメイン 一覧] を選択します。":::

1. [ **ドメイン一覧** ] ページで、編集するドメインを選択し、[ **管理**] を選択します。

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="[管理] を選択します。":::

1. [ **高度な DNS**] を選択します。

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="[高度な DNS] を選択します。":::

1. [ **ホスト レコード]** セクションで、[ **新しいレコードの追加**] を選択します。

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="[新しいレコードの追加] を選択します。":::

1. [ **Type**] ドロップダウンで、[ **SRV Record**] を選びます。

    > [!NOTE]
    > [**ADD NEW RECORD]\(新しいレコードの追加**\) を選択すると、[**種類**] ドロップダウンが自動的に表示されます。

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="SRV レコードの種類を選択します。":::

1. 新規レコードの空のボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

    |サービス|プロトコル|優先度|太さ|ポート|Target|TTL|
    |---|---|---|---|---|---|---|
    |_sip|_tls|100|1|443|sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません**|自動|
    |_sipfederationtls|_tcp|100|1|5061|sipfed.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません**|自動|

     :::image type="content" source="../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png" alt-text="テーブルの値をコピーして貼り付けます。":::

1. 変更の **保存** (チェック マーク) コントロールを選択します。

     :::image type="content" source="../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png" alt-text="[変更の保存] コントロールを選択します。":::

1. テーブルの 2 行目から値を選択して、他の SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Skype for Businessに必要な 2 つの CNAME レコードを追加する

1. [ **ホスト レコード]** セクションで、[ **新しいレコードの追加**] を選択します。

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="[新しい名前の追加] を選択します。":::

1. [ **種類** ] ドロップダウンで [ **CNAME**] を選択します。

    > [!NOTE]
    > [**ADD NEW RECORD]\(新しいレコードの追加**\) を選択すると、[**種類**] ドロップダウンが自動的に表示されます。

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="CNAME を選択します。":::

1. 新しいレコードの空のボックスに、テーブルの最初の行の値を入力またはコピーして貼り付けます。

    |型|ホスト|値|TTL|
    |---|---|---|---|
    |CNAME|sip|sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません**|自動|
    |CNAME|lyncdiscover|webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|自動|

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="テーブルから CNAME 値をコピーして貼り付けます。":::

1. 変更の **保存** (チェック マーク) コントロールを選択します。

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="[変更の保存] コントロールを選択します。":::

1. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>詳細オプション: Microsoft 365 のIntuneとモバイル デバイス管理

このサービスは、ドメインに接続するモバイル デバイスをセキュリティで保護し、リモートで管理するのに役立ちます。 モバイル デバイス管理では、ユーザーがデバイスをサービスに登録できるように、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Mobile デバイス管理に必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。 サインインするように求められます。

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap にサインインします。":::

1. ランディング ページの [ **アカウント**] で、ドロップダウン **リストから [ドメイン 一覧** ] を選択します。

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="[ドメイン 一覧] を選択します。":::

1. [ **ドメイン一覧** ] ページで、編集するドメインを選択し、[ **管理**] を選択します。

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="[管理] を選択します。":::

1. [ **高度な DNS**] を選択します。

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

1. [ **ホスト レコード]** セクションで、[ **新しいレコードの追加**] を選択します。

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="[新しいレコードの追加] を選択します。":::

1. [ **Type**] ドロップダウンで、[ **CNAME Record**] を選びます。

    > [!NOTE]
    > [**ADD NEW RECORD]\(新しいレコードの追加**\) を選択すると、[**種類**] ドロップダウンが自動的に表示されます。

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="[CNAME レコード] を選択します。":::

1. 新しいレコードの空のボックスに、テーブルの最初の行の値を入力またはコピーして貼り付けます。

    |型|ホスト|値|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|自動|
    |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|自動|

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="テーブルの値をコピーして貼り付けます。":::

1. [ **変更の保存]** コントロールを選択します。

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="[変更の保存] コントロールを選択します。":::

1. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
