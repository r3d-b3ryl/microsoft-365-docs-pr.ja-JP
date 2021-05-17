---
title: PowerShell を使用して Sway へのアクセスを無効Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: 7221a4c9-ae03-4598-81fe-a655c02f40ab
description: 組織で Sway へのアクセスをManageSway.ps1できる PowerShell スクリプトをダウンロードするMicrosoft 365します。
ms.openlocfilehash: bec96c6232eee88355997f56e49f1f99b8cc2fbd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691840"
---
# <a name="disable-access-to-sway-with-powershell-for-microsoft-365"></a><span data-ttu-id="98d7d-103">PowerShell を使用して Sway へのアクセスを無効Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="98d7d-103">Disable access to Sway with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="98d7d-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="98d7d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="98d7d-105">PowerShell ManageSway.ps1スクリプトを使用すると、Sway を含む組織のMicrosoft 365を表示および無効化できます。</span><span class="sxs-lookup"><span data-stu-id="98d7d-105">The ManageSway.ps1 PowerShell script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="98d7d-106">このスクリプトは、次のトピックで説明されている手順を自動化します。</span><span class="sxs-lookup"><span data-stu-id="98d7d-106">This script automates the procedures that are described in the following topics:</span></span>
  
- [<span data-ttu-id="98d7d-107">PowerShell でライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="98d7d-107">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="98d7d-108">PowerShell を使用してサービスへのアクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="98d7d-108">Disable access to services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
    
<span data-ttu-id="98d7d-109">スクリプトに関連付けられている 2 つのファイルをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d7d-109">You need to download the two files that are associated with the script:</span></span>
  
- <span data-ttu-id="98d7d-110">ManageSway.ps1 スクリプト: [https://go.microsoft.com/fwlink/p/?LinkId=785070](https://go.microsoft.com/fwlink/p/?LinkId=785070)</span><span class="sxs-lookup"><span data-stu-id="98d7d-110">The ManageSway.ps1 script at [https://go.microsoft.com/fwlink/p/?LinkId=785070](https://go.microsoft.com/fwlink/p/?LinkId=785070)</span></span>
    
- <span data-ttu-id="98d7d-111">スクリプト用のヘルプ ファイル: [https://go.microsoft.com/fwlink/p/?LinkId=785072](https://go.microsoft.com/fwlink/p/?LinkId=785072)</span><span class="sxs-lookup"><span data-stu-id="98d7d-111">The help file for the script at [https://go.microsoft.com/fwlink/p/?LinkId=785072](https://go.microsoft.com/fwlink/p/?LinkId=785072)</span></span>
    

