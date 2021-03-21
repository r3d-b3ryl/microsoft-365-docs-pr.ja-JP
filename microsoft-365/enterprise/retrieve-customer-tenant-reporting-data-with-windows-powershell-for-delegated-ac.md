---
title: DAP パートナー向けデータを使用して顧客Windows PowerShellレポート データを取得する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 概要:Microsoft Exchange Online用のリモートWindows PowerShellを使用して、個々の顧客テナントからレポートを取得します。
ms.openlocfilehash: 8ea5f9834bfcc0d517fc1e0938c3547d88d1d8a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927218"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="8fdf4-103">委任アクセス許可 (DAP) パートナー用 Windows PowerShell を使用して顧客のテナント レポート データを取得する</span><span class="sxs-lookup"><span data-stu-id="8fdf4-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="8fdf4-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="8fdf4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8fdf4-105">個々の顧客Windows PowerShellからMicrosoft Exchange Onlineを取得するには、リモート サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>
  
<span data-ttu-id="8fdf4-106">シンジケーションおよびクラウド ソリューション プロバイダー (CSP) パートナーは、Exchange Online PowerShell 用のリモート サーバー経由で顧客テナント レポートを直接構成するデータWindows PowerShellアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="8fdf4-107">これにより、パートナーはレポートのデータを収集および保存してから、その他の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="8fdf4-108">リモート接続を開いた後、顧客テナンシーに関するレポート データを取得することは、顧客テナンシーに対してなんらかのコマンドレットを実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>
  
<span data-ttu-id="8fdf4-109">この記事では、Exchange Online のリモート Windows PowerShellを使用して、単一の顧客テナントに接続し、レポートを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="8fdf4-110">既定では、Windows PowerShell は複数の顧客テナンシーからレポート データを集約することをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="8fdf4-111">この手順で取得するレポートは、接続先の  _DelegatedOrg_ のレポートのみです。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>
  
 
## <a name="before-you-begin"></a><span data-ttu-id="8fdf4-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="8fdf4-112">Before you begin</span></span>

- <span data-ttu-id="8fdf4-p103">Exchange Online テナントへの接続は、リモートの Windows PowerShell を使用して行う必要があります。手順については、「[委任アクセス許可 (DAP) パートナー用リモート Windows PowerShell で Exchange Online テナントに接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-p103">You need to connect to your Exchange Online tenant by using remote Windows PowerShell. For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>
    
## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="8fdf4-115">Get-StaleMailboxReport のサンプルを実行する</span><span class="sxs-lookup"><span data-stu-id="8fdf4-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="8fdf4-116">Exchange Online へのリモート セッションを開いた後、このコマンドを実行して、日付範囲が 03/25/2015 ～ 03/31/2015 の **Get-StaleMailboxReport** を取得します。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="8fdf4-p104">Exchange Online、Lync Online、および SharePoint Online には使用できるその他多数のレポート コマンドレットだけでなく、使用できるその他のメッセージ追跡用コマンドレットもあります。使用可能なレポート コマンドレットと Office 365 レポート Web サービスの詳細については、次のセクションのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fdf4-p104">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use. To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8fdf4-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fdf4-119">See also</span></span>

#### 

<span data-ttu-id="8fdf4-120">[Office 365 レポート Web サービス](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="8fdf4-120">[Office 365 Reporting web service](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span></span>
  
[<span data-ttu-id="8fdf4-121">Get-CsClientDeviceDetailReport</span><span class="sxs-lookup"><span data-stu-id="8fdf4-121">Reporting cmdlets in Exchange Online</span></span>](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[<span data-ttu-id="8fdf4-122">パートナーのヘルプ</span><span class="sxs-lookup"><span data-stu-id="8fdf4-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)