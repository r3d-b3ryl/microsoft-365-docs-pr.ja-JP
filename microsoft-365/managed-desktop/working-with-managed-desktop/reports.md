---
title: レポートを操作する
description: このサイトで使用できるさまざまなレポートMicrosoft マネージド デスクトップ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729970"
---
# <a name="work-with-reports"></a><span data-ttu-id="282e8-104">レポートを操作する</span><span class="sxs-lookup"><span data-stu-id="282e8-104">Work with reports</span></span>

<span data-ttu-id="282e8-105">Microsoft マネージド デスクトップ、組織の IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるいくつかのレポートとダッシュボードを提供します。</span><span class="sxs-lookup"><span data-stu-id="282e8-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="282e8-106">レポートは、次の 2 つの場所[](https://endpoint.microsoft.com)にあります。Microsoft エンドポイント マネージャー管理センター Microsoft 365[表示されます](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。</span><span class="sxs-lookup"><span data-stu-id="282e8-106"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="282e8-107">[レポート] Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="282e8-107">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="282e8-108">Microsoft エンドポイント マネージャー コンソールでは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("tenant") の構成とデバイスに関する問題の監視と調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="282e8-108">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="282e8-109">Microsoft Managed desktop には、メイン メニューの [レポート] の下に、登録したデバイスの Microsoft マネージド デスクトップの管理に固有のレポートを見つけるセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="282e8-109">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="282e8-110">これらのレポートには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="282e8-110">These reports include:</span></span>
- <span data-ttu-id="282e8-111">**管理対象デバイス**  > **機能更新** プログラム : このビューには、デバイス全体の機能更新プログラムのMicrosoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="282e8-111">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="282e8-112">**管理対象デバイス**  > **Office更新** プログラム : このビューには、デバイス全体のOffice更新プログラムのMicrosoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="282e8-112">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="282e8-113">さらに、Microsoft エンドポイント マネージャー を通じて複数の場所で、他の製品グループからレポートをフィルター処理して、ユーザーが管理するデバイスを具体的に含めるか除外Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="282e8-113">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="282e8-114">これらのレポートには、次のフィルター機能が統合されています。</span><span class="sxs-lookup"><span data-stu-id="282e8-114">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="282e8-115">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="282e8-115">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="282e8-116">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="282e8-116">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="282e8-117">非準拠デバイス</span><span class="sxs-lookup"><span data-stu-id="282e8-117">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="282e8-118">カスタム Microsoft マネージド デスクトップロールは、レポートへのアクセスのみをMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="282e8-118">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="282e8-119">すべてのデバイスなど、Microsoft エンドポイント マネージャーの他の部分にアクセスするには、「すべてのデバイスを使用した役割ベースのアクセス[制御」をMicrosoft Intune。](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="282e8-119">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 


 ## <a name="inventory-data"></a><span data-ttu-id="282e8-120">インベントリ データ</span><span class="sxs-lookup"><span data-stu-id="282e8-120">Inventory data</span></span>

<span data-ttu-id="282e8-121">他のレポートに加えて、ユーザーが管理するデバイスに関する情報をエクスポートMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="282e8-121">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="282e8-122">[すべての **デバイス]** タブの [デバイス] Microsoft エンドポイント マネージャーで、[すべてエクスポート] タブを使用して詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="282e8-122">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>