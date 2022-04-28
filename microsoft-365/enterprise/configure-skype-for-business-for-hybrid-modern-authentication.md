---
title: Skype for Business をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: scotv
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
description: ハイブリッドモダン認証 (PFX) を使用するようにオンプレミスでSkype for Businessを構成し、より安全なユーザー認証と承認を提供する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f5e48905416f84ed1a4c48f7e6f1a4b6477f73e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093484"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Skype for Business をオンプレミスで構成して、ハイブリッド先進認証を使用するには

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

先進認証は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、オンプレミスのSkype for Business サーバーとExchange サーバー、および分割ドメインSkype for Businessハイブリッドで使用できます。

> [!IMPORTANT]
> 先進認証 (MA) の詳細と、会社または組織で使用する理由について詳しく知りたいと思いますか? [概要については、このドキュメント](hybrid-modern-auth-overview.md)を参照してください。 MA でサポートされているトポロジSkype for Business知る必要がある場合は、こちらに記載されています。

**始める前に**、次の用語を使用します。

- 先進認証 (MA)

- ハイブリッド先進認証 (1)

- Exchange オンプレミス (EXCH)

- Exchange Online (EXO)

- Skype for Business オンプレミス (SFB)

- Skype for Business Online (SFBO)

また、この記事のグラフィックに灰色表示または淡色表示のオブジェクトがある場合は、灰色で表示される要素が MA 固有の構成に含 **まれていないことを** 意味します。

## <a name="read-the-summary"></a>概要を読む

この概要は、実行中に失われる可能性があるステップにプロセスを分解し、プロセスの場所を追跡するための全体的なチェックリストに適しています。

1. まず、すべての前提条件を満たしていることを確認します。

1. 多くの **前提条件** はSkype for BusinessとExchangeの両方で一般的であるため、[前提条件チェックリストの概要に関する記事を参照してください](hybrid-modern-auth-overview.md)。 この記事の手順を開始する  *前*  に、この操作を行います。

1. ファイルに必要な PFX 固有の情報を収集するか、OneNoteします。

1. EXO の先進認証をオンにします (まだオンになっていない場合)。

1. SFBO の先進認証をオンにします (まだ有効になっていない場合)。

1. オンプレミスのExchangeのハイブリッドモダン認証をオンにします。

1. オンプレミスのSkype for Businessのハイブリッドモダン認証をオンにします。

これらの手順では、SFB、SFBO、EXCH、および EXO の MA が有効になります。つまり、SFB と SFBO の  KF 構成に参加できるすべての製品 (EXCH/EXO への依存関係を含む)。 つまり、ユーザーがハイブリッドの任意の部分 (EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB) で作成されたメールボックスを持っている場合、完成した製品は次のようになります。

![ビジネス  PFX トポロジの混合 6 Skypeには、4 つの場所すべてで MA が適用されます。](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

ご覧のように、MA を有効にする場所は 4 つあります。 最適なユーザー エクスペリエンスを得るには、これらの 4 つの場所すべてで MA を有効にすることをお勧めします。 これらのすべての場所で MA を有効にできない場合は、環境に必要な場所でのみ MA を有効にするように手順を調整します。

サポートされているトポロジについては、[MA を使用したSkype for Businessのサポート可能性](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)に関するトピックを参照してください。

> [!IMPORTANT]
> 開始する前に、すべての前提条件が満たされていることを再確認してください。 その情報は、 [ハイブリッド先進認証の概要と前提条件に関するページに記載されています](hybrid-modern-auth-overview.md)。

## <a name="collect-all-hma-specific-info-youll-need"></a>必要なすべての   HMA 固有の情報を収集する

先進認証を使用するための [前提条件](hybrid-modern-auth-overview.md) を満たしていることを再確認した後 (上記の注を参照)、PFX を構成するために必要な情報を保持するファイルを作成する必要があります。 この記事で使用する例:

- **SIP/SMTP ドメイン**

  - 例 contoso.com (Office 365とのフェデレーション)

- **テナント ID**

  - Office 365 テナントを表す GUID (contoso.onmicrosoft.com のログイン時)。

- **SFB 2015 CU5 Web サービス URL**

デプロイされたすべての SfB 2015 プールには、内部および外部の Web サービス URL が必要です。 これらを取得するには、Skype for Business Management Shell から次のコマンドを実行します。

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- 例 内部： https://lyncwebint01.contoso.com

- 例 外部： https://lyncwebext01.contoso.com

Standard Edition サーバーを使用している場合、内部 URL は空白になります。 この場合は、内部 URL にプール fqdn を使用します。

## <a name="turn-on-modern-authentication-for-exo"></a>EXO の先進認証を有効にする

「[Exchange Online: テナントでモダン認証を有効にする方法」の手順に](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)従います。

## <a name="turn-on-modern-authentication-for-sfbo"></a>SFBO の先進認証を有効にする

「[Skype for Business Online: テナントを最新の認証に有効にする」の手順に](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)従います。

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>オンプレミスのExchangeのハイブリッドモダン認証を有効にする

「[ハイブリッドモダン認証を使用するようにオンプレミスExchange Server構成する方法](configure-exchange-server-for-hybrid-modern-authentication.md)」の手順に従います。

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>オンプレミスのSkype for Businessのハイブリッドモダン認証を有効にする

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Azure Active Directoryでオンプレミス Web サービス URL を SPN として追加する

次に、コマンドを実行して、SFBO のサービス プリンシパルとして URL (以前に収集) を追加する必要があります。

> [!NOTE]
> サービス プリンシパル名 (SPN) は Web サービスを識別し、サービスが承認されたユーザーに代わって動作できるように、それらをセキュリティ プリンシパル (アカウント名やグループなど) に関連付けます。 サーバーに対して認証を行うクライアントは、SPN に含まれる情報を利用します。

1. まず、次の手順に従ってAzure Active Directory (Azure AD) に接続[します](/powershell/azure/active-directory/overview)。

2. このコマンドをオンプレミスで実行して、SFB Web サービス URL の一覧を取得します。

   AppPrincipalId はで始まる点に `00000004`注意してください。 これは、Skype for Business Online に対応します。

   このコマンドの出力には、Standard Editionと WS URL が含まれますが、ほとんどの場合は SPN で始まる (後で`00000004-0000-0ff1-ce00-000000000000/`比較するためのスクリーンショット) ことに注意してください。

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
   ```

3. オンプレミスの内部 **または** 外部の SFB URL が見つからない場合 (たとえば、 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) これらの特定のレコードをこのリストに追加する必要があります)。

    次  *の例の URL は* 、Add コマンドの実際の URL に置き換えてください。

    ```powershell
    $x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
    $x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
    $x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
    Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
    ```

4. 手順 2 から **Get-MsolServicePrincipal** コマンドをもう一度実行し、出力を調べて、新しいレコードが追加されたことを確認します。 前のリストまたはスクリーンショットを SPN の新しいリストと比較します。 レコードの新しい一覧のスクリーンショットを撮ることもできます。 成功した場合は、2 つの新しい URL が一覧に表示されます。 この例では、SPN の一覧に特定の URL と https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/.

### <a name="create-the-evosts-auth-server-object"></a>EvoSTS 認証サーバー オブジェクトを作成する

Skype for Business管理シェルで次のコマンドを実行します。

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>ハイブリッドモダン認証を有効にする

これは、実際に MA をオンにする手順です。 前の手順はすべて、クライアント認証フローを変更せずに事前に実行できます。 認証フローを変更する準備ができたら、Skype for Business Management Shell でこのコマンドを実行します。

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>確認

PFX を有効にすると、クライアントの次のログインで新しい認証フローが使用されます。 PFX をオンにするだけでは、クライアントの再認証はトリガーされないことに注意してください。 クライアントは、認証トークンまたは証明書の有効期間に基づいて再認証します。

有効にした後で  PFX が動作していることをテストするには、テスト SFB Windows クライアントからサインアウトし、必ず [資格情報の削除] をクリックします。 もう一度サインインします。 クライアントは Modern Auth フローを使用する必要があり、ログインには、クライアントがサーバーに接続してログインする直前に表示される"職場または学校" アカウントの **Office 365プロンプトが** 含まれるようになりました。

また、"OAuth 機関" のSkype for Business クライアントの "構成情報" も確認する必要があります。 クライアント コンピューターでこれを行うには、Ctrl キーを押しながら、Windows通知トレイの [Skype for Business アイコン] を右クリックします。 表示されるメニューで [ **構成情報]** をクリックします。 デスクトップに表示される [Skype for Business構成情報] ウィンドウで、次を探します。

:::image type="content" alt-text="先進認証を使用するSkype for Business クライアントの構成情報には、Lync と EWS OAUTH 機関の https://login.windows.net/common/oauth2/authorizeURL が表示されます。" source="../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png":::

また、Ctrl キーを押しながら、Outlook クライアントのアイコン (Windows通知トレイでも) を右クリックし、[接続状態] をクリックする必要があります。 OAuth で使用されるベアラー トークンを表す AuthN 型の 'Bearer\*' に対してクライアントの SMTP アドレスを探します。

## <a name="related-articles"></a>関連記事

[モダン認証の概要に戻ります](hybrid-modern-auth-overview.md)。

Skype for Business クライアントにモダン認証を使用する方法を知る必要がありますか? ここでは、[ハイブリッド先進認証の概要と、それをオンプレミスのSkype for BusinessおよびExchange サーバーで使用するための前提条件](./hybrid-modern-auth-overview.md)について説明します。
