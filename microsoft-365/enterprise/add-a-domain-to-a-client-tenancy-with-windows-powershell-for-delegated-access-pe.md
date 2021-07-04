---
title: DAP パートナー用にドメインをクライアント テナントにWindows PowerShellする
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: '概要: PowerShell を使用Microsoft 365既存の顧客テナントに別のドメイン名を追加します。'
ms.openlocfilehash: 5ebbe11da9a93669945e7e3b096ce7afa18b5d3a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288433"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="7150a-103">委任アクセス許可 (DAP) パートナー用 Windows PowerShell でクライアント テナンシーにドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="7150a-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="7150a-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7150a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7150a-105">新しいドメインを作成し、顧客のテナントと PowerShell を関連付け、Microsoft 365を使用するよりもMicrosoft 365 管理センター。</span><span class="sxs-lookup"><span data-stu-id="7150a-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>

<span data-ttu-id="7150a-106">委任アクセス許可 (DAP) パートナー とは、シンジケート パートナーとクラウド ソリューション プロバイダー (CSP) パートナーです。</span><span class="sxs-lookup"><span data-stu-id="7150a-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="7150a-107">他の会社のネットワーク プロバイダーまたは通信プロバイダーであることもよくあります。</span><span class="sxs-lookup"><span data-stu-id="7150a-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="7150a-108">ユーザーは、Microsoft 365サービスサービスにサブスクリプションをバンドルします。</span><span class="sxs-lookup"><span data-stu-id="7150a-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="7150a-109">Microsoft 365 サブスクリプションを販売すると、顧客テナンシーに対する管理 (AOBO) アクセス許可が自動的に付与され、顧客テナンシーの管理と報告が可能になります。</span><span class="sxs-lookup"><span data-stu-id="7150a-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7150a-110">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7150a-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="7150a-111">このトピックの手順では、PowerShell を使用してConnect[にMicrosoft 365する必要があります](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="7150a-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="7150a-112">また、パートナーのテナント管理者の資格情報も必要です。</span><span class="sxs-lookup"><span data-stu-id="7150a-112">You also need your partner tenant administrator credentials.</span></span>

<span data-ttu-id="7150a-113">また、以下の情報も必要になります。</span><span class="sxs-lookup"><span data-stu-id="7150a-113">You also need the following information:</span></span>

- <span data-ttu-id="7150a-114">顧客が望む完全修飾ドメイン名 (FQDN) が必要です。</span><span class="sxs-lookup"><span data-stu-id="7150a-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>

- <span data-ttu-id="7150a-115">顧客の **テナント ID** も必要です。</span><span class="sxs-lookup"><span data-stu-id="7150a-115">You need the customer's **TenantId**.</span></span>

- <span data-ttu-id="7150a-p102">FQDN は、GoDaddy などのインターネット ドメイン名サービス (DNS) 登録業者に登録されている必要があります。公的にドメイン名を登録する方法について詳しくは、「[ドメイン名の購入方法](../admin/get-help-with-domains/buy-a-domain-name.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7150a-p102">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy. For more information on how to publically register a domain name, see [How to buy a domain name](../admin/get-help-with-domains/buy-a-domain-name.md).</span></span>

- <span data-ttu-id="7150a-118">DNS 登録業者の登録済み DNS ゾーンに TXT レコードを追加する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7150a-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="7150a-119">TXT レコードを追加する方法の詳細については、「ドメインに接続するための [DNS レコードの追加」を参照してください](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="7150a-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="7150a-120">これらの手順がうまくいかない場合は、使っている DNS 登録業者用の手順を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7150a-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>

## <a name="create-domains"></a><span data-ttu-id="7150a-121">ドメインを作成する</span><span class="sxs-lookup"><span data-stu-id="7150a-121">Create domains</span></span>

 <span data-ttu-id="7150a-p104">顧客から、既定の<domain>.onmicrosoft.comドメインを世界に対して自企業を表す主ドメインにしたくないため、追加のドメインを作成して顧客のテナンシーに関連付けるよう依頼される可能性があります。この手順では、ドメインを新規作成して顧客のテナンシーに関連付ける方法を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="7150a-p104">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world. This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>

> [!NOTE]
> <span data-ttu-id="7150a-124">これらの操作の一部を実行するには、Microsoft 365 管理センター の管理アカウントの詳細にある [サポートする企業への管理アクセスの割り当て] 設定で、サインインするパートナー管理者アカウントを [完全な管理] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7150a-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7150a-125">パートナー管理者の役割の管理の詳細については、「パートナー: 委任された管理を提供 [する」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=532435)。</span><span class="sxs-lookup"><span data-stu-id="7150a-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span>

### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="7150a-126">Azure Active Directory でドメインを作成する</span><span class="sxs-lookup"><span data-stu-id="7150a-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="7150a-127">このコマンドは、Azure Active Directory にドメインを作成しますが、公的に登録されたドメインとは関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="7150a-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="7150a-128">これは、一般に登録されたドメインを企業向け Microsoft Microsoft 365証明するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7150a-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> <span data-ttu-id="7150a-129">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7150a-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="7150a-130">これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7150a-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="7150a-131">DNS の TXT 検証レコードのデータを取得する</span><span class="sxs-lookup"><span data-stu-id="7150a-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="7150a-132">Microsoft 365 DNS TXT 検証レコードに配置する必要がある特定のデータが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7150a-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="7150a-133">データを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7150a-133">To get the data, run this command.</span></span>

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="7150a-134">これにより、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="7150a-134">This will give you output like:</span></span>

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> <span data-ttu-id="7150a-135">公的に登録された DNS ゾーンに TXT レコードを作成するには、このテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="7150a-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="7150a-136">必ずコピーし、保存してください。</span><span class="sxs-lookup"><span data-stu-id="7150a-136">Be sure to copy and save it.</span></span>

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="7150a-137">公的に登録された DNS ゾーンに TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="7150a-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="7150a-138">一Microsoft 365登録されたドメイン名に送信されるトラフィックの受け入れを開始する前に、自分が所有し、そのドメインに対する管理者権限を持っていることを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7150a-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="7150a-139">ドメインを保有していることを証明するには、ドメインに TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="7150a-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="7150a-140">TXT レコードは、ドメインでは何も行わず、ドメインの所有権が確立した後に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="7150a-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="7150a-141">TXT レコードを作成するには、「DNS レコードの追加」の手順に [従ってドメインを接続します](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="7150a-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="7150a-142">これらの手順がうまくいかない場合は、使っている DNS 登録業者用の手順を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7150a-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>

<span data-ttu-id="7150a-p111">TXT レコードが正常に作成されたことを、nslookup 経由で確認します。次の構文に従います。</span><span class="sxs-lookup"><span data-stu-id="7150a-p111">Confirm the successful creation of the TXT record via nslookup. Follow this syntax.</span></span>

```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="7150a-145">これにより、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="7150a-145">This will give you output like:</span></span>

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="7150a-146">ドメインの所有権を検証Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7150a-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="7150a-147">この最後の手順では、一般にMicrosoft 365ドメインを所有しているユーザーを検証します。</span><span class="sxs-lookup"><span data-stu-id="7150a-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="7150a-148">この手順の後Microsoft 365新しいドメイン名にルーティングされたトラフィックの受け入れが開始されます。</span><span class="sxs-lookup"><span data-stu-id="7150a-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="7150a-149">ドメインの作成と登録のプロセスを完了するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7150a-149">To complete the domain creation and registration process, run this command.</span></span>

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="7150a-150">このコマンドは出力を返しません。そのため、機能したことを確認するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7150a-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="7150a-151">コマンドを実行すると、次のようなものが返されます。</span><span class="sxs-lookup"><span data-stu-id="7150a-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a><span data-ttu-id="7150a-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="7150a-152">See also</span></span>

[<span data-ttu-id="7150a-153">パートナーのヘルプ</span><span class="sxs-lookup"><span data-stu-id="7150a-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)
