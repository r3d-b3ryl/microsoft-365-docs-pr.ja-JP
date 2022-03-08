---
title: Connectに OVH で DNS レコードをMicrosoft 365
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: ドメインを確認し、OVH for Microsoft で電子メール、Skype for Businessオンライン、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 9c181536c418baebd3ba8eb1929095ac2d828ef6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314981"
---
# <a name="connect-your-dns-records-at-ovh-to-microsoft-365"></a>Connectに OVH で DNS レコードをMicrosoft 365

探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)してください。
  
使用している DNS ホスティング プロバイダーが OVH の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。

OVH でこれらのレコードを追加すると、ドメインはユーザーのアカウントで動作Microsoft サービス。

> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。

    ![OVH ログイン。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. ダッシュボードのランディング ページの [すべてのアクティビティを表示する] **で**、編集するドメインの名前を選択します。
  
1. [ **DNS ゾーン] を選択します**。

    ![OVH DNS ゾーンを選択します。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
1. [エントリ **の追加] を選択します**。

    ![OVH エントリを追加します。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
1. **[TXT] を選択する**

    ![OVH は TXT エントリを選択します。](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウン リストから **[カスタム** ] を選択し、テキスト ボックスに値を入力します。 

    |**Record type**|**サブドメイン**|**TTL**|**値**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(空白のまま)  <br/> |3600 (秒)  <br/> |MS=msxxxxxxxx  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |

1. **[次へ]** を選択します。

1. **[確認]** を選択します。

    ![OVH は、検証のために TXT を確認します。](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
1. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

レコードを確認するには、次Microsoft 365。
  
1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。

1. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。
  
1. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。

    ![OVH ログイン。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
1. ダッシュボードのランディング ページの [すべてのアクティビティを表示する] **で**、編集するドメインの名前を選択します。
  
1. [ **DNS ゾーン] を選択します**。

    ![OVH DNS ゾーンを選択します。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
1. [エントリ **の追加] を選択します**。

    ![OVH エントリを追加します。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
1. [ **MX] を選択します**。

    ![OVH MX レコードの種類。](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウン リストから **[カスタム** ] を選択し、テキスト ボックスに値を入力します。 

    > [!NOTE]
    > 既定では、OVH はターゲットに相対表記を使用し、ドメイン名をターゲット レコードの末尾に追加します。 絶対表記を代わりに使用するには、次の表に示すように、ターゲット レコードにドットを追加します。 
  
    |**サブドメイン**|**TTL**|**優先度**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |3600 (秒)  <br/> |0  <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。 <br/> |\<domain-key\>.mail.protection.outlook.com。  <br/> **注:** Microsoft アカウントから  *\<domain-key\>*  ユーザーを取得します。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)  |

    ![メールの OVH MX レコード。](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
1. **[次へ]** を選択します。

    ![OVH MX レコードが [次へ] を選択します。](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
1. **[確認]** を選択します。

    ![OVH MX レコードが [確認] を選択します。](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)

1. DNS ゾーン ページのリスト内の他の **MX レコードを削除** します。 各レコードを選択し、[アクション] **列** でごみ箱の [削除] アイコン **を選択** します。

    ![OVH は MX レコードを削除します。](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
1. **[確認]** を選択します。

## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。

    ![OVH ログイン。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
1. ダッシュボードのランディング ページの [すべてのアクティビティを表示する] **で**、編集するドメインの名前を選択します。
  
1. [ **DNS ゾーン] を選択します**。

    ![OVH DNS ゾーンを選択します。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
1. [エントリ **の追加] を選択します**。

    ![OVH エントリを追加します。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
1. [ **CNAME] を選択します**。

    ![OVH CNAME レコードの種類を追加します。](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. 新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウン リストから **[カスタム** ] を選択し、テキスト ボックスに値を入力します。 

    |**サブドメイン**|**TTL**|**Target**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |3600 (秒)  <br/> |autodiscover.outlook.com.  <br/> |

    ![OVH CNAME レコード。](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
1. **[次へ]** を選択します。

    ![OVH CNAME 値を追加し、[次へ] を選択します。](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
1. **[確認]** を選択します。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む 1  *つの SPF*  レコードを作成します。 
  
1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。

    ![OVH ログイン。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
1. ダッシュボードのランディング ページの [すべてのアクティビティを表示する] **で**、編集するドメインの名前を選択します。
  
1. [ **DNS ゾーン] を選択します**。

    ![OVH DNS ゾーンを選択します。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
1. [エントリ **の追加] を選択します**。

    ![OVH エントリを追加します。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
1. [ **TXT] を選択します**。

1. In the boxes for the new record, type or copy and paste the following values. TTL 値を割り当てるには、ドロップダウン リストから **[カスタム** ] を選択し、テキスト ボックスに値を入力します。 

    |**サブドメイン**|**TTL**|**値**|
    |:-----|:-----|:-----|
    |(空白のまま)  <br/> |3600 (秒)  <br/> |v=spf1 include:spf.protection.outlook.com -all <br/**Note:** このエントリをコピーして貼り付け、すべての間隔が正しいままにすることをお勧めします。           |

    ![OVH SPF の TXT レコードを追加します。](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
1. **[次へ]** を選択します。

    ![OVH SPF の TXT レコードを追加し、[次へ] を選択します。](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
1. **[確認]** を選択します。

    ![OVH SPF と Confirm の TXT レコードを追加します。](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

組織で Microsoft Teams に加えて、チャット、電話会議、ビデオ通話など、オンライン通信サービスに Skype for Business を使用している場合にのみ、このオプションを選択します。 Skype には、ユーザー間通信用の 2 つの SRV レコードと、ユーザーをサービスにサインインして接続するための 2 つの CNAME レコードの 4 つのレコードが必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。

    ![OVH ログイン。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
1. ダッシュボードのランディング ページの [すべてのアクティビティを表示する] **で**、編集するドメインの名前を選択します。
  
1. [ **DNS ゾーン] を選択します**。

    ![OVH DNS ゾーンを選択します。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
1. [エントリ **の追加] を選択します**。

    ![OVH エントリを追加します。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. [ **SRV] を選択します**。

1. In the boxes for the new record, type or copy and paste the following values. TTL 値を割り当てるには、ドロップダウン リストから **[カスタム** ] を選択し、テキスト ボックスに値を入力します。 

    |**サブドメイン**|**TTL (Seconds)**| **Priority** | **Weight** | **Port**|**対象**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|3600 (s.) |100 |  1  | 443 |sipdir.online.lync.com **この値は、ピリオド (.) で終了する必要があります。**><br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。 | 
    |_sipfederationtls._tcp| 3600 (s.)|100 | 1 | 5061 | sipfed.online.lync.com。 **この値は、末尾がピリオド (.) でなければなりません**<br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。    | 
  
1. 他の SRV レコードを追加するには、[別のレコードの追加] を選択し、テーブルの次の行の値を使用してレコードを作成し、[レコードの作成] **を選択します**。

> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する 

1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。

    ![OVH ログイン。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
1. ダッシュボードのランディング ページの [すべてのアクティビティを表示する] **で**、編集するドメインの名前を選択します。
  
1. [ **DNS ゾーン] を選択します**。

    ![OVH DNS ゾーンを選択します。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
1. [エントリ **の追加] を選択します**。

    ![OVH エントリを追加します。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. [ **CNAME] を選択します**。

    ![OVH CNAME レコードの種類を追加します。](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. 新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウン リストから **[カスタム** ] を選択し、テキスト ボックスに値を入力します。 

    |**サブドメイン**| **TTL** | **Target** | 
    |:-----|:-----|:-----|
    |sip  <br/> | 3600 (s.)  <br/> |sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |lyncdiscover  <br/> |3600 (s.) |webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/>  |
  
1. **[次へ]** を選択します。

    ![OVH CNAME 値を追加し、[次へ] を選択します。](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
1. **[確認]** を選択します。

1. 他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>詳細オプション: Intune およびモバイル デバイス管理 for Microsoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理では、ユーザーがサービスにデバイスを登録できるよう、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。

    ![OVH ログイン。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
1. ダッシュボードのランディング ページの [すべてのアクティビティを表示する] **で**、編集するドメインの名前を選択します。
  
1. [ **DNS ゾーン] を選択します**。

    ![OVH DNS ゾーンを選択します。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
1. [エントリ **の追加] を選択します**。

    ![OVH エントリを追加します。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
1. [ **CNAME] を選択します**。

    ![OVH CNAME レコードの種類を追加します。](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. 新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウン リストから **[カスタム** ] を選択し、テキスト ボックスに値を入力します。 
  
    |**サブドメイン**| **TTL** | **Target** | 
    |:-----|:-----|:-----|
    |enterpriseregistration  <br/>| 3600 (s.)  <br/> |enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseenrollment  <br/>  |3600 (s.) |enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/>|

1. **[次へ]** を選択します。

    ![OVH CNAME 値を追加し、[次へ] を選択します。](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
1. **[確認]** を選択します。

1. 他の CNAME レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。