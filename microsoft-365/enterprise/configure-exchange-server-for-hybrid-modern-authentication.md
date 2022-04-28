---
title: Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: scotv
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
description: ハイブリッドモダン認証 (PFX) を使用するようにオンプレミスでExchange Serverを構成する方法について説明し、より安全なユーザー認証と承認を提供します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2ee190a541fdf3e4e77a251e040f2cb69416088c
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095754"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Hybrid Modern Authentication (PFX) は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、Exchange サーバーのオンプレミス ハイブリッド展開で使用できます。

## <a name="definitions"></a>定義

始める前に、いくつかの定義について理解しておく必要があります。

- ハイブリッド先進認証 \> HV

- オンプレミス\>ExchangeEXCH

- \> Exchange Online EXO

また、 *この記事のグラフィックに'淡色表示' または '淡色' のオブジェクトがある場合は、灰色で表示される要素は PFX 固有の構成には含まれません*。

## <a name="enabling-hybrid-modern-authentication"></a>ハイブリッドモダン認証を有効にする

HMA を有効にすると、次のことを意味します。

1. 開始する前に、事前の質問に必ずお会いください。

1. 多くの **前提条件** はSkype for BusinessとExchangeの両方で一般的であるため、[ハイブリッド先進認証の概要と、それをオンプレミスのSkype for BusinessおよびExchange サーバーで使用するための前提条件](hybrid-modern-auth-overview.md)です。 この記事の手順を開始する前に、この操作を行います。
挿入するリンクされたメールボックスに関する要件。

1. Azure ADにオンプレミス Web サービス URL を **サービス プリンシパル名 (SPN)** として追加する。 EXCH が **複数のテナント** とハイブリッドになっている場合、これらのオンプレミス Web サービス URL は、EXCH とハイブリッドになっているすべてのテナントのAzure ADに SPN として追加する必要があります。

1. すべての仮想ディレクトリが   HMA に対して有効になっていることを確認する

1. EvoSTS Auth Server オブジェクトのチェック

1. EXCH で  PFX を有効にします。

> [!NOTE]
> お使いのバージョンのOfficeは MA をサポートしていますか? [Office 2013 および Office 2016 クライアント アプリの先進認証のしくみ](modern-auth-for-office-2013-and-2016.md)に関する説明を参照してください。

## <a name="make-sure-you-meet-all-the-prerequisites"></a>すべての前提条件を満たしていることを確認する

多くの前提条件はSkype for BusinessとExchangeの両方で一般的であるため、[ハイブリッド先進認証の概要と、オンプレミスのSkype for BusinessおよびExchange サーバーで使用するための前提条件](hybrid-modern-auth-overview.md)を確認してください。 この記事の手順を開始する  *前*  に、この操作を行います。

> [!NOTE]
> Outlook Web AppとExchange コントロール パネルは、ハイブリッドモダン認証では機能しません。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Azure ADでオンプレミス Web サービス URL を SPN として追加する

オンプレミス Web サービス URL を SPN として割り当てるコマンドAzure AD実行します。 SPN は、認証と承認の間にクライアント マシンとデバイスによって使用されます。 オンプレミスからAzure Active Directory (Azure AD) への接続に使用できるすべての URL は、Azure ADに登録する必要があります (これには内部名前空間と外部名前空間の両方が含まれます)。

最初に、AADに追加する必要があるすべての URL を収集します。 オンプレミスで次のコマンドを実行します。

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*hostname*
```

クライアントが接続できる URL が、AADの HTTPS サービス プリンシパル名として一覧表示されていることを確認します。 EXCH が **複数のテナント** とハイブリッドになっている場合は、EXCH とハイブリッド内のすべてのテナントのAADにこれらの HTTPS SPN を追加する必要があります。

1. 最初に、[次の手順](connect-to-microsoft-365-powershell.md)に従ってAADに接続します。

    > [!NOTE]
    > 次のコマンドを使用できるようにするには、このページ _の Connect-MsolService_ オプションを使用する必要があります。

2. Exchange関連 URL の場合は、次のコマンドを入力します。

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   このコマンドの出力 (および後の比較のスクリーンショット) を書き留めておきます。このコマンドの出力には URL が含まれます`https://*autodiscover.yourdomain.com*``https://*mail.yourdomain.com*`が、ほとんどの場合は SPN で`00000002-0000-0ff1-ce00-000000000000/`始まります。 オンプレミスから見つからない URL がある `https://` 場合は、これらの特定のレコードをこの一覧に追加する必要があります。

3. この一覧に内部および外部の MAPI/HTTP、EWS、ActiveSync、OAB、および自動検出レコードが表示されない場合は、次のコマンドを使用して追加する必要があります (URL の例は`mail.corp.contoso.com``owa.contoso.com`次のとおりです。ただし、**URL の例は独自のものに置き換えます**)。

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 手順 2 のコマンドをもう一度実行し、出力を `Get-MsolServicePrincipal` 調べて、新しいレコードが追加されたことを確認します。 前のリスト/スクリーンショットを SPN の新しいリストと比較します。 レコードの新しいリストのスクリーンショットを撮ることもできます。 成功した場合は、2 つの新しい URL が一覧に表示されます。 この例では、SPN の一覧に特定の URL と `https://mail.corp.contoso.com` `https://owa.contoso.com`.

## <a name="verify-virtual-directories-are-properly-configured"></a>仮想ディレクトリが正しく構成されていることを確認する

次に、次のコマンドを実行して、Outlookが使用する可能性があるすべての仮想ディレクトリのExchangeで OAuth が正しく有効になっていることを確認します。

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

出力を確認して、これらの各 VDir で **OAuth** が有効になっていることを確認します。次のようになります (重要なのは "OAuth" です)。

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

OAuth が任意のサーバーと 4 つの仮想ディレクトリのいずれかに存在しない場合は、関連するコマンドを使用して追加する必要があります ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory)、 [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory)、 [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)、 [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory))。

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>EvoSTS 認証サーバー オブジェクトが存在することを確認する

この最後のコマンドのオンプレミス Exchange管理シェルに戻ります。 これで、オンプレミスに evoSTS 認証プロバイダーのエントリがあることを検証できます。

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts*"} | ft name,enabled
```

出力には、GUID を持つ Name EvoSts の AuthServer が表示され、'Enabled' 状態は True である必要があります。 これが表示されない場合は、ハイブリッド構成ウィザードの最新バージョンをダウンロードして実行する必要があります。

> [!NOTE]
> EXCH が **複数のテナント** とハイブリッドになっている場合、出力には EXCH とハイブリッドの各テナントの名前 `EvoSts - {GUID}` の 1 つの AuthServer が表示され、これらの AuthServer オブジェクトすべてに対して **Enabled** 状態が True である必要があります。

> [!IMPORTANT]
> 環境で Exchange 2010 を実行している場合、EvoSTS 認証プロバイダーは作成されません。

## <a name="enable-hma"></a>HMA を有効にする

オンプレミスの Exchange Management Shell で次のコマンドを実行し\<GUID\>、コマンド ライン内の文字列を環境内の文字列に置き換えます。

```powershell
Set-AuthServer -Identity "EvoSTS - <GUID>" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> 以前のバージョンのハイブリッド構成ウィザードでは、EvoSts AuthServer は単に GUID がアタッチされていない EvoSTS という名前でした。 実行する必要がある操作はありません。コマンドの GUID 部分を削除することで、これを反映するように上記のコマンド ラインを変更するだけです。
>
> ```powershell
> Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
> ```

EXCH バージョンが 2016 (CU18 以降) または 2019 Exchange 2020 年 9 月以降にダウンロードされた HCW で構成されている場合 Exchangeは、オンプレミスのExchange管理シェルで次のコマンドを実行します。

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> EXCH が **複数のテナント** とハイブリッドになっている場合、EXCH には、各テナントに対応するドメインを持つ複数の AuthServer オブジェクトが存在します。  **IsDefaultAuthorizationEndpoint** フラグは、これらの AuthServer オブジェクトのいずれかに対して true (**IsDefaultAuthorizationEndpoint** コマンドレットを使用) に設定する必要があります。 このフラグは、すべての Authserver オブジェクトに対して true に設定することはできません。これらの AUTHServer オブジェクトの **IsDefaultAuthorizationEndpoint** フラグのいずれかが true に設定されている場合でも、PFX が有効になります。
> 
> **DomainName** パラメーターには、テナント ドメインの値 (通常はフォーム`contoso.onmicrosoft.com`内) を使用します。

## <a name="verify"></a>確認

PFX を有効にすると、クライアントの次のログインで新しい認証フローが使用されます。 PFX をオンにするだけでは、クライアントの再認証はトリガーされないため、Exchangeが新しい設定を選択するまでに時間がかかる場合があることに注意してください。

また、Ctrl キーを押しながら、Outlook クライアントのアイコン (Windows通知トレイでも) を右クリックし、[接続状態] をクリックする必要があります。 OAuth で使用されるベアラー トークンを表す **Authn** 型 `Bearer\*`に対してクライアントの SMTP アドレスを探します。

> [!NOTE]
> HMA を使用してSkype for Businessを構成する必要がありますか? 2 つの記事が必要です。1 つは [サポートされているトポロジ](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)を一覧表示し、もう 1 つは [構成の方法を](configure-skype-for-business-for-hybrid-modern-authentication.md)示しています。

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>iOS および Android 用の Outlook でのハイブリッド先進認証の使用

TCP 443 でExchange サーバーを使用しているオンプレミスのお客様の場合は、次の IP 範囲からのネットワーク トラフィックを許可します。

```console
52.125.128.0/20
52.127.96.0/23
```

これらの IP アドレス範囲については、「[Office 365 IP アドレスと URL Web サービスに含まれていない追加のエンドポイント」](/microsoft-365/enterprise/additional-office365-ip-addresses-and-urls)にも記載されています。

## <a name="related-topics"></a>関連項目

[専用/ITAR Office 365 vNext に移行するための先進認証構成要件](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
