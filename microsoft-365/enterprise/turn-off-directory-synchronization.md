---
title: ユーザーのディレクトリ同期をオフMicrosoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: この記事では、PowerShell を使用してユーザーのディレクトリ同期をオフにする方法Microsoft 365。
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445710"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="e345f-103">ユーザーのディレクトリ同期をオフMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="e345f-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="e345f-104">PowerShell を使用すると、ディレクトリ同期をオフにし、同期されたユーザーをクラウド専用に変換できます。</span><span class="sxs-lookup"><span data-stu-id="e345f-104">You can use PowerShell to turn off directory synchronization and convert your synchronized users to cloud-only.</span></span> <span data-ttu-id="e345f-105">ただし、トラブルシューティング手順としてディレクトリ同期をオフにすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e345f-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="e345f-106">ディレクトリ同期のトラブルシューティングに関するサポートが必要な場合は、「ディレクトリ同期に関する問題を修正する」の記事[Microsoft 365](fix-problems-with-directory-synchronization.md)してください。</span><span class="sxs-lookup"><span data-stu-id="e345f-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="e345f-107">[必要に応じて](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 、ビジネス製品のサポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e345f-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="e345f-108">ディレクトリ同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="e345f-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="e345f-109">ディレクトリ同期をオフにする方法:</span><span class="sxs-lookup"><span data-stu-id="e345f-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="e345f-110">まず、必要なソフトウェアをインストールし、サブスクリプションにMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="e345f-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="e345f-111">手順については、「Connect[モジュールのMicrosoft Azure Active Directory」を参照Windows PowerShell。](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e345f-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="e345f-112">[Set-MsolDirSyncEnabled を使用してディレクトリ](/previous-versions/azure/dn194097(v=azure.100))同期を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e345f-112">Use [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="e345f-113">このコマンドを使用する場合は、ディレクトリ同期を有効に戻す前に 72 時間待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e345f-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
