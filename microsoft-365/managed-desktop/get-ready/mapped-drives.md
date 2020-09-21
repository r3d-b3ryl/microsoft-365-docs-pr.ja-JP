---
title: Microsoft マネージド デスクトップ用に、マップされたドライブを準備する
description: 確認のための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: fc216adadea8dd774901d42a754fb288412318a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104596"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="4cda1-104">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="4cda1-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="4cda1-105">多くのエンタープライズ環境には、マップされたドライブに対する従来の要件があります。これにより、ユーザーまたはチームは、ファイルを共有および保存したり、オンプレミスのアプリケーションを使用したりできます。</span><span class="sxs-lookup"><span data-stu-id="4cda1-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="4cda1-106">Microsoft では、マップされたドライブを Microsoft マネージドデスクトップと共に使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="4cda1-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="4cda1-107">代わりに、ファイルアクセスソリューションを次のように改革することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4cda1-107">Instead, we recommend that you modernize your file access solutions as follows:</span></span>
  
- <span data-ttu-id="4cda1-108">個別のユーザーによって使用されるマップされたドライブを OneDrive for Business に移行します。</span><span class="sxs-lookup"><span data-stu-id="4cda1-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="4cda1-109">Teams で使用されるマップされたドライブを移行して、ファイルを SharePoint Online に共有します。</span><span class="sxs-lookup"><span data-stu-id="4cda1-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="4cda1-110">オンプレミスのファイル共有を使用するアプリケーションを近代化またはリプレースして、その要件を削除します。</span><span class="sxs-lookup"><span data-stu-id="4cda1-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="4cda1-111">モダン化これらのサービスを使用すると、Microsoft マネージドデスクトップで最高のユーザー環境を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4cda1-111">Modernizing these services will allow the best user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4cda1-112">Microsoft FastTrack サービスは、Microsoft クラウドサービスを使用してお客様の環境をモダン化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4cda1-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="4cda1-113">必要な [サービスおよびプラン](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) で fasttrack サービスの対象となっているかどうかを確認してから、Microsoft マネージドデスクトップの準備のために直接連絡することができます。</span><span class="sxs-lookup"><span data-stu-id="4cda1-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="4cda1-114">FastTrack OneDrive for Business または SharePoint Online の移行の背景については、「 [データ移行](https://docs.microsoft.com/fasttrack/o365-data-migration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cda1-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](https://docs.microsoft.com/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="4cda1-115">Microsoft マネージドデスクトップでのマップされたドライブ</span><span class="sxs-lookup"><span data-stu-id="4cda1-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="4cda1-116">一部のユースケースでマップされたドライブを削除または置換できない場合は、microsoft Managed Desktop 管理ポータルでサポート要求を送信して、Microsoft Managed Desktop ユーザーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cda1-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop admin portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="4cda1-117">このような要求では、サポート要求に次の詳細情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cda1-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="4cda1-118">Microsoft マネージドデスクトップデバイスにマップする必要があるファイル共有場所へのすべての UNC パス</span><span class="sxs-lookup"><span data-stu-id="4cda1-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="4cda1-119">これらのファイル共有場所へのアクセスを必要とするユーザーグループ</span><span class="sxs-lookup"><span data-stu-id="4cda1-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="4cda1-120">割り当てる必要がある特定のドライブ文字 (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="4cda1-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="4cda1-121">例:</span><span class="sxs-lookup"><span data-stu-id="4cda1-121">For example:</span></span>

| <span data-ttu-id="4cda1-122">ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="4cda1-122">Drive letter</span></span> | <span data-ttu-id="4cda1-123">UNC パス</span><span class="sxs-lookup"><span data-stu-id="4cda1-123">UNC path</span></span> | <span data-ttu-id="4cda1-124">ユーザーグループ</span><span class="sxs-lookup"><span data-stu-id="4cda1-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="4cda1-125">エックス</span><span class="sxs-lookup"><span data-stu-id="4cda1-125">X:</span></span>  | <span data-ttu-id="4cda1-126">\\\ \ \ sharepoint/マーケティング</span><span class="sxs-lookup"><span data-stu-id="4cda1-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="4cda1-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="4cda1-127">ContosoMarketing</span></span> |

<span data-ttu-id="4cda1-128">ユーザーやグループがファイル共有の場所にアクセスするための適切なアクセス許可を持っており、オンプレミスのファイルサービスにアクセスできることを確認するのは完全に責任があります。</span><span class="sxs-lookup"><span data-stu-id="4cda1-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="4cda1-129">また、このようなファイル共有の要件をできるだけ早く削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cda1-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="4cda1-130">Microsoft マネージドデスクトップにマップされたドライブを展開するには</span><span class="sxs-lookup"><span data-stu-id="4cda1-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="4cda1-131">マップされたドライブを使用しないようにして、サービスリクエストを提出する前に要件を慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="4cda1-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="4cda1-132">その後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4cda1-132">Then follow these steps:</span></span>

1. <span data-ttu-id="4cda1-133">[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/)に移動し、[トラブルシューティング + サポート] を選択してから、microsoft 管理されたデスクトップ op セクションの下にある [サービスリクエスト] を探します。</span><span class="sxs-lookup"><span data-stu-id="4cda1-133">Navigate to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and select "Troubleshooting + support" then look for "Service requests" under the Microsoft Managed Deskop section.</span></span>  
2. <span data-ttu-id="4cda1-134">"マップされたドライブの展開" というタイトルのサポート要求を送信し、必要なファイル共有の詳細をすべて提供します。</span><span class="sxs-lookup"><span data-stu-id="4cda1-134">Submit a support request titled “Mapped drives deployment” and provide all the required file share details.</span></span>  
3. <span data-ttu-id="4cda1-135">Microsoft マネージドデスクトップ IT 操作は、要求が完了したときに、サポート要求の更新を使用してアドバイスします。</span><span class="sxs-lookup"><span data-stu-id="4cda1-135">Microsoft Managed Desktop IT Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="4cda1-136">最初は、この構成はテスト展開グループのデバイスにのみ展開されます。</span><span class="sxs-lookup"><span data-stu-id="4cda1-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="4cda1-137">Microsoft マネージドデスクトップの IT 運用によって展開された構成が期待どおりに動作するかどうかをテストし、確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cda1-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop IT Operations works as you expect.</span></span> <span data-ttu-id="4cda1-138">同じサポート要求の詳細にある [ディスカッション] タブを使用して返信し、テストが完了したことを Microsoft Managed Desktop IT Operations に通知します。</span><span class="sxs-lookup"><span data-stu-id="4cda1-138">Reply using the Discussion tab in the details of the same support request to notify Microsoft Managed Desktop IT Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="4cda1-139">Microsoft Managed Desktop IT 運用チームは、その構成を他の展開グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="4cda1-139">Microsoft Managed Desktop IT Operations team will then deploy the configuration to the other deployment groups.</span></span> 
