---
title: Microsoft 365 への段階的な移行に PowerShell を使用する
ms.author: kvice
author: kelleyvice-msft
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
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: PowerShell を使用して、ステージ移行を使用して移行元の電子メール システムからコンテンツを移行する方法についてMicrosoft 365。
ms.openlocfilehash: 0ec8aca643730b063ee75ead69908959a992d2dc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210484"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Microsoft 365 への段階的な移行に PowerShell を使用する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ステージ移行を使用して、ユーザー メールボックスの内容をソース 電子メール システムからMicrosoft 365に移行できます。

この記事では、Exchange Online PowerShell を使用した段階的メール移行に関するタスクを順を追って説明します。 トピック「 [電子メールの](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)段階移行について知る必要がある内容」では、移行プロセスの概要を説明します。 記事の内容に満足いただけたら、段階的メール移行を使用して、あるメール システムから別のメール システムへのメールボックスの移行を開始してください。

> [!NOTE]
> また、段階的な移行を実行するには、Exchange 管理センターを使用することもできます。 「[電子メールからメールへの移行をステージで実行する」を参照Microsoft 365。](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration)

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

このタスクの予想所要時間:移行バッチの作成に 2 ～ 5 分。 移行バッチ開始後の移行時間は、バッチ内のメールボックスの数、各メールボックスのサイズ、および使用可能なネットワーク容量によって異なります。 メールボックスを移行する時間に影響を与えるその他の要因については、「移行パフォーマンス」をMicrosoft 365[を参照してください](/Exchange/mailbox-migration/office-365-migration-best-practices)。

この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、トピック「[受信者のアクセス許可](/exchange/recipients-permissions-exchange-2013-help)」の中の「移行」エントリを参照してください。

Exchange Online PowerShell コマンドレットを使用するには、サインインしてコマンドレットをローカルの Windows PowerShell セッションにインポートする必要があります。手順については、「[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。

## <a name="migration-steps"></a>移行の手順

### <a name="step-1-prepare-for-a-staged-migration"></a>ステップ 1:段階的な移行を準備する

ステージ移行を使用してメールボックスMicrosoft 365移行する前に、移行環境に対していくつかの変更Exchangeがあります。

 **社内の Exchange Server** に Outlook Anywhere を構成する: メール移行サービスは、Outlook Anywhere (RPC over HTTP としても知られる) を使用して社内の Exchange Server に接続します。Exchange Server 2007 と Exchange 2003 における Outlook Anywhere の設定方法の詳細については、以下を参照してください。

- 「[Exchange 2007:Outlook Anywhere を有効にする方法](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))」

- 「[Exchange 2003 での Outlook Anywhere を構成する方法](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))」

> [!IMPORTANT]
> Outlook Anywhere の構成には、信頼された証明機関 (CA) によって発行された証明書を使用する必要があります。Outlook Anywhere は、自己署名入りの証明書で構成することはできません。詳細については、「[Outlook Anywhere のために SSL を構成する方法](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))」を参照してください。

 **オプション:Outlook Anywhere** を使用して Exchange 組織に接続できることを確認する: 接続設定をテストするには、次のいずれかの方法を試します。

- 企業ネットワークの外部から Outlook を使用して社内の Exchange メールボックスに接続します。

- Microsoft [リモート接続アナライザーを使用して、](https://https://testconnectivity.microsoft.com/) 接続設定をテストします。 Outlook Anywhere (RPC over HTTP) または Outlook 自動検出テストを使用します。

- Exchange Online PowerShell で次のコマンドを実行します。

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **アクセス許可を設定する** オンプレミスの Exchange 組織 (移行管理者とも呼ばれる) への接続に使用するオンプレミス ユーザー アカウントには、Microsoft 365 に移行するオンプレミス メールボックスにアクセスするために必要なアクセス許可が必要です。 このユーザー アカウントは、この手順の後半で移行エンドポイントを作成して電子メール システムに接続するときに使用されます ([手順 3: 移行エンドポイントの作成](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint))。

メールボックスを移行するために、管理者には次のアクセス許可セットのいずれかが必要です。

- 社内組織の Active Directory の **Domain Admins** グループのメンバーであること。

    or

- 社内の各メールボックスに **FullAccess** のアクセス許可が割り当てられ、社内のユーザー アカウントの **TargetAddress** プロパティを変更するための **WriteProperty** のアクセス許可が割り当てられていること。

    or

- ユーザー メールボックスを格納する社内のメールボックス データベースに **受信者** のアクセス許可が割り当てられ、社内のユーザー アカウントの **TargetAddress** プロパティを変更するための **WriteProperty** のアクセス許可が割り当てられていること。

これらのアクセス許可を設定する[Microsoft 365](/Exchange/mailbox-migration/assign-permissions-for-migration)方法については、「アクセス許可を割り当てる」を参照してください。

 **ユニファイド メッセージング (UM) を無効にする**: 移行する社内のメールボックスで UM がオンになっている場合は、移行前に UM をオフにします。移行の完了後に、メールボックスの UM をオンにします。操作手順については、「[ユーザーのユニファイド メッセージングを無効にする方法](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80))」を参照してください。

 **ディレクトリ同期を使用して、ディレクトリ内に新しいユーザー Microsoft 365。** ディレクトリ同期を使用して、組織内のすべてのオンプレミス ユーザー Microsoft 365します。

ユーザーの作成後にライセンスを付与する必要があります。ユーザーの作成後、ライセンスを追加するまでに 30 日間があります。ライセンスを追加する手順については、「[ステップ 8:移行後のタスクを完了する](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration)」を参照してください。

 Microsoft Azure Active Directory (Azure AD) 同期ツールまたは Microsoft Azure AD 同期サービスのいずれかを使用して、Microsoft 365 でオンプレミス ユーザーを同期および作成できます。 メールボックスが Microsoft 365に移行された後、オンプレミス組織のユーザー アカウントを管理し、そのユーザー アカウントを組織とMicrosoft 365します。 詳細については[、「Directory Integration」を参照してください](/previous-versions/azure/azure-services/jj573653(v=azure.100)) 。

### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>ステップ 2:段階的な移行バッチ用の CSV ファイルを作成する

Microsoft 365 に移行するオンプレミス メールボックスを持つユーザーを特定した後、コンマ区切り値 (CSV) ファイルを使用して移行バッチを作成します。 移行の実行に使用される CSV ファイルMicrosoft 365行ごとに、オンプレミスのメールボックスに関する情報が含まれます。

> [!NOTE]
> ステージ移行を使用して移行できるメールボックスの数に制限Microsoft 365はありません。 移行バッチ用の CSV ファイルに含めることができる行数は、最大 2,000 行までです。 2,000 を超えるメールボックスを移行するには、追加の CSV ファイルを作成し、各ファイルを使用して新しい移行バッチを作成します。

 **サポートされている属性**

段階的な移行用の CSV ファイルは、次の 3 つの属性をサポートします。CSV ファイルの各行はメールボックスに対応し、各属性の値を含める必要があります。

|**属性**|**説明**|**必須**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |プライマリ SMTP 電子メール アドレス (たとえば、社内メールボックスの場合は pilarp@contoso.com など) を指定します。  <br/> オンプレミスメールボックスのプライマリ SMTP アドレスを使用し、ユーザー ID は使用Microsoft 365。 たとえば、オンプレミス ドメインの名前が contoso.com で、Microsoft 365 メール ドメインの名前が service.contoso.com の場合は、CSV ファイル内の電子メール アドレスに contoso.com ドメイン名を使用します。  <br/> |必須  <br/> |
|Password  <br/> |新しいメールボックスに設定するパスワードMicrosoft 365します。 組織に適用されるパスワード制限Microsoft 365 CSV ファイルに含まれるパスワードにも適用されます。  <br/> |省略可能  <br/> |
|ForceChangePassword  <br/> |ユーザーが新しいメールボックスに初めてサインインする場合にパスワードを変更する必要Microsoft 365します。 このパラメーターの値には **True** または **False** を使用してください。 <br/> > [!NOTE]> Active Directory フェデレーション サービス (AD FS) 以上を社内組織に展開してシングル サインオン (SSO) ソリューションを実装した場合、 **ForceChangePassword** 属性の値には **False** を使用する必要があります。          |省略可能  <br/> |

 **CSV ファイル形式**

以下に、CSV ファイルの形式の例を示します。 この例では、3 つのオンプレミス メールボックスが 3 つのメールボックスにMicrosoft 365。

CSV ファイルの最初の行、つまりヘッダー行には、後続の行で指定される属性 (つまり、フィールド) の名前が示されます。各属性名はコンマで区切られます。

```powershell
EmailAddress,Password,ForceChangePassword
pilarp@contoso.com,Pa$$w0rd,False
tobyn@contoso.com,Pa$$w0rd,False
briant@contoso.com,Pa$$w0rd,False
```

ヘッダー行の下の各行は個々のユーザーを表します。これらの行には、そのユーザーのメールボックスを移行するための情報が含まれます。各行の属性値は、ヘッダー行の属性名と同じ順序で並んでいる必要があります。

CSV ファイルの作成には、任意のテキスト エディターや Excel などのアプリケーションを使用します。ファイルは .csv ファイルまたは .txt ファイルとして保存します。

> [!NOTE]
> CSV ファイルに非 ASCII 文字や特殊文字が含まれている場合は、UTF-8 などの Unicode エンコードで CSV ファイルを保存してください。アプリケーションによっては、コンピューターのシステム ロケールが CSV ファイルで使用されている言語と一致するときに、CSV ファイルを UTF-8 などの Unicode エンコードで保存した方が簡単な場合があります。

### <a name="step-3-create-a-migration-endpoint"></a>ステップ 3:移行エンドポイントを作成する
<a name="BK_Endpoint"> </a>

メールを正常に移行するにはMicrosoft 365メール システムに接続して通信する必要があります。 これを行うには、Microsoft 365エンドポイントを使用します。 PowerShell を使用して Outlook Anywhere 移行エンドポイントを作成するには、段階的な移行で、最初に[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)を行います。

移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。

Exchange Online PowerShell に "StagedEndpoint" という Outlook Anywhere 移行エンドポイントを作成するには、次のコマンドを実行します。

```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

**New-MigrationEndpoint** コマンドレットの詳細については、「[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)」を参照してください。

> [!NOTE]
> **New-MigrationEndpoint** コマンドレットで **-TargetDatabase** オプションを使用することによって、使用するサービスに対してデータベースを指定することができます。それ以外の場合、データベースは、管理メールボックスが配置されている Active Directory フェデレーション サービス (AD FS) 2.0 サイトからランダムに割り当てられます。

#### <a name="verify-it-worked"></a>機能していることを確認する

Exchange Online PowerShell で、次のコマンドを実行して "StagedEndpoint" 移行エンドポイントに関する情報を表示します。

```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>ステップ 4:段階的な移行のバッチを作成および開始する
<a name="BK_Endpoint"> </a>

Exchange Online PowerShell の **New-MigrationBatch** コマンドレットを使用すると、一括移行の移行バッチを作成できます。 _AutoStart_ パラメーターを含めると、移行バッチを作成して自動的に開始できます。また、別の方法として、 **Start-MigrationBatch** コマンドレットを使用することにより、移行バッチを作成して後で手動で開始できます。この例では、"StagedBatch1" という移行バッチを作成して、前の例で作成した移行エンドポイントを使用します。

```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

この例でも、"StagedBatch1" という移行バッチを作成して、前の例で作成した移行エンドポイントを使用します。 _AutoStart_ パラメーターが含まれていないため、移行バッチは移行ダッシュボードで、または **Start-MigrationBatch** コマンドレットを使用して手動で開始する必要があります。前述のように、一度に存在できる一括移行バッチは 1 つだけです。

```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>機能していることを確認する

Exchange Online PowerShell で次のコマンドを実行すると、「StagedBatch1」に関する情報が表示されます。

```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

また、次のコマンドを実行すると、バッチが開始されたことを確認できます。

```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

**Get-MigrationBatch** コマンドレットの詳細については、「[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)」を参照してください。

### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>ステップ 5:社内メールボックスをメールが有効なユーザーに変換する
<a name="BK_Endpoint"> </a>

メールボックスのバッチが正常に移行されたら、何らかの方法でユーザーが各自のメールにアクセスできるようにする必要があります。 メールボックスが移行されたユーザーには、オンプレミスのメールボックスとメールボックス内のメールボックスの両方Microsoft 365。 メールボックスを使用しているユーザーは、Microsoft 365メールボックス内の新しいメールの受信を停止します。

移行が完了していないので、すべてのユーザーに電子メールの送信を指示Microsoft 365準備が整っていません。 両方のメールボックスを持つユーザーに対してはどのようにすれば良いでしょうか。 既に移行済みの社内メールボックスをメールが有効なユーザーに変更することができます。 メールボックスからメールが有効なユーザーに変更する場合は、ユーザーに対して、オンプレミスのメールボックスに移動する代わりに、電子メールの Microsoft 365 を表示できます。

オンプレミスのメールボックスをメールが有効なユーザーに変換するもう 1 つの重要な理由は、プロキシ アドレスをメールが有効なユーザーにコピーして、Microsoft 365 メールボックスからプロキシ アドレスを保持する方法です。 これにより、Active Directory を使用して社内組織からクラウドベースのユーザーを管理できます。 また、すべてのメールボックスを Microsoft 365 に移行した後に、オンプレミスの Exchange Server 組織を使用停止にした場合、メールが有効なユーザーにコピーしたプロキシ アドレスはオンプレミスの Active Directory に残ります。

### <a name="step-6-delete-a-staged-migration-batch"></a>ステップ 6:段階的な移行バッチを削除する
<a name="BK_Endpoint"> </a>

 移行バッチ内のすべてのメールボックスが正常に移行された場合、バッチ内の社内メールボックスをメールが有効なユーザーに変換した後に、段階的な移行バッチを削除する準備が整います。 メールが移行バッチ内のメールボックスに転送Microsoft 365確認してください。 段階的な移行バッチを削除すると、移行サービスによって、移行バッチに関連するすべてのレコードがクリーンアップされて移行バッチが削除されます。

Exchange Online PowerShell で "StagedBatch1" 移行バッチを削除するには、次のコマンドを実行します。

```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

**Remove-MigrationBatch** コマンドレットの詳細については、「[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)」を参照してください。

#### <a name="verify-it-worked"></a>機能していることを確認する

Exchange Online PowerShell で次のコマンドを実行すると、"IMAPBatch1" に関する情報が表示されます。

```powershell
Get-MigrationBatch StagedBatch1
```

このコマンドによって、状態が **Removing** の移行バッチが返されるか、移行バッチが見つからず、削除されたことの確認を求めるエラーが返されます。

**Get-MigrationBatch** コマンドレットの詳細については、「[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)」を参照してください。

### <a name="step7-assign-licenses-to-microsoft-365-users"></a>手順 7: ユーザーにライセンスをMicrosoft 365する
<a name="BK_Endpoint"> </a>

ライセンスMicrosoft 365して、移行されたアカウントのユーザー アカウントをアクティブ化します。 ライセンスを割り当てないと、猶予期間 (30 日) が終了したときにメールボックスが無効になります。 ライセンスを割り当てるには、「ライセンスMicrosoft 365 管理センター割り当てまたは[割り当てを解除する」を参照してください](../admin/manage/assign-licenses-to-users.md)。

### <a name="step-8-complete-post-migration-tasks"></a>ステップ 8:移行後のタスクを完了する
<a name="BK_Postmigration"> </a>

- **ユーザーが各自のメールボックスに簡単にアクセスできるように、自動検出 DNS レコードを作成します。** すべてのオンプレミスメールボックスを Microsoft 365 に移行した後、Microsoft 365 組織の自動検出 DNS レコードを構成して、ユーザーが Outlook およびモバイル クライアントを使用して新しい Microsoft 365 メールボックスに簡単に接続できます。 この新しい自動検出 DNS レコードでは、組織で使用している名前空間と同じ名前空間Microsoft 365があります。 たとえば、クラウドベースの名前空間が cloud.contoso.com の場合、作成する必要のある自動検出 DNS レコードは autodiscover.cloud.contoso.com となります。

    Microsoft 365 CNAME レコードを使用して、モバイル クライアントとモバイル クライアントの自動検出Outlook実装します。 自動検出 CNAME レコードには以下の情報が含まれている必要があります。

  - **エイリアス:** autodiscover

  - **リンク先:** autodiscover.outlook.com

    詳細については、[「DNS レコードを追加してドメインに接続する」](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)を参照してください。

- **社内の Exchange サーバーの使用を停止します。** すべての電子メールが Microsoft 365 メールボックスに直接ルーティングされ、オンプレミスの電子メール組織を維持する必要がなくなったり、SSO ソリューションの実装を計画したりする必要がなくなった場合は、サーバーから Exchange をアンインストールし、オンプレミスの Exchange 組織を削除できます。

    詳細については、以下を参照してください。

  - 「[Exchange 2010 の変更または削除](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))」

  - 「[Exchange 2007 組織を削除する方法](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))」

  - 「[Exchange Server 2003 をアンインストールする方法](/previous-versions/tn-archive/bb125110(v=exchg.65))」
