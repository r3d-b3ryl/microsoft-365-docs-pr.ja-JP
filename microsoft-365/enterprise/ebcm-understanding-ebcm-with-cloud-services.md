---
title: クラウドサービスによるエンタープライズ ビジネスの継続性の管理について
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: クラウドサービスが IT サービスに含まれている場合の、ビジネスの継続性の計画と実装の違いを説明します。
ms.openlocfilehash: 2236304647275f5e2b7ddde3af1804ba749254b0
ms.sourcegitcommit: 0b2c41dad19da5f0513097c36a4ff32a5868836c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "42588720"
---
# <a name="enterprise-business-continuity-management-ebcm-with-cloud-services"></a><span data-ttu-id="2199a-103">クラウドサービスによるエンタープライズ ビジネスの継続性の管理 (EBCM) について</span><span class="sxs-lookup"><span data-stu-id="2199a-103">Enterprise business continuity management (EBCM) with cloud services</span></span>

<span data-ttu-id="2199a-104">組織のデジタル変換の一環として、Microsoft 365 クラウドサービスに依存しているビジネス プロセスに対応するために、障害復旧およびビジネスの継続性計画を見直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="2199a-104">As part of your organizations digital transformation, you need to revisit and update your disaster recovery and business continuity plans to account for the business process that depend on Microsoft 365 Cloud services.</span></span> <span data-ttu-id="2199a-105">Microsoft 365 クラウドサービス (Exchange Online、SharePoint Online、OneDrive for Business など) は、優れた回復性を持つように設計されています。</span><span class="sxs-lookup"><span data-stu-id="2199a-105">Microsoft 365 Cloud services, like Exchange Online, SharePoint Online and OneDrive for Business are designed and operated to be highly resilient.</span></span>

> [!NOTE]
> <span data-ttu-id="2199a-106">Microsoft 独自の EBCM プランの詳細については、「[エンタープライズのビジネス継続性の管理プログラムのホワイトペーパー](https://go.microsoft.com/fwlink/?linkid=2121521)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2199a-106">You can learn more about Microsoft's own EBCM plan in the [Enterprise Business Continuity Management Program whitepaper](https://go.microsoft.com/fwlink/?linkid=2121521).</span></span> <span data-ttu-id="2199a-107">ログインが必要です。</span><span class="sxs-lookup"><span data-stu-id="2199a-107">Login is required.</span></span>

<span data-ttu-id="2199a-108">たとえ回復性を備えていても、サービス インシデントは発生します。</span><span class="sxs-lookup"><span data-stu-id="2199a-108">Even with this resilience, service incidents do occur.</span></span> <span data-ttu-id="2199a-109">そのため、組織はよく準備し、ビジネスの継続性戦略を明確に定める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2199a-109">When they do, your organization should be prepared and have a well-defined business continuity strategy.</span></span>

<span data-ttu-id="2199a-110">まだ計画を見直していない場合は、ここで紹介するトピックが戦略の計画に役立ちます。また、サービスが既知の状態になるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="2199a-110">If you haven't updated your plans yet this series of topics helps you to plan your strategy so your services can fail to a known state.</span></span> <span data-ttu-id="2199a-111">これらのトピックでは、連続性の準備を改善するための主な考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="2199a-111">These topics highlight key considerations for improving your continuity readiness.</span></span>

## <a name="list-of-topics-with-links"></a><span data-ttu-id="2199a-112">トピックの一覧とリンク</span><span class="sxs-lookup"><span data-stu-id="2199a-112">List of topics with links</span></span>

- [<span data-ttu-id="2199a-113">顧客およびクラウドパートナーの責任</span><span class="sxs-lookup"><span data-stu-id="2199a-113">Customer and cloud partner responsibilities</span></span>](ebcm-customer-and-cloud-partner-ebcm-responsibilities.md)
- [<span data-ttu-id="2199a-114">Microsoft 365 サービスの回復性</span><span class="sxs-lookup"><span data-stu-id="2199a-114">Microsoft 365 service resiliency</span></span>](ebcm-m365-service-resiliency.md)
- [<span data-ttu-id="2199a-115">連続性の計画を立てる</span><span class="sxs-lookup"><span data-stu-id="2199a-115">Developing your continuity plan</span></span>](ebcm-developing-your-ebcm-plan.md)
- [<span data-ttu-id="2199a-116">Microsoft 365 のサービス インシデント対策のシナリオ</span><span class="sxs-lookup"><span data-stu-id="2199a-116">Microsoft 365 service incident mitigation scenarios</span></span>](ebcm-microsoft-365-mitigations.md)
- [<span data-ttu-id="2199a-117">Microsoft 365 ビジネス連続性計画のトレーニングとリハーサル</span><span class="sxs-lookup"><span data-stu-id="2199a-117">Microsoft 365 business continuity plan training and rehearsal</span></span>](ebcm-enterprise-business-continuity-management-plan-rehearsal-and-user-training.md)

## <a name="see-also"></a><span data-ttu-id="2199a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2199a-118">See also</span></span>

- [<span data-ttu-id="2199a-119">エンタープライズ ビジネス継続性法的免責事項</span><span class="sxs-lookup"><span data-stu-id="2199a-119">Enterprise business continuity legal disclaimer</span></span>](ebcm-legal-disclaimer.md)
