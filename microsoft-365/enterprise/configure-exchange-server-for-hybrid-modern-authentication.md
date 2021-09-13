---
title: Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: ハイブリッドモダン認証 (HMA) Exchange Serverを使用して、より安全なユーザー認証と承認を提供する、オンプレミスのユーザー認証を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7a24e2c9d1e3d2fd2d1d83d9743b6f4e19e9701
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221070"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ハイブリッドモダン認証 (HMA) は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、Exchange サーバーのオンプレミスハイブリッド展開で使用できます。

## <a name="fyi"></a>FYI

開始する前に、次の呼び出しを行います。

- ハイブリッドモダン認証 \> HMA

- Exchangeオンプレミス \> EXCH

- \>Exchange OnlineEXO

また、この記事のグラフィックに、灰色で表示される要素が *HMA* 固有の構成に含まれていないという'灰色表示' または "淡色" のオブジェクトがある場合。

## <a name="enabling-hybrid-modern-authentication"></a>ハイブリッドモダン認証の有効化

HMA をオンにすると、次の意味があります。

1. 開始する前にプレレポートを満たしてください。

1. 多くの **前提条件は**、Skype for Business と Exchange の両方で一般的です。ハイブリッドモダン認証の概要と、オンプレミスの Skype for Business サーバーと Exchange [サーバー](hybrid-modern-auth-overview.md)で使用するための前提条件です。 この記事の手順を開始する前に、これを行います。

1. Azure サーバーにサービス プリンシパル名 **(SPN)** としてオンプレミス Web サービス URL を追加AD。 EXCH が複数のテナントとハイブリッドである場合、これらのオンプレミス Web サービス URL は、EXCH とのハイブリッドにあるすべてのテナントの Azure AD で SPN として追加する必要があります。

1. すべての仮想ディレクトリが HMA に対して有効になっているか確認する

1. EvoSTS Auth Server オブジェクトの確認

1. EXCH で HMA を有効にする。

> [!NOTE]
> お使いのバージョンのOfficeサポートMA? [「2013 年および 2016 年 2016](modern-auth-for-office-2013-and-2016.md)年のクライアント アプリOffice最新の認証のしくみOfficeを参照してください。


## <a name="make-sure-you-meet-all-the-prerequisites"></a>すべての前提条件を満たしていることを確認する

多くの前提条件は、Skype for Business と Exchange Skype for Business の両方で一般的なので、ハイブリッドモダン認証の概要と、オンプレミスのサーバーと Exchange サーバーで使用するための前提条件を[確認してください](hybrid-modern-auth-overview.md)。 この記事  *の手順*  を開始する前に、これを行います。

> [!NOTE]
> Outlook Web AppおよびExchangeコントロール パネルはハイブリッドモダン認証では機能しません。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Azure サーバーにオンプレミス Web サービス URL を SPN として追加AD

オンプレミスの Web サービス URL を Azure または SPN として割り当てるAD実行します。 SPN は、認証と承認の間にクライアント コンピューターとデバイスで使用されます。 オンプレミスから Azure Active Directory (Azure AD) への接続に使用できるすべての URL は、Azure AD に登録する必要があります (これには、内部名前空間と外部名前空間の両方が含まれます)。

最初に、AAD に追加する必要があるすべての URL を収集します。 オンプレミスで次のコマンドを実行します。

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

クライアントが接続できる URL が、AAD の HTTPS サービス プリンシパル名として一覧表示されます。 EXCH が複数のテナントとハイブリッドの場合、これらの HTTPS SPN は EXCH とのハイブリッドのすべてのテナントの AAD に追加する必要があります。

1. まず、次の手順で AAD [に接続します](connect-to-microsoft-365-powershell.md)。

    > [!NOTE]
    > 以下のコマンドを _使用するには、このページConnect-MsolService_ オプションを使用する必要があります。

2. ユーザーに関連Exchange URL の場合は、次のコマンドを入力します。

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   このコマンドの出力には https://  *autodiscover.yourdomain.com*  と https:// mail.yourdomain.com  *URL* を含める必要がありますが、主に 000000002-00000-0ff1-ce000-0000-00000000000/で始まる SPN で構成されます。このコマンドの出力をメモします (および後で比較する場合はスクリーンショットを参照してください)。 不足している https:// の URL が存在する場合は、これらの特定のレコードをこの一覧に追加する必要があります。

3. この一覧に内部および外部の MAPI/HTTP、EWS、ActiveSync、OAB、および自動検出レコードが表示されていない場合は、以下のコマンドを使用して追加する必要があります (URL の例は ' と ' ' ですが、サンプル URL を独自の URL に置き換えます)。 `mail.corp.contoso.com` `owa.contoso.com` 

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 手順 2 から Get-MsolServicePrincipalコマンドを実行し、出力を確認して、新しいレコードが追加されたのを確認します。 前のリスト/スクリーンショットと SPN の新しいリストを比較します。 レコードの新しいリストのスクリーンショットを撮る場合があります。 成功した場合は、一覧に 2 つの新しい URL が表示されます。 この例では、SPN の一覧に特定の URL と  `https://mail.corp.contoso.com`  `https://owa.contoso.com` .

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

OAuth がサーバーと 4 つの仮想ディレクトリから見つからない場合は、処理を進む前に関連するコマンドを使用して追加する必要があります[(Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory) [、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory、Set-AutodiscoverVirtualDirectory)。](/powershell/module/exchange/set-webservicesvirtualdirectory) [](/powershell/module/exchange/set-oabvirtualdirectory) [](/powershell/module/exchange/set-autodiscovervirtualdirectory)

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>EvoSTS Auth Server オブジェクトが存在するを確認する

この最後のコマンドのオンプレミス Exchange管理シェルに戻します。 これで、オンプレミスに evoSTS 認証プロバイダーのエントリが含まれます。

```powershell
Get-AuthServer | where {$_.Name -like "*EvoSts*"}
```

出力に Name EvoSts の AuthServer が表示され、'Enabled' 状態は True である必要があります。 これが表示されていない場合は、最新バージョンのハイブリッド構成ウィザードをダウンロードして実行する必要があります。

> [!NOTE]
> EXCH が複数のテナントとハイブリッドになっている場合、出力には、EXCH とハイブリッドの各テナントの Name EvoSts - {GUID} の 1 つの AuthServer が表示され、これらすべての AuthServer オブジェクトに対して 'Enabled' 状態が True である必要があります。

 **重要** 環境で 2010 Exchangeを実行している場合、EvoSTS 認証プロバイダーは作成されません。

## <a name="enable-hma"></a>HMA を有効にする

オンプレミスの管理シェルでExchangeコマンドを実行します。

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

EXCH バージョンが Exchange 2016 (CU18 以上) または Exchange 2019 (CU7 以上) で、ハイブリッドが 2020 年 9 月以降にダウンロードされた HCW で構成されている場合は、オンプレミスの Exchange 管理シェルで次のコマンドを実行します。

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> EXCH が複数のテナントとハイブリッドである場合、EXCH には複数の AuthServer オブジェクトが存在し、各テナントに対応するドメインがあります。  **IsDefaultAuthorizationEndpoint** フラグは、これらの AuthServer オブジェクトの 1 つについて true に設定する必要があります **(IsDefaultAuthorizationEndpoint** コマンドレットを使用)。 すべての Authserver オブジェクトに対してこのフラグを true に設定することはできません。これらの AuthServer オブジェクトの **IsDefaultAuthorizationEndpoint** フラグの 1 つが true に設定されている場合でも、HMA は有効になります。

## <a name="verify"></a>確認する

HMA を有効にした後、クライアントの次のログインでは新しい認証フローが使用されます。 HMA をオンにしてもクライアントの再認証はトリガーされず、Exchange が新しい設定を取得するには時間がかかる場合があります。

また、ctrl キーを押しながら Outlook クライアントのアイコン (Windows 通知トレイ) を右クリックし、[接続状態] をクリックします。 OAuth で使用されるベアラー トークンを表す 'Bearer'の 'Authn' 型に対してクライアントの SMTP アドレス \* を探します。

> [!NOTE]
> HMA を使用してSkype for Business構成する必要がありますか? 2 つの記事が必要です。1 つは、サポートされているトポロジを一覧表示する記事と、構成を実行する方法[を示す記事です](configure-skype-for-business-for-hybrid-modern-authentication.md)。 [](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>iOS および Android 用の Outlook でのハイブリッド先進認証の使用

オンプレミスのお客様が TCP 443 Exchangeサーバーを使用している場合は、次の IP アドレス範囲のトラフィック処理をバイパスします。

```text
52.125.128.0/20
52.127.96.0/23
```

iOS と Android 用 Outlook アプリは、Microsoft サービス を使用して、Microsoft 365 または Office 365 をモバイル デバイスで体験し、日常の生活と仕事を見つけ、計画し、優先順位を付ける最善の方法として設計されています。 詳細については、「ハイブリッドモダン認証と iOS および Android のOutlookを使用する[」を参照してください](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。

## <a name="related-topics"></a>関連項目

[専用/ITAR から vNext への移行Office 365認証の最新の構成要件](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
