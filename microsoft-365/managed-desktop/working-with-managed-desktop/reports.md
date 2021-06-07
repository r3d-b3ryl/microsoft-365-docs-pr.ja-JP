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
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771887"
---
# <a name="work-with-reports"></a><span data-ttu-id="a8af3-104">レポートを操作する</span><span class="sxs-lookup"><span data-stu-id="a8af3-104">Work with reports</span></span>

<span data-ttu-id="a8af3-105">Microsoft マネージド デスクトップ、組織の IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるいくつかのレポートとダッシュボードを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8af3-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="a8af3-106">[レポート] Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="a8af3-106">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="a8af3-107">Microsoft エンドポイント マネージャー コンソールでは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("tenant") の構成とデバイスに関する問題の監視と調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a8af3-107">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="a8af3-108">Microsoft Managed desktop には、メイン メニューの [レポート] の下に、登録したデバイスの Microsoft マネージド デスクトップの管理に固有のレポートを見つけるセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="a8af3-108">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="a8af3-109">これらのレポートには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8af3-109">These reports include:</span></span>
- <span data-ttu-id="a8af3-110">**管理対象デバイス**  > **機能更新** プログラム : このビューには、デバイス全体の機能更新プログラムのMicrosoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8af3-110">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="a8af3-111">**管理対象デバイス**  > **Office更新** プログラム : このビューには、デバイス全体のOffice更新プログラムのMicrosoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8af3-111">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="a8af3-112">さらに、Microsoft エンドポイント マネージャー を通じて複数の場所で、他の製品グループからレポートをフィルター処理して、ユーザーが管理するデバイスを具体的に含めるか除外Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="a8af3-112">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="a8af3-113">これらのレポートには、次のフィルター機能が統合されています。</span><span class="sxs-lookup"><span data-stu-id="a8af3-113">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="a8af3-114">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="a8af3-114">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="a8af3-115">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="a8af3-115">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="a8af3-116">非準拠デバイス</span><span class="sxs-lookup"><span data-stu-id="a8af3-116">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="a8af3-117">カスタム Microsoft マネージド デスクトップロールは、レポートへのアクセスのみをMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="a8af3-117">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="a8af3-118">すべてのデバイスなど、Microsoft エンドポイント マネージャーの他の部分にアクセスするには、「すべてのデバイスを使用した役割ベースのアクセス[制御」をMicrosoft Intune。](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="a8af3-118">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 

## <a name="endpoint-analytics"></a><span data-ttu-id="a8af3-119">エンドポイント分析</span><span class="sxs-lookup"><span data-stu-id="a8af3-119">Endpoint analytics</span></span>
<span data-ttu-id="a8af3-120">Microsoft マネージド デスクトップエンドポイント分析と[統合されました](/mem/analytics/overview)。</span><span class="sxs-lookup"><span data-stu-id="a8af3-120">Microsoft Managed Desktop is now integrated with [Endpoint analytics](/mem/analytics/overview).</span></span> <span data-ttu-id="a8af3-121">これらのレポートは、組織の動作状況とユーザーに提供されるエクスペリエンスの品質を測定するための分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8af3-121">These reports give you insights for measuring how your organization is working and the quality of the experience delivered to your users.</span></span> <span data-ttu-id="a8af3-122">エンドポイント分析は、エンドポイントの **[レポート**] メニュー [Microsoft エンドポイント マネージャー。](https://endpoint.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a8af3-122">Endpoint analytics is in the **Reports** menu of [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="a8af3-123">スコアをピボットして、任意のレポートに移動Microsoft マネージド デスクトップ管理されているデバイスのみを含めるには、[フィルター]ドロップダウンを選択し、[デバイス] **Microsoft マネージド デスクトップします**。</span><span class="sxs-lookup"><span data-stu-id="a8af3-123">To pivot a score to only include devices being managed by Microsoft Managed Desktop go to any report, select the **Filter** drop down, and then select **Microsoft Managed Desktop devices**.</span></span>

<span data-ttu-id="a8af3-124">登録中に Azure AD組織 ("tenant") に対してエンドポイント分析が自動的に構成されていない場合は、自分で行います。</span><span class="sxs-lookup"><span data-stu-id="a8af3-124">If Endpoint analytics wasn't automatically configured for your Azure AD organization ("tenant") during enrollment, you can do that yourself.</span></span> <span data-ttu-id="a8af3-125">詳細については [、「Onboard in the Endpoint analytics portal」を参照してください](/mem/analytics/enroll-intune#bkmk_onboard)。</span><span class="sxs-lookup"><span data-stu-id="a8af3-125">For more information, see [Onboard in the Endpoint analytics portal](/mem/analytics/enroll-intune#bkmk_onboard).</span></span> <span data-ttu-id="a8af3-126">すべてのデバイスを登録するか、Microsoft マネージド デスクトップ デバイスのみを含める場合は、テスト、First、Fast、およびBroad のモダン ワークプレース デバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8af3-126">You can enroll all your devices or, if you want to include only Microsoft Managed Desktop devices, select the **modern workplace device** groups for Test, First, Fast, and Broad.</span></span> <span data-ttu-id="a8af3-127">これらのレポートでは、さまざまなアクセス許可が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8af3-127">These reports might require different permissions.</span></span> <span data-ttu-id="a8af3-128">詳細については、「アクセス許可」 [を参照](/mem/analytics/overview#permissions) して、役割が適切に割り当てられているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="a8af3-128">For more information, see [Permissions](/mem/analytics/overview#permissions) to ensure you have roles appropriately assigned.</span></span>

> [!NOTE]
> <span data-ttu-id="a8af3-129">プライバシー ユーザーのプライバシーを尊重するために、このフィルターを使用するには、Endpoint analytics に登録Microsoft マネージド デスクトップデバイスが 10 台を超える必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8af3-129">To better respect privacy user privacy, there must be more than 10 Microsoft Managed Desktop devices enrolled with Endpoint analytics to use this filter.</span></span>

 ## <a name="inventory-data"></a><span data-ttu-id="a8af3-130">インベントリ データ</span><span class="sxs-lookup"><span data-stu-id="a8af3-130">Inventory data</span></span>

<span data-ttu-id="a8af3-131">他のレポートに加えて、ユーザーが管理するデバイスに関する情報をエクスポートMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="a8af3-131">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="a8af3-132">[すべての **デバイス]** タブの [デバイス] Microsoft エンドポイント マネージャーで、[すべてエクスポート] タブを使用して詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="a8af3-132">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>
