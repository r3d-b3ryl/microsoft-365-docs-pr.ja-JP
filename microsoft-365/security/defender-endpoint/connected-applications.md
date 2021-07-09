---
title: Microsoft Defender for Endpoint の接続アプリケーション
ms.reviewer: ''
description: 標準の OAuth 2.0 プロトコルを使用して認証を行い、Microsoft Defender for Endpoint API で使用するためのトークンを提供する接続パートナー アプリケーションを表示します。
keywords: パートナー、アプリケーション、サードパーティ、接続、sentinelone、ルックアウト、bitdefender、corrata、morphisec、paloalto、ziften、より良いモバイル
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4b212acdf4bdf8fa53ef00763463190e204fc1ed
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339168"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8e191-104">Microsoft Defender for Endpoint の接続アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8e191-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e191-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8e191-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e191-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8e191-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8e191-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e191-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8e191-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8e191-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8e191-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8e191-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8e191-110">接続されたアプリケーションは、API を使用して Defender for Endpoint プラットフォームと統合されます。</span><span class="sxs-lookup"><span data-stu-id="8e191-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="8e191-111">アプリケーションは、標準の OAuth 2.0 プロトコルを使用して認証を行い、Microsoft Defender for Endpoint API で使用するためのトークンを提供します。</span><span class="sxs-lookup"><span data-stu-id="8e191-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="8e191-112">さらに、Azure Active Directory (Azure AD) アプリケーションを使用すると、テナント管理者は、対応するアプリを使用してアクセスできる API を明示的に制御できます。</span><span class="sxs-lookup"><span data-stu-id="8e191-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="8e191-113">接続されているアプリケーションで API [を使用](/microsoft-365/security/defender-endpoint/apis-intro) するには、次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e191-113">You'll need to follow [these steps](/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="8e191-114">接続されているアプリケーション ページにアクセスする</span><span class="sxs-lookup"><span data-stu-id="8e191-114">Access the connected application page</span></span>
<span data-ttu-id="8e191-115">左側のナビゲーション メニューで、[**エンドポイント** パートナーと  >  **API 接続アプリケーション**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e191-115">From the left navigation menu, select **Endpoints** > **Partners and APIs** > **Connected applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="8e191-116">接続されているアプリケーションの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="8e191-116">View connected application details</span></span>
<span data-ttu-id="8e191-117">[接続されたアプリケーション] ページには、組織内の Microsoft Defender for Endpoint に接続AD Azure アプリケーションに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e191-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="8e191-118">接続されているアプリケーションの使用状況を確認できます。前回の表示、過去 24 時間の要求数、過去 30 日間の傾向の要求を行います。</span><span class="sxs-lookup"><span data-stu-id="8e191-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![接続されているアプリの画像](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="8e191-120">接続されているアプリケーションの編集、再構成、または削除</span><span class="sxs-lookup"><span data-stu-id="8e191-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="8e191-121">[ **アプリケーションの設定を開** く] リンクをクリックすると、対応する Azure ADアプリケーション管理ページが Azure portal で開きます。</span><span class="sxs-lookup"><span data-stu-id="8e191-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="8e191-122">Azure portal から、接続されているアプリケーションのアクセス許可の管理、再構成、または削除を行います。</span><span class="sxs-lookup"><span data-stu-id="8e191-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
