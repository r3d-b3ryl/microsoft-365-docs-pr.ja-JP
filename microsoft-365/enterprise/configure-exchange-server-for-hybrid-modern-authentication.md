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
description: ハイブリッドモダン認証 (HMA) Exchange Serverを使用して、より安全なユーザー認証と承認を提供するオンプレミスの組織を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780286"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ハイブリッドモダン認証 (HMA) は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、Exchange サーバーのオンプレミスハイブリッド展開で使用できます。

## <a name="fyi"></a>FYI

始める前に、次の呼び出しを行います。

- ハイブリッドモダン認証 \> HMA

- Exchange オンプレミス \> EXCH

- Exchange Online \> EXO

また、この記事のグラフィックに"灰色表示" または "淡色表示" のオブジェクトがある場合、これは、灰色で表示される要素が *HMA* 固有の構成に含まれていないという意味です。

## <a name="enabling-hybrid-modern-authentication"></a>ハイブリッドのモダン認証の有効化

HMA をオンにした場合は、次の意味があります。

1. 開始する前に、事前に確認してください。

1. 多くの **前提条件** は Skype for Business と Exchange の両方で一般的です。ハイブリッドモダン認証の概要と、オンプレミスの [Skype for Business](hybrid-modern-auth-overview.md)サーバーおよび Exchange サーバーで使用するための前提条件。 この記事の手順を開始する前に、この操作を行います。

1. Azure AD でのオンプレミス Web サービス URL のサービス プリンシパル名 **(SPN)** としての追加。

1. HMA に対してすべての仮想ディレクトリが有効になっているか確認する

1. EvoSTS 認証サーバー オブジェクトの確認

1. EXCH で HMA を有効にする。

 **注** ご使用のバージョンのOfficeサポートMA? [2016 クライアント アプリの最新Office 2013およびOfficeのしくみを参照してください](modern-auth-for-office-2013-and-2016.md)。

## <a name="make-sure-you-meet-all-the-prerequisites"></a>すべての前提条件を満たしていることを確認する

多くの前提条件は Skype for Business と Exchange の両方で一般的です。このため、ハイブリッドモダン認証の概要と、オンプレミスの Skype for Business および Exchange サーバーで使用するための前提条件を [確認してください](hybrid-modern-auth-overview.md)。 この記事  *の手順*  を開始する前に、この操作を行います。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>オンプレミスの Web サービス URL を Azure AD に SPN として追加する

オンプレミスの Web サービス URL を Azure SPN として割り当てるコマンドADします。 SPN は、認証および承認時にクライアント コンピューターおよびデバイスによって使用されます。 オンプレミスから Azure Active Directory (Azure AD) への接続に使用される可能性があるすべての URL は、Azure AD に登録する必要があります (これには、内部名前空間と外部名前空間の両方が含まれます)。

まず、AAD に追加する必要があるすべての URL を収集します。 オンプレミスで次のコマンドを実行します。

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

クライアントが接続できる URL が、AAD の HTTPS サービス プリンシパル名として表示されます。

1. まず、次の手順で AAD [に接続します](connect-to-microsoft-365-powershell.md)。

   **注** 以下のコマンドを使用するには、このページの _Connect-MsolService_ オプションを使用する必要があります。

2. Exchange 関連の URL の場合は、次のコマンドを入力します。

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   このコマンドの出力には https://  *autodiscover.yourdomain.com*  と https://  *mail.yourdomain.com* URL を含める必要がありますが、そのほとんどは 000000002-0000-0ff1-ce00-00000000000000/ で始まる SPN で構成されます。 オンプレミスからhttps://が見つからない場合は、これらの特定のレコードをこのリストに追加する必要があります。

3. この一覧に内部および外部の MAPI/HTTP、EWS、ActiveSync、OAB、および自動検出レコードが表示されていない場合は、次のコマンドを使用して追加する必要があります (URL の例は ' ' と ' ' ですが、サンプル URL は独自の URL に置き換えます)。 `mail.corp.contoso.com` `owa.contoso.com` 

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 手順 2. で Get-MsolServicePrincipal コマンドを再度実行し、出力を確認して、新しいレコードが追加されたのを確認します。 前のリスト/スクリーンショットと SPN の新しいリストを比較します。 レコードの新しいリストのスクリーンショットを撮る場合があります。 成功した場合は、一覧に 2 つの新しい URL が表示されます。 この例では、SPN の一覧に特定の URL と  `https://mail.corp.contoso.com`  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>仮想ディレクトリが正しく構成されていることを確認する

次のコマンドを実行して、Outlook が使用する可能性があるすべての仮想ディレクトリの Exchange で OAuth が正しく有効にされていることを確認します。

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

出力を確認して、これらの各 VDir で **OAuth** が有効になっていることを確認します。次のように表示されます (確認する重要な部分は 'OAuth' です)。

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

OAuth がサーバーと 4 つの仮想ディレクトリに存在しなされていない場合は、次に進む前に、関連するコマンド (Set-MapiVirtualDirectory、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory、Set-AutodiscoverVirtualDirectory) を使用して追加する必要があります。[](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory) [](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory) [](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory) [](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>EvoSTS 認証サーバー オブジェクトが存在するを確認する

この最後のコマンドについて、オンプレミスの Exchange 管理シェル に戻る。 これで、オンプレミスに evoSTS 認証プロバイダーのエントリが設定されているのを検証できます。

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

出力には Name EvoSts の AuthServer が表示され、'Enabled' 状態は True である必要があります。 表示されていない場合は、最新バージョンのハイブリッド構成ウィザードをダウンロードして実行する必要があります。

 **重要** 環境で Exchange 2010 を実行している場合、EvoSTS 認証プロバイダーは作成されません。

## <a name="enable-hma"></a>HMA を有効にする

オンプレミスの Exchange 管理シェル で次のコマンドを実行します。

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>確認する

HMA を有効にした後、クライアントの次のログインでは新しい認証フローが使用されます。 HMA を有効にしただけで、クライアントの再認証はトリガーしない点に注意してください。 クライアントは、認証トークンまたは証明書の有効期間に基づいて再認証します。

また、Outlook クライアントのアイコン (Windows 通知トレイ内) を右クリックして [接続状態] をクリックすると同時に、Ctrl キーを押したままにします。 OAuth で使用されるベアラー トークンを表す 'Bearer' の 'Authn' タイプに対してクライアントの SMTP アドレス \* を探します。

 **注** HMA を使用して Skype for Business を構成する必要がある場合 2 つの記事が必要になります。1 つはサポートされているトポロジを示し、もう 1 つは構成の方法[を示しています](configure-skype-for-business-for-hybrid-modern-authentication.md)。 [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>iOS および Android 用の Outlook でのハイブリッド先進認証の使用

TCP 443 で Exchange サーバーを使用しているオンプレミスのお客様は、次の IP 範囲のトラフィック処理をバイパスします。

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>関連項目

[Office 365 専用/ITAR から vNext への移行のための最新の認証構成要件](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
