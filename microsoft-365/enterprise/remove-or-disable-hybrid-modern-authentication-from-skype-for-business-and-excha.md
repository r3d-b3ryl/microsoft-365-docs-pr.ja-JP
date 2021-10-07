---
title: Skype for Business および Exchange からのハイブリッド先進認証の削除または無効化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: この記事では、ハイブリッドモダン認証を削除または無効にする方法について、Skype for BusinessおよびExchange。
ms.openlocfilehash: efc84ead5ea8219e77391f2a8ebe51e5fa23da8c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202813"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Skype for Business および Exchange からのハイブリッド先進認証の削除または無効化

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ハイブリッドモダン認証 (HMA) を有効にして、現在の環境に適しない場合にのみ、HMA を無効にできます。 この記事では、その方法について説明します。
  
## <a name="who-is-this-article-for"></a>Whoは次の記事ですか?

Skype for Business Online またはオンプレミス、および/または Exchange Online またはオンプレミスでモダン認証を有効にし、HMA を無効にする必要がある場合は、次の手順を実行します。

> [!IMPORTANT]
> Skype for Business Online[](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)またはオンプレミスで、混在トポロジ HMA を持ち、開始する前にサポートされているトポロジを確認する必要がある場合は、「モダン認証でサポートされる Skype for Business トポロジ」の記事を参照してください。
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>ハイブリッドモダン認証を無効にする方法 (Exchange)

1. **Exchange : 管理** シェルを開Exchangeコマンドを実行します。 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Connect PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)を使用します。 次のコマンドを実行して  *、OAuth2ClientProfileEnabled*  フラグを 'false' に設定します。

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>ハイブリッドモダン認証を無効にする方法 (Skype for Business)

1. **Skype for Business : 管理** シェルで次のコマンドSkype for Business実行します。

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for Business : リモート** [powerShell ConnectオンラインSkype for Businessオンライン](manage-skype-for-business-online-with-microsoft-365-powershell.md)にアクセスします。 次のコマンドを実行して、モダン認証を無効にします。

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[モダン認証の概要にリンクします](hybrid-modern-auth-overview.md) 。 
