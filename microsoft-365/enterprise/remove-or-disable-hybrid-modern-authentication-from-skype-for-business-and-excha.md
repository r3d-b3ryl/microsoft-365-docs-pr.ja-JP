---
title: Skype for Business および Exchange からのハイブリッド先進認証の削除または無効化
ms.author: kvice
author: kelleyvice-msft
manager: scotv
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
description: この記事では、Skype for BusinessおよびExchangeから Hybrid Modern Authentication を削除または無効にする方法について説明します。
ms.openlocfilehash: 6456873f7338b97b3255f3976e7520580ac2a142
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66017791"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Skype for Business および Exchange からのハイブリッド先進認証の削除または無効化

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Hybrid Modern Authentication (PFX) を有効にして、現在の環境に適していないと見つけた場合にのみ、PFX を無効にできます。 この記事では、その方法について説明します。

## <a name="who-is-this-article-for"></a>この記事の対象はWhoですか?

Skype for Business Online またはオンプレミス、および/またはExchange Onlineまたはオンプレミスで先進認証を有効にしていて、PFX を無効にする必要がある場合は、次の手順に従います。

> [!IMPORTANT]
> Skype for Business Online またはオンプレミスの場合は、「[モダン認証でサポートされているSkype for Business トポロジ](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)」の記事を参照してください。混合トポロジ PFX があり、開始する前にサポートされているトポロジを確認する必要があります。

## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>ハイブリッドモダン認証を無効にする方法 (Exchange)

1. **オンプレミスExchange**: [Exchange管理シェルを開](/powershell/exchange/open-the-exchange-management-shell)き、次のコマンドを実行します。

   ```powershell
   Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
   Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
   ```

2. **Exchange Online**: [PowerShell のExchange OnlineにConnect](/powershell/exchange/connect-to-exchange-online-powershell)します。 モダン認証を無効にするには、次のコマンドを実行します。

   ```powershell
   Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
   ```

## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>ハイブリッドモダン認証を無効にする方法 (Skype for Business)

1. **オンプレミスSkype for Business**: Skype for Business Management Shell で次のコマンドを実行します。

   ```powershell
   Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
   ```

2. **オンラインSkype for Business**: [Skype for Business Online PowerShell にConnect](manage-skype-for-business-online-with-microsoft-365-powershell.md)します。 モダン認証を無効にするには、次のコマンドを実行します。

   ```powershell
   Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
   ```

[モダン認証の概要に戻ります](hybrid-modern-auth-overview.md)。
