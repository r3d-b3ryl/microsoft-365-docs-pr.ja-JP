---
title: Microsoft の脅威保護 Api の概要
description: Microsoft の脅威保護で利用可能な Api について
keywords: api、api、概要、インシデント、インシデント、脅威を探す
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 5b62ba22fc765c0f6f3febe00cc5043d37619acf
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650401"
---
# <a name="overview-of--microsoft-threat-protection-apis"></a><span data-ttu-id="57036-104">Microsoft の脅威保護 Api の概要</span><span class="sxs-lookup"><span data-stu-id="57036-104">Overview of  Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="57036-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="57036-105">**Applies to:**</span></span>
- <span data-ttu-id="57036-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="57036-106">Microsoft Threat Protection</span></span>


>[!IMPORTANT] 
><span data-ttu-id="57036-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="57036-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="57036-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="57036-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="57036-109">Microsoft の脅威保護ソリューションは、統合対応のプラットフォームの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="57036-109">Microsoft Threat Protection solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="57036-110">Lop レベルの Microsoft 脅威保護 Api を使用すると、共有インシデントと高度な検索テーブルに基づいてワークフローを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="57036-110">The lop-level Microsoft Threat Protection APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="57036-111">**インシデントキューの組み合わせ** -セキュリティ担当者は、攻撃対象範囲と影響を受ける資産全体がグループ化され、インシデント API の下で適時に表面化されることを保証することによって、重要なものに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="57036-111">**Combined incidents queue** - Helps security professionals focus on what's critical by ensuring that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="57036-112">**クロス積脅威** 検索-セキュリティチームは、さまざまな保護製品によって収集された未加工のデータを使用して独自のカスタムクエリを作成することによって、侵害の兆候を探すことができます。</span><span class="sxs-lookup"><span data-stu-id="57036-112">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="57036-113">これらの Api セットに加えて、さまざまな保護製品は、各製品の機能に基づいて改革するのに役立つ追加の Api を公開しています。</span><span class="sxs-lookup"><span data-stu-id="57036-113">In addition to these set of APIs each of the various protection products expose additional APIs to help you innovate based on each product capabilities.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57036-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="57036-114">Related topics</span></span>
- [<span data-ttu-id="57036-115">Microsoft Threat Protectin Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="57036-115">Access the Microsoft Threat Protectin APIs</span></span>](api-access.md)
- [<span data-ttu-id="57036-116">その他の API リソース</span><span class="sxs-lookup"><span data-stu-id="57036-116">Other API resources</span></span>](api-articles.md)
