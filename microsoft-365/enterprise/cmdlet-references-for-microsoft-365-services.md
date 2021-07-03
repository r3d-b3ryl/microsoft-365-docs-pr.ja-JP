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
description: Azure AD Microsoft 365、Exchange Online、Exchange Online、SharePoint Online、Skype for Business Online、およびセキュリティ & コンプライアンスの PowerShell コマンドレットリファレンスを&します。
ms.openlocfilehash: 9f47b5d1aecfad59c920d2af8d8fdecc420f76d0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286863"
---
# <a name="cmdlet-references-for-microsoft-365-services"></a><span data-ttu-id="95c5c-103">Microsoft 365 サービスのコマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="95c5c-103">Cmdlet references for Microsoft 365 services</span></span>

<span data-ttu-id="95c5c-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="95c5c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="95c5c-105">この記事では、PowerShell がサポートする各サービスMicrosoft 365サービスおよび接続手順に関するコマンドレットMicrosoft 365説明します。</span><span class="sxs-lookup"><span data-stu-id="95c5c-105">This article provides cmdlet references for the various Microsoft 365 services and connection instructions for each Microsoft 365 service that PowerShell supports.</span></span>

> [!NOTE]
> <span data-ttu-id="95c5c-106">すべてのサービスに一度に接続するには、ConnectウィンドウMicrosoft 365のすべてのサービスにWindows PowerShell[してください](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-106">To connect to all services at once, see [Connect to all Microsoft 365 services in a single Windows PowerShell window](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md).</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="95c5c-107">Azure Active DirectoryPowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="95c5c-107">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="95c5c-108">コマンドレットAzure Active Directory用Graph PowerShell のリファレンス トピックは、次のドキュメントの[「Azure Active Directory PowerShell Graph」にGraphされています](/powershell/azure/active-directory/install-adv2)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-108">The Azure Active Directory PowerShell for Graph cmdlet reference topics are in the Reference section of the [Azure Active Directory PowerShell for Graph documentation](/powershell/azure/active-directory/install-adv2).</span></span>

<span data-ttu-id="95c5c-109">コマンドレットAzure Active Directory参照Windows PowerShellモジュールのトピックは[、msOnline (msOnline)](/powershell/azure/active-directory/overview)ドキュメントのAzure Active Directoryセクションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="95c5c-109">The Azure Active Directory Module for Windows PowerShell cmdlet reference topics is in the Reference section of the [Azure Active Directory (MSOnline) documentation](/powershell/azure/active-directory/overview).</span></span>

<span data-ttu-id="95c5c-110">PowerShell Microsoft 365手順については[、「PowerShell を使用ConnectするMicrosoft 365」を参照してください](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-110">For Microsoft 365 PowerShell connection instructions, see [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="exchange-online-powershell-cmdlets"></a><span data-ttu-id="95c5c-111">Exchange Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="95c5c-111">Exchange Online PowerShell cmdlets</span></span>

<span data-ttu-id="95c5c-112">Exchange Onlineコマンドレットリファレンスのトピックは、PowerShell のドキュメントのリファレンス[セクションExchange Online参照してください](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-112">Exchange Online cmdlet reference topics are in the Reference section of the [Exchange Online PowerShell documentation](/powershell/exchange/exchange-online-powershell).</span></span>

<span data-ttu-id="95c5c-113">PowerShell の接続手順についてはExchange Online PowerShell のConnect[をExchange Onlineしてください](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-113">For connection instructions for Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="95c5c-114">SharePoint Online、Skype for Business Online、Microsoft 365 などの他のサービスのレポートコマンドレットは、PowerShell でExchange Onlineできます。</span><span class="sxs-lookup"><span data-stu-id="95c5c-114">Reporting cmdlets for other services, such as SharePoint Online, Skype for Business Online, and Microsoft 365 user activity, are available in Exchange Online PowerShell.</span></span> <span data-ttu-id="95c5c-115">詳しくは、「[Exchange Online のレポート作成のコマンドレット](/powershell/exchange/exchange-online-powershell)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="95c5c-115">For more information, see [Reporting cmdlets in Exchange Online](/powershell/exchange/exchange-online-powershell).</span></span>

## <a name="sharepoint-online-powershell-cmdlets"></a><span data-ttu-id="95c5c-116">SharePoint Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="95c5c-116">SharePoint Online PowerShell cmdlets</span></span>

<span data-ttu-id="95c5c-117">オンライン SharePointについては、「オンライン コマンドレットの[インデックス Windows PowerShell」をSharePointしてください](/powershell/module/sharepoint-online/)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-117">For SharePoint Online cmdlets, see [Index of Windows PowerShell for SharePoint Online cmdlets](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="95c5c-118">オンライン PowerShell の接続SharePointについては、「オンライン管理シェルのセットアップ」をSharePoint[を参照Windows PowerShellしてください](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-118">For connection instructions for SharePoint Online PowerShell, see [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

## <a name="skype-for-business-online-powershell-cmdlets"></a><span data-ttu-id="95c5c-119">Skype for Business Online の PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="95c5c-119">Skype for Business Online PowerShell cmdlets</span></span>

<span data-ttu-id="95c5c-120">オンライン コマンドレットSkype for Businessトピックについては、「オンライン コマンドレットSkype for Business[を参照してください](/previous-versions//mt228132(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="95c5c-120">For Skype for Business Online cmdlet reference topics, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="95c5c-121">オンライン PowerShell の接続Skype for Businessについては、「Manage [Skype for Business Online with PowerShell」を参照してください](manage-skype-for-business-online-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-121">For connection instructions for Skype for Business Online PowerShell, see [Manage Skype for Business Online with PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md).</span></span>

## <a name="security--compliance-center-powershell-cmdlets"></a><span data-ttu-id="95c5c-122">セキュリティ & コンプライアンス センター PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="95c5c-122">Security & Compliance Center PowerShell cmdlets</span></span>

<span data-ttu-id="95c5c-123">コンプライアンス センター&のリファレンスについては、「セキュリティ とコンプライアンスの [PowerShell」](/powershell/exchange/scc-powershell)のドキュメント&セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="95c5c-123">The Security & Compliance Center cmdlet references are in the Reference section of the [Security & Compliance PowerShell documentation](/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="95c5c-124">Security & コンプライアンス センター PowerShell の接続手順については、「セキュリティ Connectコンプライアンス センター [PowerShell &」を参照してください](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="95c5c-124">For connection instructions for Security & Compliance Center PowerShell, see [Connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="see-also"></a><span data-ttu-id="95c5c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="95c5c-125">See also</span></span>

[<span data-ttu-id="95c5c-126">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="95c5c-126">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="95c5c-127">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="95c5c-127">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)