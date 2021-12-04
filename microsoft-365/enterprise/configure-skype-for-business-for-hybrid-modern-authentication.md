---
title: Skype for Business をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: ハイブリッドモダン認証 (HMA) Skype for Businessを使用して、より安全なユーザー認証と承認を提供するために、オンプレミスのユーザー認証を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dd42aa6befdbb646217a9829dd59c0821fbd29d3
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301188"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Skype for Business をオンプレミスで構成して、ハイブリッド先進認証を使用するには

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

モダン認証は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、Skype for Business サーバーオンプレミスおよび Exchange サーバーオンプレミス、およびスプリットドメイン Skype for Business ハイブリッドで利用できます。

> [!IMPORTANT]
> モダン認証 (MA) の詳細と、会社や組織で使用する理由について知りたがっていますか? 概要 [については、](hybrid-modern-auth-overview.md) このドキュメントを確認してください。 この機能でサポートSkype for BusinessトポロジをMAする必要がある場合は、ここで説明します。

**開始する前に**、次の用語を使用します。

- モダン認証 (MA)

- ハイブリッドモダン認証 (HMA)

- Exchangeオンプレミス (EXCH)

- Exchange Online (EXO)

- Skype for Businessオンプレミス (SFB)

- Skype for Business オンライン (SFBO)

また、この記事のグラフィックにグレー表示または淡色表示のオブジェクトがある場合は、灰色で表示される要素が MA固有の構成に含まれません。

## <a name="read-the-summary"></a>概要を読む

この概要では、プロセスを実行中に迷子になる可能性がある手順に分け、全体のチェックリストでプロセスの場所を追跡できます。

1. 最初に、すべての前提条件を満たしていることを確認します。

1. 多くの **前提条件は**、Skype for BusinessとExchangeに共通していますので、プレ req チェックリストの概要 [の記事を参照してください](hybrid-modern-auth-overview.md)。 この記事  *の手順*  を開始する前に、これを行います。

1. ファイルまたはファイルに必要な HMA 固有の情報を収集OneNote。

1. EXO のモダン認証を有効にします (まだ有効にしていない場合)。

1. SFBO のモダン認証を有効にします (まだ有効ではない場合)。

1. オンプレミスのハイブリッドモダン認証Exchangeオンにします。

1. オンプレミスのハイブリッドモダン認証Skype for Businessオンにします。

これらの手順は、SFB、SFBO、EXCH、EXO の MA を有効にします。つまり、SFB と SFBO の HMA 構成に参加できるすべての製品 (EXCH/EXO への依存関係を含む)。 つまり、ユーザーがハイブリッドの任意の部分 (EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB) にメールボックスを作成している場合、完成した製品は次のように表示されます。

![ビジネス HMA トポロジSkype 6 個の混在したMA 4 つの場所すべてでオンに設定されています。](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

ご覧のように、この機能を有効にする場所は 4 MA! 最適なユーザー エクスペリエンスを得る場合は、これらの 4 つの場所MAを有効にすることをお勧めします。 これらのすべての場所で MA をオンにできない場合は、環境に必要な場所でのみ MA を有効にできるよう手順を調整します。

サポートされている[トポロジについては、「サポートSkype for Business MA」](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)を参照してください。

> [!IMPORTANT]
> 開始する前に、すべての前提条件を満たしていることを確認してください。 この情報については、「ハイブリッドモダン認証の概要 [と前提条件」を参照してください](hybrid-modern-auth-overview.md)。

## <a name="collect-all-hma-specific-info-youll-need"></a>必要なすべての HMA 固有の情報を収集する

モダン認証を使用するための前提条件を満たしていることを確認[](hybrid-modern-auth-overview.md)した後 (上記のメモを参照)、前の手順で HMA を構成するために必要な情報を保持するファイルを作成する必要があります。 この記事で使用される例を次に示します。

- **SIP/SMTP ドメイン**

  - 例 contoso.com (サーバーとOffice 365)

- **テナント ID**

  - テナント (Office 365ログイン時) を表す GUID contoso.onmicrosoft.com。

- **SFB 2015 CU5 Web サービス URL**

すべての SfB 2015 プールを展開するには、内部および外部の Web サービス URL が必要です。 これらを取得するには、管理シェルから次Skype for Business実行します。

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- 例 内部: https://lyncwebint01.contoso.com

- 例 外部: https://lyncwebext01.contoso.com

サーバーを使用しているStandard Edition内部 URL は空白になります。 この場合は、内部 URL にプール fqdn を使用します。

## <a name="turn-on-modern-authentication-for-exo"></a>EXO のモダン認証を有効にする

次の手順に従います[:Exchange Online: 最新の認証のためにテナントを有効にする方法。](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)

## <a name="turn-on-modern-authentication-for-sfbo"></a>SFBO のモダン認証を有効にする

次の手順に従います[:Skype for Business: モダン認証のためにテナントを有効にします](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>オンプレミスのハイブリッドモダン認証Exchange有効にする

手順については、「ハイブリッドモダン認証を使用Exchange Serverオンプレミスで構成する方法」[を参照してください](configure-exchange-server-for-hybrid-modern-authentication.md)。

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>オンプレミスのハイブリッドモダン認証Skype for Business有効にする

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>オンプレミスの Web サービス URL を SPN として追加Azure Active Directory

これで、SFBO のサービス プリンシパルとして URL (前に収集) を追加するコマンドを実行する必要があります。

> [!NOTE]
> サービス プリンシパル名 (SPN) は、Web サービスを識別し、それらをセキュリティ プリンシパル (アカウント名やグループなど) に関連付けて、サービスが承認されたユーザーの代理として機能します。 サーバーに対して認証されるクライアントは、SPN に含まれる情報を利用します。

1. まず、次の手順Azure Active Directory (Azure AD)[に接続します](/powershell/azure/active-directory/overview)。

2. このコマンドをオンプレミスで実行して、SFB Web サービス URL の一覧を取得します。

   AppPrincipalId はで始まる点に注意してください `00000004` 。 これはオンラインのSkype for Businessします。

   このコマンドの出力には Standard Edition URL と WS URL が含まれますが、主にで始まる SPN で構成されます。 `00000004-0000-0ff1-ce00-000000000000/`

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
   ```

3. 社内 **の内部または** 外部の SFB URL が見つからない場合 (たとえば、これらの特定のレコードをこのリスト https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) に追加する必要があります)。

    [追加] コマンド  *で、以下の URL の* 例を実際の URL に置き換える必要があります。

    ```powershell
    $x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
    $x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
    $x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
    Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
    ```

4. 手順 2 から **Get-MsolServicePrincipal** コマンドを再度実行し、出力を確認して、新しいレコードが追加されたのを確認します。 前のリストまたはスクリーンショットを SPN の新しいリストと比較します。 レコードの新しいリストのスクリーンショットを撮る場合があります。 成功した場合は、リストに 2 つの新しい URL が表示されます。 この例では、SPN の一覧に特定の URL と https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>EvoSTS Auth Server オブジェクトの作成

管理シェルで次のコマンドSkype for Business実行します。

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>ハイブリッドモダン認証の有効化

これは、実際にユーザー設定をオンにするMA。 前のすべての手順は、クライアント認証フローを変更せずに、前もって実行できます。 認証フローを変更する準備ができたら、管理シェルでこのコマンドSkype for Business実行します。

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>確認する

HMA を有効にした後、クライアントの次のログインでは新しい認証フローが使用されます。 HMA をオンにしても、クライアントに対して再認証がトリガーされるという点に注意してください。 クライアントは、持っている認証トークンまたは証明書の有効期間に基づいて再認証されます。

HMA が有効にした後で動作しているテストを行う場合は、テスト SFB クライアントからサインアウトしWindows [資格情報の削除] をクリックしてください。 もう一度サインインします。 クライアントはモダン **認証** フローを使用する必要があります。ログインには、クライアントがサーバーに接続してログインする直前に表示される「仕事または学校」アカウントの Office 365 プロンプトが含まれます。

また、「OAuth Authority」のクライアントのSkype for Business構成情報を確認する必要があります。 クライアント コンピューターでこれを行うには、Ctrl キーを押しながら、[通知] トレイの [Skype for Business アイコンWindowsクリックします。 表示 **されるメニューの** [構成情報] をクリックします。 デスクトップに表示Skype for Business [構成情報] ウィンドウで、次の情報を探します。

:::image type="content" alt-text="モダン認証を使用する Skype for Businessクライアントの構成情報には、 の Lync および EWS OAUTH Authority URL が表示されます https://login.windows.net/common/oauth2/authorize 。" source="../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png":::

また、ctrl キーを押しながら Outlook クライアントのアイコン (Windows 通知トレイ) を右クリックし、[接続状態] をクリックします。 OAuth で使用されるベアラー トークンを表す'Bearer'の AuthN 型に対してクライアントの SMTP アドレス \* を探します。

## <a name="related-articles"></a>関連記事

[モダン認証の概要にリンクします](hybrid-modern-auth-overview.md)。

最新の認証をクライアントに使用する方法を知るSkype for Businessですか? ここでは、ハイブリッドモダン認証の概要と、オンプレミスのサーバーおよびサーバーで使用するためのSkype for Business[前提条件Exchangeがあります](./hybrid-modern-auth-overview.md)。
