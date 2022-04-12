---
title: Cloudflare で DNS レコードをMicrosoft 365にConnectする
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: ドメインを確認し、Cloudflare for Microsoft で電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 164a681cccac3385d2ca963ac58706c8e743bc1e
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780371"
---
# <a name="connect-your-dns-records-at-cloudflare-to-microsoft-365"></a>Cloudflare で DNS レコードをMicrosoft 365にConnectする

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

使用している DNS ホスティング プロバイダーが Cloudflare の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。

## <a name="before-you-begin"></a>はじめに

ドメインの DNS レコードを設定するには、次の 2 つのオプションがあります。

- [**ドメイン Connectを使用する**](#use-domain-connect-to-verify-and-set-up-your-domain) 別のメール サービス プロバイダーでドメインを設定していない場合は、ドメイン Connect手順を使用して、Microsoft 365で使用する新しいドメインを自動的に確認して設定します。

    または

- [**手動の手順を使用する**](#create-dns-records-with-manual-setup) 次の手動手順を使用してドメインを確認し、ドメイン レジストラーに追加するレコードをいつ、どのレコードにするかを選択します。 これにより、たとえば便宜上、新しい MX (メール) レコードを設定できます。

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>ドメイン Connectを使用してドメインを確認して設定する

次の手順に従って、Microsoft 365を使用して Cloudflare ドメインを自動的に確認して設定します。

1. Microsoft 365 管理センターで [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**ドメイン**</a>] を選択し、設定するドメインを選択します。

1. 3 つのドット (その他のアクション) \> を選択して **、[セットアップの開始]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. [ドメインの接続方法] でページで、[ **続行**] を選択します。

1. [DNS レコードの追加] ページで、[ **DNS レコードの追加**] を選択します。

1. Cloudflare ログイン ページで、アカウントにサインインし、[承認] を選択 **します**。

    これで、Microsoft 365のドメイン設定が完了します。

## <a name="create-dns-records-with-manual-setup"></a>手動セットアップを使用して DNS レコードを作成する

Cloudflare でこれらのレコードを追加すると、Microsoft 365 サービスを操作するようにドメインが設定されます。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。

Cloudflare にサインアップしたときに、Cloudflare の [ Setup] プロセスを使用してドメインを追加しました。

追加したドメインは、Cloudflare または別のドメイン レジストラーから購入されました。 Microsoft 365でドメインの DNS レコードを確認して作成するには、最初にドメイン レジストラーでネームサーバーを変更して Cloudflare ネームサーバーを使用するようにする必要があります。

ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。

1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。

2. 次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。

    |型|値|
    |---|---|
    |1 番目のネーム サーバー|Cloudflare によって提供されるネーム サーバーの値を使用します。|
    |2 番目のネーム サーバー|Cloudflare によって提供されるネーム サーバーの値を使用します。|

    > [!TIP]
    > You should use at least two name server records. 他にネーム サーバーが一覧表示されている場合は、それらを削除する必要があります。

3. 変更内容を保存します。

> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft メールとその他のサービスがすべてドメインで動作するように設定されます。

### <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. ホーム ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[ **DNS**] を選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[ **+レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから TXT の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|TTL|コンテンツ|
    |---|---|---|:----|
    |TXT|@|30 minutes|MS=*msXXXXXXXXXXX* <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-TXT-save.png" alt-text="[レコードの追加] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

ドメイン レジストラーのサイトにレコードを追加したので、Microsoft に戻ってレコードを検索します。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

Microsoft 365でレコードを確認するには:

1. 管理センターで、**設定** \> ドメインに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。

1. [ドメイン] ページで、確認するドメインを選択し、[ **セットアップの開始]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。

1. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. ホーム ページで、更新するドメインを選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[ **DNS**] を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[ **+レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから MX の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

   |種類|氏名|メール サーバー|TTL|優先度|
   |---|---|---|---|---|
   |MX|@|*\<domain-key\>*.mail.protection.outlook.com <br/> **メモ：** Microsoft 365 アカウントから取得します *\<domain-key\>*。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|30 分|1 <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。 <br/>|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-mx-save.png" alt-text="[レコードの追加] を選択します。":::

1. [MX レコード] セクションに他の **MX レコード** がある場合は、[ **編集]** を選択して削除し、[削除] を選択 **します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-mx-delete.png" alt-text="[削除] を選択します。":::

1. 確認ダイアログ ボックスで、[ **削除** ] を選択して変更を確定します。

### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. ホーム ページで、更新するドメインを選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[ **DNS**] を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. **[DNS 管理**] ページで、[**+レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから CNAME の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|Target|TTL|
    |---|---|---|---|
    |CNAME|autodiscover|autodiscover.outlook.com|Auto|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="[保存] を選択します。":::

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、必要なMicrosoft 365値を現在のレコードに追加して、両方の値セットを含む *1 つの* SPF レコードを作成します。

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. ホーム ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[ **DNS**] を選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[ **+レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから TXT の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|TTL|コンテンツ|
    |---|---|---|---|
    |TXT|@|30 minutes|v=spf1 include:spf.protection.outlook.com -all <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-TXT-save.png" alt-text="[保存] を選択します。":::

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

Microsoft Teamsに加えて、組織がチャット、電話会議、ビデオ通話などのオンラインコミュニケーション サービスにSkype for Businessを使用している場合にのみ、このオプションを選択します。 Skypeには、ユーザー間通信用の 2 つの SRV レコードと、ユーザーをサインインしてサービスに接続するための 2 つの CNAME レコードの 4 つのレコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

> [!IMPORTANT]
> Cloudflare は、この機能を利用できるようにする責任があることに注意してください。 以下の手順と現在の Cloudflare GUI (グラフィカル ユーザー インターフェイス) の間に不一致が見られる場合は、[Cloudflare Community](https://community.cloudflare.com/)を利用します。

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. ホーム ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[ **DNS**] を選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[**+レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから SRV の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|サービス|プロトコル|TTL|優先度|太さ|ポート|Target|
    |---|---|---|---|---|---|---|---|---|
    |SRV|*domain_name* を使用します。たとえば、contoso.com|_sip|TLS|30 分|100|1|443|sipfed.online.lync.com|
    |SRV|_sipfederationtls|TCP|*domain_name* を使用します。たとえば、contoso.com|30 分|100|1|5061|sipfed.online.lync.com|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-srv-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 番目の行から値をコピーして、他の SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Skype for Businessに必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. ホーム ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[ **DNS**] を選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[**+レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから CNAME の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|Target|TTL|
    |---|---|---|---|
    |CNAME|sip|sipdir.online.lync.com <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|
    |CNAME|lyncdiscover|webdir.online.lync.com. <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|

1. **[保存] を選択します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 行目の値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>詳細オプション: Microsoft 365のIntuneとモバイル デバイス管理

このサービスは、ドメインに接続するモバイル デバイスをセキュリティで保護し、リモートで管理するのに役立ちます。 モバイル デバイス管理では、ユーザーがデバイスをサービスに登録できるように、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Mobile デバイス管理に必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. ホーム ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[ **DNS**] を選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[**+レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから CNAME の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|Target|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net. <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|
    |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com. <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 行目の値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
