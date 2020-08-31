---
title: Windows ベースの DNS を使用して Microsoft の DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: Windows ベースの DNS で、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: f0c2b8c4aaaa1012e0f11e3778c7ca6b092c053f
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306949"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows ベースの DNS を使用して Microsoft の DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
   
Windows ベースの DNS を使用して独自の DNS レコードをホストする場合は、この記事の手順に従って、電子メール、Skype for Business Online などのレコードを設定します。
  
まず、 [dns レコードを Windows ベースの dns で検索して](#find-your-dns-records-in-windows-based-dns) 更新できるようにする必要があります。 また、オンプレミスの Active Directory を Microsoft と同期することを計画している場合は、オンプレミスの [Active directory で UPN として使用される、ルーティング可能でない電子メールアドレス](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)を参照してください。
  
DNS レコードの追加後にメールフローなどに問題が発生した場合は、「 [ドメイン名または dns レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Windows ベース DNS 内の DNS レコードを検索する
<a name="BKMK_find_your_dns_1"> </a>ドメインの DNS レコードがあるページに移動します。 Windows Server 2008 で作業している場合は、[実行]**を開き**  >  **Run**ます。 Windows Server 2012 で作業している場合は、Windows キーと **r**キーを押します。 「 **Dnsmgmnt**」と入力し、[ **OK]** を選択します。 DNS マネージャーで、[ ** \<DNS server name\> \> 前方参照ゾーン  **] を展開します。 ドメインを選択します。 これで、DNS レコードを作成する準備ができました。
   
## <a name="add-mx-record"></a>MX レコードの追加
<a name="BKMK_add_MX"> </a>

MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにします。
- 追加する MX レコードには、次のように表示される値 ( **アドレス値へのポイント** ) が含まれています。ここで、は、mail.protection.outlook.com のように見えます。ここで、 \<MX token\> \<MX token\> は MSxxxxxxx のような値です。 
- Microsoft の [DNS レコードの追加] ページの [Exchange Online] セクションの [MX] 行で、[point to アドレス] の下に表示されている値をコピーします。 この値は、このタスクで作成しているレコードで使用します。 
- ドメインの [DNS マネージャー] ページで、[**アクション**  >  **メールエクスチェンジャー (MX)**] に移動します。 ドメインのこのページを見つけるには、「 [Windows ベースの dns で dns レコードを検索](#find-your-dns-records-in-windows-based-dns)する」を参照してください。  
- [ **新しいリソースレコード** ] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。 
    - Host Name:  
    - @Address: Microsoft からコピーしたのと同じ値にポイントを貼り付けます。  
    - Pref: 
- [ **Save Changes**] を選びます。
- 古い MX レコードをすべて削除します。 他の場所に電子メールをルーティングする、このドメインの古い MX レコードがある場合は、古いレコードの横にあるチェックボックスをオンにして、[**削除**  >  **OK]** を選択します。 
   
## <a name="add-cname-records"></a>CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

Microsoft に必要な CNAME レコードを追加します。 追加の CNAME レコードが Microsoft に表示されている場合は、次に示す同じ一般的な手順を追加します。
  
> [!IMPORTANT]
> Microsoft 用のモバイルデバイス管理 (MDM) を使用している場合は、2つの CNAME レコードを追加作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (MDM を持っていない場合は、この手順を省略できます)。 

- ドメインの [DNS マネージャー] ページで、[ **Action**  >  **CNAME (cname)**] に移動します。
- [ **新しいリソースレコード** ] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    - ホスト名: 自動検出
    - 種類: 
    - CNAMEAddress: autodiscover.outlook.com
- [ **O**K] を選択します。

SIP CNAME レコードを追加します。 
- ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。 
- [ **新しいリソースレコード** ] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    - ホスト名: sip
    - 型: CNAME
    - アドレス: sipdir.online.lync.com
- **[OK]** を選択します。

Skype for Business Online の自動検出の CNAME レコードを追加します。  
- ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。 [ **新しいリソースレコード** ] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    - ホスト名: lyncdiscover
    - 型: CNAME
    - アドレス: webdir.online.lync.com
- **[OK]** を選択します。
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Microsoft のモバイルデバイス管理 (MDM) に対して2つの CNAME レコードを追加する

> [!IMPORTANT]
> Microsoft 用のモバイルデバイス管理 (MDM) を使用している場合は、2つの CNAME レコードを追加作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (MDM を使用していない場合は、この手順を省略できます)。 
  

MDM Enterpriseregistration CNAME レコードを追加します。  
- ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。 
- [ **新しいリソースレコード** ] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
- ホスト名: enterpriseregistration
- 型: CNAME
- アドレス: enterpriseregistration.windows.net
- **[OK]** を選択します。 

MDM Enterpriseenrollment CNAME レコードを追加します。 
-  ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。 
-  [ **新しいリソースレコード** ] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    - ホスト名: enterpriseenrollment
    - 型: CNAME
    - アドレス: enterpriseenrollment-s.manage.microsoft.com
- **[OK]** を選択します。
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、値のセットを含む  *1 つ*  の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。 
  
自分のドメインの SPF TXT レコードを追加して、電子メールのスパム防止に役立てます。
  
- このレコード (マーケティング電子メールの文字列など) の TXT 値には、既に他の文字列が含まれている場合がありますが、これは問題ありません。 これらの文字列をそのまま残して、この文字列を追加し、各文字列を二重引用符で区切って配置します。 
- ドメインの [DNS マネージャー] ページで、[ **アクション** \> **テキスト (TXT)**] に移動します。 
-  [ **新しいリソースレコード** ] ダイアログボックスで、フィールドが正確に次の値に設定されていることを確認します。 
 > [!IMPORTANT]
> Windows DNS マネージャーの一部のバージョンでは、ドメインがセットアップされていて、txt レコードの作成時にホーム名が既定で親ドメインになっている場合があります。 このような場合、TXT レコードを追加するときに、@ またはドメイン名に設定するのではなく、ホスト名を空白 (値なし) に設定します。 

-  ホストの種類:@
-  レコードの種類: TXT
-  アドレス: v = spf1 には、以下のようにします。 
         
-  **[OK]** を選択します。
   
## <a name="add-srv-records"></a>SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

Microsoft に必要な2つの SRV レコードを追加します。

Skype for Business Online web 会議の SIP SRV レコードを追加します。  <br/> 
-  ドメインの [DNS マネージャー] ページで、[ **アクション** \> **その他の新しいレコード**] に移動します。 
-   [ **リソースレコードの種類** ] ウィンドウで、[ **サービスロケーション (SRV)**] を選択し、[ **レコードの作成**] を選択します。 
-   [ **新しいリソースレコード** ] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    -  サービス: _sip
    -  プロトコル: _tls
    -  優先度: 100
    -  重み: 1
    -  ポート: 443
    -  ターゲット (ホスト名): sipdir.online.lync.com
-  **[OK]** を選択します。 


Skype for Business Online フェデレーションの SIP SRV レコードを追加します。  
-  ドメインの [DNS マネージャー] ページで、[ **アクション** \> **その他の新しいレコード**] に移動します。  
-  [ **リソースレコードの種類** ] ウィンドウで、[ **サービスロケーション (SRV)**] を選択し、[ **レコードの作成**] を選択します。 
-   [ **新しいリソースレコード** ] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    -  サービス: _sipfederationtls
    -  プロトコル: _tcp
    -  優先度: 100
    -  重み: 1
    -  ポート: 5061
    -  ターゲット (ホスト名): sipfed.online.lync.com
-  **[OK]** を選択します。 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>ドメインを所有していることを確認するためにレコードを追加します (まだ登録していない場合)。
<a name="BKMK_verify"> </a>

Microsoft サービスをセットアップするために DNS レコードを追加する前に、Microsoft は、追加しているドメインを所有していることを確認する必要があります。 これを行うには、以下の手順に従ってレコードを追加します。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認する場合にのみ使用します。その他には影響しません。 
  

1. Microsoft から情報を収集します。  <br/> 
2. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。 
3. [ **ドメイン** ] ページで、確認するドメインの [ **操作** ] 列で、[ **セットアップの開始**] を選択します。 
4. [ **Microsoft へのドメインの追加** ] ページで、[ **ステップ1の開始**] を選択します。 
5. [ **自分のドメインを所有** していることを確認します] ページで、[ **この手順を実行するための** 手順を参照してください] ドロップダウンリストで、[ **一般的な手順**] を選択します。 
6. テーブルから、移動先またはポイントを [Address value] にコピーします。 次の手順で必要になります。 この値をコピーして貼り付けることをお勧めします。これにより、すべてのスペースが正しく保たれるようになります。

TXT レコードを追加します。 
-  ドメインの [DNS マネージャー] ページで、[ **アクション** \> **テキスト (TXT)**] に移動します。 
-   [ **新しいリソースレコード** ] ダイアログボックスで、[ **編集**] を選択します。  
-  [**新しいリソースレコード**] ダイアログボックスの [**ユーザー設定のホスト名**] 領域で、フィールドが正確に次の値に設定されていることを確認します。 

> [!IMPORTANT] 
> Windows DNS マネージャーの一部のバージョンでは、ドメインがセットアップされていて、txt レコードの作成時にホーム名が既定で親ドメインになっている場合があります。 このような場合、TXT レコードを追加するときに、@ またはドメイン名に設定するのではなく、ホスト名を空白 (値なし) に設定します。 

- ホスト名:@
- 型: TXT
- [住所]: コピー先またはポイントを、Microsoft からコピーしたばかりのアドレス値に貼り付けます。  
- [ **OK 完了]** を選択し  >  **Done**ます。

Microsoft のドメインを確認します。  
> [!IMPORTANT]
> この操作を行う前に15分ほど待ってから、作成したレコードがインターネットを介して更新できるようにします。       

- Microsoft に戻って、次の手順に従って確認を要求します。 このチェックボックスでは、前の手順で追加した TXT レコードを探します。 正しい TXT レコードが見つかった場合、ドメインは確認されます。  
1. 管理センターで、[ドメインの**セットアップ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> ] ページに移動します。
2. [ **ドメイン** ] ページで、確認するドメインの [ **処理** ] 列で、[ **セットアップの開始**] を選択します。 
3. [ **自分のドメインを所有** していることを確認してください] ページで、[ **完了]、[今すぐ確認**] の順に選択し、確認のダイアログボックスで [ **完了**] を選択します。 
   
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>オンプレミスの Active Directory で UPN として使用される、ルーティング不可能な電子メールアドレス
<a name="BKMK_ADNote"> </a>

オンプレミスの Active Directory を Microsoft と同期することを計画している場合は、Active Directory のユーザープリンシパル名 (UPN) サフィックスが有効なドメインサフィックスであることを確認します。これは、@contoso など、サポートされていないドメインサフィックスではありません。 UPN サフィックスを変更する必要がある場合は、「 [ディレクトリ同期のためにルーティング不能なドメインを準備する方法](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
