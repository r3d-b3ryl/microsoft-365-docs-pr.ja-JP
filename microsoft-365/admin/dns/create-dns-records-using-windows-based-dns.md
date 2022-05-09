---
title: Windows ベースの DNS を使って Microsoft の DNS レコードを作成する
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを microsoft 向けのWindows ベースの DNS で設定する方法について説明します。
ms.openlocfilehash: 0349366e1cb3af23de1161a69b9b37305cc1237a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313483"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows ベースの DNS を使って Microsoft の DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
   
Windows ベースの DNS を使用して独自の DNS レコードをホストする場合は、この記事の手順に従って、電子メール、Skype for Business Online などのレコードを設定します。
  
開始するには、[DNS レコードを更新できるように、Windows ベースの DNS で DNS レコードを検索](#find-your-dns-records-in-windows-based-dns)する必要があります。 また、オンプレミスの Active Directoryを Microsoft と同期する予定の場合は、オンプレミス[の Active Directory で UPN として使用されるルーティング不可能な電子メール アドレスに関](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)するページを参照してください。
  
DNS レコードを追加した後のメール フローやその他の問題に関する問題については、「 [ドメイン名または DNS レコードを変更した後の問題のトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Windows ベース DNS 内の DNS レコードを検索する
<a name="BKMK_find_your_dns_1"> </a> ドメインの DNS レコードがあるページに移動します。 Windows Server 2008 で作業している場合は、**StartRun** に移動 **します** > 。 Windows Server 2012 を使っている場合は、Windows キーを押して、**R** キーを押します。 「**dnsmgmnt.msc**」と入力して、[**OK**] を選択します。 DNS マネージャーで、[**前方参照ゾーン] を展開\<DNS server name\>\>します**。 ドメインを選択します。 これで DNS レコードを作成する準備が整いました。
   
## <a name="add-mx-record"></a>MX レコードを追加する
<a name="BKMK_add_MX"> </a>

ドメインの電子メールが Microsoft に届くよう MX レコードを追加します。
- 追加する MX レコードには、次のような値 ( **アドレスを指すポイント** の値) が含まれています。 \<MX token\>.mail.protection.outlook.com、MSxxxxxxx \<MX token\> のような値です。 
- Microsoft の [DNS レコードの追加] ページの [Exchange Online] セクションの [MX] 行から、[アドレスのポイント] に一覧表示されている値をコピーします。 この値は、このタスクで作成するレコードで使用します。 
- ドメインの [DNS マネージャー] ページで、**ActionMail** >  **交換機 (MX)** に移動します。 ドメインのこのページについては、「[Windows ベースの DNS で DNS レコードを検索](#find-your-dns-records-in-windows-based-dns)する」を参照してください。  
- [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。 
    - ホスト名: 
    - @Address: Microsoft からコピーしたアドレスの値にポイントを貼り付けます。  
    - 県： 
- [**変更を保存**] を選択します。
- 古い MX レコードをすべて削除します。 メールを別の場所にルーティングするこのドメインの古い MX レコードがある場合は、古い各レコードの横にあるチェック ボックスをオンにし、**DeleteOK** >  を選択します。 
   
## <a name="add-cname-records"></a>CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

Microsoft に必要な CNAME レコードを追加します。 Microsoft に追加の CNAME レコードが一覧表示されている場合は、次に示すのと同じ一般的な手順に従って追加します。
  
> [!IMPORTANT]
> Microsoft 用のモバイル デバイス管理 (MDM) がある場合は、2 つの追加の CNAME レコードを作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (MDM がない場合は、この手順をスキップできます)。 

- ドメインの [DNS マネージャー] ページで、**ActionCNAME** >  **(CNAME)** に移動します。
- [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。  
    - ホスト名: 自動検出
    - 種類: 
    - CNAMEAddress: autodiscover.outlook.com
- **[OK] を** 選択します。

SIP CNAME レコードを追加します。 
- ドメインの [DNS マネージャー] ページで、[アクション **CNAME (CNAME)]** に移動 **します**\>。 
- [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。  
    - ホスト名: sip
    - 型: CNAME
    - 住所: sipdir.online.lync.com
- **[OK]** を選択します。

Skype for Business Online Autodiscover CNAME レコードを追加します。  
- ドメインの [DNS マネージャー] ページで、[アクション **CNAME (CNAME)]** に移動 **します**\>。 [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。  
    - ホスト名: lyncdiscover
    - 型: CNAME
    - 住所: webdir.online.lync.com
- **[OK]** を選択します。
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Microsoft 用モバイル デバイス管理 (MDM) 用に 2 つの CNAME レコードを追加する

> [!IMPORTANT]
> Microsoft 用のモバイル デバイス管理 (MDM) がある場合は、2 つの追加の CNAME レコードを作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. >(MDM がない場合は、この手順をスキップできます)。 
  

MDM Enterpriseregistration CNAME レコードを追加します。  
- ドメインの [DNS マネージャー] ページで、[アクション **CNAME (CNAME)]** に移動 **します**\>。 
- [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。  
- ホスト名: enterpriseregistration
- 型: CNAME
- 住所: enterpriseregistration.windows.net
- **[OK]** を選択します。 

MDM Enterpriseenrollment CNAME レコードを追加します。 
-  ドメインの [DNS マネージャー] ページで、[アクション **CNAME (CNAME)]** に移動 **します**\>。 
-  [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。  
    - ホスト名: enterpriseenrollment
    - 型: CNAME
    - 住所: enterpriseenrollment-s.manage.microsoft.com
- **[OK]** を選択します。
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1 つの*  SPF レコードを作成します。 
  
ドメインの SPF TXT レコードを追加して、電子メールのスパムを防ぎます。
  
- このレコードの TXT 値に他の文字列 (マーケティングメールの文字列など) が既に含まれている可能性があります。これは問題ありません。 これらの文字列を配置したまま、この文字列を追加し、各文字列の周囲に二重引用符を配置して区切ります。 
- ドメインの [DNS マネージャー] ページで、[ **アクション** \> **テキスト (TXT)]** に移動します。 
-  [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。 
 > [!IMPORTANT]
> 一部のバージョンの Windows DNS マネージャーでは、txt レコードを作成するときにホーム名が既定で親ドメインに設定されるようにドメインが設定されている場合があります。 このような場合は、TXT レコードを追加するときに、ホスト名を @またはドメイン名に設定するのではなく、空白 (値なし) に設定します。 

-  ホストの種類:@
-  レコードの種類: TXT
-  アドレス: v=spf1 include:spf.protection.outlook.com -all 
         
-  **[OK]** を選択します。
   
## <a name="add-srv-records"></a>SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

Microsoft に必要な 2 つの SRV レコードを追加します。

Skype for Business Online Web 会議の SIP SRV レコードを追加します。  <br/> 
-  ドメインの [DNS マネージャー] ページで、[アクション **その他の新しいレコード****]** \> に移動します。 
-   [ **リソース レコードの種類** ] ウィンドウで[ **サービスの場所 (SRV)]**、[ **レコードの作成**] の順に選択します。 
-   [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。  
    -  サービス: _sip
    -  プロトコル: _tls
    -  優先度: 100
    -  重み: 1
    -  ポート: 443
    -  ターゲット (ホスト名): sipdir.online.lync.com
-  **[OK]** を選択します。 


Skype for Business Online フェデレーションの SIP SRV レコードを追加します。  
-  ドメインの [DNS マネージャー] ページで、[アクション **その他の新しいレコード****]** \> に移動します。  
-  [ **リソース レコードの種類** ] ウィンドウで[ **サービスの場所 (SRV)]**、[ **レコードの作成**] の順に選択します。 
-   [ **新しいリソース レコード** ] ダイアログ ボックスで、フィールドが次の値に正確に設定されていることを確認します。  
    -  サービス: _sipfederationtls
    -  プロトコル: _tcp
    -  優先度: 100
    -  重み: 1
    -  ポート: 5061
    -  ターゲット (ホスト名): sipfed.online.lync.com
-  **[OK]** を選択します。 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>まだドメインを所有していない場合は、ドメインを所有していることを確認するレコードを追加します
<a name="BKMK_verify"> </a>

Microsoft サービスを設定するために DNS レコードを追加する前に、Microsoft は追加するドメインを所有していることを確認する必要があります。 これを行うには、次の手順に従ってレコードを追加します。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認する場合にのみ使用します。その他には影響しません。 
  

1. Microsoft から情報を収集します。  <br/> 
2. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。 
3. [ **ドメイン** ] ページで、確認するドメインの [ **アクション]** 列で、[ **セットアップの開始**] を選択します。 
4. [ **Microsoft にドメインを追加する] ページで** 、[ **開始手順 1**] を選択します。 
5. **[自分がドメインを所有していることを確認** する] ページの [**この手順を実行するための手順** を確認する] ボックスの一覧で、[**全般手順**] を選択します。 
6. テーブルから、[宛先] または [ポイントから住所] の値をコピーします。 次の手順で必要になります。 すべての間隔が正しいままになるように、この値をコピーして貼り付けすることをお勧めします。

TXT レコードを追加します。 
-  ドメインの [DNS マネージャー] ページで、[ **アクション** \> **テキスト (TXT)]** に移動します。 
-   [ **新しいリソース レコード** ] ダイアログ ボックスで、[編集] を選択 **します**。  
-  [**新しいリソース レコード**] ダイアログ ボックスの [**カスタム ホスト名**] 領域で、フィールドが正確に次の値に設定されていることを確認します。 

> [!IMPORTANT] 
> 一部のバージョンの Windows DNS マネージャーでは、txt レコードを作成するときにホーム名が既定で親ドメインに設定されるようにドメインが設定されている場合があります。 このような場合は、TXT レコードを追加するときに、ホスト名を @またはドメイン名に設定するのではなく、空白 (値なし) に設定します。 

- ホスト名:@
- 型: TXT
- 住所: Microsoft からコピーした [宛先] または [ポイント先住所] の値をここに貼り付けます。  
- **OKDone を選択します** > 。

Microsoft でドメインを確認します。  
> [!IMPORTANT]
> 作成したレコードがインターネット経由で更新できるように、これを行う前に約 15 分待ちます。       

- Microsoft に戻るし、次の手順に従って確認チェックを要求します。 このチェックでは、前の手順で追加した TXT レコードが検索されます。 正しい TXT レコードが見つかると、ドメインが検証されます。  
1. 管理センターで、[**セットアップ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。
2. [ **ドメイン** ] ページで、確認するドメインの [ **アクション** ] 列で、[ **セットアップの開始**] を選択します。 
3. [ **自分がドメインを所有していることを確認** する] ページで、[完了] を選択し **、今すぐ確認** し、確認ダイアログ ボックスで [完了] を選択 **します**。 
   
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>on-prem Active Directory で UPN として使用されるルーティング不可能な電子メール アドレス
<a name="BKMK_ADNote"> </a>

オンプレミスの Active Directoryを Microsoft と同期する予定の場合は、Active Directory ユーザー プリンシパル名 (UPN) サフィックスが有効なドメイン サフィックスであり、@contoso.local などのサポートされていないドメイン サフィックスでないことを確認します。 UPN サフィックスを変更する必要がある場合は、「 [ルーティング不可能なドメインをディレクトリ同期用に準備する方法」を](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

## <a name="related-content"></a>関連コンテンツ

[Micrsoft 365 から別のホストにドメインを転送する](../get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host.md) (記事)\
[カスタム ドメインからのパイロット Microsoft 365](../misc/pilot-microsoft-365-from-my-custom-domain.md) (記事)\
[ドメインの FAQ](../setup/domains-faq.yml) (記事)