---
title: 任意の DNS ホスティング プロバイダーで DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: 任意の DNS ホスティング プロバイダーで Microsoft 365 用のドメインを確認し、DNS レコードを作成する方法について説明します。
ms.custom: okr_smb
ms.openlocfilehash: 85392bfbd19072d582e7c2db7ce3a8c7bf466176
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628496"
---
# <a name="create-dns-records-at-any-dns-hosting-provider"></a>任意の DNS ホスティング プロバイダーで DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
[ホスト固有の命令](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580)の一覧からお使いのホストを見つけ、手順に従って必要なすべてのレコードを追加します。 
  
ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。
  
レコードを各自でセットアップする場合は、以下のレコードを追加します。検証レコードと MX レコードはドメインに固有です。それらをセットアップするには、ドメインに固有な "トークン" 値を取得して使用する必要があります。この手順については以下で説明します。
  
> [!IMPORTANT]
> 各 DNS レコード タイプを作るための情報を入力したり貼り付けたりするボックスまたは "*フィールド*" の正確な名前は、DNS ホストによって異なります。ここに記載されている手順が実際の Web サイトのどのフィールドに該当するのかについては、DNS ホストの Web サイトのヘルプを参照してください。使用している DNS ホストの手順が「[Microsoft 365 の DNS レコードを作成する](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx)」に記載されているかどうかをご確認ください。 > DNS ホストによっては、必要なレコード タイプの一部を作成できないため、Microsoft 365 の[サービスが制限される](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)場合があります。ドメインのホストが SRV、TXT、CNAME などのレコードをサポートしていない場合は、必要なすべてのレコードをサポートする DNS ホストに[ドメインを移行する](../get-help-with-domains/buy-a-domain-name.md)ことをお勧めします。高速の自動プロセスで Microsoft 365 をセットアップする場合は、ドメインを GoDaddy に移行することをお勧めします。 
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間はわずか数分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>確認のため TXT レコードまたは MX レコードを追加する
<a name="BKMK_verify"> </a>

> [!NOTE]
> これらのレコードのいずれか一方を作成します。推奨されるレコードの種類は TXT ですが、一部の DNS ホスティング プロバイダーではサポートしていないため、代わりに MX レコードを作成してもかまいません。 
  
Microsoft 365 のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
 **DNS ホスティング プロバイダーの Web サイトで、新しいレコードを作成できる場所を見つけます。**
  
1. DNS ホスティング プロバイダーの Web サイトにサインインします。
    
2. ドメインを選びます。
    
3. ドメインに関する DNS レコードを編集可能なページを探します。
    
 **レコードを作成します。**
  
1. TXT レコードと MX レコードのどちらを作成しているかに応じて、次のいずれかを実行します。
    
  - **TXT レコードを作成する場合は、以下の値を使います。**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type**|**Alias** または **Host Name**|**Value**|**TTL**|
|TXT|次のいずれかを実行します。「 **@** 」と入力するか、フィールドを空白のままにするか、ドメイン名を入力します。    <br/> **注:** このフィールドの要件は、DNS ホストによって異なります。 |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。  <br/>        [確認する方法](../get-help-with-domains/information-for-dns-records.md)     <br/>     |この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。  |
   
  - **MX レコードを作成する場合は、以下の値を使います。**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type**|**Alias** または **Host Name**|**Value**|**Priority**|**TTL**|
|MX|**@** か自分のドメインの名前のいずれかを入力します。 |MS=ms *XXXXXXXX* <br/> **注:** これは例です。 Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。    <br/>       [確認する方法](../get-help-with-domains/information-for-dns-records.md)     <br/>     |**Priority** には、メール フローに使われる MX レコードとの競合を避けるために、既存の MX レコードよりも低い優先度を指定します。 <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> |この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 |
   
2. レコードを保存します。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。
  
Microsoft 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
       
4. **[ドメインの確認]** ページで、**[確認]** を選択します。   
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-mx-record-to-route-email"></a>MX レコードを追加してメールをルーティングする
<a name="BKMK_add_MX"> </a>

MX レコードを追加して、自分のドメインのメールが Microsoft 365 に届くようにします。  "*ドメインの MX レコードを更新すると、お客様のドメインを使用するユーザーのすべての新しいメールが、Microsoft 365 に届くようになります*"。 [メールと連絡先を Microsoft 365 に移行する](../setup/migrate-email-and-contacts-admin.md)ことを決定しない限り、既に所有しているメールは現在のメール ホストに保持されます。 
  
  
 **タスク**
  
ドメインのレコードを作成できるページを見つけます。
  
1. DNS ホストの Web サイトにサインインします。
    
2. ドメインを選びます。
    
3. ドメインに関する DNS レコードを編集可能なページを探します。
    
::: moniker range="o365-worldwide"

追加する MX レコードには、 **ポイント先のアドレス**を示す値が含まれており、\<MX token\>.mail.protection.outlook.com (\<MX token\> の値は MSxxxxxxx など) のような内容です。   

::: moniker-end

::: moniker range="o365-germany"

追加する MX レコードには、 **ポイント先のアドレス**を示す値が含まれており、\<MX token\>.mail.protection.outlook.de (\<MX token\> の値は MSxxxxxxx など) のような内容です。   

::: moniker-end

1. DNS ホストの Web サイトで、新しい MX レコードを追加します。
    
    ここで、Microsoft 365 から [MX レコードの情報を取得](../get-help-with-domains/information-for-dns-records.md)します。 
    
2. 上の手順の MX レコードから **[ポイント先のアドレス]** の値をコピーします。 
    
    この値は、次の手順で説明するように、DNS ホストのサイトでレコードを作成するときに使います。
    
3. DNS ホストのサイトで、新しい MX レコードのフィールドに以下の値が正確に設定されていることを確認します。
    
  - [**Record Type**]: **MX**
    
  - **Priority**: MX レコードの優先度には、最高を表す値 (通常は **0**) を設定します。
    
    優先度の詳細については、「[MX 優先度とは何ですか?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。
    
  - **Host Name**: **@**
    
  - **Points to address**: Microsoft 365 からコピーした **[ポイント先のアドレス]** の値をここに貼り付けます。 
    
  - **TTL**: この値は、**1 時間** または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 
    
4. レコードを保存します。
    
その他の MX レコードを削除します。
  
Microsoft 365 以外の場所にメールを送信する MX レコードがこのドメインにある場合は、該当のレコードをすべて削除します。
  
## <a name="add-three-cname-records"></a>3 つの CNAME レコードを追加する
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

次の手順に従って、Microsoft 365 に必要な 3 つの CNAME レコードを追加します。Microsoft 365 にさらに CNAME レコードが一覧に含まれている場合は、これと同じ全般的な手順に従って追加します。
  
DNS ホストの Web サイトで、3 つの新しい CNAME レコードを、一般的には 1 つずつ作成します。
  
1. 新規レコードごとのボックスに次の値を入力するか、コピーして貼り付けます。 最初の 3 つの新しいレコードをそれぞれ追加したら、別の CNAME レコードを作成します。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hour  <br/> |
|CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 hour  <br/> |
|CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 時間  <br/> |
   
   > [!NOTE]
   > **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 > これらのレコードは、Exchange、Lync、Skype for Business のハイブリッド展開には適用されません。 
  
2. 終了したら、レコードを保存します。
    
::: moniker-end
::: moniker range="o365-germany"

次の手順に従って、Microsoft 365 に必要な 3 つの CNAME レコードを追加します。Microsoft 365 にさらに CNAME レコードが一覧に含まれている場合は、これと同じ全般的な手順に従って追加します。
  
DNS ホストの Web サイトで、3 つの新しい CNAME レコードを、一般的には 1 つずつ作成します。
  
1. 新規レコードごとのボックスに次の値を入力するか、コピーして貼り付けます。 最初の 3 つの新しいレコードをそれぞれ追加したら、別の CNAME レコードを作成します。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 hour  <br/> |
|CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 hour  <br/> |
|CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 時間  <br/> |
   
   > [!NOTE]
   > **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 > これらのレコードは、Exchange、Lync、Skype for Business のハイブリッド展開には適用されません。 
  
2. 終了したら、レコードを保存します。
    
::: moniker-end

::: moniker range="o365-21vianet"

次の手順に従って、Microsoft 365 に必要な 3 つの CNAME レコードを追加します。Microsoft 365 にさらに CNAME レコードが一覧に含まれている場合は、これと同じ全般的な手順に従って追加します。
  
DNS ホストの Web サイトで、3 つの新しい CNAME レコードを、一般的には 1 つずつ作成します。
  
1. 新規レコードごとのボックスに次の値を入力するか、コピーして貼り付けます。 最初の 3 つの新しいレコードをそれぞれ追加したら、別の CNAME レコードを作成します。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.partner.outlook.cn  <br/> |1 時間  <br/> |
|CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 時間  <br/> |
|CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 時間  <br/> |
   
   > [!NOTE]
   > **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 > これらのレコードは、Exchange、Lync、Skype for Business のハイブリッド展開には適用されません。 
  
2. 終了したら、レコードを保存します。
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft-365"></a>Mobile Device Management (MDM) for Microsoft 365 用として 2 つの CNAME レコードを追加する
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Mobile Device Management (MDM) for Microsoft 365 を使用している場合は、追加の CNAME レコードを 2 つ作成する必要があります。手順は、他の 4 つの CNAME レコードと同じですが、次の表の値を入力します。 > (MDM がない場合は、この手順を省略できます。) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |EnterpriseRegistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hour  <br/> |
|CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 hour  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Mobile Device Management (MDM) for Microsoft 365 を使用している場合は、追加の CNAME レコードを 2 つ作成する必要があります。手順は、他の 4 つの CNAME レコードと同じですが、次の表の値を入力します。 > (MDM がない場合は、この手順を省略できます。) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Host** <br/> |**Points to** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 hour  <br/> |
|CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 時間  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが "*1 つ*" の SPF レコードに含まれるようにします。
  
DNS ホストの Web サイトで、既存の SPF レコードを編集するか、SPF 用の新しい TXT レコードを作成します。
  
> [!IMPORTANT]
> SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング方法があります。それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Microsoft 365 用に構成する必要もあります。使用を開始する場合は、「[DKIM を使用して、Microsoft 365 のドメインから送信される送信電子メールを検証する](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)」を参照してください。次に、「[DMARC を使用して Microsoft 365 でメールを検証する](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)」を参照してください。 
  
1. 新規レコードのボックスに、下記から状況に合った値のセットを入力するか、コピーして貼り付けます。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Host** <br/> |**TXT Value** <br/> |**TTL** <br/> |
|TXT (テキスト)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |1 時間  <br/> |
   
   **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 
    
2. 終了したら、レコードを保存します。
    
3. SPF レコードを検証するには、[SPF 検証ツール](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)のいずれかを使用します。

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが "*1 つ*" の SPF レコードに含まれるようにします。 
  
DNS ホストの Web サイトで、既存の SPF レコードを編集するか、SPF 用の新しい TXT レコードを作成します。
  
> [!IMPORTANT]
> SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング方法があります。それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Microsoft 365 用に構成する必要もあります。使用を開始する場合は、「[DKIM を使用して、Microsoft 365 のドメインから送信される送信電子メールを検証する](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)」を参照してください。次に、「[DMARC を使用して Microsoft 365 でメールを検証する](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)」を参照してください。 
  
1. 新規レコードのボックスに、下記から状況に合った値のセットを入力するか、コピーして貼り付けます。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type**|**Host**|**TXT Value**|**TTL**|
|TXT (テキスト)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |1 時間|
   
   **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 
    
2. 終了したら、レコードを保存します。
    
3. SPF レコードを検証するには、[SPF 検証ツール](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)のいずれかを使用します。
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが "*1 つ*" の SPF レコードに含まれるようにします。 
  
DNS ホストの Web サイトで、既存の SPF レコードを編集するか、SPF 用の新しい TXT レコードを作成します。
  
> [!IMPORTANT]
> SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング方法があります。それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Microsoft 365 用に構成する必要もあります。使用を開始する場合は、「[DKIM を使用して、Microsoft 365 のドメインから送信される送信電子メールを検証する](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)」を参照してください。次に、「[DMARC を使用して Microsoft 365 でメールを検証する](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)」を参照してください。 
  
1. 新規レコードのボックスに、下記から状況に合った値のセットを入力するか、コピーして貼り付けます。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type**|**Host**|**TXT Value**|**TTL**|
|TXT (テキスト)|@|v=spf1 include:spf.protection.partner.outlook.cn -all> [!NOTE]> スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |1 時間|
   
   **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 
    
2. 終了したら、レコードを保存します。
    
3. SPF レコードを検証するには、[SPF 検証ツール](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)のいずれかを使用します。
    
::: moniker-end

## <a name="add-two-srv-records"></a>2 つの SRV レコードを追加する
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

DNS ホストの Web サイトで、2 つの新しい SRV レコードを、一般的には 1 つずつ作成します。 つまり、Web サイトで 1 つ目の SRV レコードを追加してから、別の SRV レコードの作成を選びます。
  
1. 新規レコードごとのボックスに次の値を入力するか、コピーして貼り付けます。 **(DNS ホストでこれらの値が個別のフィールドとして用意されていない場合の SRV の作成については、下の注を参照してください。)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Name** <br/> |**Target** <br/> |**Protocol** <br/> |**Service** <br/> |**Priority** <br/> |**Weight** <br/> |**Port** <br/> |**TTL** <br/> |
|SRV (Service)  <br/> |@  <br/> (@ が許可されていない場合は、空白のままにします)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hour  <br/> |
|SRV (Service)  <br/> |@  <br/> (@ が許可されていない場合は、空白のままにします)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 時間  <br/> |
   
  > [!NOTE]
  >  **Name** の場合: これを **@** に設定することが DNS ホストで許可されていない場合、空白のままにします。 この方法は、Service 値のフィールドと Protocol 値のフィールドが DNS ホストに個別に用意されている場合に *のみ* 使用します。 それ以外の場合は、下の Service と Protocol に関する注を参照してください。 

>  **Service** と **Protocol** の場合: DNS ホストの SRV レコードにこれらのフィールドが提供されていない場合は、**Service** 値と **Protocol** 値をレコードの **Name** 値として指定する必要があります。 (注: DNS ホストによっては、**Name** フィールドが **Host**、**Hostname**、**Subdomain** など、他の名称になっている場合があります)。結合された値を設定するには、値をドットで区切って単一の文字列を作成します。  例: **Name**: _sip._tls 

>  **Priority**、**Weight**、**Port** の場合: DNS ホストの SRV レコードにこれらのフィールドが提供されていない場合は、これらをレコードの **Target** 値として指定する必要があります。 (注: DNS ホストによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。結合された値を設定するには、値をスペースで区切り、末尾にドットを付けて単一の文字列を作成します。 値は、Priority、Weight、Port、Target の順で含める必要があります。 例: **Target**: 100 1 443 sipdir.online.lync.com. 

>  **Priority**、**Weight**、**Port** のバリエーション: 一部の DNS ホストでは、これらの必須フィールドすべてではないものの、その一部が個別に提供されています。 このような DNS ホスト サイトでは、個別に表示されない値を、レコードの **Target** 値の結合文字列として正しい順序で指定します。 (注: DNS ホストによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。結合された値を設定するには、値をスペースで区切って、個別に表示されないフィールド用の単一の文字列を作成します。 値は、Priority、Weight、Port、Target の *順序通りに* 含める必要があります。ただし、個別のフィールドが用意されている値は除外します。 たとえば、Priority のフィールドが個別に用意されている場合は、Weight、Port、Target の値のみを次のように連結します。**Target**: 1 443 sipdir.online.lync.com 

> **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 
  
2. 終了したら、レコードを保存します。
    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
::: moniker-end


::: moniker range="o365-germany"

DNS ホストの Web サイトで、2 つの新しい SRV レコードを、一般的には 1 つずつ作成します。 つまり、Web サイトで 1 つ目の SRV レコードを追加してから、別の SRV レコードの作成を選びます。
  
1. 新規レコードごとのボックスに次の値を入力するか、コピーして貼り付けます。 **(DNS ホストでこれらの値が個別のフィールドとして用意されていない場合の SRV の作成については、下の注を参照してください。)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Name** <br/> |**Target** <br/> |**Protocol** <br/> |**Service** <br/> |**Priority** <br/> |**Weight** <br/> |**Port** <br/> |**TTL** <br/> |
|SRV (Service)  <br/> |@  <br/> (@ が許可されていない場合は、空白のままにします)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hour  <br/> |
|SRV (Service)  <br/> |@  <br/> (@ が許可されていない場合は、空白のままにします)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 時間  <br/> |
   
 > [!NOTE]
 >  **Name** の場合: これを **@** に設定することが DNS ホストで許可されていない場合、空白のままにします。 この方法は、Service 値のフィールドと Protocol 値のフィールドが DNS ホストに個別に用意されている場合に *のみ* 使用します。 それ以外の場合は、下の Service と Protocol に関する注を参照してください。 

>  **Service** と **Protocol** の場合: DNS ホストの SRV レコードにこれらのフィールドが提供されていない場合は、**Service** 値と **Protocol** 値をレコードの **Name** 値として指定する必要があります。 (注: DNS ホストによっては、**Name** フィールドが **Host**、**Hostname**、**Subdomain** など、他の名称になっている場合があります)。結合された値を設定するには、値をドットで区切って単一の文字列を作成します。 >  例: **Name**: _sip._tls 

>  **Priority**、**Weight**、**Port** の場合: DNS ホストの SRV レコードにこれらのフィールドが提供されていない場合は、これらをレコードの **Target** 値として指定する必要があります。 (注: DNS ホストによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。結合された値を設定するには、値をスペースで区切り、末尾にドットを付けて単一の文字列を作成します。 値は、Priority、Weight、Port、Target の順で含める必要があります。 >  例: **Target**: 100 1 443 sipdir.online.lync.de. 

>  **Priority**、**Weight**、**Port** のバリエーション: 一部の DNS ホストでは、これらの必須フィールドすべてではないものの、その一部が個別に提供されています。 このような DNS ホスト サイトでは、個別に表示されない値を、レコードの **Target** 値の結合文字列として正しい順序で指定します。 (注: DNS ホストによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。結合された値を設定するには、値をスペースで区切って、個別に表示されないフィールド用の単一の文字列を作成します。 値は、Priority、Weight、Port、Target の *順序通りに* 含める必要があります。ただし、個別のフィールドが用意されている値は除外します。 >  たとえば、Priority のフィールドが個別に用意されている場合は、Weight、Port、Target の値のみを次のように連結します。**Target**: 1 443 sipdir.online.lync.de 

>  **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 
  
2. 終了したら、レコードを保存します。
    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
::: moniker-end


::: moniker range="o365-21vianet"

DNS ホストの Web サイトで、2 つの新しい SRV レコードを、一般的には 1 つずつ作成します。 つまり、Web サイトで 1 つ目の SRV レコードを追加してから、別の SRV レコードの作成を選びます。
  
1. 新規レコードごとのボックスに次の値を入力するか、コピーして貼り付けます。 **(DNS ホストでこれらの値が個別のフィールドとして用意されていない場合の SRV の作成については、下の注を参照してください。)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Name** <br/> |**Target** <br/> |**Protocol** <br/> |**Service** <br/> |**Priority** <br/> |**Weight** <br/> |**Port** <br/> |**TTL** <br/> |
|SRV (Service)  <br/> |@  <br/> (@ が許可されていない場合は、空白のままにします)  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hour  <br/> |
|SRV (Service)  <br/> |@  <br/> (@ が許可されていない場合は、空白のままにします)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 時間  <br/> |
   
 > [!NOTE]
 >  **Name** の場合: これを **@** に設定することが DNS ホストで許可されていない場合、空白のままにします。 この方法は、Service 値のフィールドと Protocol 値のフィールドが DNS ホストに個別に用意されている場合に *のみ* 使用します。 それ以外の場合は、下の Service と Protocol に関する注を参照してください。 

>  **Service** と **Protocol** の場合: DNS ホストの SRV レコードにこれらのフィールドが提供されていない場合は、**Service** 値と **Protocol** 値をレコードの **Name** 値として指定する必要があります。 (注: DNS ホストによっては、**Name** フィールドが **Host**、**Hostname**、**Subdomain** など、他の名称になっている場合があります)。結合された値を設定するには、値をドットで区切って単一の文字列を作成します。 >  例: **Name**: _sip._tls 

>  **Priority**、**Weight**、**Port** の場合: DNS ホストの SRV レコードにこれらのフィールドが提供されていない場合は、これらをレコードの **Target** 値として指定する必要があります。 (注: DNS ホストによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。結合された値を設定するには、値をスペースで区切り、末尾にドットを付けて単一の文字列を作成します。 値は、Priority、Weight、Port、Target の順で含める必要があります。 >  例: **Target**: 100 1 443 sipdir.online.partner.lync.cn. 

>  **Priority**、**Weight**、**Port** のバリエーション: 一部の DNS ホストでは、これらの必須フィールドすべてではないものの、その一部が個別に提供されています。 このような DNS ホスト サイトでは、個別に表示されない値を、レコードの **Target** 値の結合文字列として正しい順序で指定します。 (注: DNS ホストによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。結合された値を設定するには、値をスペースで区切って、個別に表示されないフィールド用の単一の文字列を作成します。 値は、Priority、Weight、Port、Target の *順序通りに* 含める必要があります。ただし、個別のフィールドが用意されている値は除外します。 >  たとえば、Priority のフィールドが個別に用意されている場合は、Weight、Port、Target の値のみを次のように連結します。**Target**: 1 443 sipdir.online.partner.lync.cn 

>  **TTL** の場合: この値は、**1 時間**または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 
  
2. 終了したら、レコードを保存します。
    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>DNS レコードの更新について
<a name="BKMK_MoreAbout"> </a>

 **ドメインの DNS ホストで DNS レコードを更新する方法がわかっている場合は**、Microsoft 365 の DNS 値を使ってドメインの DNS ホストでレコードを編集し、MX レコードや SPF レコードのセットアップなどを行います。[こちらで説明する手順に従って](../get-help-with-domains/information-for-dns-records.md)、使用する特定の値を探すか、ドメイン セットアップ ウィザードの実行中に特定の値を確認してください。
  
 **必要な DNS レコードの追加方法がわからない場合は**、[「ドメインを設定する (ホストに固有の手順)」](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide)を参照して、まず [Microsoft 365 の DNS レコードの作成に必要な情報を収集します](../get-help-with-domains/information-for-dns-records.md)。 次に、このトピックの一般的な手順に従ってドメインの DNS レコードをセットアップして、メールなど、Microsoft 365 サービスでドメインを使用できるようにします。
  
 **カスタム ドメインで使用する Web サイトがない場合は**、セットアップをすべて自分で行う代わりに、Microsoft 365 でドメインの DNS レコードをセットアップして管理できます。Microsoft 365 で [カスタム ドメインの DNS レコードをセットアップして管理する 2 つのオプションについては、こちらを参照してください](https://support.office.com/article/5980474a-097f-4f21-a864-21245314957f.aspx)。 
  

