---
title: Microsoft 365 への IMAP 移行に PowerShell を使用する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/17/2020
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: PowerShell を使用して、Microsoft 365へのインターネット メール アクセス プロトコル (IMAP) 移行を実行する方法について説明します。
ms.openlocfilehash: f93d56379dfa82ec3a369c89b35fc40d49fa1537
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65078660"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>Microsoft 365 への IMAP 移行に PowerShell を使用する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365を展開するプロセスの一環として、ユーザー メールボックスの内容をインターネット メール アクセス プロトコル (IMAP) 電子メール サービスからMicrosoft 365に移行することを選択できます。 この記事では、Exchange Online PowerShell を使用した電子メールの IMAP 移行作業を順を追って説明します。

> [!NOTE]
> <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>を使用して IMAP 移行を実行することもできます。 [「IMAP メールボックスを移行する](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

このタスクの予想所要時間:移行バッチの作成に 2 ～ 5 分。 移行バッチ開始後の移行時間は、バッチ内のメールボックスの数、各メールボックスのサイズ、および使用可能なネットワーク容量によって異なります。 メールボックスをMicrosoft 365に移行するのにかかる時間に影響するその他の要因については、「[移行パフォーマンス](/Exchange/mailbox-migration/office-365-migration-best-practices)」を参照してください。

この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、トピック「[受信者のアクセス許可](/exchange/recipients-permissions-exchange-2013-help)」内の表にある「移行」エントリを参照してください。

Exchange Online PowerShell コマンドレットを使用するには、サインインしてコマンドレットをローカルの Windows PowerShell セッションにインポートする必要があります。手順については、「[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。

IMAP の移行には次の制限が適用されます。

- ユーザーの受信トレイまたは他のメール フォルダー内のアイテムのみ、移行できます。連絡先、予定表アイテム、またはタスクを移行することはできません。

- 最大で 500,000 アイテムをユーザーのメールボックスから移行できます。

- 移行できるメッセージの最大サイズは 35 MB です。

## <a name="migration-steps"></a>移行の手順

### <a name="step-1-prepare-for-an-imap-migration"></a>ステップ 1:IMAP 移行を準備する
<a name="BK_Step1"> </a>

- **IMAP 組織のドメインがある場合は、それをMicrosoft 365組織の承認済みドメインとして追加します。** Microsoft 365 メールボックスに対して既に所有しているのと同じドメインを使用する場合は、まずそれを承認済みドメインとしてMicrosoft 365に追加する必要があります。 追加したら、Microsoft 365でユーザーを作成できます。 詳細については、[ドメインを参照](../admin/setup/add-domain.md)してください。

- **各ユーザーをMicrosoft 365に追加して、メールボックスを作成します。** 手順については、「[ユーザーをビジネス向けにMicrosoft 365に追加する」を](../admin/add-users/add-users.md)参照してください。

- **IMAP サーバーの FQDN を取得します**。IMAP 移行エンドポイントを作成するときに、メールボックス データの移行元の IMAP サーバーの完全修飾ドメイン名 (FQDN) (フル コンピューター名ともいう) を指定する必要があります。IMAP クライアントまたは PING コマンドを使用して、インターネット経由での FQDN サーバーとの通信に FQDN を使用できることを確認します。

- **IMAP 接続を許可するファイアウォールを構成します**。IMAP サーバーをホストする組織のファイアウォールでポートを開く必要があります。そうすることで、移行中 Microsoft データセンターから発信するネットワーク トラフィックが IMAP サーバーをホストする組織に入ることができます。Microsoft データセンターが使用する IP アドレスの一覧については、「[Office 365 の URL と IP アドレスの範囲](./urls-and-ip-address-ranges.md)」を参照してください。

- **IMAP 組織内のメールボックスにアクセスする管理者アカウントのアクセス許可を割り当てます**。CSV ファイルで管理者の資格情報を使用する場合は、使用するアカウントに、社内メールボックスへのアクセスに必要なアクセス許可が必要になります。ユーザーのメールボックスへのアクセスに必要なアクセス許可は、特定の IMAP サーバーによって決定されます。

- **Exchange Online PowerShell コマンドレットを使用するには**、サインインしてコマンドレットをローカルの Windows PowerShell セッションにインポートする必要があります。手順については、「[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

    移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。

- **IMAP サーバーに接続できることを確認します**。IMAP サーバーへの接続設定をテストするには、Exchange Online PowerShell で次のコマンドを実行します。

  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    **Port** パラメーターの値については、通常、暗号化されていない接続やトランスポート層セキュリティ (TLS) 接続には 143 を使用し、SSL 接続には 993 を使用します。

### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>ステップ 2:IMAP 移行バッチ用の CSV ファイルを作成する

IMAP 移行バッチでそのメールボックスを移行するユーザーのグループを特定します。CSV ファイルの各行には、IMAP メッセージング システム内のメールボックスに接続するために必要な情報が含まれています。

各ユーザーの必須属性は次のとおりです。

- **EmailAddress** は、ユーザーのMicrosoft 365メールボックスのユーザー ID を指定します。

- **UserName** は、IMAP サーバー上のメールボックスへのアクセスに使用するアカウントのログオン名を指定します。

- **Password** は、 **UserName** 列のアカウントのパスワードを指定します。

以下に、CSV ファイルの形式の例を示します。この例では、3 人のメールボックスが移行されます。

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

**UserName** 属性については、ユーザー名に加えて、IMAP サーバーのメールボックスへのアクセスに必要なアクセス許可が割り当てられているアカウントの資格情報を使用できます。以下はいくつかの IMAP サーバーで使用されている特定の形式の一部です。

 **Microsoft Exchange:**

Microsoft Exchange の IMAP 実装から電子メールを移行する場合、CSV ファイルでは **UserName** 属性に **Domain/Admin_UserName/User_UserName** という形式を使用します。 たとえば、Terry Adams さん、Ann Beebe さん、Paul Cannon さんのメールを Exchange から移行するとします。 メール管理者アカウントがあり、ユーザー名は **mailadmin** で、パスワードは **Pssw0rd\@** です。 CSV ファイルは次のようになります。

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot:**

Dovecot IMAP サーバーなどの簡易認証およびセキュリティ層 (SASL) をサポートする IMAP サーバーの場合は、アスタリスク (*) が構成可能な区切り文字である **User_UserName*Admin_UserName** 形式を使用します。 管理者資格情報 **mailadmin** と **Pssw0rd\@** を使用して、Dovecot IMAP サーバーから同じユーザーのメールを移行しているとします。 この場合、CSV ファイルは次のようになります。

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint:**

Mirapoint Message Server からメールを移行する場合は、管理者資格情報 **の形式#user\@ domain#Admin_UserName#** を使用します。 管理者資格情報 **mailadmin** と **Pssw0rd\@** を使用して Mirapoint からメールを移行するには、CSV ファイルは次のようになります。

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**

Courier IMAP などの一部のソース 電子メール システムでは、メールボックス管理者の資格情報を使用してメールボックスをMicrosoft 365に移行することはできません。 代わりに、仮想共有フォルダーを使用するように移行元の電子メール システムを設定することができます。 仮想共有フォルダーを使用すると、移行元の電子メール システムのユーザーのメールボックスにアクセスするためにメールボックスの管理資格情報を使用できます。 Courier IMAP の仮想共有フォルダーを構成する方法の詳細については、「[共有フォルダー](https://go.microsoft.com/fwlink/p/?LinkId=398870)」を参照してください。

移行元の電子メール システムで仮想共有フォルダーをセットアップしてからメールボックスを移行するには、オプション属性 **UserRoot** を移行ファイルに含める必要があります。この属性では、移行元電子メール システムの仮想共有フォルダー構造にある各ユーザーのメールボックスの場所を指定します。たとえば、Terry のメールボックスへのパスは /users/terry.adams です。

以下に、 **UserRoot** 属性を含む CSV ファイルの例を示します。

```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>ステップ 3:IMAP 移行エンドポイントを作成する

メールを正常に移行するには、Microsoft 365がソース 電子メール システムに接続して通信する必要があります。 これを行うために、Microsoft 365は移行エンドポイントを使用します。 移行エンドポイントは、同時に移行するメールボックスの数、および 24 時間ごとに 1 回行われる増分同期中に同時に同期するメールボックスの数も定義します。 IMAP 移行用に移行エンドポイントを作成するには、最初に[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)を行います。

移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。

Exchange Online PowerShell で "IMAPEndpoint" という IMAP 移行エンドポイントを作成するには、次のコマンドを実行します。

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

また、同時移行、増分の同時移行、および使用するポートを指定するパラメーターを追加することもできます。次の Exchange Online PowerShell コマンドは、50 の同時移行と最大 25 の同時増分同期をサポートする "IMAPEndpoint" という IMAP 移行エンドポイントを作成します。さらに、このエンドポイントを TLS 暗号化用にポート 143 を使用するように構成します。

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

**New-MigrationEndpoint** コマンドレットの詳細については、「[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)」を参照してください。

#### <a name="verify-it-worked"></a>機能していることを確認する

Exchange Online PowerShell で次のコマンドを実行すると、"IMAPEndpoint" に関する情報が表示されます。

```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>ステップ 4:IMAP 移行バッチを作成および開始する

[New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) コマンドレットを使用すると、IMAP 移行用の移行バッチを作成できます。 _AutoStart_ パラメーターを含めると、移行バッチを作成して自動的に開始できます。代わりに、移行バッチを作成してから、後で [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) コマンドレットを使用して開始することができます。

次の Exchange Online PowerShell コマンドは、"IMAPEndpoint" という IMAP エンドポイントを使用して "IMAPBatch1" という移行バッチを自動的に開始します。

```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>機能していることを確認する

[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) コマンドレットを実行すると、"IMAPBatch1" に関する情報を表示できます。

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

また、次のコマンドを実行すると、バッチが開始されたことを確認できます。

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>手順 5: メールをMicrosoft 365にルーティングする

電子メール システムでは、電子メールを配信する場所を知るために、MX レコードと呼ばれる DNS レコードを使用します。 電子メールの移行プロセス中、MX レコードの宛先は移行元の電子メール システムでした。 Microsoft 365への電子メールの移行が完了したので、MX レコードをMicrosoft 365にポイントします。 これにより、メールがMicrosoft 365メールボックスに確実に配信されます。 MX レコードを移動することによって、準備ができたら古い電子メール システムをオフにすることもできます。

多くの DNS プロバイダーについては、MX レコードを変更するための具体的な手順があります。 使用している DNS プロバイダーが含まれていない場合、または一般的な手順を知りたい場合は、 [「MX レコードの一般的な手順」](https://go.microsoft.com/fwlink/?LinkId=397449)も参照してください。

御社のお客様およびパートナーの電子メール システムが MX レコードの変更を認識するまでに最大 72 時間かかることがあります。次の作業に進むまで、72 時間以上待ちます。手順 6: IMAP 移行バッチを削除する。

### <a name="step-6-delete-imap-migration-batch"></a>ステップ 6:IMAP 移行バッチを削除する

MX レコードを変更し、すべてのメールがMicrosoft 365メールボックスにルーティングされていることを確認したら、メールがMicrosoft 365されることをユーザーに通知します。 その後、IMAP 移行バッチを削除できます。 移行バッチを削除する前に、次の点を確認します。

- すべてのユーザーがMicrosoft 365メールボックスを使用しています。 バッチが削除されると、オンプレミスのExchange Server上のメールボックスに送信されたメールは、対応するMicrosoft 365メールボックスにコピーされません。

- Microsoft 365メールボックスは、メールが直接送信され始めた後、少なくとも 1 回は同期されました。 これを行うには、移行バッチの [最終同期時刻] ボックスの値が、メールがMicrosoft 365メールボックスに直接ルーティングされ始めた場合よりも新しく設定されていることを確認します。

Exchange Online PowerShell から "IMAPBatch1" 移行バッチを削除するには、次のコマンドを実行します。

```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

**Remove-MigrationBatch** コマンドレットの詳細については、「[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)」を参照してください。

#### <a name="verify-it-worked"></a>機能していることを確認する

Exchange Online PowerShell で次のコマンドを実行すると、"IMAPBatch1" に関する情報が表示されます。

```powershell
Get-MigrationBatch IMAPBatch1"
```

このコマンドによって、状態が **Removing** の移行バッチが返されるか、移行バッチが見つからず、削除されたことの確認を求めるエラーが返されます。

**Get-MigrationBatch** コマンドレットの詳細については、「[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)」を参照してください。

## <a name="see-also"></a>関連項目

[IMAP の移行に関するトラブルシューティング](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)