---
title: DAP パートナー用に Windows PowerShell を使用して Microsoft 365 を管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: シンジケートおよびクラウドソリューションプロバイダー (CSP) パートナーが Windows PowerShell を使用して、Microsoft 365 の顧客テナントを管理する方法。
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429880"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="f9ff2-103">委任アクセス許可パートナー用 Windows PowerShell を使用して Microsoft 365 を管理する方法</span><span class="sxs-lookup"><span data-stu-id="f9ff2-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="f9ff2-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="f9ff2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f9ff2-105">委任アクセス許可 (DAP) パートナー とは、シンジケート パートナーとクラウド ソリューション プロバイダー (CSP) パートナーです。</span><span class="sxs-lookup"><span data-stu-id="f9ff2-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="f9ff2-106">多くは、ネットワークプロバイダーまたは通信プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="f9ff2-106">Many are network or telecom providers.</span></span> <span data-ttu-id="f9ff2-107">これらのサブスクリプションは、Microsoft 365 のサブスクリプションをサービス製品にバンドルしています。</span><span class="sxs-lookup"><span data-stu-id="f9ff2-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="f9ff2-108">これらのユーザーは、Microsoft 365 サブスクリプションを販売する際に、(AOBO) のテナンシーに対する代理人アクセス許可が自動的に付与されるので、それらのテナンシーを管理および報告できます。</span><span class="sxs-lookup"><span data-stu-id="f9ff2-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="f9ff2-109">これらのタスクは、Microsoft 365 管理センターでは実行が困難です。</span><span class="sxs-lookup"><span data-stu-id="f9ff2-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f9ff2-110">次のような管理タスクを実行するために、Microsoft 365 では、PowerShell を使用する方がはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="f9ff2-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="f9ff2-111">すべて **のお客** 様のすべてのお客様のドメインを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="f9ff2-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="f9ff2-112">顧客テナント内のすべてのユーザーと割り当てられたライセンスを識別する</span><span class="sxs-lookup"><span data-stu-id="f9ff2-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="f9ff2-113">一部の管理タスクは、PowerShell でのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9ff2-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="f9ff2-114">次の記事は、配信および CSP パートナーが PowerShell を使用して顧客テナンシーを管理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9ff2-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="f9ff2-115">委任アクセス許可 (DAP) パートナー用 Windows PowerShell で Microsoft 365 テナントを管理する</span><span class="sxs-lookup"><span data-stu-id="f9ff2-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="f9ff2-116">委任アクセス許可 (DAP) パートナー用 Windows PowerShell でクライアント テナンシーにドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="f9ff2-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="f9ff2-117">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="f9ff2-117">Connect to Exchange Online PowerShell</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="f9ff2-118">委任アクセス許可 (DAP) パートナー用 Windows PowerShell を使用して顧客のテナント レポート データを取得する</span><span class="sxs-lookup"><span data-stu-id="f9ff2-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   