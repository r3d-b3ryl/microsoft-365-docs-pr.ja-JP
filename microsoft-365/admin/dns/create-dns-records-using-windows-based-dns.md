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
description: ドメインを確認し、Microsoft の電子メール、Skype for Business オンライン、その他のサービスの DNS レコードWindows設定する方法について説明します。
ms.openlocfilehash: 0349366e1cb3af23de1161a69b9b37305cc1237a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313483"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows ベースの DNS を使って Microsoft の DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
   
Windows ベースの DNS を使用して独自の DNS レコードをホストする場合は、この記事の手順に従って、電子メール、Skype for Business Online などのためにレコードを設定します。
  
開始するには、DNS レコードを更新するために、Windows[ベースの DNS で DNS](#find-your-dns-records-in-windows-based-dns) レコードを検索する必要があります。 また、オンプレミスの Active Directory と Microsoft の同期を計画している場合は、「 [On-prem Active Directory で UPN](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory) として使用される展開不可の電子メール アドレス」を参照してください。
  
DNS レコードを追加した後のメール フローなどの問題に関する問題については、「ドメイン名または DNS レコードを変更した後の問題のトラブルシューティング [」を参照してください](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Windows ベース DNS 内の DNS レコードを検索する
<a name="BKMK_find_your_dns_1"> </a> ドメインの DNS レコードがあるページに移動します。 サーバー 2008 で作業Windows **StartRun** に **移動** > します。 Windows Server 2012 を使っている場合は、Windows キーを押して、**R** キーを押します。 「**dnsmgmnt.msc**」と入力して、[**OK**] を選択します。 DNS マネージャーで、[前方参照領域 **]\<DNS server name\>\> を展開します**。 ドメインを選択します。 これで DNS レコードを作成する準備が整いました。
   
## <a name="add-mx-record"></a>MX レコードの追加
<a name="BKMK_add_MX"> </a>

ドメインのメールが Microsoft に送信される MX レコードを追加します。
- 追加する MX レコードには、MSxxxxxxx のような値である .mail.protection.outlook.com \<MX token\> のような値 (アドレスのポイント値) \<MX token\>が含まれます。 
- Microsoft の [DNS レコードの追加] ページExchange Onlineセクションの MX 行から、[ポイント先アドレス] の下に一覧表示されている値をコピーします。 この値は、このタスクで作成するレコードで使用します。 
- ドメインの [DNS マネージャー] ページで、[**ActionMail** >  **Exchanger (MX)] に移動します**。 ドメインのこのページを見つけるには、「DNS レコードを検索する」を参照[Windowsベースの DNS を参照してください](#find-your-dns-records-in-windows-based-dns)。  
- [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。 
    - Host Name:  
    - @Address: ここで、Microsoft からコピーしたアドレス値にポイントを貼り付けます。  
    - Pref: 
- [**変更を保存**] を選択します。
- 古い MX レコードをすべて削除します。 メールを別の場所にルーティングするこのドメインの古い MX レコードがある場合は、各古いレコードの横にあるチェック ボックスをオンにし、[**DeleteOK** > ] を選択 **します**。 
   
## <a name="add-cname-records"></a>CNAME レコードの追加
<a name="BKMK_add_CNAME"> </a>

Microsoft に必要な CNAME レコードを追加します。 Microsoft に追加の CNAME レコードが表示されている場合は、ここに示すのと同じ一般的な手順に従ってレコードを追加します。
  
> [!IMPORTANT]
> Microsoft 用のモバイル デバイス管理 (MDM) がある場合は、2 つの追加の CNAME レコードを作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (MDM を使用していない場合は、この手順を省略できます)。 

- ドメインの DNS マネージャー ページで、**ActionCNAME** >  **(CNAME)に移動します**。
- [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    - ホスト名: 自動検出
    - 種類: 
    - CNAMEAddress: autodiscover.outlook.com
- [ **OK] を選択** します。

SIP CNAME レコードを追加します。 
- ドメインの [DNS マネージャー] ページで、[アクション  \> **CNAME ] (CNAME) に移動します**。 
- [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    - ホスト名: sip
    - 種類: CNAME
    - アドレス: sipdir.online.lync.com
- **[OK]** を選択します。

オンライン自動Skype for Business CNAME レコードを追加します。  
- ドメインの [DNS マネージャー] ページで、[アクション  \> **CNAME ] (CNAME) に移動します**。 [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    - ホスト名: lyncdiscover
    - 種類: CNAME
    - アドレス: webdir.online.lync.com
- **[OK]** を選択します。
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Microsoft のモバイル デバイス管理 (MDM) に 2 つの CNAME レコードを追加する

> [!IMPORTANT]
> Microsoft 用のモバイル デバイス管理 (MDM) がある場合は、2 つの追加の CNAME レコードを作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. >(MDM を使用していない場合は、この手順を省略できます)。 
  

MDM Enterpriseregistration CNAME レコードを追加します。  
- ドメインの [DNS マネージャー] ページで、[アクション  \> **CNAME ] (CNAME) に移動します**。 
- [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
- ホスト名: enterpriseregistration
- 種類: CNAME
- アドレス: enterpriseregistration.windows.net
- **[OK]** を選択します。 

MDM Enterpriseenrollment CNAME レコードを追加します。 
-  ドメインの [DNS マネージャー] ページで、[アクション  \> **CNAME ] (CNAME) に移動します**。 
-  [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    - ホスト名: enterpriseenrollment
    - 種類: CNAME
    - アドレス: enterpriseenrollment-s.manage.microsoft.com
- **[OK]** を選択します。
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む 1  *つの SPF*  レコードを作成します。 
  
ドメインの SPF TXT レコードを追加して、メールスパムを防止します。
  
- このレコードの TXT 値に他の文字列 (マーケティングメール用の文字列など) が既に含まれる場合があります。これは問題ありません。 これらの文字列はそのままにし、この文字列を追加し、各文字列を二重引用符で囲み、それらを分離します。 
- ドメインの [DNS マネージャー] ページで、[アクション テキスト  \> **] (TXT) に移動します**。 
-  [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。 
 > [!IMPORTANT]
> 一部のバージョンWindows DNS マネージャーでは、txt レコードを作成するときにホーム名が既定で親ドメインに設定されている可能性があります。 この状況では、TXT レコードを追加するときに、ホスト名を @ またはドメイン名に設定する代わりに、ホスト名を空白 (値なし) に設定します。 

-  ホストの種類:@
-  レコードの種類: TXT
-  アドレス: v=spf1 include:spf.protection.outlook.com -all 
         
-  **[OK]** を選択します。
   
## <a name="add-srv-records"></a>SRV レコードの追加
<a name="BKMK_add_SRV"> </a>

Microsoft に必要な 2 つの SRV レコードを追加します。

オンライン Web 会議の SIP SRV レコードSkype for Business追加します。  <br/> 
-  ドメインの [DNS マネージャー] ページで、[アクション] [その他の **新しいレコード]** \> **に移動します**。 
-   [リソース レコード **の種類] ウィンドウで** 、[ **サービスの場所 ] (SRV)** を選択し、[レコードの作成] **を選択します**。 
-   [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    -  サービス: _sip
    -  プロトコル: _tls
    -  優先度: 100
    -  重み: 1
    -  ポート: 443
    -  ターゲット (ホスト名): sipdir.online.lync.com
-  **[OK]** を選択します。 


オンライン フェデレーションの SIP SRV レコードSkype for Business追加します。  
-  ドメインの [DNS マネージャー] ページで、[アクション] [その他の **新しいレコード]** \> **に移動します**。  
-  [リソース レコード **の種類] ウィンドウで** 、[ **サービスの場所 ] (SRV)** を選択し、[レコードの作成] **を選択します**。 
-   [新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。  
    -  サービス: _sipfederationtls
    -  プロトコル: _tcp
    -  優先度: 100
    -  重み: 1
    -  ポート: 5061
    -  ターゲット (ホスト名): sipfed.online.lync.com
-  **[OK]** を選択します。 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>まだドメインを所有していない場合は、レコードを追加してドメインを所有している必要があります。
<a name="BKMK_verify"> </a>

DNS レコードを追加してドメイン をセットアップする前Microsoft サービス、追加するドメインを所有している必要があります。 これを行うには、以下の手順に従ってレコードを追加します。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認する場合にのみ使用します。その他には影響しません。 
  

1. Microsoft から情報を収集します。  <br/> 
2. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。 
3. [ドメイン **] ページで**、確認するドメインの [アクション] 列で、[セットアップの開始] **を選択します**。 
4. [Microsoft に **ドメインを追加する] ページで** 、[手順 **1 の開始] を選択します**。 
5. [自分の **ドメインを所有することを確認** する] ページの  [この手順を実行するための手順を表示する] ドロップダウン リストで、[全般手順] を **選択します**。 
6. 表から、[宛先] または [ポイントからアドレス] の値をコピーします。 次の手順に必要です。 この値をコピーして貼り付け、すべての間隔が正しいままにすることをお勧めします。

TXT レコードを追加します。 
-  ドメインの [DNS マネージャー] ページで、[アクション テキスト  \> **] (TXT) に移動します**。 
-   [新しい **リソース レコード] ダイアログ ボックス** で、[編集] を **選択します**。  
-  [新 **しいリソース レコード] ダイアログ** ボックスの [カスタム ホスト名] 領域で、フィールドが次の値に正確に設定されている必要があります。 

> [!IMPORTANT] 
> 一部のバージョンWindows DNS マネージャーでは、txt レコードを作成するときにホーム名が既定で親ドメインに設定されている可能性があります。 この状況では、TXT レコードを追加するときに、ホスト名を @ またはドメイン名に設定する代わりに、ホスト名を空白 (値なし) に設定します。 

- ホスト名:@
- タイプ: TXT
- [アドレス]: Microsoft からコピーした [宛先] または [ポイント先アドレス] の値をここに貼り付けます。  
- [ **OKDone** > **] を選択します**。

Microsoft でドメインを確認します。  
> [!IMPORTANT]
> これを行う前に約 15 分待つ必要があります。そのため、作成したレコードはインターネットを通して更新できます。       

- Microsoft に戻り、以下の手順に従って検証チェックを要求します。 このチェックでは、前の手順で追加した TXT レコードが確認されます。 正しい TXT レコードが見つけたら、ドメインが検証されます。  
1. 管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a> します。
2. [ドメイン **] ページで**、確認するドメインの [アクション] 列で、[セットアップの開始] **を選択します**。 
3. [ドメイン **の所有を確認** する] ページで、[完了] を選択し、[今すぐ確認] を選択し、[確認] ダイアログ ボックスで [完了] を選択 **します**。 
   
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>on-prem Active Directory で UPN として使用される、ルートできない電子メール アドレス
<a name="BKMK_ADNote"> </a>

オンプレミスの Active Directory と Microsoft の同期を計画している場合は、Active Directory ユーザー プリンシパル名 (UPN) サフィックスが有効なドメイン サフィックスであり、@contoso.local などのサポートされていないドメイン サフィックスで構成されていないことを確認する必要があります。 UPN サフィックスを変更する必要がある場合は、「ディレクトリ同期用にルートできないドメインを準備する方法」 [を参照してください](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

## <a name="related-content"></a>関連コンテンツ

[Micrsoft 365 から別のホストにドメインを](../get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host.md) 転送する (記事)\
[カスタム Microsoft 365からのパイロット テスト](../misc/pilot-microsoft-365-from-my-custom-domain.md) (記事)\
[ドメインの FAQ](../setup/domains-faq.yml) (記事)