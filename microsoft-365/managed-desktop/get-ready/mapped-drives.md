---
title: Microsoft マネージド デスクトップ用に、マップされたドライブを準備する
description: 確認する重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 34b2186ea3f9129ae7bb602aee879d7d23424136
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841066"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="509e0-104">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="509e0-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="509e0-105">多くのエンタープライズ環境には、マップされたドライブに関するレガシ要件があります。この要件により、ユーザーやチームはファイルを共有および保存したり、オンプレミス アプリケーションを共有したり保存したりできます。</span><span class="sxs-lookup"><span data-stu-id="509e0-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="509e0-106">Microsoft では、Microsoft マネージド デスクトップでマップされたドライブを使用することを推奨しません。</span><span class="sxs-lookup"><span data-stu-id="509e0-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="509e0-107">代わりに、ファイル アクセス ソリューションを次のようにモダン化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="509e0-107">Instead, we recommend that you modernize your file access solutions as follows:</span></span>
  
- <span data-ttu-id="509e0-108">個々のユーザーが使用するマップされたドライブを OneDrive for Business に移行します。</span><span class="sxs-lookup"><span data-stu-id="509e0-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="509e0-109">チームがファイルを共有するために使用するマップされたドライブを SharePoint Online に移行します。</span><span class="sxs-lookup"><span data-stu-id="509e0-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="509e0-110">オンプレミスのファイル共有を使用するアプリケーションをモダン化または置換して、その要件を削除します。</span><span class="sxs-lookup"><span data-stu-id="509e0-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="509e0-111">これらのサービスをモダン化すると、Microsoft マネージド デスクトップで最適なユーザー エクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="509e0-111">Modernizing these services will allow the best user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="509e0-112">Microsoft FastTrack サービスは、Microsoft クラウド サービスを使用して環境をモダン化する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="509e0-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="509e0-113">対象となるサービスとプランで FastTrack サービスの対象かどうかを確認[](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans)し、Microsoft マネージド デスクトップの準備のために直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="509e0-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="509e0-114">FastTrack OneDrive for Business または SharePoint Online 移行の背景情報については、「データ移行」 [を参照してください](https://docs.microsoft.com/fasttrack/o365-data-migration)。</span><span class="sxs-lookup"><span data-stu-id="509e0-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](https://docs.microsoft.com/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="509e0-115">Microsoft マネージド デスクトップ上のマップされたドライブ</span><span class="sxs-lookup"><span data-stu-id="509e0-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="509e0-116">一部の使用例で、マップされたドライブを削除または置換できない場合は、Microsoft マネージド デスクトップ管理ポータルでサポート要求を送信して、Microsoft マネージド デスクトップ ユーザーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="509e0-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop admin portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="509e0-117">このような要求の場合は、サポート要求に次の詳細を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="509e0-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="509e0-118">Microsoft マネージド デスクトップ デバイスにマップする必要があるファイル共有の場所へのすべての UNC パス</span><span class="sxs-lookup"><span data-stu-id="509e0-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="509e0-119">これらのファイル共有の場所へのアクセスが必要なユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="509e0-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="509e0-120">割り当てる必要がある特定のドライブ文字 (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="509e0-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="509e0-121">例:</span><span class="sxs-lookup"><span data-stu-id="509e0-121">For example:</span></span>

| <span data-ttu-id="509e0-122">ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="509e0-122">Drive letter</span></span> | <span data-ttu-id="509e0-123">UNC パス</span><span class="sxs-lookup"><span data-stu-id="509e0-123">UNC path</span></span> | <span data-ttu-id="509e0-124">ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="509e0-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="509e0-125">X:</span><span class="sxs-lookup"><span data-stu-id="509e0-125">X:</span></span>  | <span data-ttu-id="509e0-126">\\\server\share\Marketing</span><span class="sxs-lookup"><span data-stu-id="509e0-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="509e0-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="509e0-127">ContosoMarketing</span></span> |

<span data-ttu-id="509e0-128">ユーザーとグループがファイル共有の場所にアクセスするための適切なアクセス許可を持ち、維持し、オンプレミスのファイル サービスにアクセス可能なままにすることは、完全にユーザーの責任です。</span><span class="sxs-lookup"><span data-stu-id="509e0-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="509e0-129">また、このようなファイル共有の要件はできるだけ早く削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="509e0-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="509e0-130">Microsoft マネージド デスクトップにマップされたドライブを展開するには</span><span class="sxs-lookup"><span data-stu-id="509e0-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="509e0-131">マップされたドライブを回避できないことを確認し、サービス要求を送信する前に要件を慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="509e0-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="509e0-132">次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="509e0-132">Then follow these steps:</span></span>

1. <span data-ttu-id="509e0-133">Microsoft [Endpoint Manager に移動](https://endpoint.microsoft.com/) し、[トラブルシューティング + サポート] を選択し、[Microsoft マネージド デスクトップ] セクションで [サービス要求] を探します。</span><span class="sxs-lookup"><span data-stu-id="509e0-133">Navigate to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and select "Troubleshooting + support" then look for "Service requests" under the Microsoft Managed Desktop section.</span></span>  
2. <span data-ttu-id="509e0-134">「マップされたドライブの展開」というタイトルのサポート要求を送信し、必要なすべてのファイル共有の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="509e0-134">Submit a support request titled “Mapped drives deployment” and provide all the required file share details.</span></span>  
3. <span data-ttu-id="509e0-135">Microsoft マネージド デスクトップ IT 運用は、要求が完了したら、サポート要求の更新を使用してアドバイスします。</span><span class="sxs-lookup"><span data-stu-id="509e0-135">Microsoft Managed Desktop IT Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="509e0-136">最初は、この構成はテスト展開グループ内のデバイスにのみ展開されます。</span><span class="sxs-lookup"><span data-stu-id="509e0-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="509e0-137">Microsoft マネージド デスクトップ IT 操作によって展開された構成が期待通り動作するかどうかをテストして確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="509e0-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop IT Operations works as you expect.</span></span> <span data-ttu-id="509e0-138">テストが完了したら、同じサポート要求の詳細にある [ディスカッション] タブを使用して返信し、Microsoft マネージド デスクトップ IT 操作に通知します。</span><span class="sxs-lookup"><span data-stu-id="509e0-138">Reply using the Discussion tab in the details of the same support request to notify Microsoft Managed Desktop IT Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="509e0-139">その後、Microsoft マネージド デスクトップ IT 運用チームは、構成を他の展開グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="509e0-139">Microsoft Managed Desktop IT Operations team will then deploy the configuration to the other deployment groups.</span></span> 
