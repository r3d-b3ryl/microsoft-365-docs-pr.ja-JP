---
title: IONOS で DNS レコードを 1&1 Microsoft 365 Connectする
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: ドメインを確認し、1&1 つの IONOS for Microsoft で電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 8afdfed0998a262b1df4c95a63e9086e4f71e5b6
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780679"
---
# <a name="connect-your-dns-records-at-ionos-by-11-to-microsoft-365"></a>IONOS で DNS レコードを 1&1 Microsoft 365 Connectする

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

IONOS by 1&1 が DNS ホスティング プロバイダーである場合は、この記事の手順に従ってドメインを確認し、電子メール、Skype for Business Online などの DNS レコードを設定します。

## <a name="before-you-begin"></a>開始する前に

ドメインの DNS レコードを設定するには、次の 2 つのオプションがあります。

- [**ドメイン Connectを使用する**](#use-domain-connect-to-verify-and-set-up-your-domain) 別のメール サービス プロバイダーでドメインを設定していない場合は、ドメイン Connect手順を使用して、Microsoft 365で使用する新しいドメインを自動的に確認して設定します。

    または

- [**手動の手順を使用する**](#create-dns-records-with-manual-setup) 次の手動手順を使用してドメインを確認し、ドメイン レジストラーに追加するレコードをいつ、どのレコードにするかを選択します。 これにより、たとえば便宜上、新しい MX (メール) レコードを設定できます。

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>ドメイン Connectを使用してドメインを確認して設定する

次の手順に従って、MICROSOFT 365を使用して、1&1 つのドメインで IONOS を自動的に確認して設定します。

1. Microsoft 365 管理センターで **設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a> を選択し、設定するドメインを選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-1.png" alt-text="Microsoft 365でドメインを選択します。":::

1. 3 つのドット (その他のアクション) を選択>、[ **セットアップの開始]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. [ドメインの接続方法] でページで、[ **続行**] を選択します。

1. [DNS レコードの追加] ページで、[ **DNS レコードの追加**] を選択します。

1. IONOS by 1&1 ログイン ページで、アカウントにサインインし、**Connect**、**許可** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-3.png" alt-text="[Connect]、[許可] の順に選択します。":::

    これで、Microsoft 365のドメイン設定が完了します。

## <a name="create-dns-records-with-manual-setup"></a>手動セットアップを使用して DNS レコードを作成する

IONOS でこれらのレコードを 1&1 ずつ追加すると、ドメインはMicrosoft サービスで動作するように設定されます。

> [!CAUTION]
> IONOS by 1&1 では、ドメインが MX レコードと最上位の自動検出 CNAME レコードの両方を持つことが許可されないことに注意してください。 このため、Exchange Online for Microsoft を構成する方法が制限されます。 回避策がありますが、IONOS でサブドメインを 1&1 ずつ作成した経験がある場合 **にのみ** 使用することをお勧めします。
> この[サービスの制限](../setup/domains-faq.yml)にもかかわらず、IONOS で独自の Microsoft DNS レコードを 1&1 で管理することを選択した場合は、この記事の手順に従ってドメインを確認し、電子メール、Skype for Business Online などの DNS レコードを設定します。

> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

1. 作業を開始するには、 [このリンク](https://my.1and1.com/)を使用して、IONOS の 1&1 のドメイン ページに移動します。 You'll be prompted to log in.

1. **メニューを** 選択し、**ドメインと SSL** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::

1. 更新するドメインの **[アクション]** で、歯車コントロールを選択し、 **DNS** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから DNS を選択します。":::

1. [ **レコードの追加]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **TXT** セクションを選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-4.png" alt-text="TXT セクションを選択します。":::

1. [DNS レコードの追加] ページの新しいレコードのボックスに、次の表の値を入力またはコピーして貼り付けます。

    |ホスト名|値|TTL|
    |---|---|---|
    |(このフィールドは空白のままにします)|MS=ms *XXXXXXXX*  <br/> 注: これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|1 hour|

1. **[保存]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-5.png" alt-text="[保存] を選択します。":::

    数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

Microsoft 365でレコードを確認するには:

1. 管理センターで、**設定** \> ドメインに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。

1. [ドメイン] ページで、確認するドメインを選択し、[ **セットアップの開始]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。

1. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

> [!NOTE]
> 1und1.de に登録している場合は、 [ここでサインインします](https://go.microsoft.com/fwlink/?linkid=859152)。

1. 作業を開始するには、 [このリンク](https://my.1and1.com/)を使用して、IONOS の 1&1 のドメイン ページに移動します。 You'll be prompted to log in.

1. **メニューを** 選択し、**ドメインと SSL** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::

1. 更新するドメインの **[アクション]** で、歯車コントロールを選択し、 **DNS** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから DNS を選択します。":::

1. [ **レコードの追加]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **MX** セクションを選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX.png" alt-text="MX セクションを選択します。":::

1. [DNS レコードの追加] ページの新しいレコードのボックスに、次の表の値を入力またはコピーして貼り付けます。

    |ホスト名|Points to |Priority|TTL|
    |---|---|---|---|
    |@|*\<domain-key\>*.mail.protection.outlook.com  <br/>  注: Microsoft アカウントから取得します \<domain-key\> 。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|10  <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。|1 hour|

1. **[保存]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX-Save.png" alt-text="[保存] を選択します。":::

1. MX レコードが既に一覧表示されている場合は、[**レコードの追加]** ページの [レコードごみ箱の削除] を選択して、それぞれを **削除** します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Delete.png" alt-text="[レコードの削除] を選択します。":::

### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

> [!NOTE]
> 1und1.de に登録している場合は、 [ここでサインインします](https://go.microsoft.com/fwlink/?linkid=859152)。

1. 作業を開始するには、 [このリンク](https://my.1and1.com/)を使用して、IONOS の 1&1 のドメイン ページに移動します。 You'll be prompted to log in.

1. **メニューを** 選択し、**ドメインと SSL** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::

1. 更新するドメインの **[アクション]** で、歯車コントロールを選択し、 **DNS** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから DNS を選択します。":::

   次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します

   (これは、1&1 つの IONOS が最上位レベルの CNAME レコードを 1 つだけサポートしていますが、Microsoft では複数の CNAME レコードが必要であるためです。

   最初に、Autodiscover サブドメインを作成します。

1. サブドメイン **を選択します**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="[サブドメイン] を選択します。":::

1. [ **サブドメインの追加]** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="[サブドメインの追加] を選択します。":::

1. 新しい **サブドメインの [サブドメインの追加]** ボックスで、次の表の **[サブドメインの追加]** の値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します)。

    |サブドメインを追加する|Alias|
    |---|---|
    |autodiscover|autodiscover.outlook.com|

1. 先ほど作成 **した自動検出** サブドメインの **[アクション]** で、歯車コントロールを選択し、ドロップダウン リストから **DNS** を選択します。

1. [ **レコードの追加]** を選択し、 **CNAME** セクションを選択します。

1. [**Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。

    |サブドメインを追加する|Alias|
    |---|---|
    |autodiscover|autodiscover.outlook.com|

1. **[保存]** を選択します。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1 つの*  SPF レコードを作成します。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)を参照してください。 SPF レコードを検証するには、これらの[SPF 検証ツール](../setup/domains-faq.yml)のいずれかを使用します。

> [!NOTE]
> 1und1.de に登録している場合は、 [ここでサインインします](https://go.microsoft.com/fwlink/?linkid=859152)。

1. 作業を開始するには、 [このリンク](https://my.1and1.com/)を使用して、IONOS の 1&1 のドメイン ページに移動します。 You'll be prompted to log in.

1. **メニューを** 選択し、**ドメインと SSL** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::

1. 更新するドメインの **[アクション]** で、歯車コントロールを選択し、 **DNS** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから DNS を選択します。":::

1. [ **レコードの追加]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **SPF (TXT)** セクションを選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT.png" alt-text="SPF (TXT) セクションを選択します。":::

1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

    |種類|ホスト名|値|TTL|
    |---|---|---|---|
    |SPF (TXT)|(このフィールドは空のままにします。)|v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|1 時間|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT-Save.png" alt-text="[保存] を選択します。":::

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

Microsoft Teamsに加えて、組織がチャット、電話会議、ビデオ通話などのオンラインコミュニケーション サービスにSkype for Businessを使用している場合にのみ、このオプションを選択します。 Skypeには、ユーザー間通信用の 2 つの SRV レコードと、ユーザーをサインインしてサービスに接続するための 2 つの CNAME レコードの 4 つのレコードが必要です。

### <a name="add-two-additional-cname-records"></a>2 つの CNAME レコードを追加する

1. 作業を開始するには、 [このリンク](https://my.1and1.com/)を使用して、IONOS の 1&1 のドメイン ページに移動します。 You'll be prompted to log in.

1. **メニューを** 選択し、**ドメインと SSL** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::

1. 更新するドメインの **[アクション]** で、歯車コントロールを選択し、 **DNS** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから DNS を選択します。":::

   次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します

   (これは、1&1 つの IONOS が最上位レベルの CNAME レコードを 1 つだけサポートしていますが、Microsoft では複数の CNAME レコードが必要であるためです。

   最初に、lyncdiscover サブドメインを作成します。

1. サブドメイン **を選択します**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="[サブドメイン] を選択します。":::

1. [ **サブドメインの追加]** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="[サブドメインの追加] を選択します。":::

1. 新しい **サブドメインの [サブドメインの追加]** ボックスで、次の表の **[サブドメインの追加]** の値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します)。

    |サブドメインを追加する|Alias|
    |---|---|
    |lyncdiscover   |webdir.online.lync.com  |

1. 先ほど作成 **した lyncdiscover** サブドメインの **[アクション]** で、歯車コントロールを選択し、ドロップダウン リストから **[DNS**] を選択します。

1. [ **レコードの追加]** を選択し、 **CNAME** セクションを選択します。

1. [**Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。

    |Create Subdomain|Alias|
    |---|---|
    |lyncdiscover|webdir.online.lync.com|

1. 別のサブドメイン (SIP) を作成する: [ **サブドメインの追加]** を選択します。

1. 新しい **サブドメインの [サブドメインの追加]** ボックスで、次の表の **[サブドメインの追加]** の値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します)。

    |サブドメインを追加する|Alias|
    |---|---|
    |sip|sipdir.online.lync.com|

1. 作成したサブドメインの **[アクション]** で、歯車コントロールを選択し、ドロップダウン リストから **[DNS** ] を選択します。

1. [ **レコードの追加]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **CNAME** セクションを選択します。

1. [ **エイリアス:** ] ボックスに、次の表の **エイリアス** 値のみを入力またはコピーして貼り付けます。

    |Create Subdomain|Alias|
    |---|---|
    |sip|sipdir.online.lync.com|

1. 免責事項の [ **I am aware**] チェック ボックスをオンにして、[ **Save**] を選択します。

## <a name="add-the-two-srv-records-required-for-microsoft"></a>Microsoft に必要な 2 つの SRV レコードを追加する

> [!NOTE]
> 1und1.de に登録している場合は、 [ここでサインインします](https://go.microsoft.com/fwlink/?linkid=859152)。

1. 作業を開始するには、 [このリンク](https://my.1and1.com/)を使用して、IONOS の 1&1 のドメイン ページに移動します。 You'll be prompted to log in.

1. **メニューを** 選択し、**ドメインと SSL** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::

1. 更新するドメインの **[アクション]** で、歯車コントロールを選択し、 **DNS** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから DNS を選択します。":::

1. [ **レコードの追加]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **[SRV**] セクションを選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV.png" alt-text="[SRV] セクションを選択します。":::

1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

    |種類|サービス|プロトコル|ホスト名|Points to |優先度|太さ|ポート|TTL|
    |---|---|---|---|---|---|---|---|---|
    |SRV|_sip|tls|(このフィールドは空のままにします。)|sipdir.online.lync.com|100|1|443|1 hour|
    |SRV|_sipfederationtls|tcp|(このフィールドは空のままにします。)|sipfed.online.lync.com|100|1|5061|1 時間|

1. **[保存]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV-Save.png" alt-text="[保存] を選択します。":::

1. 残りの SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>詳細オプション: Microsoft 365のIntuneとモバイル デバイス管理

このサービスは、ドメインに接続するモバイル デバイスをセキュリティで保護し、リモートで管理するのに役立ちます。 モバイル デバイス管理では、ユーザーがデバイスをサービスに登録できるように、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

> [!IMPORTANT]
> 他の CNAME レコードに使用したサブドメインプロシージャに従い、次の表の値を指定します。

1. 作業を開始するには、 [このリンク](https://my.1and1.com/)を使用して、IONOS の 1&1 のドメイン ページに移動します。 You'll be prompted to log in.

1. **メニューを** 選択し、**ドメインと SSL** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::

1. 更新するドメインの **[アクション]** で、歯車コントロールを選択し、 **DNS** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから DNS を選択します。":::

   次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します

   (これは、1&1 つの IONOS が最上位レベルの CNAME レコードを 1 つだけサポートしていますが、Microsoft では複数の CNAME レコードが必要であるためです。

   最初に、lyncdiscover サブドメインを作成します。

1. サブドメイン **を選択します**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="[サブドメイン] を選択します。":::

1. [ **サブドメインの追加]** を選択します。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="[サブドメインの追加] を選択します。":::

1. 新しい **サブドメインの [サブドメインの追加]** ボックスで、次の表の **[サブドメインの追加]** の値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します)。

    |サブドメインを追加する|Alias|
    |---|---|
    |enterpriseregistration|enterpriseregistration.windows.net|

1. 先ほど作成した **enterpriseregistration** サブドメインの **[アクション]** で、歯車コントロールを選択し、ドロップダウン リストから **DNS** を選択します。

1. [ **レコードの追加]** を選択し、 **CNAME** セクションを選択します。

1. [**Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。

    |サブドメインを追加する|Alias|
    |---|---|
    |enterpriseregistration|enterpriseregistration.windows.net|

1. 別のサブドメインを作成する: [ **サブドメインの追加]** を選択します。

1. 新しい **サブドメインの [サブドメインの追加]** ボックスで、次の表の **[サブドメインの追加]** の値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します)。

    |サブドメインを追加する|Alias|
    |---|---|
    |enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|

1. 先ほど作成した **enterpriseenrollment** サブドメインの **[アクション]** で、歯車コントロールを選択し、ドロップダウン リストから **DNS** を選択します。

1. [ **レコードの追加]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **CNAME** セクションを選択します。

1. [ **エイリアス:** ] ボックスに、次の表の **エイリアス** 値のみを入力またはコピーして貼り付けます。

    |Create Subdomain|Alias|
    |---|---|
    |enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|

1. 免責事項の [ **I am aware**] チェック ボックスをオンにして、[ **Save**] を選択します。
