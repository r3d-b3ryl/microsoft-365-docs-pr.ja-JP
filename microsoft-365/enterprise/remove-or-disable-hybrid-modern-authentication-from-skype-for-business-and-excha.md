---
title: Skype for Business および Exchange からのハイブリッド先進認証の削除または無効化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: この記事では、Skype for Business および Exchange からハイブリッドモダン認証を削除または無効にする方法について説明します。
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927290"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="d53a6-103">Skype for Business および Exchange からのハイブリッド先進認証の削除または無効化</span><span class="sxs-lookup"><span data-stu-id="d53a6-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="d53a6-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="d53a6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d53a6-105">ハイブリッドモダン認証 (HMA) を有効にして、現在の環境に適しない場合にのみ、HMA を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d53a6-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="d53a6-106">この記事では、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d53a6-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="d53a6-107">この記事は誰の記事ですか?</span><span class="sxs-lookup"><span data-stu-id="d53a6-107">Who is this article for?</span></span>

<span data-ttu-id="d53a6-108">Skype for Business Online またはオンプレミス、Exchange Online またはオンプレミスでモダン認証を有効にし、HMA を無効にする必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d53a6-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d53a6-109">Skype for[Business Online](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)またはオンプレミスの場合、混在トポロジ HMA を使用し、開始する前にサポートされているトポロジを確認する必要がある場合は、「モダン認証でサポートされる Skype for Business トポロジ」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d53a6-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="d53a6-110">ハイブリッドモダン認証 (Exchange) を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="d53a6-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="d53a6-111">**Exchange オンプレミス: Exchange** 管理シェルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d53a6-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="d53a6-112">**Exchange Online**: [リモート PowerShell を使用して Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="d53a6-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="d53a6-113">次のコマンドを実行して  *、OAuth2ClientProfileEnabled*  フラグを 'false' に設定します。</span><span class="sxs-lookup"><span data-stu-id="d53a6-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="d53a6-114">ハイブリッドモダン認証を無効にする方法 (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="d53a6-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="d53a6-115">**Skype for Business オンプレミス**: Skype for Business 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d53a6-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="d53a6-116">**Skype for Business Online**: [リモート PowerShell を使用して Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) に接続します。</span><span class="sxs-lookup"><span data-stu-id="d53a6-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="d53a6-117">次のコマンドを実行して、モダン認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d53a6-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="d53a6-118">[モダン認証の概要にリンクします](hybrid-modern-auth-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="d53a6-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
