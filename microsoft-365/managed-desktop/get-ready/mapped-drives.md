---
title: Microsoft マネージド デスクトップ用に、マップされたドライブを準備する
description: 確認するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: cd45d6155fc0e01f6a285f6182aa051281d160e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922910"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="200ee-104">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="200ee-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="200ee-105">多くのエンタープライズ環境では、マップされたドライブに関する従来の要件を満たして、ユーザーまたはチームがファイルを共有および保存したり、オンプレミス アプリケーションを共有したり保存したりできます。</span><span class="sxs-lookup"><span data-stu-id="200ee-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="200ee-106">Microsoft では、Microsoft Managed Desktop でマップされたドライブを使用することをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="200ee-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="200ee-107">代わりに、次のようにファイル アクセス ソリューションを最新化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="200ee-107">Instead, we recommend that you modernize your file access solutions as follows:</span></span>
  
- <span data-ttu-id="200ee-108">個々のユーザーが使用するマップされたドライブを OneDrive for Business に移行します。</span><span class="sxs-lookup"><span data-stu-id="200ee-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="200ee-109">チームが使用するマップされたドライブを移行して、ファイルを SharePoint Online に共有します。</span><span class="sxs-lookup"><span data-stu-id="200ee-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="200ee-110">オンプレミスのファイル共有を使用するアプリケーションを最新化または置き換え、その要件を削除します。</span><span class="sxs-lookup"><span data-stu-id="200ee-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="200ee-111">これらのサービスを最新化すると、Microsoft Managed Desktop で最高のユーザー エクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="200ee-111">Modernizing these services will allow the best user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="200ee-112">Microsoft FastTrack Services は、Microsoft Cloud Services を使用して環境を最新化する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="200ee-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="200ee-113">FastTrack サービスの対象かどうかを確認するには、「対象サービスとプラン」[](/fasttrack/m365-eligible-services-and-plans)を参照し、Microsoft マネージ デスクトップの準備のために直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="200ee-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="200ee-114">FastTrack OneDrive for Business または SharePoint Online 移行の背景については、「データ移行」 [を参照してください](/fasttrack/o365-data-migration)。</span><span class="sxs-lookup"><span data-stu-id="200ee-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="200ee-115">Microsoft Managed Desktop 上のマップされたドライブ</span><span class="sxs-lookup"><span data-stu-id="200ee-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="200ee-116">一部の使用例でマップされたドライブを削除または置き換えできない場合は、Microsoft Managed Desktop 管理ポータルでサポート要求を送信して、Microsoft Managed Desktop ユーザーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="200ee-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop admin portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="200ee-117">このような要求の場合は、サポート要求に次の詳細を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="200ee-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="200ee-118">Microsoft Managed Desktop デバイスにマップする必要があるファイル共有場所へのすべての UNC パス</span><span class="sxs-lookup"><span data-stu-id="200ee-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="200ee-119">これらのファイル共有場所へのアクセスを必要とするユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="200ee-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="200ee-120">割り当てる必要がある特定のドライブ文字 (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="200ee-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="200ee-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="200ee-121">For example:</span></span>

| <span data-ttu-id="200ee-122">ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="200ee-122">Drive letter</span></span> | <span data-ttu-id="200ee-123">UNC パス</span><span class="sxs-lookup"><span data-stu-id="200ee-123">UNC path</span></span> | <span data-ttu-id="200ee-124">ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="200ee-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="200ee-125">X:</span><span class="sxs-lookup"><span data-stu-id="200ee-125">X:</span></span>  | <span data-ttu-id="200ee-126">\\\server\share\Marketing</span><span class="sxs-lookup"><span data-stu-id="200ee-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="200ee-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="200ee-127">ContosoMarketing</span></span> |

<span data-ttu-id="200ee-128">ユーザーとグループがファイル共有の場所にアクセスするための適切なアクセス許可を持ち、維持し、オンプレミスのファイル サービスにアクセス可能な状態を維持することは、完全にユーザーの責任です。</span><span class="sxs-lookup"><span data-stu-id="200ee-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="200ee-129">また、そのようなファイル共有の要件をできるだけ早く削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="200ee-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="200ee-130">Microsoft Managed Desktop にマップされたドライブを展開するには</span><span class="sxs-lookup"><span data-stu-id="200ee-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="200ee-131">マップされたドライブを避けず、サービス要求を送信する前に要件を慎重に確認していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="200ee-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="200ee-132">次に、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="200ee-132">Then follow these steps:</span></span>

1. <span data-ttu-id="200ee-133">[[Microsoft Endpoint Manager]](https://endpoint.microsoft.com/)に移動し、[トラブルシューティングとサポート] を選択し、[Microsoft 管理デスクトップ] セクションで [サービス要求] を探します。</span><span class="sxs-lookup"><span data-stu-id="200ee-133">Navigate to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and select "Troubleshooting + support" then look for "Service requests" under the Microsoft Managed Desktop section.</span></span>  
2. <span data-ttu-id="200ee-134">"マップされたドライブの展開" というタイトルのサポート要求を送信し、必要なすべてのファイル共有の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="200ee-134">Submit a support request titled “Mapped drives deployment” and provide all the required file share details.</span></span>  
3. <span data-ttu-id="200ee-135">Microsoft Managed Desktop IT Operations は、要求が完了したら、サポート要求の更新プログラムを使用して助言します。</span><span class="sxs-lookup"><span data-stu-id="200ee-135">Microsoft Managed Desktop IT Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="200ee-136">最初は、この構成はテスト展開グループ内のデバイスにのみ展開されます。</span><span class="sxs-lookup"><span data-stu-id="200ee-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="200ee-137">Microsoft Managed Desktop IT Operations によって展開された構成が期待通り動作するかどうかをテストして確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="200ee-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop IT Operations works as you expect.</span></span> <span data-ttu-id="200ee-138">テストが完了したら、同じサポート要求の詳細にある [ディスカッション] タブを使用して返信し、Microsoft Managed Desktop IT Operations に通知します。</span><span class="sxs-lookup"><span data-stu-id="200ee-138">Reply using the Discussion tab in the details of the same support request to notify Microsoft Managed Desktop IT Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="200ee-139">その後、Microsoft Managed Desktop IT Operations チームが構成を他の展開グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="200ee-139">Microsoft Managed Desktop IT Operations team will then deploy the configuration to the other deployment groups.</span></span>