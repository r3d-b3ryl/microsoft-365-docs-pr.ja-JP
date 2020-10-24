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
description: Azure AD、Exchange Online、SharePoint Online、Skype for Business Online、セキュリティ & コンプライアンスに関する Microsoft 365 PowerShell コマンドレットリファレンスを検索します。
ms.openlocfilehash: 75cfb4e0293a12649708deb3607166075842bba7
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754506"
---
# <a name="cmdlet-references-for-microsoft-365-services"></a><span data-ttu-id="581ac-103">Microsoft 365 サービスのコマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="581ac-103">Cmdlet references for Microsoft 365 services</span></span> 

<span data-ttu-id="581ac-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="581ac-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="581ac-105">この記事では、PowerShell がサポートする Microsoft 365 サービスごとに、さまざまな Microsoft 365 サービスおよび接続手順についてのコマンドレットリファレンスを示します。</span><span class="sxs-lookup"><span data-stu-id="581ac-105">This article provides cmdlet references for the various Microsoft 365 services and connection instructions for each Microsoft 365 service that PowerShell supports.</span></span>
  
> [!NOTE]
> <span data-ttu-id="581ac-106">一度にすべてのサービスに接続するには、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 サービスに接続する](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-106">To connect to all services at once, see [Connect to all Microsoft 365 services in a single Windows PowerShell window](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md).</span></span>
  
## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="581ac-107">Azure Active Directory PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="581ac-107">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="581ac-108">Graph の Azure Active Directory PowerShell コマンドレットリファレンストピックは、 [Azure Active Directory powershell For graph のドキュメント](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)のリファレンスセクションにあります。</span><span class="sxs-lookup"><span data-stu-id="581ac-108">The Azure Active Directory PowerShell for Graph cmdlet reference topics are in the Reference section of the [Azure Active Directory PowerShell for Graph documentation](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

<span data-ttu-id="581ac-109">Windows PowerShell の Azure Active Directory モジュールのコマンドレットリファレンスのトピックは、「 [Azure Active directory (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)」のドキュメントの「reference」セクションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="581ac-109">The Azure Active Directory Module for Windows PowerShell cmdlet reference topics is in the Reference section of the [Azure Active Directory (MSOnline) documentation](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

<span data-ttu-id="581ac-110">Microsoft 365 PowerShell の接続手順については、「 [Connect To microsoft 365 With PowerShell](connect-to-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-110">For Microsoft 365 PowerShell connection instructions, see [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
## <a name="exchange-online-powershell-cmdlets"></a><span data-ttu-id="581ac-111">Exchange Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="581ac-111">Exchange Online PowerShell cmdlets</span></span>

<span data-ttu-id="581ac-112">Exchange Online のコマンドレットのリファレンストピックは、 [Exchange online の PowerShell ドキュメント](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)の「reference」セクションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="581ac-112">Exchange Online cmdlet reference topics are in the Reference section of the [Exchange Online PowerShell documentation](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span></span>
  
<span data-ttu-id="581ac-113">Exchange Online PowerShell の接続手順については、「 [Exchange Online powershell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-113">For connection instructions for Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
> [!NOTE]
> <span data-ttu-id="581ac-114">Exchange Online PowerShell では、SharePoint Online、Skype for Business Online、Microsoft 365 のユーザーアクティビティなど、他のサービスのレポートコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="581ac-114">Reporting cmdlets for other services, such as SharePoint Online, Skype for Business Online, and Microsoft 365 user activity, are available in Exchange Online PowerShell.</span></span> <span data-ttu-id="581ac-115">詳しくは、「[Exchange Online のレポート作成のコマンドレット](https://go.microsoft.com/fwlink/p/?LinkId=691595)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="581ac-115">For more information, see [Reporting cmdlets in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=691595).</span></span> 
  
## <a name="sharepoint-online-powershell-cmdlets"></a><span data-ttu-id="581ac-116">SharePoint Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="581ac-116">SharePoint Online PowerShell cmdlets</span></span>

<span data-ttu-id="581ac-117">SharePoint Online のコマンドレットについては、「 [Index Of Windows PowerShell For Sharepoint online コマンドレット](https://go.microsoft.com/fwlink/p/?LinkId=691476)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-117">For SharePoint Online cmdlets, see [Index of Windows PowerShell for SharePoint Online cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=691476).</span></span>
  
<span data-ttu-id="581ac-118">SharePoint Online PowerShell の接続手順については、「 [Sharepoint Online 管理シェル Windows powershell 環境](https://go.microsoft.com/fwlink/p/?LinkId=691603)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-118">For connection instructions for SharePoint Online PowerShell, see [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkId=691603).</span></span>
  
## <a name="skype-for-business-online-powershell-cmdlets"></a><span data-ttu-id="581ac-119">Skype for Business Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="581ac-119">Skype for Business Online PowerShell cmdlets</span></span>

<span data-ttu-id="581ac-120">Skype for business Online のコマンドレットのリファレンストピックについては、「 [skype For Business online のコマンドレット](https://technet.microsoft.com/library/mt228132.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-120">For Skype for Business Online cmdlet reference topics, see [Skype for Business Online cmdlets](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="581ac-121">Skype for business Online PowerShell の接続手順については、「 [powershell を使用して skype For Business online を管理](manage-skype-for-business-online-with-microsoft-365-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-121">For connection instructions for Skype for Business Online PowerShell, see [Manage Skype for Business Online with PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md).</span></span>

## <a name="security--compliance-center-powershell-cmdlets"></a><span data-ttu-id="581ac-122">セキュリティ & コンプライアンスセンターの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="581ac-122">Security & Compliance Center PowerShell cmdlets</span></span>

<span data-ttu-id="581ac-123">セキュリティ & コンプライアンスセンターのコマンドレットのリファレンスについては、「 [セキュリティ & コンプライアンス PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell)」のドキュメントの「参照」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-123">The Security & Compliance Center cmdlet references are in the Reference section of the [Security & Compliance PowerShell documentation](https://docs.microsoft.com/powershell/exchange/scc-powershell).</span></span>
  
<span data-ttu-id="581ac-124">セキュリティ & コンプライアンスセンター PowerShell の接続手順については、「 [セキュリティ & コンプライアンスセンター powershell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ac-124">For connection instructions for Security & Compliance Center PowerShell, see [Connect to the Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="see-also"></a><span data-ttu-id="581ac-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="581ac-125">See also</span></span>

[<span data-ttu-id="581ac-126">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="581ac-126">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="581ac-127">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="581ac-127">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
