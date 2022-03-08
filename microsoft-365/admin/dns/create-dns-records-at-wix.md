---
title: Connectに Wix で DNS レコードをMicrosoft 365
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
description: ドメインを確認し、Wix for Microsoft で電子メール、オンライン、Skype for Businessサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 9a9e230a46967ab6c012199e7f4fc6426fdc67bf
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314855"
---
# <a name="connect-your-dns-records-at-wix-to-microsoft-365"></a>Connectに Wix で DNS レコードをMicrosoft 365

探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
使用している DNS ホスティング プロバイダーが Wix の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。

Wix でこれらのレコードを追加すると、ドメインはユーザーのアカウントで動作Microsoft サービス。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft でドメインを使用する前に、ドメインを所有している必要があります。 ドメイン レジストラーでアカウントにログインし、DNS レコードを作成する機能は、ドメインを所有している Microsoft に証明されます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。必要に応じて、後で削除することができます。 

> [!NOTE]
> WIX では、サブドメインの DNS エントリはサポートされていません。
  
1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

2. [ **Domains** > **....] を** 選択し、ドロップダウン リストから **[DNS レコード** の管理] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

3. DNS **エディターの TXT** **(テキスト) 行で [+ レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-TXT-add-record.png" alt-text="[レコードの追加] を選択します。":::

4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   ||||
   |:-----|:-----|:-----|
   | **ホスト名 **<br/> | **TXT Value** <br/> | **TTL** <br/> |
   |自動入力 (空白のままにする)  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |

5. **SelectSave**。

   :::image type="content" source="../../media/dns-wix/wix-domains-txt-save.png" alt-text="[保存] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。


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

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

1. [ **Domains** > **....] を** 選択し、ドロップダウン リストから **[DNS レコード** の管理] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

1. [ **MX (メール 交換)] で、[** MX レコードの **編集] を選択します**。 

   :::image type="content" source="../../media/dns-wix/wix-domains-edit-mx-records.png" alt-text="[MX レコードの編集] を選択します。":::

1. ドロップダウン **リストから [** その他] を選択し、[+ レコードの追加 **] を選択します**。

   :::image type="content" source="../../media/dns-wix/wix-domains-other.png" alt-text="ドロップダウン リストから [その他] を選択します。":::

1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   | **Host Name** | **ポイント先** | **Priority** | **TTL** |
   |:-----|:-----|:-----|:-----|
   |自動的に設定される <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **注:** Microsoft アカウントから  *\<domain-key\>*  ユーザーを取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md) |0  <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。 | 1 Hour|

1. その他の MX レコードが一覧表示されている場合は、それぞれの MX レコードを削除します。

   :::image type="content" source="../../media/dns-wix/wix-domains-mx-delete.png" alt-text="[削除] を選択します。":::

1. **[保存]** を選択します。

## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

2. [ **Domains** > **....] を** 選択し、ドロップダウン リストから **[DNS レコード** の管理] を選択します。 

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

3. CNAME **レコードの** DNS エディター **の CNAME (エイリアス)** 行で [+ レコードの追加] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   | **Host Name** | **Value** | **TTL** |
   |:-----|:-----|:-----|
   |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |

5. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="[保存] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む 1  *つの SPF*  レコードを作成します。  
  
1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

2. [ **Domains** > **....] を** 選択し、ドロップダウン リストから **[DNS レコード** の管理] を選択します。 

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

3. DNS **エディターの TXT** **(テキスト) 行で [+ レコードの追加]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-TXT-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

   **注**: Wix は DNS エディターで SPF 行を提供します。 その行を無視し、 **TXT (テキスト)** 行を使用して、以下の SPF 値を入力します。 

4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   | **Host Name** | **Value** | **TTL** |
   |:-----|:-----|:-----|
   |[空白のままにする]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。<br/> | 1 Hour |

5. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-txt-save.png" alt-text="[保存] を選択します。":::

   数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスに組織がネットワーク通信サービスを使用している場合にのみMicrosoft Teams。 Skypeには、ユーザー間通信用の 2 つの SRV レコードと、ユーザーをサービスにサインインして接続するための 2 つの CNAME レコードの 4 つのレコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

1. [ **Domains** > **....] を** 選択し、ドロップダウン リストから **[DNS レコード** の管理] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

1. DNS **エディターの SRV** 行 **で [+** レコードの追加] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-srv-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. 新しいレコードのボックスに、テーブルの最初の行の値を入力またはコピーして貼り付けます。

   | **Service** | **Protocol** | **ホスト名** | **Weight** | **Port** | **Target** | **Priority** | **TTL** |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |自動的に設定される |1  |443   |sipdir.online.lync.com |100 |1 Hour |
   |sipfed|tcp |自動的に設定される|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |

1. **[保存]** を選択します。
  
   :::image type="content" source="../../media/dns-wix/wix-domains-srv-save.png" alt-text="[保存] を選択します。":::

1. テーブルの 2 行目から値をコピーして、他の SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. DNS **エディターの** **CNAME (Aliases)** 行で [+ 追加] を選択し、次の表の最初の行の値を入力します。

   |**Type**|**Host**|**Value**|**TTL**|
   |:-----|:-----|:-----|:-----|
   |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
   |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
  
1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="[保存] を選択します。":::
  
1. テーブルの 2 行目から値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>詳細オプション: Intune とモバイル デバイスの管理 (Microsoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理では、ユーザーがサービスにデバイスを登録できるよう、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。

1. [ **Domains** > **....] を** 選択し、ドロップダウン リストから **[DNS レコード** の管理] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="ドロップダウン リストから [DNS レコードの管理] を選択します。":::

1. CNAME **レコードの** DNS エディター **の CNAME (エイリアス)** 行で [+ レコードの追加] を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-add-record.png" alt-text="[+ レコードの追加] を選択します。":::

1. 次の表の最初の行の値を入力します。

    |**Type**|**Host**|**Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration <br/> |enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
  
1. **[保存]** を選択します。

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="[保存] を選択します。":::
  
1. テーブルの 2 行目から値をコピーして、他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。