---
title: 123-reg.co.uk で DNS レコードをMicrosoft 365にConnectする
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Microsoft の 123-reg.co.uk で、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 262aa3757e6dde90d328f596f43b20952d3080b0
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568140"
---
# <a name="connect-your-dns-records-at-123-regcouk-to-microsoft-365"></a>123-reg.co.uk で DNS レコードをMicrosoft 365にConnectする

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。

使用している DNS ホスティング プロバイダーが 123-reg.co.uk の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。

123-reg.co.uk でこれらのレコードを追加すると、Microsoft サービスで動作するようにドメインが設定されます。

> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

2. **[ドメイン**] を選択し、[ドメイン名の概要] ページで、確認するドメインの名前を選択するか、コントロール パネルに移動します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="確認するドメインを選択します。":::

3. [ドメインの管理] ページの [ **詳細設定] の** [ **DNS の管理**] を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

4. [DNS の管理] ページで、[ **高度な DNS** ] タブを選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::

5. 新しいレコードの **[種類** ] ボックスで、ドロップダウン リストから **TXT/SPF** を選択し、次の表の他の値を入力またはコピーして貼り付けます。

    |Hostname|Type|Destination TXT/SPF|
    |---|---|---|
    |@|TXT/SPF|MS=*msXXXXXXXXXXX* <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|

   :::image type="content" source="../../media/dns-123reg/123reg-domains-TypeTXTSPF.png" alt-text="ドロップダウン リストから TXT/SPF の種類を選択し、値を入力します。":::

6. **[追加]** を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-TXTSPF-Add.png" alt-text="[追加] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

ドメイン レジストラーのサイトにレコードを追加したので、Microsoft に戻り、レコードの検索を要求します。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

Microsoft 365でレコードを確認するには:

1. 管理センターで、**設定** \> ドメインに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。

1. [ドメイン] ページで、確認するドメインを選択し、[ **セットアップの開始]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。

1. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

2. On the Domain name overview page, select the name of the domain that you want to edit.

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [ **詳細設定] の** [ **DNS の管理**] を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

4. [DNS の管理] ページで、[ **高度な DNS** ] タブを選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::

5. 新しいレコードの **[種類** ] ボックスでドロップダウン リストから **[MX** ] を選択し、次の表の他の値を入力またはコピーして貼り付けます。

    |Hostname|Type|Priority|Destination MX|
    |---|---|---|---|
    |@|MX|1 <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。|*\<domain-key\>*.mail.protection.outlook.com。 <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **注: Microsoft アカウントから** 取得\<domain-key\> します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|

   :::image type="content" source="../../media/dns-123reg/123reg-domains-MX.png" alt-text="ドロップダウン リストから MX の種類を選択し、値を入力します。":::

6. **[追加]** を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-MX-Add.png" alt-text="[追加] を選択します。":::

7. その他の MX レコードがある場合は、そのレコードの **[削除 ( ごみ箱)]** アイコンを選択して、それぞれを削除します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-MX-delete.png" alt-text="[削除] (ごみ箱) を選択します。":::

## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

2. On the Domain name overview page, select the name of the domain that you want to edit.

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [ **詳細設定] の** [ **DNS の管理**] を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

4. [DNS の管理] ページで、[ **高度な DNS** ] タブを選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::

5. CNAME レコードを追加します。

    新しいレコードの **[種類** ] ボックスで、ドロップダウン リストから **[CNAME** ] を選択し、次の表の他の値を入力またはコピーして貼り付けます。

    |Hostname|Type|Destination CNAME|
    |---|---|---|
    |autodiscover|CNAME|autodiscover.outlook.com. <br/> **この値は、末尾がピリオド (.) でなければなりません**|

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME.png" alt-text="ドロップダウン リストから CNAME の種類を選択し、値を入力します。":::

6. **[追加]** を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME-Add.png" alt-text="[追加] を選択します。":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 ドメインの SPF レコードが既にある場合は、Microsfot 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む *1 つの* SPF レコードを作成します。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)を参照してください。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

2. On the Domain name overview page, select the name of the domain that you want to edit.

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [ **詳細設定] の** [ **DNS の管理**] を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

4. [DNS の管理] ページで、[ **高度な DNS** ] タブを選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::

5. 新しいレコードの **[種類** ] ボックスで、ドロップダウン リストから **TXT/SPF** を選択し、次の表の他の値を入力またはコピーして貼り付けます。

    |Hostname|Type|Destination TXT/SPF|
    |---|---|---|
    |@|TXT/SPF|v=spf1 include:spf.protection.outlook.com -all <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|

   :::image type="content" source="../../media/dns-123reg/123reg-domains-TypeTXTSPF.png" alt-text="ドロップダウン リストから TXT/SPF の種類を選択し、値を入力します。":::

6. **[追加]** を選択します。

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

Microsoft Teamsに加えて、組織がチャット、電話会議、ビデオ通話などのオンラインコミュニケーション サービスにSkype for Businessを使用している場合にのみ、このオプションを選択します。 Skypeには、ユーザー間通信用の 2 つの SRV レコードと、ユーザーをサインインしてサービスに接続するための 2 つの CNAME レコードの 4 つのレコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

2. On the Domain name overview page, select the name of the domain that you want to edit.

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [ **詳細設定] の** [ **DNS の管理**] を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

4. [DNS の管理] ページで、[ **高度な DNS** ] タブを選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::

5. 2 つの SRV レコードの最初のレコードを追加します。

   新しいレコードの **[種類** ] ボックスで、ドロップダウン リストから **[SRV** ] を選択し、次の表の他の値を入力またはコピーして貼り付けます。

    |Hostname|Type|Priority|TTL|Destination SRV|
    |---|---|---|---|---|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません** <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません** <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|

   :::image type="content" source="../../media/dns-123reg/123reg-domains-TypeTXTSPF.png" alt-text="ドロップダウン リストから TXT/SPF の種類を選択し、値を入力します。":::

6. **[追加]** を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-TXTSPF-Add.png" alt-text="[追加] を選択します。":::

7. 残りの SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Skype for Businessに必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

1. On the Domain name overview page, select the name of the domain that you want to edit.

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

1. [ドメインの管理] ページの [ **詳細設定] の** [ **DNS の管理**] を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [DNS の管理] ページで、[ **高度な DNS** ] タブを選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::

1. 1 番目の CNAME レコードを追加します。

    新しいレコードの **[種類** ] ボックスで、ドロップダウン リストから **[CNAME** ] を選択し、次の表の他の値を入力またはコピーして貼り付けます。

    |Hostname|Type|Destination CNAME|
    |---|---|---|
    |sip|CNAME|sipdir.online.lync.com <br/> **この値は、末尾がピリオド (.) でなければなりません**|
    |lyncdiscover|CNAME|webdir.online.lync.com. <br/> **この値は、末尾がピリオド (.) でなければなりません**|

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME.png" alt-text="ドロップダウン リストから CNAME の種類を選択し、値を入力します。":::

1. **[追加]** を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME-Add.png" alt-text="[追加] を選択します。":::

1. 他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>詳細オプション: Microsoft 365のIntuneとモバイル デバイス管理

このサービスは、ドメインに接続するモバイル デバイスをセキュリティで保護し、リモートで管理するのに役立ちます。 モバイル デバイス管理では、ユーザーがデバイスをサービスに登録できるように、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Mobile デバイス管理に必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

1. On the Domain name overview page, select the name of the domain that you want to edit.

   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

1. [ドメインの管理] ページの [ **詳細設定] の** [ **DNS の管理**] を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [DNS の管理] ページで、[ **高度な DNS** ] タブを選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::

1. 1 番目の CNAME レコードを追加します。

    新しいレコードの **[種類** ] ボックスで、ドロップダウン リストから **[CNAME** ] を選択し、次の表の他の値を入力またはコピーして貼り付けます。

   |Hostname|Type|Destination CNAME|
   |---|---|---|
   |enterpriseregistration|CNAME|enterpriseregistration.windows.net. <br/> **この値は、末尾がピリオド (.) でなければなりません**|
   |enterpriseenrollment|CNAME|enterpriseenrollment.manage.microsoft.com。 <br/> **この値は、末尾がピリオド (.) でなければなりません**|

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME.png" alt-text="ドロップダウン リストから CNAME の種類を選択し、値を入力します。":::

1. **[追加]** を選択します。

   :::image type="content" source="../../media/dns-123reg/123reg-domains-CNAME-Add.png" alt-text="[追加] を選択します。":::

1. 他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
