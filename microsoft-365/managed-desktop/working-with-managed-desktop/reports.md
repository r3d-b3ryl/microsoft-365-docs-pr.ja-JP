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
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921352"
---
# <a name="work-with-reports"></a><span data-ttu-id="864ab-103">レポートを操作する</span><span class="sxs-lookup"><span data-stu-id="864ab-103">Work with reports</span></span>

<span data-ttu-id="864ab-104">Microsoft マネージド デスクトップには、組織内の IT 管理者がデバイスの多様な側面を理解するために使用できる、いくつかのレポートとダッシュボードがあります。</span><span class="sxs-lookup"><span data-stu-id="864ab-104">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="864ab-105">レポートは [、Microsoft Endpoint Manager](https://endpoint.microsoft.com) と [Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)管理センターの 2 つの場所にあります。</span><span class="sxs-lookup"><span data-stu-id="864ab-105"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="864ab-106">Microsoft Endpoint Manager のレポート</span><span class="sxs-lookup"><span data-stu-id="864ab-106">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="864ab-107">Microsoft Endpoint Manager コンソールは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("テナント") の構成とデバイスに関する問題の監視と調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="864ab-107">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="864ab-108">Microsoft マネージド デスクトップには、メインメニューの [レポート] の下にセクションがあります。このセクションでは、登録したデバイスの Microsoft マネージド デスクトップの管理に固有のレポートを見つけられます。</span><span class="sxs-lookup"><span data-stu-id="864ab-108">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="864ab-109">これらのレポートには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="864ab-109">These reports include:</span></span>
- <span data-ttu-id="864ab-110">**管理対象デバイス**  > **機能更新** プログラム : このビューには、Microsoft マネージド デスクトップ デバイス全体の機能更新プログラムの全体的な状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="864ab-110">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="864ab-111">**管理対象デバイス**  > **Office更新**: このビューには、Microsoft マネージド デスクトップ デバイスOffice更新プログラムの全体的な状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="864ab-111">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="864ab-112">さらに、Microsoft Endpoint Manager の複数の場所では、他の製品グループからのレポートをフィルター処理して、Microsoft マネージド デスクトップで管理されているデバイスを具体的に含めるか除外することができます。</span><span class="sxs-lookup"><span data-stu-id="864ab-112">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="864ab-113">これらのレポートには、次のフィルタリング機能が統合されています。</span><span class="sxs-lookup"><span data-stu-id="864ab-113">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="864ab-114">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="864ab-114">All devices</span></span>](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="864ab-115">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="864ab-115">Device compliance</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="864ab-116">準拠しないデバイス</span><span class="sxs-lookup"><span data-stu-id="864ab-116">Noncompliant devices</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="864ab-117">カスタムの Microsoft マネージド デスクトップの役割は、Microsoft マネージド デスクトップ レポートへのアクセスのみを保証します。</span><span class="sxs-lookup"><span data-stu-id="864ab-117">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="864ab-118">すべてのデバイスなど、Microsoft Endpoint Manager の他の部分にアクセスするには、Microsoft Intune による役割ベースのアクセス[制御を参照してください](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="864ab-118">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span></span> 

## <a name="reports-in-microsoft-365-admin-center"></a><span data-ttu-id="864ab-119">Microsoft 365 管理センターのレポート</span><span class="sxs-lookup"><span data-stu-id="864ab-119">Reports in Microsoft 365 Admin Center</span></span>

<span data-ttu-id="864ab-120">Microsoft Managed Desktop Insights レポートを見つけるには [、Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)管理センターを開き、[レポート] に移動して [Microsoft マネージド デスクトップ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="864ab-120">You can find Microsoft Managed Desktop insights reports by opening the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop), and then navigating to **Reports** and selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="864ab-121">これらのレポートへの直接リンクは、ホーム ページの Microsoft Endpoint Manager の **[Microsoft マネージド** デスクトップ] [タブから実行することもできます](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="864ab-121">You can also follow the direct link to these reports from the **Microsoft Managed Desktop** tab on the homepage [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span> 

<span data-ttu-id="864ab-122">これらのレポートには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="864ab-122">These reports include:</span></span> 

- <span data-ttu-id="864ab-123">[利用状況の分析](usage-insights.md) 情報 - このビューは、Microsoft マネージド デスクトップ デバイスの使用状況の指標を提供します。</span><span class="sxs-lookup"><span data-stu-id="864ab-123">[Usage insights](usage-insights.md) - This view provides usage metrics for your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="864ab-124">[信頼性の分析](reliability-insights.md) 情報 - このビューには、管理対象デバイスの正常性の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="864ab-124">[Reliability insights](reliability-insights.md) - This view provides you with a health summary of your managed devices.</span></span>
- <span data-ttu-id="864ab-125">[バッテリーの分析](battery-insights.md) 情報 - このビューには、環境内のデバイスに対するアプリの電力消費量と、バッテリー残量の計画に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="864ab-125">[Battery insights](battery-insights.md) - This view shows you information about the energy consumption of apps and projected battery life for devices in your environment.</span></span>
- <span data-ttu-id="864ab-126">[Windows セキュリティ更新プログラムの分析](security-update-insights.md) 情報 - このビューには、Microsoft マネージド デスクトップ デバイスのセキュリティ更新プログラムの状態に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="864ab-126">[Windows security update insights](security-update-insights.md) - This view shows you information about the status of security updates for your Microsoft Managed Desktop devices.</span></span>

 ## <a name="inventory-data"></a><span data-ttu-id="864ab-127">インベントリ データ</span><span class="sxs-lookup"><span data-stu-id="864ab-127">Inventory data</span></span>

<span data-ttu-id="864ab-128">その他のレポートに加えて、Microsoft マネージド デスクトップで管理されているデバイスに関する情報をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="864ab-128">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="864ab-129">Microsoft Endpoint Manager **の [** デバイス] 領域の[デバイス] ビューで、[すべてエクスポート] タブを使用して、詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="864ab-129">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>
