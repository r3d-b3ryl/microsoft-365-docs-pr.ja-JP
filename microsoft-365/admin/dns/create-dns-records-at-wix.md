---
title: Wix で DNS レコードをMicrosoft 365にConnectする
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: ドメインを確認し、Wix for Microsoft で電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 58d7819e006183a35272811ed791d3236f9fc742
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780315"
---
# <a name="connect-your-dns-records-at-wix-to-microsoft-365"></a>Wix で DNS レコードをMicrosoft 365にConnectする

探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

使用している DNS ホスティング プロバイダーが Wix の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。

Wix でこれらのレコードを追加すると、Microsoft サービスで動作するようにドメインが設定されます。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft でドメインを使用する前に、お客様が所有していることを確認する必要があります。 ドメイン レジストラーでアカウントにログインし、DNS レコードを作成する機能は、ドメインを所有していることを Microsoft に証明します。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。必要に応じて、後で削除することができます。

> [!NOTE]
> WIX では、サブドメインの DNS エントリはサポートされていません。

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

2. **[Domains** \> **...**] を選択し、ドロップダウン リストから [**DNS レコードの管理**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

3. DNS エディターの **TXT (テキスト)** 行で [**+ レコードの追加**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-TXT-add-record.png" alt-text="[レコードの追加] を選択します。":::

4. In the boxes for the new record, type or copy and paste the values from the following table.

   |ホスト名|TXT Value|TTL|
   |---|---|---|
   |自動的に設定 (空白のままに)|MS=*msXXXXXXXXXXX* <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|1 Hour|

5. **SelectSave**。

   :::image type="content" source="../../media/dns-wix/wix-domains-txt-save.png" alt-text="[保存] を選択します。":::

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

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

1. **[Domains** \> **...**] を選択し、ドロップダウン リストから [**DNS レコードの管理**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

1. **[MX (メール交換)] で**、[**MX レコードの編集**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-edit-mx-records.png" alt-text="[MX レコードの編集] を選択します。":::

1. ドロップダウン リストから [ **その他** ] を選択し、[ **+ レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-other.png" alt-text="ドロップダウン リストから [その他] を選択します。":::

1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   |ホスト名|Points to |Priority|TTL|
   |---|---|---|---|
   |自動的に設定される|*\<domain-key\>*.mail.protection.outlook.com <br/> **メモ：** Microsoft アカウントから取得します *\<domain-key\>* 。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)|0 <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。|1 Hour|

1. 他に MX レコードが一覧表示されている場合は、それぞれを削除します。

  :::image type="content" source="../../media/dns-wix/wix-domains-mx-delete.png" alt-text="[削除] を選択します。":::

1. **[保存]** を選択します。

## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

2. **[Domains** \> **...**] を選択し、ドロップダウン リストから [**DNS レコードの管理**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

3. CNAME レコードの DNS エディターの **CNAME (エイリアス)** 行で [+ レコードの **追加**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   |ホスト名|値|TTL|
   |---|---|---|
   |autodiscover|autodiscover.outlook.com|1 Hour|

5. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="[保存] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む *1 つの* SPF レコードを作成します。

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

2. **[Domains** \> **...**] を選択し、ドロップダウン リストから [**DNS レコードの管理**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

3. DNS エディターの **TXT (テキスト)** 行で [**+ レコードの追加**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-TXT-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

   **注**: Wix は、DNS エディターで SPF 行を提供します。 その行を無視し、 **TXT (Text)** 行を使用して、以下の SPF 値を入力します。

4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   |ホスト名|値|TTL|
   |---|---|---|
   |[空白のままにする]|v=spf1 include:spf.protection.outlook.com -all <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|1 Hour|

5. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-txt-save.png" alt-text="[保存] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

Microsoft Teamsに加えて、組織がチャット、電話会議、ビデオ通話などのオンラインコミュニケーション サービスにSkype for Businessを使用している場合にのみ、このオプションを選択します。 Skypeには、ユーザー間通信用の 2 つの SRV レコードと、ユーザーをサインインしてサービスに接続するための 2 つの CNAME レコードの 4 つのレコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

1. **[Domains** \> **...**] を選択し、ドロップダウン リストから [**DNS レコードの管理**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

1. DNS エディターの **SRV** 行で [**+ レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-srv-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. 新しいレコードのボックスに、テーブルの最初の行の値を入力またはコピーして貼り付けます。

   |サービス|プロトコル|ホスト名|太さ|ポート|Target|Priority|TTL|
   |---|---|---|---|---|---|---|---|
   |sip|tls|自動的に設定される|1|443|sipdir.online.lync.com|100|1 Hour|
   |sipfed|tcp|自動的に設定される|1|5061|sipfed.online.lync.com|100|1 Hour|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-srv-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 番目の行から値をコピーして、他の SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Skype for Businessに必要な 2 つの CNAME レコードを追加する

1. DNS エディターの **CNAME (エイリアス)** 行で **[+ 追加**] を選択し、次の表の最初の行の値を入力します。

   |型|Host|値|TTL|
   |---|---|---|---|
   |CNAME|sip|sipdir.online.lync.com <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|
   |CNAME|lyncdiscover|webdir.online.lync.com. <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 行目の値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>詳細オプション: Microsoft 365のIntuneとモバイル デバイス管理

このサービスは、ドメインに接続するモバイル デバイスをセキュリティで保護し、リモートで管理するのに役立ちます。 モバイル デバイス管理では、ユーザーがデバイスをサービスに登録できるように、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Mobile デバイス管理に必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

1. **[Domains** \> **...**] を選択し、ドロップダウン リストから [**DNS レコードの管理**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

1. CNAME レコードの DNS エディターの **CNAME (エイリアス)** 行で [+ レコードの **追加**] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. 次の表の最初の行の値を入力します。

    |型|Host|値|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net. <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|
    |CNAME|enterpriseenrollment|enterpriseenrollment.manage.microsoft.com。 <br/> **この値は、末尾がピリオド (.) でなければなりません**|1 Hour|

1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 行目の値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
