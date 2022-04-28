---
title: Microsoft 365 への一括移行に PowerShell を使用する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
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
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: PowerShell を使用して、Microsoft 365への一括移行を実行して、ソース電子メール システムからコンテンツを一度に移動する方法について説明します。
ms.openlocfilehash: ede2dfc25897012c5cb7e5469abea49e6db4292e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65078693"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Microsoft 365 への一括移行に PowerShell を使用する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

一括移行を使用して、ユーザー メールボックスの内容をソース 電子メール システムから一度にMicrosoft 365に移行できます。 この記事では、Exchange Online PowerShell を使用した電子メールの一括移行の作業を順を追って説明します。

トピック「Microsoft 365[への一括メール移行について知](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)っておくべきこと」を確認することで、移行プロセスの概要を確認できます。 記事の内容に満足いただけたら、段階的メール移行を使用して、あるメール システムから別のメール システムへのメールボックスの移行を開始してください。

> [!NOTE]
> <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>を使用して、一括移行を実行することもできます。 [「Microsoft 365へのメールの一括移行を実行する」を](/Exchange/mailbox-migration/cutover-migration-to-office-365)参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

このタスクの予想所要時間:移行バッチの作成に 2 ～ 5 分。 移行バッチ開始後の移行時間は、バッチ内のメールボックスの数、各メールボックスのサイズ、および使用可能なネットワーク容量によって異なります。 メールボックスをMicrosoft 365に移行するのにかかる時間に影響するその他の要因については、「[移行パフォーマンス](/Exchange/mailbox-migration/office-365-migration-best-practices)」を参照してください。

この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、トピック「[受信者のアクセス許可](/exchange/recipients-permissions-exchange-2013-help)」内の表にある「移行」エントリを参照してください。

Exchange Online PowerShell コマンドレットを使用するには、サインインしてコマンドレットをローカルの Windows PowerShell セッションにインポートする必要があります。手順については、「[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。

## <a name="migration-steps"></a>移行の手順

### <a name="step-1-prepare-for-a-cutover-migration"></a>ステップ 1:一括移行を準備する
<a name="BK_Step1"> </a>

- **オンプレミスのExchange組織を、Microsoft 365 組織の承認済みドメインとして追加します。** 移行サービスでは、オンプレミスのメールボックスの SMTP アドレスを使用して、新しいMicrosoft 365 メールボックスの Microsoft Online Services ユーザー ID と電子メール アドレスを作成します。 Exchange ドメインが承認済みドメインまたはMicrosoft 365組織のプライマリ ドメインでない場合、移行は失敗します。 詳細については、「 [ドメインを確認する](../admin/setup/add-domain.md)」を参照してください。

- **社内 Exchange サーバーで Outlook Anywhere を構成する。** 電子メール移行サービスは、RPC over HTTP または Outlook Anywhere を使用して社内 Exchange サーバーに接続します。Exchange 2010、Exchange 2007、および Exchange 2003 で Outlook Anywhere をセットアップする方法については、以下のトピックを参照してください。

  - 「[Exchange 2010:Outlook Anywhere を有効にする](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))」

  - 「[Exchange 2007:Outlook Anywhere を有効にする方法](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))」

  - 「[Exchange 2003:RPC over HTTP の展開シナリオ](/previous-versions/tn-archive/bb124876(v=exchg.65))」

  - 「[Exchange 2003 での Outlook Anywhere を構成する方法](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))」

    > [!IMPORTANT]
    > Outlook Anywhere の構成は、信頼された証明機関 (CA) により発行された証明書を使用して行う必要があります。自己署名入りの証明書では構成できません。詳細については、「[Outlook Anywhere のために SSL を構成する方法](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))」を参照してください。

- **Outlook Anywhere を使用して Exchange 組織に接続できることを確認する。** 次のいずれかの方法で、接続設定をテストしてください:

  - 企業ネットワークの外部から Microsoft Outlook を使用して、社内 Exchange メールボックスに接続します。

  - Microsoft [Exchange リモート接続アナライザー](https://www.testexchangeconnectivity.com/)を使用して接続設定をテストします。Outlook Anywhere (RPC over HTTP) または Outlook 自動検出テストを使用します。

  - Exchange Online PowerShell で次のコマンドを実行します。

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Exchange 組織のメールボックスへのアクセスに必要なアクセス許可を社内ユーザー アカウントに割り当てる。** オンプレミスのExchange組織への接続に使用するオンプレミス ユーザー アカウント (移行管理者とも呼ばれます) には、Microsoft 365に移行するオンプレミスメールボックスにアクセスするために必要なアクセス許可が必要です。 このユーザー アカウントは、社内組織の移行エンドポイントを作成するために使用されます。

    以下の一覧に、一括移行を使用してメールボックスを移行するために必要な管理者権限を示します。3 つの可能なオプションがあります。

  - 移行管理者は、社内組織の Active Directory の **Domain Admins** グループのメンバーである必要がある。

    または

  - 移行管理者は、各社内メールボックスへの **フル アクセス** のアクセス許可が割り当てられている必要がある。

    または

  - 移行管理者は、ユーザーのメールボックスを格納する社内メールボックス データベースへの **受信者** アクセス許可が割り当てられている必要がある。

- **ユニファイド メッセージングを無効にする。** 移行する社内メールボックスでユニファイド メッセージング (UM) が有効である場合、メールボックスを移行する前にメールボックスで UM を無効にする必要があります。移行が完了すると、メールボックスで UM を有効にできます。

- **セキュリティ グループと代理人** 電子メール移行サービスは、オンプレミスの Active Directory グループがセキュリティ グループであるかどうかを検出できないため、移行されたグループをMicrosoft 365のセキュリティ グループとしてプロビジョニングすることはできません。 Microsoft 365 テナントにセキュリティ グループを含める場合は、一括移行を開始する前に、まず空のメールが有効なセキュリティ グループをMicrosoft 365 テナントにプロビジョニングする必要があります。 さらに、この移行方法では、メールボックス、メール ユーザー、メール連絡先、およびメールが有効なグループのみを移動します。 Microsoft 365に移行されていないユーザーなどの他の Active Directory オブジェクトが、移行するオブジェクトにマネージャーまたはデリゲートとして割り当てられている場合は、移行する前にオブジェクトから削除する必要があります。

### <a name="step-2-create-a-migration-endpoint"></a>ステップ 2:移行エンドポイントを作成する
<a name="BK_Step2"> </a>

電子メールを正常に移行するには、Microsoft 365ソース電子メール システムに接続して通信する必要があります。 これを行うために、Microsoft 365は移行エンドポイントを使用します。 一括移行用に Outlook Anywhere の移行エンドポイントを作成するには、最初に [リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)を行います。

移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](/powershell/exchange/)」を参照してください。

Exchange Online PowerShell で次のコマンドを実行します。

```powershell
$Credentials = Get-Credential
```

この例では、[Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) コマンドレットを使用して、社内の Exchange サーバーへの接続設定を取得およびテストしてから、この接続設定を使用して "CutoverEndpoint" という移行エンドポイントを作成します。

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> **New-MigrationEndpoint** コマンドレットで **-TargetDatabase** オプションを使用することによって、使用するサービスに対してデータベースを指定することができます。それ以外の場合、データベースは、管理メールボックスが配置されている Active Directory フェデレーション サービス (AD FS) 2.0 サイトからランダムに割り当てられます。

#### <a name="verify-it-worked"></a>機能していることを確認する

Exchange Online PowerShell で、次のコマンドを実行して "CutoverEndpoint" 移行エンドポイントに関する情報を表示します。

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>ステップ 3:一括移行バッチを作成する
<a name="BK_Step3"> </a>

Exchange Online PowerShell の **New-MigrationBatch** コマンドレットを使用すると、一括移行の移行バッチを作成できます。 _AutoStart_ パラメーターを含めると、移行バッチを作成して自動的に開始できます。また、別の方法として、 **Start-MigrationBatch** コマンドレットを使用することにより、移行バッチを作成して後で手動で開始できます。この例では、"CutoverBatch" という移行バッチを作成して、前の例で作成した移行エンドポイントを使用します。

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

この例でも、"CutoverBatch" という移行バッチを作成して、前の例で作成した移行エンドポイントを使用します。 _AutoStart_ パラメーターが含まれていないため、移行バッチは移行ダッシュボードで、または **Start-MigrationBatch** コマンドレットを使用して手動で開始する必要があります。前述のように、一度に存在できる一括移行バッチは 1 つだけです。

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>機能していることを確認する

一括移行用の移行バッチが正常に作成されたことを確認するには、Exchange Online PowerShell で次のコマンドを実行して、新しい移行バッチに関する情報を表示します。

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>ステップ 4:一括移行バッチを開始する

Exchange Online PowerShell で移行バッチを開始するには、次のコマンドを実行します。そうすると、"CutoverBatch" という移行バッチが作成されます。

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>機能していることを確認する

移行バッチが正常に開始されると、移行ダッシュボードのバッチの状態は「同期中」になります。Exchange Online PowerShell を使用して移行バッチが正常に開始したことを確認するには、次のコマンドを実行します。

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>手順 5: メールをMicrosoft 365にルーティングする

電子メール システムでは、電子メールを配信する場所を知るために、MX レコードと呼ばれる DNS レコードを使用します。 電子メールの移行プロセス中、MX レコードの宛先は移行元の電子メール システムでした。 Microsoft 365への電子メールの移行が完了したので、MX レコードをMicrosoft 365にポイントします。 これにより、メールがMicrosoft 365メールボックスに確実に配信されます。 MX レコードを移動することによって、準備ができたら古い電子メール システムをオフにすることもできます。

多くの DNS プロバイダーについては、MX レコードを変更するための具体的な手順があります。 使用している DNS プロバイダーが含まれていない場合、または一般的な手順を知りたい場合は、 [「MX レコードの一般的な手順」](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx)も参照してください。

御社のお客様およびパートナーの電子メール システムが MX レコードの変更を認識するまでに最大 72 時間かかることがあります。次の作業に進むまで、72 時間以上待ちます。 [ステップ 6:一括移行バッチを削除する](#step-6-delete-the-cutover-migration-batch).

### <a name="step-6-delete-the-cutover-migration-batch"></a>ステップ 6:一括移行バッチを削除する

MX レコードを変更し、すべてのメールがMicrosoft 365メールボックスにルーティングされていることを確認したら、メールがMicrosoft 365されることをユーザーに通知します。 その後、一括移行バッチを削除できます。 移行バッチを削除する前に、次の点を確認します。

- すべてのユーザーがMicrosoft 365メールボックスを使用しています。 バッチが削除されると、オンプレミスのExchange Server上のメールボックスに送信されたメールは、対応するMicrosoft 365メールボックスにコピーされません。

- Microsoft 365メールボックスは、メールが直接送信され始めた後、少なくとも 1 回は同期されました。 これを行うには、移行バッチの [最終同期時刻] ボックスの値が、メールがMicrosoft 365メールボックスに直接ルーティングされ始めた場合よりも新しく設定されていることを確認します。

Exchange Online PowerShell で "CutoverBatch" 移行バッチを削除するには、次のコマンドを実行します。

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>セクション 7:ユーザー ライセンスの割り当て

 **ライセンスを割り当てて、移行されたアカウントのMicrosoft 365ユーザー アカウントをアクティブ化します。** ライセンスを割り当てないと、猶予期間が終了したとき (30 日) にメールボックスが無効になります。 Microsoft 365 管理センターでライセンスを割り当てるには、「[ライセンスの割り当てまたは割り当ての解除](../admin/manage/assign-licenses-to-users.md)」を参照してください。

### <a name="step-8-complete-post-migration-tasks"></a>ステップ 8:移行後のタスクを完了する

- **ユーザーが各自のメールボックスに簡単にアクセスできるように、自動検出 DNS レコードを作成します。** すべてのオンプレミス メールボックスをMicrosoft 365に移行したら、Microsoft 365組織の自動検出 DNS レコードを構成して、ユーザーがOutlookおよびモバイル クライアントを使用して新しいMicrosoft 365 メールボックスに簡単に接続できるようにします。 この新しい自動検出 DNS レコードでは、Microsoft 365組織で使用しているのと同じ名前空間を使用する必要があります。 たとえば、クラウドベースの名前空間が cloud.contoso.com の場合、作成する必要のある自動検出 DNS レコードは autodiscover.cloud.contoso.com となります。

    Exchange Serverを維持する場合は、移行後に自動検出 DNS CNAME レコードが内部 DNS と外部 DNS の両方のMicrosoft 365を指すようにする必要があることを確認して、Outlook クライアントが正しいメールボックスに接続するようにする必要もあります。

    > [!NOTE]
    >  Exchange 2007、Exchange 2010、および Exchange 2013 では、 `Set-ClientAccessServer AutodiscoverInternalConnectionURI` を `Null` に設定する必要もあります。

    Microsoft 365では、CNAME レコードを使用して、Outlook およびモバイル クライアントの自動検出サービスを実装します。 自動検出 CNAME レコードには以下の情報が含まれている必要があります。

  - **エイリアス:** autodiscover

  - **リンク先:** autodiscover.outlook.com

    詳細については、[「DNS レコードを追加してドメインに接続する」](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)を参照してください。

- **社内の Exchange サーバーの使用を停止します。** すべての電子メールがMicrosoft 365メールボックスに直接ルーティングされていることを確認し、オンプレミスの電子メール組織を維持する必要がなくなったり、シングル サインオン (SSO) ソリューションを実装する予定がない場合は、サーバーからExchangeをアンインストールし、オンプレミスのExchange組織を削除できます。

    詳細については、以下を参照してください。

  - 「[Exchange 2010 の変更または削除](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))」

  - 「[Exchange 2007 組織を削除する方法](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))」

  - 「[Exchange Server 2003 をアンインストールする方法](/previous-versions/tn-archive/bb125110(v=exchg.65))」