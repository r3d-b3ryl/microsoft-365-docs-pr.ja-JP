---
title: Connect Cloudflare で DNS レコードを削除して、Microsoft 365
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
description: ドメインを確認し、Cloudflare for Microsoft で電子メール、Skype for Business、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: a7f1307530d5dc874120db0f40b631ada4b833e8
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568051"
---
# <a name="connect-your-dns-records-at-cloudflare-to-microsoft-365"></a>Connect Cloudflare で DNS レコードを削除して、Microsoft 365

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

使用している DNS ホスティング プロバイダーが Cloudflare の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。

## <a name="before-you-begin"></a>はじめに

ドメインの DNS レコードを設定するには、次の 2 つのオプションがあります。

- [**[ドメイン Connect を**](#use-domain-connect-to-verify-and-set-up-your-domain)使用する] 別の電子メール サービス プロバイダーでドメインを設定していない場合は、ドメイン Connect の手順を使用して、新しいドメインを自動的に確認し、Microsoft 365 で使用する設定を行います。

    または

- [**手動の手順を使用する**](#create-dns-records-with-manual-setup) 以下の手動手順を使用してドメインを確認し、ドメイン レジストラーに追加するレコードを選択します。 これにより、便利な場合など、新しい MX (メール) レコードを設定できます。

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>ドメインを確認Connect設定するには、Domain Connectを使用します。

次の手順に従って、Cloudflare ドメインを自動的に確認して設定Microsoft 365。

1. [ドメイン **Microsoft 365 管理センター] を**\>設定し、セットアップするドメインを選択します。<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

1. 3 つのドット (その他のアクション) を選択し、[セットアップの開始] \> **を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. [ドメインの接続方法]ページで、[続行] **を選択します**。

1. [DNS レコードの追加] ページで、[DNS レコードの **追加] を選択します**。

1. Cloudflare ログイン ページで、アカウントにサインインし、[承認] を選択 **します**。

    これで、ドメインのセットアップが完了Microsoft 365。

## <a name="create-dns-records-with-manual-setup"></a>手動セットアップで DNS レコードを作成する

Cloudflare でこれらのレコードを追加すると、ドメインはユーザーサービスを処理Microsoft 365されます。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。

Cloudflare にサインアップしたときに、Cloudflare の [ Setup] プロセスを使用してドメインを追加しました。

追加したドメインは、Cloudflare または別のドメイン レジストラーから購入されました。 Microsoft 365 でドメインの DNS レコードを確認して作成するには、まず、Cloudflare ネーム サーバーを使用するために、ドメイン レジストラーでネーム サーバーを変更する必要があります。

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
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft の電子メールと他のサービスはすべて、ドメインで動作する設定に設定されます。

### <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. [ホーム] ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[DNS] を **選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[+レコードの **追加] を選択します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから TXT の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|TTL|コンテンツ|
    |---|---|---|:----|
    |TXT|@|30 minutes|MS=*msXXXXXXXX* <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-TXT-save.png" alt-text="[レコードの追加] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

ドメイン レジストラーのサイトにレコードを追加したので、Microsoft に戻ってレコードを検索します。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

レコードを確認するには、次Microsoft 365。

1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。

1. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。

1. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. [ホーム] ページで、更新するドメインを選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[DNS] を **選択します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[+レコードの **追加] を選択します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから MX の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

   |種類|氏名|メール サーバー|TTL|優先度|
   |---|---|---|---|---|
   |MX|@|*\<domain-key\>*.mail.protection.outlook.com <br/> **注:** 自分のアカウント *\<domain-key\>* からMicrosoft 365します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|30 分|1 <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。 <br/>|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-mx-save.png" alt-text="[レコードの追加] を選択します。":::

1. [MX レコード] セクションに他の **MX** レコードが一覧表示されている場合は、[編集] を選択して削除し、[削除] を選択 **します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-mx-delete.png" alt-text="[削除] を選択します。":::

1. 確認ダイアログ ボックスで、[削除] **を選択して** 変更を確認します。

### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. [ホーム] ページで、更新するドメインを選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[DNS] を **選択します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. **[DNS 管理] ページで**、[+レコードの **追加] を選択します。**

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから CNAME の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|Target|TTL|
    |---|---|---|---|
    |CNAME|autodiscover|autodiscover.outlook.com|Auto|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="[保存] を選択します。":::

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、現在のレコードにMicrosoft 365値を追加して、両方の値セットを含む 1 *つの SPF* レコードを作成します。

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. [ホーム] ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[DNS] を **選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[+レコードの **追加] を選択します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから TXT の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|TTL|コンテンツ|
    |---|---|---|---|
    |TXT|@|30 minutes|v=spf1 include:spf.protection.outlook.com -all <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-TXT-save.png" alt-text="[保存] を選択します。":::

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスに組織がネットワーク通信サービスを使用している場合にのみMicrosoft Teams。 Skype 4 つのレコードが必要です。ユーザー間通信には 2 つの SRV レコード、サービスにユーザーをサインインして接続するには 2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

> [!IMPORTANT]
> Cloudflare は、この機能を利用できる状態にするための責任を負います。 以下の手順と現在の Cloudflare GUI (グラフィカル ユーザー インターフェイス) の間に不一致が発生した場合は、[Cloudflare](https://community.cloudflare.com/) インターフェイスをCommunity。

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. [ホーム] ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[DNS] を **選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[+レコードの **追加] を選択します。**

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから SRV の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|サービス|プロトコル|TTL|優先度|太さ|ポート|Target|
    |---|---|---|---|---|---|---|---|---|
    |SRV|ユーザー設定を *domain_name*。たとえば、contoso.com|_sip|TLS|30 分|100|1|443|sipfed.online.lync.com|
    |SRV|_sipfederationtls|TCP|ユーザー設定を *domain_name*。たとえば、contoso.com|30 分|100|1|5061|sipfed.online.lync.com|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-srv-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 行目から値をコピーして、他の SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. [ホーム] ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[DNS] を **選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[+レコードの **追加] を選択します。**

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから CNAME の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|Target|TTL|
    |---|---|---|---|
    |CNAME|sip|sipdir.online.lync.com <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|
    |CNAME|lyncdiscover|webdir.online.lync.com. <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|

1. [保存] を **選択します**。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 行目から値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高度なオプション: Intuneとモバイル デバイス管理のMicrosoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理サービスにデバイスを登録するには、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>モバイル デバイスに必要な 2 つの CNAME レコードを追加デバイス管理

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。

1. [ホーム] ページで、更新するドメインを選択します。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::

1. ドメインの [概要] ページで、[DNS] を **選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

1. [DNS 管理] ページで、[+レコードの **追加] を選択します。**

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="[レコードの追加] を選択します。":::

1. ドロップダウン リストから CNAME の種類を選択し、このテーブルの値を入力またはコピーして貼り付けます。

    |種類|氏名|Target|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net. <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|
    |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com. <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 行目から値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
