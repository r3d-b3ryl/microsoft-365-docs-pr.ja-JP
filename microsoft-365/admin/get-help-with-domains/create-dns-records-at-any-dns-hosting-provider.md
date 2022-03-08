---
title: DNS レコードを追加して自分のドメインを接続する
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: ドメインを確認して、レジストラーのアカウントの DNS レコードを更新することで、任意の DNS ホスティング プロバイダーでドメインを Microsoft 365 に接続します。
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
- admindeeplinkMAC
ms.openlocfilehash: 17a3a63dfb3faedb5ff213b24dd14abd57f55bb3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316927"
---
# <a name="add-dns-records-to-connect-your-domain"></a>DNS レコードを追加して自分のドメインを接続する

サードパーティのホスティング プロバイダーからドメインを購入した場合は、レジストラーのアカウントの DNS レコードを更新することで、それを Microsoft 365 に接続できます。

これらの手順を完了すると、お客様のドメインは、ドメインを購入したホストには登録されたままとなりますが、Microsoft 365 では、メール アドレス (user@yourdomain.com など) やその他のサービスで使用できます。

ドメインを追加しない場合、組織内のユーザーは、メール アドレスに onmicrosoft.com ドメインを使用します。 ユーザーを追加する前にドメインを追加することが重要です。それにより、ユーザーを再度セットアップする必要がなくなります。

探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.yml) を確認してください。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>手順 1: TXT または MX レコードを追加してドメインの所有を確認する 

### <a name="recommended-verify-with-a-txt-record"></a>推奨: TXT レコードで確認する

まず、Microsoft 365 に追加するドメインを所有していることを証明する必要があります。

1. Microsoft 365 管理センター にサインインし **[すべて表示]** > **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**[ドメイン]**</a>を選択します。
2. 新しいブラウザー タブまたはウィンドウで、使用している DNS ホスティング プロバイダーにサインインし、DNS 設定を管理している場所を検索します (例: ゾーン ファイルの設定、ドメインの管理、ドメイン マネージャー、DNS マネージャー)。
3. プロバイダーの DNS マネージャーのページに移動し、管理センターで示された TXT レコードをドメインに追加します。

   このレコードを追加しても、既存のメールやその他のサービスには影響はありません。このレコードは、お客様のドメインが Microsoft 365 に接続された後、安全に削除することができます。

   例:

   - TXT 名: `@`
   - TXT 値: MS=ms######## (管理センターの固有 ID)
   - TTL: `3600` (またはプロバイダーの既定値)

4. レコードを保存し、管理センターに戻り、[**確認**] を選択します。 レコードの変更には通常 15 分ほどかかりますが、登録には時間がかかる場合があります。 少し時間をかけて、変更内容が反映されるように何度か試してください。

Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

### <a name="verify-with-an-mx-record"></a>MX レコードで確認する

レジストラーが TXT レコードの追加をサポートしていない場合は、MX レコードを追加することで確認できます。

1. Microsoft 365 管理センター にサインインし **[すべて表示]** > **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**[ドメイン]**</a>を選択します。
2. 新しいブラウザー タブまたはウィンドウで、使用している DNS ホスティング プロバイダーにサインインし、DNS 設定を管理している場所を検索します (例: ゾーン ファイルの設定、ドメインの管理、ドメイン マネージャー、DNS マネージャー)。
3. プロバイダーの DNS マネージャーのページに移動し、管理センターで示された MX レコードをドメインに追加します。

この MX レコードの **優先度** は、ドメインのすべての既存の MX レコードで最高でなくてはなりません。 それ以外の場合、メールの送受信が妨げられます。 ドメイン確認が完了したら、すぐにこのレコードを削除する必要があります。

フィールドが次の値に設定されていることを確認します。

- Record Type: `MX`
- 優先度: まだ使用されていない大きな値に設定します。
- Host Name: `@`
- Points to address: 管理センターから値をコピーし、ここに貼り付けます。
- TTL: `3600` (またはプロバイダーの既定値)

Microsoft で正しい MX レコードが見つかった場合、ドメインは確認済みとなります。

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>手順 2: DNS レコードを追加して Microsoft サービスに接続する

新しいブラウザー タブまたはウィンドウで、使用している DNS ホスティング プロバイダーにサインインし、DNS 設定を管理している場所を検索します (例: ゾーン ファイルの設定、ドメインの管理、ドメイン マネージャー、DNS マネージャー)。

有効にするサービスに応じて、いくつかの異なる種類の DNS レコードを追加します。

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>メール用の MX レコードを追加する (Outlook、Exchange Online)

**開始する前に:** ユーザーがお客様のドメインのメールを既に所有している場合は (user@yourdomain.com など)、MX レコードをセットアップする前に管理センターでアカウントを作成します。 こうすることで、引き続きメールを受信できます。 ドメインの MX レコードを更新すると、お客様のドメインを使用するユーザーのすべての新しいメールが、Microsoft 365 に届くようになります。 [メールと連絡先を Microsoft 365 に移行すること](../setup/migrate-email-and-contacts-admin.md)を決定しない限り、既に所有しているメールは現在のメール ホストに保持されます。

MX レコードの情報は、管理センターのドメイン セットアップ ウィザードから取得されます。

ホスティング プロバイダーの Web サイトで、新しい MX レコードを追加します。
フィールドが次の値に設定されていることを確認します。

- Record Type: `MX`
- Priority: 使用可能な最高の値を設定します。通常は `0` です。
- Host Name: `@`
- Points to address: 管理センターから値をコピーし、ここに貼り付けます。
- TTL: `3600` (またはプロバイダーの既定値)

レコードを保存して、他の MX レコードを削除します。

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>CNAME レコードを追加して他のサービスに接続する (Teams、Exchange Online、AAD、MDM)

CNAME レコードの情報は、管理センターのドメイン セットアップ ウィザードから取得されます。

ホスティング プロバイダーの Web サイトで、接続するサービスごとに CNAME レコードを追加します。
フィールドが次の値に設定されていることを確認します。

- Record Type: `CNAME (Alias)`
- Host: 管理センターからコピーした値をここに貼り付けます。
- Points to address: 管理センターから値をコピーし、ここに貼り付けます。
- TTL: `3600` (またはプロバイダーの既定値)

### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>SPF TXT レコードを追加または編集して迷惑メールの防止に役立てる (Outlook、Exchange Online) 

**開始する前に:** 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、ホスティング プロバイダーの Web サイトの現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが *1 つ* の SPF レコードに含まれるようにします。

ホスティング プロバイダーの Web サイトで、既存の SPF レコードを編集するか、SPF レコードを作成します。
フィールドが次の値に設定されていることを確認します。

- Record Type: `TXT (Text)`
- Host: `@`
- TXT Value: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600` (またはプロバイダーの既定値)

レコードを保存します。

SPF レコードを検証するには、[SPF 検証ツール](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)のいずれかを使用します。

SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング方法があります。それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Microsoft 365 用に構成する必要もあります。

使用を開始する場合は、「[DKIM を使用して、Microsoft 365 のドメインから送信される送信電子メールを検証する](../../security/office-365-security/use-dkim-to-validate-outbound-email.md)」、「[DMARC を使用して Microsoft 365 のメールを検証する](../../security/office-365-security/use-dmarc-to-validate-email.md)」を参照してください。

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>コミュニケーション サービス用の SRV レコードを追加する (Teams、Skype for Business) 

ホスティング プロバイダーの Web サイトで、接続するサービスごとに SRV レコードを追加します。
フィールドが次の値に設定されていることを確認します。

- Record Type: `SRV (Service)`
- 名前: `@`
- Target: 管理センターから値をコピーし、ここに貼り付けます。
- Protocol: 管理センターから値をコピーし、ここに貼り付けます。
- Service: 管理センターから値をコピーし、ここに貼り付けます。
- 優先度: `100`
- Weight: `1`
- Port: 管理センターから値をコピーし、ここに貼り付けます。
- TTL: `3600` (またはプロバイダーの既定値)

レコードを保存します。

#### <a name="srv-record-field-restrictions-and-workarounds"></a>SRV レコードのフィールドの制限と回避策

一部のホスティング プロバイダーは、SRV レコード内のフィールド値を制限します。 これらの制限の一般的な回避策をいくつか紹介します。

##### <a name="name"></a>名前

ホスティング プロバイダーが、このフィールドに **@** の設定を許可しない場合は、空白のままにします。 この方法は、ホスティング プロバイダーが Service 値と Protocol 値のフィールドを個別に用意している場合に *のみ* 使用します。 それ以外の場合は、下の Service と Protocol に関する注を参照してください。

##### <a name="service-and-protocol"></a>Service と Protocol

ホスティング プロバイダーが SRV レコードにこれらのフィールドを用意していない場合は、**Service** 値と **Protocol** 値をレコードの **Name** フィールドに指定する必要があります。 (注: ホスティング プロバイダーによっては、**Name** フィールドが **Host**、**Hostname**、**Subdomain** など、他の名称になっている場合があります)。これらの値を追加するには、値をドットで区切って単一の文字列を作成します。

例: `_sip._tls`

##### <a name="priority-weight-and-port"></a>Priority、Weight、Port

ホスティング プロバイダーが SRV レコードにこれらのフィールドを用意していない場合は、レコードの **Target** フィールドにそれらの値を指定する必要があります。 (注: ホスティング プロバイダーによっては、**Target** フィールドが **Content**、**IP Address**、**Target Host** など、他の名称になっている場合があります)。

これらの値を追加するには、1 つの文字列を作成し、値をスペースで区切り、*場合によってはをドットで終えます* (不明な場合はプロバイダーに問い合わせてください)。値は、Priority、Weight、Port、Target の順に含まれている必要があります。

- 例 1: `100 1 443 sipdir.online.lync.com.`
- 例 2: `100 1 443 sipdir.online.lync.com`

## <a name="related-content"></a>関連コンテンツ

[任意のドメイン レジストラーで Microsoft 365 をセットアップするためにネームサーバーを変更する](change-nameservers-at-any-domain-registrar.md) (記事)\
[ドメインまたは DNS レコードを追加後に問題を特定して解決する](find-and-fix-issues.md) (記事)\
[ドメインの管理](/admin) (リンク ページ)
