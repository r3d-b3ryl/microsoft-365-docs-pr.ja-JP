---
title: DAP パートナーのWindows PowerShellを使用してクライアント テナントにドメインを追加する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: '概要: PowerShell for Microsoft 365を使用して、既存の顧客テナントに代替ドメイン名を追加します。'
ms.openlocfilehash: c4dcdb34f9065009ccaa77d23222601506b537b5
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099040"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>委任アクセス許可 (DAP) パートナー用 Windows PowerShell でクライアント テナンシーにドメインを追加する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

新しいドメインを作成し、お客様のテナントと PowerShell に関連付けて、Microsoft 365 管理センターを使用するよりも迅速にMicrosoft 365できます。

委任アクセス許可 (DAP) パートナー とは、シンジケート パートナーとクラウド ソリューション プロバイダー (CSP) パートナーです。 他の会社のネットワーク プロバイダーまたは通信プロバイダーであることもよくあります。 Microsoft 365サブスクリプションを顧客に対するサービス オファリングにバンドルします。 Microsoft 365 サブスクリプションを販売すると、顧客テナンシーを管理およびレポートできるように、顧客テナンシーに対する代理管理 (AOBO) アクセス許可が自動的に付与されます。
## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

このトピックの手順では、[PowerShell を使用してMicrosoft 365にConnectに接続する](connect-to-microsoft-365-powershell.md)必要があります。

また、パートナーのテナント管理者の資格情報も必要です。

また、以下の情報も必要になります。

- 顧客が望む完全修飾ドメイン名 (FQDN) が必要です。

- 顧客の **テナント ID** も必要です。

- FQDN は、GoDaddy などのインターネット ドメイン名サービス (DNS) 登録業者に登録されている必要があります。公的にドメイン名を登録する方法について詳しくは、「[ドメイン名の購入方法](../admin/get-help-with-domains/buy-a-domain-name.md)」をご覧ください。

- DNS 登録業者の登録済み DNS ゾーンに TXT レコードを追加する方法を理解する必要があります。 TXT レコードを追加する方法の詳細については、「 [DNS レコードを追加してドメインを接続する」を参照してください](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 これらの手順がうまくいかない場合は、使っている DNS 登録業者用の手順を検索する必要があります。

## <a name="create-domains"></a>ドメインを作成する

 顧客から、既定の\<domain>.onmicrosoft.comドメインを世界に対して自企業を表す主ドメインにしたくないため、追加のドメインを作成して顧客のテナンシーに関連付けるよう依頼される可能性があります。この手順では、ドメインを新規作成して顧客のテナンシーに関連付ける方法を順を追って説明します。

> [!NOTE]
> これらの操作の一部を実行するには、サインインするパートナー管理者アカウントを、Microsoft 365 管理センターの **管理者** アカウントの詳細にある [**サポートする会社に管理アクセスを割り当てる**] 設定の [完全管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">] に</a>設定する必要があります。 パートナー管理者ロールの管理の詳細については、「 [パートナー: 委任された管理を提供する」](https://go.microsoft.com/fwlink/p/?LinkId=532435)を参照してください。

### <a name="create-the-domain-in-azure-active-directory"></a>Azure Active Directory でドメインを作成する

このコマンドは、Azure Active Directory にドメインを作成しますが、公的に登録されたドメインとは関連付けられません。 これは、企業向けの Microsoft Microsoft 365に対してパブリックに登録されたドメインを所有していることを証明するときに発生します。

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>DNS の TXT 検証レコードのデータを取得する

 Microsoft 365は、DNS TXT 検証レコードに配置する必要がある特定のデータを生成します。 データを取得するには、次のコマンドを実行します。

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

これにより、次のような出力が得られます。

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> 公的に登録された DNS ゾーンに TXT レコードを作成するには、このテキストが必要です。 必ずコピーし、保存してください。

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>公的に登録された DNS ゾーンに TXT レコードを追加する

Microsoft 365が、パブリックに登録されたドメイン名に送信されるトラフィックの受け入れを開始する前に、自分が所有し、ドメインに対する管理者権限を持っていることを証明する必要があります。 ドメインを保有していることを証明するには、ドメインに TXT レコードを作成します。 TXT レコードは、ドメインでは何も行わず、ドメインの所有権が確立した後に削除することができます。 TXT レコードを作成するには、「DNS レコードの追加」の手順に従って [ドメインを接続します](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 これらの手順がうまくいかない場合は、使っている DNS 登録業者用の手順を検索する必要があります。

TXT レコードが正常に作成されたことを、nslookup 経由で確認します。次の構文に従います。

```console
nslookup -type=TXT <FQDN of registered domain>
```

これにより、次のような出力が得られます。

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a>Microsoft 365でのドメイン所有権の検証

この最後の手順では、パブリックに登録されたドメインを所有していることをMicrosoft 365することを検証します。 この手順の後、Microsoft 365は新しいドメイン名にルーティングされたトラフィックの受け入れを開始します。 ドメインの作成と登録のプロセスを完了するには、次のコマンドを実行します。

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

このコマンドは出力を返しません。そのため、機能したことを確認するために、次のコマンドを実行します。

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

コマンドを実行すると、次のようなものが返されます。

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a>関連項目

[パートナーのヘルプ](https://go.microsoft.com/fwlink/p/?LinkID=533477)
