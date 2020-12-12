---
title: Windows ベースの DNS を使用して Microsoft の DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: ドメインを確認し、メール、Skype for Business Online、その他のサービスの DNS レコードを Windows ベースの DNS for Microsoft でセットアップする方法について説明します。
ms.openlocfilehash: 8202ffe10b4a0ff9c94d863d92fc55c47ebb38d3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656845"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows ベースの DNS を使用して Microsoft の DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
   
Windows ベースの DNS を使用して独自の DNS レコードをホストする場合は、この記事の手順に従って、メールや Skype for Business Online などのためにレコードを設定します。
  
開始するには、Dns レコードを [更新できるよう、Windows ベースの DNS](#find-your-dns-records-in-windows-based-dns) で DNS レコードを検索する必要があります。 また、オンプレミスの Active Directory と Microsoft の同期を計画している場合は、「オンプレミスの Active Directory で [UPN](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)として使用される、アウトアウトできないメール アドレス」を参照してください。
  
DNS レコードの追加後のメール フローなどの問題については、「ドメイン名または DNS レコードを変更した後の問題のトラブルシューティング [」を参照してください](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Windows ベース DNS 内の DNS レコードを検索する
<a name="BKMK_find_your_dns_1"></a>ドメインの DNS レコードがあるページに移動します。 If you're working in Windows Server 2008, go to **Start**  >  **Run**. If you're working in Windows Server 2012, press the Windows key and **r**. **「dnsmgmnt.msc」と** 入力し **、[OK] を選択します**。 DNS マネージャーで、[前方参照 **\<DNS server name\> \> ゾーン] を展開します**。 ドメインを選択します。 これで、DNS レコードを作成する準備ができました。
   
## <a name="add-mx-record"></a>MX レコードを追加する
<a name="BKMK_add_MX"> </a>

MX レコードを追加して、ドメインのメールが Microsoft に届く。
- 追加する MX レコードには、次のような値 (ポイント **先** アドレス値) が含まれます。.mail.protection.outlook.com は \<MX token\> \<MX token\> MSxxxxxxx のような値です。 
- Microsoft の [DNS レコードの追加] ページの Exchange Online セクションの MX 行から、[ポイント先アドレス] の下に表示されている値をコピーします。 このタスクで作成するレコードでこの値を使用します。 
- ドメインの DNS マネージャー ページで、Action   >  **Mail Exchanger (MX) に移動します**。 ドメインのこのページを見つけるには [、「Windows ベースの DNS で DNS レコードを検索する」を参照してください](#find-your-dns-records-in-windows-based-dns)。  
- [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。 
    - ホスト名: 
    - @Address: Microsoft からコピーしたポイント先アドレスの値をここに貼り付けます。  
    - Pref: 
- [変更 **の保存] を選択します**。
- 古い MX レコードをすべて削除します。 電子メールを別の場所にルーティングする古い MX レコードがある場合は、各古いレコードの横にあるチェック ボックスをオンにして、[  >  **削除 OK]** を選択します。 
   
## <a name="add-cname-records"></a>CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

Microsoft に必要な CNAME レコードを追加します。 追加の CNAME レコードが Microsoft にリストされている場合は、ここに示すのと同じ一般的な手順に従って追加します。
  
> [!IMPORTANT]
> Microsoft のモバイル デバイス管理 (MDM) を使用している場合は、2 つの追加の CNAME レコードを作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (MDM を使用していない場合は、この手順を省略できます)。 

- On the DNS Manager page for the domain, go to **Action**  >  **CNAME (CNAME)**.
- [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    - ホスト名: autodiscover
    - 種類: 
    - CNAMEAddress: autodiscover.outlook.com
- **[O K] を** 選択します。

SIP CNAME レコードを追加します。 
- On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**. 
- [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    - ホスト名: sip
    - 型: CNAME
    - 住所: sipdir.online.lync.com
- **[OK]** をクリックします。

Skype for Business Online 自動検出 CNAME レコードを追加します。  
- On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**. [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    - ホスト名: lyncdiscover
    - 型: CNAME
    - 住所: webdir.online.lync.com
- **[OK]** をクリックします。
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Microsoft のモバイル デバイス管理 (MDM) 用に 2 つの CNAME レコードを追加する

> [!IMPORTANT]
> Microsoft のモバイル デバイス管理 (MDM) を使用している場合は、2 つの追加の CNAME レコードを作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. >(MDM を使用していない場合は、この手順を省略できます)。) 
  

MDM Enterpriseregistration CNAME レコードを追加します。  
- On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**. 
- [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
- ホスト名: enterpriseregistration
- 型: CNAME
- 住所: enterpriseregistration.windows.net
- **[OK]** をクリックします。 

MDM Enterpriseenrollment CNAME レコードを追加します。 
-  On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**. 
-  [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    - ホスト名: enterpriseenrollment
    - 型: CNAME
    - 住所: enterpriseenrollment-s.manage.microsoft.com
- **[OK]** をクリックします。
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft の値を現在のレコードに追加して、両方の値のセットを含む  *1*  つの SPF レコードを作成します。 
  
ドメインの SPF TXT レコードを追加して、迷惑メールを防止します。
  
- このレコードの TXT 値には、既に他の文字列 (マーケティング電子メールの文字列など) が含まれる場合があります。これで問題ありません。 これらの文字列はそのまま残し、この文字列を追加して、各文字列を二重引用符で囲み、それらを分離します。 
- On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**. 
-  [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。 
 > [!IMPORTANT]
> 一部のバージョンの Windows DNS マネージャーでは、txt レコードを作成するときに、ホーム名が既定で親ドメインに設定されている場合があります。 この場合、TXT レコードを追加するときに、ホスト名を @ またはドメイン名に設定するのではなく、空白 (値なし) に設定します。 

-  ホストの種類:@
-  レコードの種類: TXT
-  アドレス: v=spf1 include:spf.protection.outlook.com -all 
         
-  **[OK]** をクリックします。
   
## <a name="add-srv-records"></a>SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

Microsoft に必要な 2 つの SRV レコードを追加します。

Skype for Business Online Web 会議の SIP SRV レコードを追加します。  <br/> 
-  On the DNS Manager page for your domain, go to **Action** \> **Other New Records**. 
-   [リソース **レコードの種類] ウィンドウで** 、[サービスの場所 **(SRV)**] を選択し、[レコードの作成] **を選択します**。 
-   [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    -  サービス: _sip
    -  プロトコル: _tls
    -  優先度: 100
    -  重み: 1
    -  ポート: 443
    -  ターゲット (ホスト名): sipdir.online.lync.com
-  **[OK]** をクリックします。 


Skype for Business Online フェデレーションの SIP SRV レコードを追加します。  
-  On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.  
-  [リソース **レコードの種類] ウィンドウで** 、[サービスの場所 **(SRV)**] を選択し、[レコードの作成] **を選択します**。 
-   [新 **しいリソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    -  サービス: _sipfederationtls
    -  プロトコル: _tcp
    -  優先度: 100
    -  重み: 1
    -  ポート: 5061
    -  ターゲット (ホスト名): sipfed.online.lync.com
-  **[OK]** をクリックします。 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>まだドメインを所有していない場合は、レコードを追加してドメインを所有している必要があります。
<a name="BKMK_verify"> </a>

Microsoft サービスをセットアップするために DNS レコードを追加する前に、Microsoft は追加するドメインを所有している必要があります。 これを行うには、次の手順に従ってレコードを追加します。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認する場合にのみ使用します。その他には影響しません。 
  

1. Microsoft から情報を収集します。  <br/> 
2. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。 
3. On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**. 
4. On the **Add a domain to Microsoft** page, select Start step **1**. 
5. On the **Confirm that you own your domain** page, in the See **instructions for performing this step with** drop-down list, choose General **instructions**. 
6. 表から [宛先] または [ポイント先アドレス] の値をコピーします。 次の手順で必要です。 この値をコピーして貼り付け、スペースはすべて正しく入力することをお勧めします。

TXT レコードを追加します。 
-  On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**. 
-   [新しい **リソース レコード] ダイアログ ボックス** で、[編集] を **選択します**。  
-  [**新しいリソース レコード**]ダイアログ ボックスの [カスタム ホスト名] 領域で、フィールドが次の値に正確に設定されている必要があります。 

> [!IMPORTANT] 
> 一部のバージョンの Windows DNS マネージャーでは、txt レコードを作成するときに、ホーム名が既定で親ドメインに設定されている場合があります。 この場合、TXT レコードを追加するときに、ホスト名を @ またはドメイン名に設定するのではなく、空白 (値なし) に設定します。 

- ホスト名:@
- 型: TXT
- アドレス: Microsoft からコピーした宛先またはポイント先のアドレスの値をここに貼り付けます。  
- [OK **完了] を**  >  **選択します**。

Microsoft でドメインを確認します。  
> [!IMPORTANT]
> これを行う前に約 15 分待つ必要があります。これにより、作成したレコードがインターネット全体で更新される可能性があります。       

- Microsoft に戻り、次の手順に従って確認チェックを要求します。 チェックでは、前の手順で追加した TXT レコードが見えます。 正しい TXT レコードが見つけると、ドメインが検証されます。  
1. 管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a> します。
2. On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**. 
3. On the **Confirm that you own your domain** page, select **done, verify now,** and then in the confirmation dialog box, select **Finish**. 
   
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>オンプレムの Active Directory で UPN として使用される、ルートできない電子メール アドレス
<a name="BKMK_ADNote"> </a>

オンプレミスの Active Directory を Microsoft と同期する予定の場合は、Active Directory ユーザー プリンシパル名 (UPN) サフィックスが有効なドメイン サフィックスであり、サポートされていないドメイン サフィックス (@contoso.local など) で構成されていないことを確認する必要があります。 UPN サフィックスを変更する必要がある場合は、「ディレクトリ同期用にアウトできないドメインを準備する方法」 [を参照してください](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
