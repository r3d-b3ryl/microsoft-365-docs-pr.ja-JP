---
title: Microsoft の eNomCentral で DNS レコードを作成する
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: eNomCentral for Microsoft のドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 528659667ee062c8cf767bed0989558020032924
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910368"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>Microsoft の eNomCentral で DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。

使用している DNS ホスティング プロバイダーが eNomCentral の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。

eNomCentral でこれらのレコードを追加すると、ドメインが Microsoft サービスで動作するために設定されます。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

次の手順を実行するか、[ビデオ (46 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。

1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. [ **自分のドメイン]** で、編集するドメインの名前を選択します。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   ドロップダウン リスト **から [レコード** の種類] の値を選択します。

   |ホスト名|Record Type|Address|
   |---|---|---|
   |@|TXT|MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. [保存 **] を選択します**。

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。

Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

2. **[ドメイン]** ページで、確認するドメインを選択します。

3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。

4. **[ドメインの確認]** ページで、**[確認]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

次の手順を実行するか、[ビデオ (3 分 40 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。

1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. [ **自分のドメイン]** で、編集するドメインの名前を選択します。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. [ **Manage Domain**] ボックスの一覧で、[ **Email Settings**] を選びます。

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. [ **Service Selection**] ボックスで、[ **User (MX)**] を選びます。

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. In the boxes for the new record, type or copy and paste the values from the following table.

   |ホスト名|Address|Pref|
   |---|---|---|
   |@| *\<domain-key\>*  .mail.protection.outlook.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|10    <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. [保存 **] を選択します**。

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. 他の既存の MX レコードがある場合は、そのレコードのチェック ボックスをオンにして選びます。

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. [削除 **] チェック ボックスをオンにします**。

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

次の手順を実行するか、[ビデオ (4 分 24 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。

1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. [ **自分のドメイン]** で、編集するドメインの名前を選択します。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 新しい **行を選択します**。

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. 6 つの新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。

   ドロップダウン リスト **から [レコード** の種類] の値を選択します。

   |ホスト名|Record Type|Address|
   |---|---|---|
   |autodiscover|CNAME (Alias)|autodiscover.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|
   |sip|CNAME (Alias)|sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません**|
   |lyncdiscover|CNAME (Alias)|webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|
   |enterpriseregistration|CNAME (Alias)|enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|
   |enterpriseenrollment|CNAME (Alias)|enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません**|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. [保存 **] を選択します**。

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。

次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。

1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. [ **自分のドメイン]** で、編集するドメインの名前を選択します。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   ドロップダウン リスト **から [レコード** の種類] の値を選択します。

   |ホスト名|Record Type|Address|
   |---|---|---|
   |@|TXT|v=spf1 include:spf.protection.outlook.com -all  <br/>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. [保存 **] を選択します**。

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

次の手順を実行するか、[ビデオ (5 分 50 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。

1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. [ **自分のドメイン]** で、編集するドメインの名前を選択します。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 新しい行の右側 **にある [SRV** または **SPF レコードの追加] を選択します**。

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. 2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

   |サービス|プロトコル|Priority|太さ|ポート|ターゲット (ホスト名)|
   |---|---|---|---|---|---|
   |_sip|_tls|100|1|443|sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません**|
   |_sipfederationtls|_tcp|100|1|5061|sipfed.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません**|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. [保存] **を選択する**

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。