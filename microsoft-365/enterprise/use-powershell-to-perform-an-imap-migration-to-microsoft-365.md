---
title: Microsoft 365 への IMAP 移行に PowerShell を使用する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: PowerShell を使用してインターネット メール アクセス プロトコル (IMAP) の移行を実行する方法についてMicrosoft 365。
ms.openlocfilehash: 679cf222d7474349907d1c21f38a30b5fd86f798
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229637"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="c4fac-103">Microsoft 365 への IMAP 移行に PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="c4fac-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="c4fac-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="c4fac-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c4fac-105">Microsoft 365 を展開するプロセスの一環として、ユーザー メールボックスの内容をインターネット メール アクセス プロトコル (IMAP) メール サービスから Microsoft 365 に移行できます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="c4fac-106">この記事では、Exchange Online PowerShell を使用した電子メールの IMAP 移行作業を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="c4fac-107">また、IMAP 移行を実行するには、Exchange 管理センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="c4fac-108">「IMAP [メールボックスの移行」を参照してください](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="c4fac-108">See [Migrate your IMAP mailboxes](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c4fac-109">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c4fac-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="c4fac-110">このタスクの予想所要時間:移行バッチの作成に 2 ～ 5 分。</span><span class="sxs-lookup"><span data-stu-id="c4fac-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="c4fac-111">移行バッチ開始後の移行時間は、バッチ内のメールボックスの数、各メールボックスのサイズ、および使用可能なネットワーク容量によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c4fac-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="c4fac-112">メールボックスを移行する時間に影響を与えるその他の要因については、「移行パフォーマンス」をMicrosoft 365[を参照してください](/Exchange/mailbox-migration/office-365-migration-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="c4fac-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="c4fac-p104">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、トピック「[受信者のアクセス許可](/exchange/recipients-permissions-exchange-2013-help)」内の表にある「移行」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="c4fac-p105">Exchange Online PowerShell コマンドレットを使用するには、サインインしてコマンドレットをローカルの Windows PowerShell セッションにインポートする必要があります。手順については、「[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="c4fac-117">移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-117">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="c4fac-118">IMAP の移行には次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-118">The following restrictions apply to IMAP migrations:</span></span>

- <span data-ttu-id="c4fac-p106">ユーザーの受信トレイまたは他のメール フォルダー内のアイテムのみ、移行できます。連絡先、予定表アイテム、またはタスクを移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p106">Only items in a user's inbox or other mail folders can be migrated. You can't migrate contacts, calendar items, or tasks.</span></span>

- <span data-ttu-id="c4fac-121">最大で 500,000 アイテムをユーザーのメールボックスから移行できます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>

- <span data-ttu-id="c4fac-122">移行できるメッセージの最大サイズは 35 MB です。</span><span class="sxs-lookup"><span data-stu-id="c4fac-122">The maximum message size that can be migrated is 35 MB.</span></span>

## <a name="migration-steps"></a><span data-ttu-id="c4fac-123">移行の手順</span><span class="sxs-lookup"><span data-stu-id="c4fac-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="c4fac-124">ステップ 1:IMAP 移行を準備する</span><span class="sxs-lookup"><span data-stu-id="c4fac-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="c4fac-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="c4fac-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="c4fac-126">**IMAP 組織のドメインがある場合は、そのドメインを組織の受け入Microsoft 365します。**</span><span class="sxs-lookup"><span data-stu-id="c4fac-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="c4fac-127">既に所有しているドメインと同じドメインを Microsoft 365 メールボックスに使用する場合は、まずそのドメインを承認されたドメインとして追加Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c4fac-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="c4fac-128">追加した後で、ユーザーを新しいユーザーにMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c4fac-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="c4fac-129">詳細については、「ドメインを確認[する」を参照してください](../admin/setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="c4fac-129">For more information, see[Verify your domain](../admin/setup/add-domain.md).</span></span>

- <span data-ttu-id="c4fac-130">**各ユーザーをメールボックスにMicrosoft 365に追加します。**</span><span class="sxs-lookup"><span data-stu-id="c4fac-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="c4fac-131">手順については、「ビジネス向け[ユーザーをMicrosoft 365する」を参照してください](../admin/add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="c4fac-131">For instructions, see[Add users to Microsoft 365 for business](../admin/add-users/add-users.md).</span></span>

- <span data-ttu-id="c4fac-p109">**IMAP サーバーの FQDN を取得します**。IMAP 移行エンドポイントを作成するときに、メールボックス データの移行元の IMAP サーバーの完全修飾ドメイン名 (FQDN) (フル コンピューター名ともいう) を指定する必要があります。IMAP クライアントまたは PING コマンドを使用して、インターネット経由での FQDN サーバーとの通信に FQDN を使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p109">**Obtain the FQDN of the IMAP server**. You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint. Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>

- <span data-ttu-id="c4fac-p110">**IMAP 接続を許可するファイアウォールを構成します**。IMAP サーバーをホストする組織のファイアウォールでポートを開く必要があります。そうすることで、移行中 Microsoft データセンターから発信するネットワーク トラフィックが IMAP サーバーをホストする組織に入ることができます。Microsoft データセンターが使用する IP アドレスの一覧については、「[Office 365 の URL と IP アドレスの範囲](./urls-and-ip-address-ranges.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p110">**Configure the firewall to allow IMAP connections**. You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server. For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](./urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="c4fac-p111">**IMAP 組織内のメールボックスにアクセスする管理者アカウントのアクセス許可を割り当てます**。CSV ファイルで管理者の資格情報を使用する場合は、使用するアカウントに、社内メールボックスへのアクセスに必要なアクセス許可が必要になります。ユーザーのメールボックスへのアクセスに必要なアクセス許可は、特定の IMAP サーバーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p111">**Assign the administrator account permissions to access mailboxes in your IMAP organization**. If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes. The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span>

- <span data-ttu-id="c4fac-p112">**Exchange Online PowerShell コマンドレットを使用するには**、サインインしてコマンドレットをローカルの Windows PowerShell セッションにインポートする必要があります。手順については、「[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p112">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

    <span data-ttu-id="c4fac-143">移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-143">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

- <span data-ttu-id="c4fac-p113">**IMAP サーバーに接続できることを確認します**。IMAP サーバーへの接続設定をテストするには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p113">**Verify that you can connect to your IMAP server**. Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>

  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="c4fac-146">**Port** パラメーターの値については、通常、暗号化されていない接続やトランスポート層セキュリティ (TLS) 接続には 143 を使用し、SSL 接続には 993 を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>

### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="c4fac-147">ステップ 2:IMAP 移行バッチ用の CSV ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="c4fac-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="c4fac-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="c4fac-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="c4fac-p114">IMAP 移行バッチでそのメールボックスを移行するユーザーのグループを特定します。CSV ファイルの各行には、IMAP メッセージング システム内のメールボックスに接続するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p114">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch. Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>

<span data-ttu-id="c4fac-151">各ユーザーの必須属性は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4fac-151">Here are the required attributes for each user:</span></span>

- <span data-ttu-id="c4fac-152">**EmailAddress は**、ユーザーのメールボックスのユーザー ID をMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>

- <span data-ttu-id="c4fac-153">**UserName** は、IMAP サーバー上のメールボックスへのアクセスに使用するアカウントのログオン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>

- <span data-ttu-id="c4fac-154">**Password** は、 **UserName** 列のアカウントのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-154">**Password** specifies the password for the account in the **UserName** column.</span></span>

<span data-ttu-id="c4fac-p115">以下に、CSV ファイルの形式の例を示します。この例では、3 人のメールボックスが移行されます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p115">Here's an example of the format for the CSV file. In this example, three mailboxes are migrated:</span></span>

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="c4fac-157">**UserName** 属性については、ユーザー名に加えて、IMAP サーバーのメールボックスへのアクセスに必要なアクセス許可が割り当てられているアカウントの資格情報を使用できます。以下はいくつかの IMAP サーバーで使用されている特定の形式の一部です。</span><span class="sxs-lookup"><span data-stu-id="c4fac-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>

 <span data-ttu-id="c4fac-158">**Microsoft Exchange:**</span><span class="sxs-lookup"><span data-stu-id="c4fac-158">**Microsoft Exchange:**</span></span>

<span data-ttu-id="c4fac-159">Microsoft Exchange の IMAP 実装から電子メールを移行する場合、CSV ファイルでは **UserName** 属性に **Domain/Admin_UserName/User_UserName** という形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="c4fac-160">たとえば、Terry Adams さん、Ann Beebe さん、Paul Cannon さんのメールを Exchange から移行するとします。</span><span class="sxs-lookup"><span data-stu-id="c4fac-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="c4fac-161">メール管理者アカウントがあります。ユーザー名は **mailadmin** で、パスワードは **P \@ ssw0rd です**。</span><span class="sxs-lookup"><span data-stu-id="c4fac-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P\@ssw0rd**.</span></span> <span data-ttu-id="c4fac-162">CSV ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c4fac-162">Here's what your CSV file would look like:</span></span>

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="c4fac-163">**Dovecot:**</span><span class="sxs-lookup"><span data-stu-id="c4fac-163">**Dovecot:**</span></span>

<span data-ttu-id="c4fac-164">Dovecot IMAP サーバーなどの単純認証およびセキュリティ層 (SASL) をサポートする IMAP サーバーの場合は、アスタリスク ( \* ) が構成可能な区切り文字である **形式 User_UserName\*Admin_UserName** を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="c4fac-165">管理者資格情報 **mailadmin** と **P \@ ssw0rd** を使用して、同じユーザーのメールを Dovecot IMAP サーバーから移行するとします。</span><span class="sxs-lookup"><span data-stu-id="c4fac-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P\@ssw0rd**.</span></span> <span data-ttu-id="c4fac-166">この場合、CSV ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c4fac-166">Here's what your CSV file would look like:</span></span>

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="c4fac-167">**Mirapoint:**</span><span class="sxs-lookup"><span data-stu-id="c4fac-167">**Mirapoint:**</span></span>

<span data-ttu-id="c4fac-168">Mirapoint Message Server から電子メールを移行する場合は、管理者資格情報#user **\@ domain#Admin_UserName#** の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-168">If you're migrating email from Mirapoint Message Server, use the format **#user\@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="c4fac-169">管理者資格情報 mailadmin と **P \@ ssw0rd** を使用して **Mirapoint** からメールを移行するには、CSV ファイルは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P\@ssw0rd**, your CSV file would look like this:</span></span>

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="c4fac-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="c4fac-170">**Courier IMAP:**</span></span>

<span data-ttu-id="c4fac-171">Courier IMAP などの一部のソース メール システムでは、メールボックス管理者の資格情報を使用してメールボックスをユーザーに移行Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c4fac-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="c4fac-172">代わりに、仮想共有フォルダーを使用するように移行元の電子メール システムを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="c4fac-173">仮想共有フォルダーを使用すると、移行元の電子メール システムのユーザーのメールボックスにアクセスするためにメールボックスの管理資格情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="c4fac-174">Courier IMAP の仮想共有フォルダーを構成する方法の詳細については、「[共有フォルダー](https://go.microsoft.com/fwlink/p/?LinkId=398870)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>

<span data-ttu-id="c4fac-p120">移行元の電子メール システムで仮想共有フォルダーをセットアップしてからメールボックスを移行するには、オプション属性 **UserRoot** を移行ファイルに含める必要があります。この属性では、移行元電子メール システムの仮想共有フォルダー構造にある各ユーザーのメールボックスの場所を指定します。たとえば、Terry のメールボックスへのパスは /users/terry.adams です。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p120">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file. This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system. For example, the path to Terry's mailbox is /users/terry.adams.</span></span>

<span data-ttu-id="c4fac-178">以下に、 **UserRoot** 属性を含む CSV ファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>

```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="c4fac-179">ステップ 3:IMAP 移行エンドポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="c4fac-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="c4fac-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="c4fac-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="c4fac-181">メールを正常に移行するには、Microsoft 365メール システムに接続して通信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4fac-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="c4fac-182">これを行うには、Microsoft 365エンドポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="c4fac-183">移行エンドポイントは、同時に移行するメールボックスの数、および 24 時間ごとに 1 回行われる増分同期中に同時に同期するメールボックスの数も定義します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="c4fac-184">IMAP 移行用に移行エンドポイントを作成するには、最初に[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)を行います。</span><span class="sxs-lookup"><span data-stu-id="c4fac-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="c4fac-185">移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-185">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="c4fac-186">Exchange Online PowerShell で "IMAPEndpoint" という IMAP 移行エンドポイントを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="c4fac-p122">また、同時移行、増分の同時移行、および使用するポートを指定するパラメーターを追加することもできます。次の Exchange Online PowerShell コマンドは、50 の同時移行と最大 25 の同時増分同期をサポートする "IMAPEndpoint" という IMAP 移行エンドポイントを作成します。さらに、このエンドポイントを TLS 暗号化用にポート 143 を使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p122">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use. The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations. It also configures the endpoint to use port 143 for TLS encryption.</span></span>

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="c4fac-190">**New-MigrationEndpoint** コマンドレットの詳細については、「[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="c4fac-191">機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="c4fac-191">Verify it worked</span></span>

<span data-ttu-id="c4fac-192">Exchange Online PowerShell で次のコマンドを実行すると、"IMAPEndpoint" に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>

```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="c4fac-193">ステップ 4:IMAP 移行バッチを作成および開始する</span><span class="sxs-lookup"><span data-stu-id="c4fac-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="c4fac-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="c4fac-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="c4fac-p123">[New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) コマンドレットを使用すると、IMAP 移行用の移行バッチを作成できます。 _AutoStart_ パラメーターを含めると、移行バッチを作成して自動的に開始できます。代わりに、移行バッチを作成してから、後で [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) コマンドレットを使用して開始することができます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p123">You can use the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet to create a migration batch for an IMAP migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) cmdlet.</span></span>

<span data-ttu-id="c4fac-198">次の Exchange Online PowerShell コマンドは、"IMAPEndpoint" という IMAP エンドポイントを使用して "IMAPBatch1" という移行バッチを自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>

```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="c4fac-199">機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="c4fac-199">Verify it worked</span></span>

<span data-ttu-id="c4fac-200">[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) コマンドレットを実行すると、"IMAPBatch1" に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-200">Run the [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) cmdlet to display information about the "IMAPBatch1":</span></span>

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="c4fac-201">また、次のコマンドを実行すると、バッチが開始されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-201">You can also verify that the batch has started by running the following command:</span></span>

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="c4fac-202">手順 5: メールをメールにルーティングMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="c4fac-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="c4fac-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="c4fac-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="c4fac-204">電子メール システムでは、電子メールを配信する場所を知るために、MX レコードと呼ばれる DNS レコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="c4fac-205">電子メールの移行プロセス中、MX レコードの宛先は移行元の電子メール システムでした。</span><span class="sxs-lookup"><span data-stu-id="c4fac-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="c4fac-206">メールの移行が完了Microsoft 365、MX レコードを現在のユーザーにMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c4fac-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="c4fac-207">これにより、メールがユーザーのメールボックスに配信Microsoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="c4fac-208">MX レコードを移動することによって、準備ができたら古い電子メール システムをオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span>

<span data-ttu-id="c4fac-209">多くの DNS プロバイダーについては、MX レコードを変更するための具体的な手順があります。</span><span class="sxs-lookup"><span data-stu-id="c4fac-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="c4fac-210">使用している DNS プロバイダーが含まれていない場合、または一般的な手順を知りたい場合は、 [「MX レコードの一般的な手順」](https://go.microsoft.com/fwlink/?LinkId=397449)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>

<span data-ttu-id="c4fac-p126">御社のお客様およびパートナーの電子メール システムが MX レコードの変更を認識するまでに最大 72 時間かかることがあります。次の作業に進むまで、72 時間以上待ちます。手順 6: IMAP 移行バッチを削除する。</span><span class="sxs-lookup"><span data-stu-id="c4fac-p126">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span>

### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="c4fac-213">ステップ 6:IMAP 移行バッチを削除する</span><span class="sxs-lookup"><span data-stu-id="c4fac-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="c4fac-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="c4fac-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="c4fac-215">MX レコードを変更し、すべてのメールが Microsoft 365 メールボックスにルーティングされているのを確認した後、ユーザーにメールが送信Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c4fac-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="c4fac-216">その後、IMAP 移行バッチを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="c4fac-217">移行バッチを削除する前に、次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-217">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="c4fac-218">すべてのユーザーがメールボックスMicrosoft 365使用しています。</span><span class="sxs-lookup"><span data-stu-id="c4fac-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="c4fac-219">バッチが削除された後、オンプレミスのメールボックスに送信Exchange Serverは、対応するメールボックスにMicrosoft 365されません。</span><span class="sxs-lookup"><span data-stu-id="c4fac-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="c4fac-220">Microsoft 365メールが直接送信され始めた後、少なくとも 1 回はメールボックスが同期されました。</span><span class="sxs-lookup"><span data-stu-id="c4fac-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="c4fac-221">これを行うには、移行バッチの [最後に同期された時刻] ボックスの値が、メールがメールボックスに直接ルーティングされ始めた場合よりもMicrosoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="c4fac-222">Exchange Online PowerShell から "IMAPBatch1" 移行バッチを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4fac-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="c4fac-223">**Remove-MigrationBatch** コマンドレットの詳細については、「[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="c4fac-224">機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="c4fac-224">Verify it worked</span></span>

<span data-ttu-id="c4fac-225">Exchange Online PowerShell で次のコマンドを実行すると、"IMAPBatch1" に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>

```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="c4fac-226">このコマンドによって、状態が **Removing** の移行バッチが返されるか、移行バッチが見つからず、削除されたことの確認を求めるエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="c4fac-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>

<span data-ttu-id="c4fac-227">**Get-MigrationBatch** コマンドレットの詳細については、「[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fac-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4fac-228">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4fac-228">See also</span></span>

[<span data-ttu-id="c4fac-229">IMAP の移行に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c4fac-229">IMAP Migration Troubleshooter</span></span>](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)