---
title: PowerShell で Microsoft 365を管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- O365ITProTrain
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 932d57c0-1520-4f0f-8ec9-9966d646480f
description: PowerShell を使用して Microsoft 365 のユーザー、ライセンス、および365アプリを管理する方法について説明します。
ms.openlocfilehash: b1e8353eac1fb2917330ef5b5c2c7752fe5b1824
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655853"
---
# <a name="manage-microsoft-365-with-powershell"></a><span data-ttu-id="a8968-103">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="a8968-103">Manage Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="a8968-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="a8968-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a8968-105">Microsoft 365 の PowerShell は、Microsoft 365 管理センターを補完する強力な管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="a8968-105">PowerShell for Microsoft 365 is a powerful management tool that complements the Microsoft 365 admin center.</span></span> <span data-ttu-id="a8968-106">たとえば、PowerShell オートメーションを使用して、複数のユーザーアカウントとライセンスを簡単に管理したり、レポートを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="a8968-106">For example, you can use PowerShell automation to easily manage multiple user accounts and licenses and to create reports.</span></span>

<span data-ttu-id="a8968-107">PowerShell を使用して Microsoft 365 を管理する方法については、以下のトピックをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="a8968-107">Select from the following topics to learn how to use PowerShell to manage Microsoft 365:</span></span>
  
- [<span data-ttu-id="a8968-108">**作業の開始**</span><span class="sxs-lookup"><span data-stu-id="a8968-108">**Get started**</span></span>](getting-started-with-microsoft-365-powershell.md)

    <span data-ttu-id="a8968-109">Microsoft 365 の PowerShell に精通しておらず、Microsoft 365 モジュールをインストールしてサブスクリプションに接続する場合は、ここから開始してください。</span><span class="sxs-lookup"><span data-stu-id="a8968-109">Start here if you're not familiar with PowerShell for Microsoft 365, and you want to install the Microsoft 365 modules and connect to your subscription.</span></span>

- [<span data-ttu-id="a8968-110">**ユーザーアカウント、ライセンス、およびグループ**</span><span class="sxs-lookup"><span data-stu-id="a8968-110">**User accounts, licenses, and groups**</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

    <span data-ttu-id="a8968-111">オートメーションコマンドを使用してユーザーアカウント、ライセンス、グループを管理する方法について知りたい場合は、ここから開始してください。</span><span class="sxs-lookup"><span data-stu-id="a8968-111">Start here if want to learn about using automation commands to manage user accounts, licenses, and groups.</span></span>

- [<span data-ttu-id="a8968-112">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="a8968-112">**SharePoint**</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)

    <span data-ttu-id="a8968-113">オートメーションコマンドを使用して SharePoint を管理する場合は、ここから開始してください。</span><span class="sxs-lookup"><span data-stu-id="a8968-113">Start here if you want to use automation commands to manage SharePoint.</span></span>

- [<span data-ttu-id="a8968-114">**Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="a8968-114">**Exchange Online**</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

    <span data-ttu-id="a8968-115">Exchange Online を管理する場合は、ここから開始してください。</span><span class="sxs-lookup"><span data-stu-id="a8968-115">Start here if you want to manage Exchange Online.</span></span>

- [<span data-ttu-id="a8968-116">**電子メールの移行**</span><span class="sxs-lookup"><span data-stu-id="a8968-116">**Email migration**</span></span>](use-powershell-for-email-migration-to-microsoft-365.md)

    <span data-ttu-id="a8968-117">既存のシステムからメールを移行する場合は、ここから開始してください。</span><span class="sxs-lookup"><span data-stu-id="a8968-117">Start here if you want to migrate your email from pre-existing systems.</span></span>

- [<span data-ttu-id="a8968-118">**セキュリティ/コンプライアンス センター**</span><span class="sxs-lookup"><span data-stu-id="a8968-118">**Security & Compliance Center**</span></span>](https://docs.microsoft.com/powershell/exchange/scc-powershell)

    <span data-ttu-id="a8968-119">セキュリティ & コンプライアンスセンターの機能を管理する場合は、ここから開始してください。</span><span class="sxs-lookup"><span data-stu-id="a8968-119">Start here if you want to manage Security & Compliance Center features.</span></span>

- [<span data-ttu-id="a8968-120">**代理アクセス許可 (DAP) パートナー**</span><span class="sxs-lookup"><span data-stu-id="a8968-120">**Delegated Access Permissions (DAP) partners**</span></span>](manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-dap-p.md)

    <span data-ttu-id="a8968-121">シンジケートおよびクラウドソリューションプロバイダー (CSP) パートナーを使用して、Microsoft 365 の顧客テナントを管理する場合は、ここから開始してください。</span><span class="sxs-lookup"><span data-stu-id="a8968-121">Start here if you want to use Syndication and Cloud Solution Provider (CSP) partners to manage your Microsoft 365 customer tenants.</span></span>

- [<span data-ttu-id="a8968-122">**Skype for Business Online**</span><span class="sxs-lookup"><span data-stu-id="a8968-122">**Skype for Business Online**</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)

    <span data-ttu-id="a8968-123">Skype for Business Online を管理するには、ここから開始してください。</span><span class="sxs-lookup"><span data-stu-id="a8968-123">Start here to manage Skype for Business Online.</span></span>
