---
title: MSSP に送信されるアラート通知を構成する
description: MSSP に送信されるアラート通知を構成する
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166055"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="8ad10-104">MSSP に送信されるアラート通知を構成する</span><span class="sxs-lookup"><span data-stu-id="8ad10-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ad10-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8ad10-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ad10-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ad10-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8ad10-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ad10-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8ad10-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8ad10-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8ad10-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8ad10-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="8ad10-110">この手順は、MSSP カスタマーまたは MSSP によって実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ad10-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="8ad10-111">MSSP のお客様に代わってこれを構成するための適切なアクセス許可を MSSP に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad10-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="8ad10-112">ポータルへのアクセスが許可されると、アラート通知ルールを作成して、テナントに関連付けられたアラートが作成され、条件が満たされた場合にメールが MSSP に送信されます。</span><span class="sxs-lookup"><span data-stu-id="8ad10-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="8ad10-113">詳細については、「アラート通知の [ルールを作成する」を参照してください](configure-email-notifications.md#create-rules-for-alert-notifications)。</span><span class="sxs-lookup"><span data-stu-id="8ad10-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="8ad10-114">次のチェック ボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad10-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="8ad10-115">**[組織名を含** める] - 顧客名が電子メール通知に追加されます</span><span class="sxs-lookup"><span data-stu-id="8ad10-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="8ad10-116">**[テナント固有のポータル リンクを含める** ] - アラート リンク URL には、ターゲット テナント ポータルに直接アクセスできるテナント固有のパラメーター (tid=target_tenant_id) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ad10-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="8ad10-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ad10-117">Related topics</span></span>
- [<span data-ttu-id="8ad10-118">ポータルへの MSSP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="8ad10-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="8ad10-119">MSSP カスタマー ポータルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="8ad10-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="8ad10-120">顧客テナントからアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="8ad10-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
