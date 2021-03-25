---
title: Microsoft Defender Security Center MSSP カスタマー ポータルにアクセスする
description: Microsoft Defender Security Center MSSP カスタマー ポータルにアクセスする
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164859"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="39e96-104">Microsoft Defender Security Center MSSP カスタマー ポータルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="39e96-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="39e96-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="39e96-105">**Applies to:**</span></span>
- [<span data-ttu-id="39e96-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39e96-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="39e96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39e96-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="39e96-108">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="39e96-108">**Applies to:**</span></span>

- [<span data-ttu-id="39e96-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39e96-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="39e96-110">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="39e96-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="39e96-111">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="39e96-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="39e96-112">これらの一連の手順は、MSSP に向けて指示されます。</span><span class="sxs-lookup"><span data-stu-id="39e96-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="39e96-113">既定では、MSSP のお客様は、次の URL を使用して Microsoft Defender セキュリティ センター テナントにアクセスします `https://securitycenter.windows.com` 。</span><span class="sxs-lookup"><span data-stu-id="39e96-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="39e96-114">ただし、MSSP は、MSSP カスタマー ポータルにアクセスするには、テナント固有の URL を次の形式で  `https://securitycenter.windows.com?tid=customer_tenant_id` 使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39e96-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="39e96-115">一般に、MSSP は、管理する予定の MSSP 顧客の Azure ADに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39e96-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="39e96-116">次の手順を使用して、MSSP カスタマー テナント ID を取得し、その ID を使用してテナント固有の URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="39e96-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="39e96-117">MSSP として、資格情報を使用して Azure ADにログインします。</span><span class="sxs-lookup"><span data-stu-id="39e96-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="39e96-118">ディレクトリを MSSP 顧客のテナントに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="39e96-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="39e96-119">[Azure **Active Directory >プロパティ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39e96-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="39e96-120">[ディレクトリ ID] フィールドにテナント ID があります。</span><span class="sxs-lookup"><span data-stu-id="39e96-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="39e96-121">次の URL の値を置き換え、MSSP カスタマー ポータル `customer_tenant_id` にアクセスします `https://securitycenter.windows.com?tid=customer_tenant_id` 。</span><span class="sxs-lookup"><span data-stu-id="39e96-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="39e96-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="39e96-122">Related topics</span></span>
- [<span data-ttu-id="39e96-123">ポータルへの MSSP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="39e96-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="39e96-124">アラート通知の構成</span><span class="sxs-lookup"><span data-stu-id="39e96-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="39e96-125">顧客テナントからアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="39e96-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
