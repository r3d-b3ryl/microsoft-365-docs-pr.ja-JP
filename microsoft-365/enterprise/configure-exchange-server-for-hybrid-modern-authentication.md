---
title: Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/27/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: ハイブリッドモダン認証 (HMA) Exchange Serverを使用して、より安全なユーザー認証と承認を提供する、オンプレミスのユーザー認証を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0889008595717308695c1ad9c5d2a9f1766d1ea
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61934491"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ハイブリッドモダン認証 (HMA) は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、Exchange サーバーのオンプレミスハイブリッド展開で使用できます。

## <a name="definitions"></a>定義

始める前に、いくつかの定義に精通している必要があります。

- ハイブリッドモダン認証 \> HMA

- Exchangeオンプレミス \>EXCH

- Exchange Online \> EXO

また、この記事のグラフィックに、灰色で表示される要素が *HMA* 固有の構成に含まれていないという'灰色表示' または "淡色" のオブジェクトがある場合。

## <a name="enabling-hybrid-modern-authentication"></a>ハイブリッドモダン認証の有効化

HMA をオンにすると、次の意味があります。

1. 開始する前にプレレポートを満たしてください。

1. 多くの **前提条件は**、Skype for Business と Exchange の両方で一般的です。ハイブリッドモダン認証の概要と、オンプレミスの Skype for Business サーバーと Exchange [サーバー](hybrid-modern-auth-overview.md)で使用するための前提条件です。 この記事の手順を開始する前に、これを行います。
挿入するリンクされたメールボックスに関する要件。

1. オンプレミスの Web サービス URL をサービス プリンシパル **名 (SPN)** として追加Azure AD。 EXCH が複数のテナントとハイブリッドである場合、これらのオンプレミス Web サービス URL は、EXCH とのハイブリッドにあるすべてのテナントの Azure AD で SPN として追加する必要があります。

1. すべての仮想ディレクトリが HMA に対して有効になっているか確認する

1. EvoSTS Auth Server オブジェクトの確認

1. EXCH で HMA を有効にする。

> [!NOTE]
> お使いのバージョンのOfficeサポートMA? [「2013 年および 2016 年 2016](modern-auth-for-office-2013-and-2016.md)年のクライアント アプリOffice最新の認証のしくみOfficeを参照してください。

## <a name="make-sure-you-meet-all-the-prerequisites"></a>すべての前提条件を満たしていることを確認する

多くの前提条件は、Skype for Business と Exchange Skype for Business の両方で一般的なので、ハイブリッドモダン認証の概要と、オンプレミスのサーバーと Exchange サーバーで使用するための前提条件を[確認してください](hybrid-modern-auth-overview.md)。 この記事  *の手順*  を開始する前に、これを行います。

> [!NOTE]
> Outlook Web AppおよびExchangeコントロール パネルはハイブリッドモダン認証では機能しません。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>オンプレミスの Web サービス URL を SPN として追加Azure AD

オンプレミス Web サービス URL を SPN として割り当てるコマンドAzure ADします。 SPN は、認証と承認の間にクライアント コンピューターとデバイスで使用されます。 オンプレミスから Azure Active Directory (Azure AD) への接続に使用される可能性があるすべての URL を Azure AD に登録する必要があります (これには、内部名前空間と外部名前空間の両方が含まれます)。

最初に、追加する必要があるすべての URL をグループにAAD。 オンプレミスで次のコマンドを実行します。

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*hostname*
```

クライアントが接続できる URL が HTTPS サービス プリンシパル名として一覧表示AAD。 EXCH が複数のテナントとハイブリッドである場合、これらの HTTPS SPN は EXCH とのハイブリッドのすべてのテナントの AAD に追加する必要があります。

1. 最初に、次の手順AADに[接続します](connect-to-microsoft-365-powershell.md)。

    > [!NOTE]
    > 以下のコマンドを _使用するには、このページConnect-MsolService_ オプションを使用する必要があります。

2. ユーザーに関連Exchange URL の場合は、次のコマンドを入力します。

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   このコマンドの出力は、URL を含める必要がありますが、主にで始まる SPN で構成されるこのコマンドの出力に注意してください (および後で比較する場合はスクリーンショットを `https://*autodiscover.yourdomain.com*` `https://*mail.yourdomain.com*` 参照してください `00000002-0000-0ff1-ce00-000000000000/` )。 オンプレミスの URL が見つからない場合は、これらの特定のレコード `https://` をこの一覧に追加する必要があります。

3. この一覧に内部および外部の MAPI/HTTP、EWS、ActiveSync、OAB、および自動検出レコードが表示されていない場合は、以下のコマンドを使用して追加する必要があります (URL の例は次のとおりですが、URL の例を独自の URL に置き換えます)。 `mail.corp.contoso.com` `owa.contoso.com` 

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 手順 2 からコマンドを再度実行し、出力を確認して、新しいレコードが追加 `Get-MsolServicePrincipal` されたのを確認します。 前のリスト/スクリーンショットと SPN の新しいリストを比較します。 レコードの新しいリストのスクリーンショットを撮る場合があります。 成功した場合は、一覧に 2 つの新しい URL が表示されます。 この例では、SPN の一覧に特定の URL と `https://mail.corp.contoso.com` `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>仮想ディレクトリが適切に構成されていることを確認する

次に、次のコマンドを実行Exchange使用する可能性があるすべての仮想ディレクトリ Outlookで OAuth が正しく有効になっているか確認します。

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

出力を確認して、 **これらの各 VDir** で OAuth が有効になっていることを確認します。次のように表示されます (また、重要な確認は 'OAuth' です)。

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

OAuth がサーバーと 4 つの仮想ディレクトリから欠落している場合は、処理を進む前に関連するコマンドを使用して追加する必要があります[(Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory) [、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory、Set-AutodiscoverVirtualDirectory)。](/powershell/module/exchange/set-webservicesvirtualdirectory) [](/powershell/module/exchange/set-oabvirtualdirectory) [](/powershell/module/exchange/set-autodiscovervirtualdirectory)

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>EvoSTS Auth Server オブジェクトが存在するを確認する

この最後のコマンドのオンプレミス Exchange管理シェルに戻します。 これで、オンプレミスに evoSTS 認証プロバイダーのエントリが含まれます。

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts*"} | ft name,enabled
```

出力には、GUID を持つ Name EvoSts の AuthServer が表示され、'Enabled' 状態は True である必要があります。 これが表示されていない場合は、最新バージョンのハイブリッド構成ウィザードをダウンロードして実行する必要があります。

> [!NOTE]
> EXCH が複数のテナントとハイブリッドになっている場合、出力に EXCH とのハイブリッドの各テナントの Name の 1 つの AuthServer が表示され、これらの `EvoSts - {GUID}` AuthServer オブジェクトのすべてで Enabled 状態がTrue である必要があります。

> [!IMPORTANT]
> 環境で 2010 Exchangeを実行している場合、EvoSTS 認証プロバイダーは作成されません。

## <a name="enable-hma"></a>HMA を有効にする

オンプレミスの Exchange管理シェルで次のコマンドを実行し、コマンド ラインで環境内の文字列 \<GUID\> に置き換えます。

```powershell
Set-AuthServer -Identity "EvoSTS - <GUID>" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> ハイブリッド構成ウィザードの以前のバージョンでは、EvoSts AuthServer は GUID が添付されていない EvoSTS という名前でした。 実行する必要のあるアクションはありません。上記のコマンド ラインを変更して、コマンドの GUID 部分を削除してこれを反映します。
>
> ```powershell
> Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
> ```

EXCH バージョンが Exchange 2016 (CU18 以上) または Exchange 2019 (CU7 以上) で、ハイブリッドが 2020 年 9 月以降にダウンロードされた HCW で構成されている場合は、オンプレミスの Exchange 管理シェルで次のコマンドを実行します。

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> EXCH が複数のテナントとハイブリッドである場合、EXCH には複数の AuthServer オブジェクトが存在し、各テナントに対応するドメインがあります。  **IsDefaultAuthorizationEndpoint** フラグは、これらの AuthServer オブジェクトの 1 つについて true に設定する必要があります **(IsDefaultAuthorizationEndpoint** コマンドレットを使用)。 すべての Authserver オブジェクトに対してこのフラグを true に設定することはできません。これらの AuthServer オブジェクトの **IsDefaultAuthorizationEndpoint** フラグの 1 つが true に設定されている場合でも、HMA は有効になります。
> 
> **DomainName パラメーターの** 場合は、テナント ドメインの値を使用します。これは、通常はフォームです `contoso.onmicrosoft.com` 。

## <a name="verify"></a>確認する

HMA を有効にした後、クライアントの次のログインでは新しい認証フローが使用されます。 HMA をオンにしてもクライアントの再認証はトリガーされず、Exchange が新しい設定を取得するには時間がかかる場合があります。

また、ctrl キーを押しながら Outlook クライアントのアイコン (Windows 通知トレイ) を右クリックし、[接続状態] をクリックします。 OAuth で使用されるベアラー トークンを表す **Authn** 型に対してクライアントの SMTP アドレス `Bearer\*` を探します。

> [!NOTE]
> HMA を使用してSkype for Business構成する必要がありますか? 2 つの記事が必要です。1 つは、サポートされているトポロジを一覧表示する記事と、構成を実行する方法[を示す記事です](configure-skype-for-business-for-hybrid-modern-authentication.md)。 [](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>iOS および Android 用の Outlook でのハイブリッド先進認証の使用

オンプレミスのお客様が TCP 443 の Exchangeサーバーを使用している場合は、次の IP 範囲からのネットワーク トラフィックを許可します。

```console
52.125.128.0/20
52.127.96.0/23
```

これらの IP アドレス範囲は、「IP アドレスと URL Web サービスに含まれていない追加[Office 365」にも記載されています](/microsoft-365/enterprise/additional-office365-ip-addresses-and-urls)。

## <a name="related-topics"></a>関連項目

[専用/ITAR から vNext への移行Office 365認証の最新の構成要件](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
