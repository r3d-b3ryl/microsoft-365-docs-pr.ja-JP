---
title: Microsoft 365 への段階的な移行に PowerShell を使用する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/07/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: 段階的な移行を使用して PowerShell を使用して、時間の経過と共にソース 電子メール システムからコンテンツを移動する方法について説明Microsoft 365。
ms.openlocfilehash: 26c12208c00e6b9b33b0be850a4791ddca804c8c
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014214"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Microsoft 365 への段階的な移行に PowerShell を使用する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

段階的な移行を使用して、ユーザー メールボックスの内容を移行元の電子メール システムから時間の経過と共にMicrosoft 365に移行できます。

この記事では、Exchange Online PowerShell を使用した段階的メール移行に関するタスクを順を追って説明します。 段階的な [電子メール移行について知ってお](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)くべきことというトピックでは、移行プロセスの概要を説明します。 記事の内容に満足いただけたら、段階的メール移行を使用して、あるメール システムから別のメール システムへのメールボックスの移行を開始してください。

> [!NOTE]
> <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>を使用して、段階的な移行を実行することもできます。 [「Microsoft 365への電子メールの段階的な移行を実行する」を](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration)参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

このタスクの予想所要時間:移行バッチの作成に 2 ～ 5 分。 移行バッチ開始後の移行時間は、バッチ内のメールボックスの数、各メールボックスのサイズ、および使用可能なネットワーク容量によって異なります。 メールボックスをMicrosoft 365に移行するのにかかる時間に影響するその他の要因については、「[移行パフォーマンス](/Exchange/mailbox-migration/office-365-migration-best-practices)」を参照してください。

この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、トピック「[受信者のアクセス許可](/exchange/recipients-permissions-exchange-2013-help)」の中の「移行」エントリを参照してください。

Exchange Online PowerShell コマンドレットを使用するには、サインインしてコマンドレットをローカルの Windows PowerShell セッションにインポートする必要があります。 手順については、[PowerShell をExchange OnlineするConnect](/powershell/exchange/connect-to-exchange-online-powershell)を参照してください。

移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。

## <a name="migration-steps"></a>移行の手順

### <a name="step-1-prepare-for-a-staged-migration"></a>ステップ 1:段階的な移行を準備する

段階的な移行を使用してメールボックスをMicrosoft 365に移行する前に、Exchange環境にいくつかの変更を加える必要があります。

 **社内の Exchange Server** に Outlook Anywhere を構成する: メール移行サービスは、Outlook Anywhere (RPC over HTTP としても知られる) を使用して社内の Exchange Server に接続します。Exchange Server 2007 と Exchange 2003 における Outlook Anywhere の設定方法の詳細については、以下を参照してください。

- 「[Exchange 2007:Outlook Anywhere を有効にする方法](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))」

- 「[Exchange 2003 での Outlook Anywhere を構成する方法](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))」

> [!IMPORTANT]
> Outlook Anywhere の構成には、信頼された証明機関 (CA) によって発行された証明書を使用する必要があります。Outlook Anywhere は、自己署名入りの証明書で構成することはできません。詳細については、「[Outlook Anywhere のために SSL を構成する方法](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))」を参照してください。

 **オプション:Outlook Anywhere** を使用して Exchange 組織に接続できることを確認する: 接続設定をテストするには、次のいずれかの方法を試します。

- 企業ネットワークの外部から Outlook を使用して社内の Exchange メールボックスに接続します。

- [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) を使用して接続設定をテストします。 Outlook Anywhere (RPC over HTTP) または Outlook 自動検出テストを使用します。

- Exchange Online PowerShell で次のコマンドを実行します。

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **アクセス許可を設定する** オンプレミスのExchange組織への接続に使用するオンプレミス ユーザー アカウント (移行管理者とも呼ばれます) には、Microsoft 365に移行するオンプレミスメールボックスにアクセスするために必要なアクセス許可が必要です。 このユーザー アカウントは、この手順の後半で移行エンドポイントを作成して電子メール システムに接続するときに使用 [されます。手順 3: 移行エンドポイントを作成します](#step-3-create-a-migration-endpoint)。

メールボックスを移行するために、管理者には次のアクセス許可セットのいずれかが必要です。

- 社内組織の Active Directory の **Domain Admins** グループのメンバーであること。

    or

- 社内の各メールボックスに **FullAccess** のアクセス許可が割り当てられ、社内のユーザー アカウントの **TargetAddress** プロパティを変更するための **WriteProperty** のアクセス許可が割り当てられていること。

    or

- ユーザー メールボックスを格納する社内のメールボックス データベースに **受信者** のアクセス許可が割り当てられ、社内のユーザー アカウントの **TargetAddress** プロパティを変更するための **WriteProperty** のアクセス許可が割り当てられていること。

これらのアクセス許可を設定する方法については、「メールボックスを[Microsoft 365に移行するためのアクセス許可を割り当てる」を](/Exchange/mailbox-migration/assign-permissions-for-migration)参照してください。

 **ユニファイド メッセージング (UM) を無効にする**: 移行する社内のメールボックスで UM がオンになっている場合は、移行前に UM をオフにします。移行の完了後に、メールボックスの UM をオンにします。操作手順については、「[ユーザーのユニファイド メッセージングを無効にする方法](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80))」を参照してください。

 **ディレクトリ同期を使用して、Microsoft 365に新しいユーザーを作成します。** ディレクトリ同期を使用して、Microsoft 365組織内のすべてのオンプレミス ユーザーを作成します。

ユーザーの作成後にライセンスを付与する必要があります。ユーザーの作成後、ライセンスを追加するまでに 30 日間があります。ライセンスを追加する手順については、「[ステップ 8:移行後のタスクを完了する](#step-8-complete-post-migration-tasks)」を参照してください。

 Microsoft Azure Active Directory (Azure AD) 同期ツールまたはMicrosoft Azure AD Sync Services のいずれかを使用して、オンプレミス ユーザーを同期してMicrosoft 365に作成できます。 メールボックスをMicrosoft 365に移行すると、オンプレミス組織内のユーザー アカウントが管理され、Microsoft 365組織と同期されます。 詳細については、「[ディレクトリの統合](/previous-versions/azure/azure-services/jj573653(v=azure.100)) 」を参照してください。

### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>ステップ 2:段階的な移行バッチ用の CSV ファイルを作成する

Microsoft 365に移行するオンプレミスメールボックスを持つユーザーを特定したら、コンマ区切り値 (CSV) ファイルを使用して移行バッチを作成します。 移行を実行するためにMicrosoft 365によって使用される CSV ファイル内の各行には、オンプレミスのメールボックスに関する情報が含まれています。

> [!NOTE]
> 段階的な移行を使用してMicrosoft 365に移行できるメールボックスの数に制限はありません。 移行バッチ用の CSV ファイルに含めることができる行数は、最大 2,000 行までです。 2,000 を超えるメールボックスを移行するには、追加の CSV ファイルを作成し、各ファイルを使用して新しい移行バッチを作成します。

 **サポートされている属性**

段階的な移行用の CSV ファイルは、次の 3 つの属性をサポートします。CSV ファイルの各行はメールボックスに対応し、各属性の値を含める必要があります。

|**属性**|**説明**|**必須**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |プライマリ SMTP 電子メール アドレス (たとえば、社内メールボックスの場合は pilarp@contoso.com など) を指定します。  <br/> Microsoft 365からのユーザー ID ではなく、オンプレミスメールボックスのプライマリ SMTP アドレスを使用します。 たとえば、オンプレミス ドメインに contoso.com という名前が付けられ、Microsoft 365電子メール ドメインに service.contoso.com という名前が付けられている場合は、CSV ファイル内の電子メール アドレスに contoso.com ドメイン名を使用します。  <br/> |必須  <br/> |
|Password  <br/> |新しいMicrosoft 365 メールボックスに設定するパスワード。 Microsoft 365組織に適用されるすべてのパスワード制限は、CSV ファイルに含まれるパスワードにも適用されます。  <br/> |省略可能  <br/> |
|ForceChangePassword  <br/> |ユーザーが新しいMicrosoft 365 メールボックスに初めてサインインする際にパスワードを変更する必要があるかどうかを指定します。 このパラメーターの値には **True** または **False** を使用してください。 <br/> > [!NOTE]> Active Directory フェデレーション サービス (AD FS) 以上を社内組織に展開してシングル サインオン (SSO) ソリューションを実装した場合、 **ForceChangePassword** 属性の値には **False** を使用する必要があります。          |省略可能  <br/> |

 **CSV ファイル形式**

以下に、CSV ファイルの形式の例を示します。 この例では、3 つのオンプレミス メールボックスがMicrosoft 365に移行されます。

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

電子メールを正常に移行するには、Microsoft 365ソース電子メール システムに接続して通信する必要があります。 これを行うために、Microsoft 365は移行エンドポイントを使用します。 PowerShell を使用して Outlook Anywhere 移行エンドポイントを作成するには、段階的な移行で、最初に[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)を行います。

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

Exchange Online PowerShell の **New-MigrationBatch** コマンドレットを使用すると、一括移行の移行バッチを作成できます。 _AutoStart_ パラメーターを含めると、移行バッチを作成して自動的に開始できます。また、別の方法として、 **Start-MigrationBatch** コマンドレットを使用することにより、移行バッチを作成して後で手動で開始できます。この例では、"StagedBatch1" という移行バッチを作成して、前の例で作成した移行エンドポイントを使用します。

```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

この例でも、"StagedBatch1" という移行バッチを作成して、前の例で作成した移行エンドポイントを使用します。 _AutoStart_ パラメーターは含まれていないため、移行ダッシュボードまたは **Start-MigrationBatch** コマンドレットを使用して、移行バッチを手動で開始する必要があります。 前述のように、一度に存在できる一括移行バッチは 1 つだけです。

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

メールボックスのバッチが正常に移行されたら、何らかの方法でユーザーが各自のメールにアクセスできるようにする必要があります。 メールボックスが移行されたユーザーは、オンプレミスのメールボックスと、Microsoft 365内のメールボックスの両方を持つようになりました。 Microsoft 365にメールボックスを持つユーザーは、オンプレミスのメールボックスで新しいメールの受信を停止します。

移行は完了していないため、すべてのユーザーに電子メールのMicrosoft 365を指示する準備はまだできていない。 両方のメールボックスを持つユーザーに対してはどのようにすれば良いでしょうか。 既に移行済みの社内メールボックスをメールが有効なユーザーに変更することができます。 メールボックスからメールが有効なユーザーに変更する場合は、オンプレミスのメールボックスに移動する代わりに、ユーザーに電子メールのMicrosoft 365を指示できます。

オンプレミスメールボックスをメールが有効なユーザーに変換するもう 1 つの重要な理由は、プロキシ アドレスをメールが有効なユーザーにコピーして、Microsoft 365 メールボックスからプロキシ アドレスを保持することです。 これにより、Active Directory を使用して社内組織からクラウドベースのユーザーを管理できます。 また、すべてのメールボックスをMicrosoft 365に移行した後でオンプレミスのExchange Server組織を使用停止にすることにした場合、メールが有効なユーザーにコピーしたプロキシ アドレスはオンプレミスの Active Directoryに残ります。

### <a name="step-6-delete-a-staged-migration-batch"></a>ステップ 6:段階的な移行バッチを削除する

 移行バッチ内のすべてのメールボックスが正常に移行された場合、バッチ内の社内メールボックスをメールが有効なユーザーに変換した後に、段階的な移行バッチを削除する準備が整います。 移行バッチ内のMicrosoft 365メールボックスにメールが転送されていることを確認してください。 段階的な移行バッチを削除すると、移行サービスによって、移行バッチに関連するすべてのレコードがクリーンアップされて移行バッチが削除されます。

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

### <a name="step7-assign-licenses-to-microsoft-365-users"></a>手順 7: Microsoft 365 ユーザーにライセンスを割り当てる

ライセンスを割り当てて、移行されたアカウントのMicrosoft 365ユーザー アカウントをアクティブ化します。 ライセンスを割り当てないと、猶予期間 (30 日) が終了したときにメールボックスが無効になります。 Microsoft 365 管理センターでライセンスを割り当てるには、「[ライセンスの割り当てまたは割り当ての解除](../admin/manage/assign-licenses-to-users.md)」を参照してください。

### <a name="step-8-complete-post-migration-tasks"></a>ステップ 8:移行後のタスクを完了する

- **ユーザーが各自のメールボックスに簡単にアクセスできるように、自動検出 DNS レコードを作成します。** すべてのオンプレミス メールボックスをMicrosoft 365に移行したら、Microsoft 365組織の自動検出 DNS レコードを構成して、ユーザーがOutlookおよびモバイル クライアントを使用して新しいMicrosoft 365 メールボックスに簡単に接続できるようにします。 この新しい自動検出 DNS レコードでは、Microsoft 365組織で使用しているのと同じ名前空間を使用する必要があります。 たとえば、クラウドベースの名前空間が cloud.contoso.com の場合、作成する必要のある自動検出 DNS レコードは autodiscover.cloud.contoso.com となります。

    Microsoft 365では、CNAME レコードを使用して、Outlook およびモバイル クライアントの自動検出サービスを実装します。 自動検出 CNAME レコードには以下の情報が含まれている必要があります。

  - **エイリアス:** autodiscover

  - **リンク先:** autodiscover.outlook.com

    詳細については、[「DNS レコードを追加してドメインに接続する」](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)を参照してください。

- **社内の Exchange サーバーの使用を停止します。** すべての電子メールがMicrosoft 365メールボックスに直接ルーティングされていることを確認した後、オンプレミスのメール組織を維持する必要がなくなったり、SSO ソリューションの実装を計画したりする必要がなくなったら、サーバーからExchangeをアンインストールし、オンプレミスのExchange組織を削除できます。

> [!NOTE]
> Exchange の使用を停止すると、予期しない結果が起こる可能性があります。 オンプレミスの Exchange 組織の使用を停止する前に、Microsoft サポートに連絡することをお勧めします。

詳細については、以下を参照してください。

- 「[Exchange 2010 の変更または削除](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))」

- 「[Exchange 2007 組織を削除する方法](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))」

- 「[Exchange Server 2003 をアンインストールする方法](/previous-versions/tn-archive/bb125110(v=exchg.65))」
