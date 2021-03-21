---
title: Microsoft 365 サービスのコマンドレットリファレンス
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 3a1ea1a6-edbd-4922-9ad3-0b075f7f9009
description: Azure AD、Exchange Online、SharePoint Online、Skype for Business Online、およびセキュリティ & コンプライアンスに関する Microsoft 365 PowerShell コマンドレットリファレンスを&します。
ms.openlocfilehash: 524f9b6c84741a2a31cd8e5727142fc735ad7128
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928216"
---
# <a name="cmdlet-references-for-microsoft-365-services"></a><span data-ttu-id="0f0c0-103">Microsoft 365 サービスのコマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="0f0c0-103">Cmdlet references for Microsoft 365 services</span></span> 

<span data-ttu-id="0f0c0-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="0f0c0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0f0c0-105">この記事では、PowerShell がサポートする Microsoft 365 サービスごとに、さまざまな Microsoft 365 サービスと接続手順に関するコマンドレットリファレンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-105">This article provides cmdlet references for the various Microsoft 365 services and connection instructions for each Microsoft 365 service that PowerShell supports.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f0c0-106">すべてのサービスに一度に接続するには、「単一のサービス ウィンドウで [すべての Microsoft 365](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)サービスに接続Windows PowerShellしてください。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-106">To connect to all services at once, see [Connect to all Microsoft 365 services in a single Windows PowerShell window](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md).</span></span>
  
## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="0f0c0-107">Azure Active Directory PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="0f0c0-107">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="0f0c0-108">Azure Active Directory PowerShell for Graph コマンドレットのリファレンス トピックは [、Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)ドキュメントのリファレンス セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-108">The Azure Active Directory PowerShell for Graph cmdlet reference topics are in the Reference section of the [Azure Active Directory PowerShell for Graph documentation](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

<span data-ttu-id="0f0c0-109">コマンドレットリファレンス トピックWindows PowerShell Azure Active Directory モジュールは [、Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0)ドキュメントのリファレンス セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-109">The Azure Active Directory Module for Windows PowerShell cmdlet reference topics is in the Reference section of the [Azure Active Directory (MSOnline) documentation](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

<span data-ttu-id="0f0c0-110">Microsoft 365 PowerShell 接続手順については [、「Connect to Microsoft 365 with PowerShell」を参照してください](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-110">For Microsoft 365 PowerShell connection instructions, see [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
## <a name="exchange-online-powershell-cmdlets"></a><span data-ttu-id="0f0c0-111">Exchange Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="0f0c0-111">Exchange Online PowerShell cmdlets</span></span>

<span data-ttu-id="0f0c0-112">Exchange Online コマンドレットのリファレンス トピックは、Exchange Online PowerShell ドキュメントのリファレンス [セクションに含まれています](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-112">Exchange Online cmdlet reference topics are in the Reference section of the [Exchange Online PowerShell documentation](/powershell/exchange/exchange-online-powershell).</span></span>
  
<span data-ttu-id="0f0c0-113">Exchange Online PowerShell の接続手順については、「Connect [to Exchange Online PowerShell」を参照してください](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-113">For connection instructions for Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f0c0-114">SharePoint Online、Skype for Business Online、Microsoft 365 ユーザー アクティビティなどの他のサービスのレポートコマンドレットは、Exchange Online PowerShell で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-114">Reporting cmdlets for other services, such as SharePoint Online, Skype for Business Online, and Microsoft 365 user activity, are available in Exchange Online PowerShell.</span></span> <span data-ttu-id="0f0c0-115">詳しくは、「[Exchange Online のレポート作成のコマンドレット](/powershell/exchange/exchange-online-powershell)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-115">For more information, see [Reporting cmdlets in Exchange Online](/powershell/exchange/exchange-online-powershell).</span></span> 
  
## <a name="sharepoint-online-powershell-cmdlets"></a><span data-ttu-id="0f0c0-116">SharePoint Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="0f0c0-116">SharePoint Online PowerShell cmdlets</span></span>

<span data-ttu-id="0f0c0-117">SharePoint Online コマンドレットについては [、「Index of Windows PowerShell SharePoint Online コマンドレット」を参照してください](/powershell/module/sharepoint-online/)。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-117">For SharePoint Online cmdlets, see [Index of Windows PowerShell for SharePoint Online cmdlets](/powershell/module/sharepoint-online/).</span></span>
  
<span data-ttu-id="0f0c0-118">SharePoint Online PowerShell の接続手順については [、「SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)管理シェルをセットアップする」を参照Windows PowerShellしてください。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-118">For connection instructions for SharePoint Online PowerShell, see [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>
  
## <a name="skype-for-business-online-powershell-cmdlets"></a><span data-ttu-id="0f0c0-119">Skype for Business Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="0f0c0-119">Skype for Business Online PowerShell cmdlets</span></span>

<span data-ttu-id="0f0c0-120">Skype for Business Online コマンドレットのリファレンス トピックについては [、「Skype for Business Online コマンドレット」を参照してください](/previous-versions//mt228132(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-120">For Skype for Business Online cmdlet reference topics, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="0f0c0-121">Skype for Business Online PowerShell の接続手順については、「Manage [Skype for Business Online with PowerShell」を参照してください](manage-skype-for-business-online-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-121">For connection instructions for Skype for Business Online PowerShell, see [Manage Skype for Business Online with PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md).</span></span>

## <a name="security--compliance-center-powershell-cmdlets"></a><span data-ttu-id="0f0c0-122">セキュリティ & コンプライアンス センター PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="0f0c0-122">Security & Compliance Center PowerShell cmdlets</span></span>

<span data-ttu-id="0f0c0-123">コンプライアンス センター&のリファレンスについては、「セキュリティ とコンプライアンスの [PowerShell」](/powershell/exchange/scc-powershell)のドキュメント&セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-123">The Security & Compliance Center cmdlet references are in the Reference section of the [Security & Compliance PowerShell documentation](/powershell/exchange/scc-powershell).</span></span>
  
<span data-ttu-id="0f0c0-124">コンプライアンス センター PowerShell のセキュリティ &手順については、「Connect to the Security [& コンプライアンス センター PowerShell」を参照してください](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0f0c0-124">For connection instructions for Security & Compliance Center PowerShell, see [Connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f0c0-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f0c0-125">See also</span></span>

[<span data-ttu-id="0f0c0-126">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="0f0c0-126">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0f0c0-127">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="0f0c0-127">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)