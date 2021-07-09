---
title: MSSP カスタマー Microsoft 365 Defenderにアクセスする
description: MSSP カスタマー Microsoft 365 Defenderにアクセスする
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339588"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a><span data-ttu-id="498cd-104">MSSP カスタマー Microsoft 365 Defenderにアクセスする</span><span class="sxs-lookup"><span data-stu-id="498cd-104">Access the Microsoft 365 Defender MSSP customer portal</span></span>

<span data-ttu-id="498cd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="498cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="498cd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="498cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="498cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="498cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="498cd-108">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="498cd-108">**Applies to:**</span></span>

- [<span data-ttu-id="498cd-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="498cd-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="498cd-110">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="498cd-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="498cd-111">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="498cd-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="498cd-112">これらの一連の手順は、MSSP に向けて指示されます。</span><span class="sxs-lookup"><span data-stu-id="498cd-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="498cd-113">既定では、MSSP のお客様は次の URL Microsoft Defender セキュリティ センターテナントにアクセスします `https://securitycenter.windows.com` 。</span><span class="sxs-lookup"><span data-stu-id="498cd-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="498cd-114">ただし、MSSP は、MSSP カスタマー ポータルにアクセスするには、テナント固有の URL を次の形式で  `https://securitycenter.windows.com?tid=customer_tenant_id` 使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="498cd-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="498cd-115">一般に、MSSP は、管理する予定の MSSP 顧客の Azure ADに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="498cd-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="498cd-116">次の手順を使用して、MSSP カスタマー テナント ID を取得し、その ID を使用してテナント固有の URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="498cd-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="498cd-117">MSSP として、資格情報を使用して Azure ADにログインします。</span><span class="sxs-lookup"><span data-stu-id="498cd-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="498cd-118">ディレクトリを MSSP 顧客のテナントに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="498cd-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="498cd-119">[プロパティ **Azure Active Directory >] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="498cd-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="498cd-120">[ディレクトリ ID] フィールドにテナント ID があります。</span><span class="sxs-lookup"><span data-stu-id="498cd-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="498cd-121">次の URL の値を置き換え、MSSP カスタマー ポータル `customer_tenant_id` にアクセスします `https://securitycenter.windows.com?tid=customer_tenant_id` 。</span><span class="sxs-lookup"><span data-stu-id="498cd-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="498cd-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="498cd-122">Related topics</span></span>
- [<span data-ttu-id="498cd-123">ポータルへの MSSP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="498cd-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="498cd-124">アラート通知を構成する</span><span class="sxs-lookup"><span data-stu-id="498cd-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="498cd-125">顧客テナントからアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="498cd-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
