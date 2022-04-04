---
title: Connect DNS レコードを web.com にMicrosoft 365
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
description: ドメインを確認し、Microsoft 向けメール、Skype for Business、その他のサービスの DNS レコード web.com 説明します。
ms.openlocfilehash: 612c22b518402fccaf9ced76b2506aa15c0e89f6
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568414"
---
# <a name="connect-your-dns-records-at-webcom-to-microsoft-365"></a>Connect DNS レコードを web.com にMicrosoft 365

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

DNS web.com プロバイダーである場合は、この記事の手順に従ってドメインを確認し、電子メール、Skype for Business Online などについて DNS レコードを設定します。

これらのレコードを web.com すると、ドメインはユーザーと一緒に動作Microsoft サービス。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。

アカウントにサインアップすると web.com セットアップ プロセスを使用してドメイン web.com **しました** 。

Microsoft でドメインの DNS レコードを確認して作成するには、まず、ドメイン レジストラーでネーム サーバーを変更して、ドメイン ネーム サーバーを使用 web.com 必要があります。

ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。

1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。

2. 次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。

    |型|値|
    |---|---|
    |1 番目のネーム サーバー|ユーザーが指定するネーム サーバーの値 web.com。|
    |2 番目のネーム サーバー|ユーザーが指定するネーム サーバーの値 web.com。|

    > [!TIP]
    > You should use at least two name server records. 他にネーム サーバーが一覧表示されている場合は、それらを削除する必要があります。

3. 変更内容を保存します。

> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft の電子メールと他のサービスはすべて、ドメインで動作する設定に設定されます。

## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

1. 開始するには、このリンクを使用して、web.com の [ドメイン] ページに [移動します](https://checkout.web.com/manage-it/index.jsp)。 最初にログインします。

1. ランディング ページで、[ドメイン名] **を選択します**。

1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::

1. 下にスクロールして [ **高度なツール] を** 選択し、[ **高度な DNS レコード**] の横にある [管理] を選択 **します**。

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

1. [高度な DNS レコードの管理] ページで、[+ **レコードの追加] を選択します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. [ **種類]** で、 **ドロップダウン リストから [TXT** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-TXT.png" alt-text="[種類] ドロップダウン リストから [TXT] を選択します。":::

1. 次の表の値を選択するか、コピーして貼り付けます。

    |参照|TXT 値|TTL|
    |---|---|:----|
    |@|MS=*msXXXXXXXX* <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|1 Hour|

1. [ **追加] を選択します**。

    作成したレコードがインターネット上で更新できるよう、新しい TXT レコードを確認する前に数分待ちます。

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

レコードを確認するには、次Microsoft 365。

1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。

1. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。

1. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. 開始するには、このリンクを使用して、web.com の [ドメイン] ページに [移動します](https://checkout.web.com/manage-it/index.jsp)。 最初にログインします。

1. ランディング ページで、[ドメイン名] **を選択します**。

1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::

1. 下にスクロールして [ **高度なツール] を** 選択し、[ **高度な DNS レコード**] の横にある [管理] を選択 **します**。

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

1. [高度な DNS レコードの管理] ページで、[+ **レコードの追加] を選択します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. [ **種類]** で、 **ドロップダウン リストから [MX** ] を選択します。

1. 次の表の値を選択するか、コピーして貼り付けます。

    |参照先|メール サーバー|Priority|TTL|
    |---|---|---|---|
    |@|*\<domain-key\>*.mail.protection.outlook.com <br/> **注:** Microsoft 管理センター *\<domain-key\>* からユーザーを取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。 <br/> 1|1 Hour|

1. [ **追加] を選択します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-mx-add.png" alt-text="[追加] を選択します。":::

1. その他の MX レコードがある場合は、編集ツールを選択してすべてのレコードを削除し、レコードごとに **削除** します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-edit.png" alt-text="[編集] を選択します。":::

## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. 開始するには、このリンクを使用して、web.com の [ドメイン] ページに [移動します](https://checkout.web.com/manage-it/index.jsp)。 最初にログインします。

1. ランディング ページで、[ドメイン名] **を選択します**。

1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::

1. 下にスクロールして [ **高度なツール] を** 選択し、[ **高度な DNS レコード**] の横にある [管理] を選択 **します**。

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

1. [高度な DNS レコードの管理] ページで、[+ **レコードの追加] を選択します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. [ **種類]** で、 **ドロップダウン リストから [CNAME** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="[種類] ドロップダウン リストから [CNAME] を選択します。":::

1. 次の表の値を選択するか、コピーして貼り付けます。

    |参照先|ホスト名|Alias to (エイリアス)|TTL|
    |---|---|---|---|
    |その他のホスト|autodiscover|autodiscover.outlook.com|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="CNAME 値を入力するか、コピーしてウィンドウに貼り付けます。":::

1. [ **追加] を選択します**。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む 1 *つの SPF* レコードを作成します。

1. 開始するには、このリンクを使用して、web.com の [ドメイン] ページに [移動します](https://checkout.web.com/manage-it/index.jsp)。 最初にログインします。

1. ランディング ページで、[ドメイン名] **を選択します**。

1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::

1. 下にスクロールして [ **高度なツール] を** 選択し、[ **高度な DNS レコード**] の横にある [管理] を選択 **します**。

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

1. [高度な DNS レコードの管理] ページで、[+ **レコードの追加] を選択します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. [ **種類]** で、 **ドロップダウン リストから [TXT** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-TXT.png" alt-text="[種類] ドロップダウン リストから [TXT] を選択します。":::

1. 次の表の値を選択するか、コピーして貼り付けます。

    |参照先|TXT 値|TTL|
    |---|---|---|
    |@|v=spf1 include:spf.protection.outlook.com -all <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|1 Hour|

1. [ **追加] を選択します**。

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスに組織がネットワーク通信サービスを使用している場合にのみMicrosoft Teams。 Skype 4 つのレコードが必要です。ユーザー間通信には 2 つの SRV レコード、サービスにユーザーをサインインして接続するには 2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. 開始するには、このリンクを使用して、web.com の [ドメイン] ページに [移動します](https://checkout.web.com/manage-it/index.jsp)。 最初にログインします。

1. ランディング ページで、[ドメイン名] **を選択します**。

1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::

1. 下にスクロールして [ **高度なツール] を** 選択し、[ **高度な DNS レコード**] の横にある [管理] を選択 **します**。

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

1. [高度な DNS レコードの管理] ページで、[+ **レコードの追加] を選択します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. [ **種類]** で、 **ドロップダウン リストから [SRV** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-srv.png" alt-text="[種類] ドロップダウン リストから [SRV] を選択します。":::

1. 次の表の値を選択するか、コピーして貼り付けます。

    |型|サービス|プロトコル|太さ|ポート|Target|Priority|TTL|
    |---|---|---|---|---|---|---|---|
    |SRV|_sip|TLS|100|443|sipdir.online.lync.com <br/> **この値はピリオド (.) で終了できません。**|1|1 Hour|
    |SRV|_sipfederationtls|TCP|100|5061|sipfed.online.lync.com <br/> **この値はピリオド (.) で終了できません。**|1|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-srv-add.png" alt-text="テーブルの値を入力するか、コピーして SRV レコード ウィンドウに貼り付けます。":::

1. [ **追加] を選択します**。

1. テーブルの 2 行目から値をコピーして、他の SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. 開始するには、このリンクを使用して、web.com の [ドメイン] ページに [移動します](https://checkout.web.com/manage-it/index.jsp)。 最初にログインします。

1. ランディング ページで、[ドメイン名] **を選択します**。

1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::

1. 下にスクロールして [ **高度なツール] を** 選択し、[ **高度な DNS レコード**] の横にある [管理] を選択 **します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

1. [高度な DNS レコードの管理] ページで、[+ **レコードの追加] を選択します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. [ **種類]** で、 **ドロップダウン リストから [CNAME** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="[種類] ドロップダウン リストから [CNAME] を選択します。":::

1. 次の表の値を選択するか、コピーして貼り付けます。

    |型|参照先|ホスト名|Alias to (エイリアス)|TTL|
    |---|---|---|---|---|
    |CNAME|その他のホスト|sip|sipdir.online.lync.com <br/> **この値はピリオド (.) で終了できません。**|1 Hour|
    |CNAME|その他のホスト|lyncdiscover|webdir.online.lync.com <br/> **この値はピリオド (.) で終了できません。**|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="CNAME 値を入力するか、コピーしてウィンドウに貼り付けます。":::

1. [ **追加] を選択します**。

1. テーブルの 2 行目から値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高度なオプション: Intuneとモバイル デバイス管理のMicrosoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理サービスにデバイスを登録するには、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>モバイル デバイスに必要な 2 つの CNAME レコードを追加デバイス管理

1. 開始するには、このリンクを使用して、web.com の [ドメイン] ページに [移動します](https://checkout.web.com/manage-it/index.jsp)。 最初にログインします。

1. ランディング ページで、[ドメイン名] **を選択します**。

1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::

1. 下にスクロールして [ **高度なツール] を** 選択し、[ **高度な DNS レコード**] の横にある [管理] を選択 **します**。

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

1. [高度な DNS レコードの管理] ページで、[+ **レコードの追加] を選択します**。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. [ **種類]** で、 **ドロップダウン リストから [CNAME** ] を選択します。

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname.png" alt-text="[種類] ドロップダウン リストから [CNAME] を選択します。":::

1. 次の表の値を選択するか、コピーして貼り付けます。

    |型|参照先|ホスト名|Alias to (エイリアス)|TTL|
    |---|---|---|---|---|
    |CNAME|その他のホスト|enterpriseregistration|enterpriseregistration.windows.net <br/> **この値はピリオド (.) で終了できません。**|1 Hour|
    |CNAME|その他のホスト|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com <br/> **この値はピリオド (.) で終了できません。**|1 Hour|

    :::image type="content" source="../../media/dns-webcom/webcom-domains-cname-values.png" alt-text="テーブルの CNAME 値を入力するか、コピーしてウィンドウに貼り付けます。":::

1. [ **追加] を選択します**。

1. テーブルの 2 行目から値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
