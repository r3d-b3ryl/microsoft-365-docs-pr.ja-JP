---
title: Microsoft 365 へのメール移行に PowerShell を使用する
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 795158e1-7dfc-4d9e-b805-373dd576c4e7
description: この記事では、PowerShell を使用して既存のシステムから Microsoft 365 に電子メールを移行する方法について説明します。
ms.openlocfilehash: afbed872c3cac483c63e8a2d537931220c3c349c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692222"
---
# <a name="use-powershell-for-email-migration-to-microsoft-365"></a><span data-ttu-id="8d112-103">Microsoft 365 へのメール移行に PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="8d112-103">Use PowerShell for email migration to Microsoft 365</span></span>

<span data-ttu-id="8d112-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="8d112-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8d112-105">管理者が最初に Microsoft 365 をセットアップすると、多くのユーザーは既存のシステムから電子メールを移行します。</span><span class="sxs-lookup"><span data-stu-id="8d112-105">When administrators first set up Microsoft 365, many of them migrate email from existing systems.</span></span> <span data-ttu-id="8d112-106">この操作は、Microsoft 365 管理センターを使用して行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="8d112-106">You can also do this by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="8d112-107">さらに、Windows PowerShell を使用して電子メールを移行することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d112-107">You can also use Windows PowerShell to migrate email.</span></span>
  
<span data-ttu-id="8d112-108">Windows PowerShell を使用して、Microsoft 365 に電子メールを移行します。</span><span class="sxs-lookup"><span data-stu-id="8d112-108">Use Windows PowerShell to migrate email to Microsoft 365.</span></span> 
  
- [<span data-ttu-id="8d112-109">Microsoft 365 への一括移行に PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="8d112-109">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md)
    
- [<span data-ttu-id="8d112-110">Microsoft 365 への IMAP 移行に PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="8d112-110">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>](use-powershell-to-perform-an-imap-migration-to-microsoft-365.md)
    
- [<span data-ttu-id="8d112-111">Microsoft 365 への段階的な移行に PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="8d112-111">Use PowerShell to perform a staged migration to Microsoft 365</span></span>](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md)
    
## <a name="related-topics"></a><span data-ttu-id="8d112-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d112-112">Related topics</span></span>

[<span data-ttu-id="8d112-113">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="8d112-113">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8d112-114">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="8d112-114">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8d112-115">PowerShell を使用して SharePoint Online を管理する</span><span class="sxs-lookup"><span data-stu-id="8d112-115">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
<span data-ttu-id="8d112-116">[Windows PowerShell を使用して Microsoft 365 でレポートを作成する](use-windows-powershell-to-create-reports-in-microsoft-365.md) 
[Microsoft 365 PowerShell を使用する必要がある理由](why-you-need-to-use-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="8d112-116">[Use Windows PowerShell to create reports in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
[Why you need to use Microsoft 365 PowerShell](why-you-need-to-use-microsoft-365-powershell.md)</span></span>
  
[<span data-ttu-id="8d112-117">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="8d112-117">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

