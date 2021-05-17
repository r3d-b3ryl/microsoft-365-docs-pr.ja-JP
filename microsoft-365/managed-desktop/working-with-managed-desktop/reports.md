---
title: レポートを操作する
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917684"
---
# <a name="work-with-reports"></a><span data-ttu-id="50963-103">レポートを操作する</span><span class="sxs-lookup"><span data-stu-id="50963-103">Work with reports</span></span>

<span data-ttu-id="50963-104">Microsoft マネージド デスクトップ、組織の IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるいくつかのレポートとダッシュボードを提供します。</span><span class="sxs-lookup"><span data-stu-id="50963-104">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="50963-105">レポートは、次の 2 つの場所[](https://endpoint.microsoft.com)にあります。Microsoft エンドポイント マネージャー管理センター Microsoft 365[表示されます](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。</span><span class="sxs-lookup"><span data-stu-id="50963-105"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="50963-106">[レポート] Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="50963-106">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="50963-107">Microsoft エンドポイント マネージャー コンソールでは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("tenant") の構成とデバイスに関する問題の監視と調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="50963-107">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="50963-108">Microsoft Managed desktop には、メイン メニューの [レポート] の下に、登録したデバイスの Microsoft マネージド デスクトップの管理に固有のレポートを見つけるセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="50963-108">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="50963-109">これらのレポートには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="50963-109">These reports include:</span></span>
- <span data-ttu-id="50963-110">**管理対象デバイス**  > **機能更新** プログラム : このビューには、デバイス全体の機能更新プログラムのMicrosoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="50963-110">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="50963-111">**管理対象デバイス**  > **Office更新** プログラム : このビューには、デバイス全体のOffice更新プログラムのMicrosoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="50963-111">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="50963-112">さらに、Microsoft エンドポイント マネージャー を通じて複数の場所で、他の製品グループからレポートをフィルター処理して、ユーザーが管理するデバイスを具体的に含めるか除外Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="50963-112">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="50963-113">これらのレポートには、次のフィルター機能が統合されています。</span><span class="sxs-lookup"><span data-stu-id="50963-113">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="50963-114">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="50963-114">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="50963-115">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="50963-115">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="50963-116">非準拠デバイス</span><span class="sxs-lookup"><span data-stu-id="50963-116">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="50963-117">カスタム Microsoft マネージド デスクトップロールは、レポートへのアクセスのみをMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="50963-117">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="50963-118">すべてのデバイスなど、Microsoft エンドポイント マネージャーの他の部分にアクセスするには、「すべてのデバイスを使用した役割ベースのアクセス[制御」をMicrosoft Intune。](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="50963-118">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 

## <a name="reports-in-microsoft-365-admin-center"></a><span data-ttu-id="50963-119">管理センター Microsoft 365レポート</span><span class="sxs-lookup"><span data-stu-id="50963-119">Reports in Microsoft 365 Admin Center</span></span>

<span data-ttu-id="50963-120">分析情報レポートMicrosoft マネージド デスクトップ見つけるには、管理センターを開Microsoft 365[レポート] に移動し、[レポート] を選択 **Microsoft マネージド デスクトップ。** [](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)</span><span class="sxs-lookup"><span data-stu-id="50963-120">You can find Microsoft Managed Desktop insights reports by opening the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop), and then navigating to **Reports** and selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="50963-121">これらのレポートへの直接リンクは、ホームページの **[Microsoft マネージド デスクトップ]** タブ [からMicrosoft エンドポイント マネージャー。](https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="50963-121">You can also follow the direct link to these reports from the **Microsoft Managed Desktop** tab on the homepage [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span> 

<span data-ttu-id="50963-122">これらのレポートには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="50963-122">These reports include:</span></span> 

- <span data-ttu-id="50963-123">[利用状況の分析](usage-insights.md)情報 - このビューは、ユーザーのデバイスの使用状況Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="50963-123">[Usage insights](usage-insights.md) - This view provides usage metrics for your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="50963-124">[信頼性の分析情報](reliability-insights.md) - このビューには、管理対象デバイスの正常性の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50963-124">[Reliability insights](reliability-insights.md) - This view provides you with a health summary of your managed devices.</span></span>
- <span data-ttu-id="50963-125">[バッテリーの分析](battery-insights.md) 情報 - このビューには、環境内のデバイスのアプリのエネルギー消費量と、投影されるバッテリ寿命に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50963-125">[Battery insights](battery-insights.md) - This view shows you information about the energy consumption of apps and projected battery life for devices in your environment.</span></span>
- <span data-ttu-id="50963-126">[Windows更新プログラムの分析](security-update-insights.md)情報 - このビューには、デバイスのセキュリティ更新プログラムの状態に関するMicrosoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="50963-126">[Windows security update insights](security-update-insights.md) - This view shows you information about the status of security updates for your Microsoft Managed Desktop devices.</span></span>

 ## <a name="inventory-data"></a><span data-ttu-id="50963-127">インベントリ データ</span><span class="sxs-lookup"><span data-stu-id="50963-127">Inventory data</span></span>

<span data-ttu-id="50963-128">他のレポートに加えて、ユーザーが管理するデバイスに関する情報をエクスポートMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="50963-128">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="50963-129">[すべての **デバイス]** タブの [デバイス] Microsoft エンドポイント マネージャーで、[すべてエクスポート] タブを使用して詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="50963-129">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>