---
title: 管理センターでのセキュリティ &コンプライアンス センター& Exchange DLP の動作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: セキュリティ & コンプライアンス センターの DLP とメール フロー ルール (トランスポート ルール) が管理センターでどのように動作Exchangeします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34ddee1c1f0997852b6e59295ab9b630acc3ba3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177179"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="cfd5b-103">コンプライアンス センターと管理センターの間Microsoft 365 DLP の動作Exchange方法</span><span class="sxs-lookup"><span data-stu-id="cfd5b-103">How DLP works between the Microsoft 365 Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="cfd5b-104">このMicrosoft 365、2 つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-104">In Microsoft 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="cfd5b-105">Microsoft 365 **コンプライアンス** センターでは、SharePoint、OneDrive、Exchange、Teams、および現在のエンドポイント デバイスのコンテンツを保護するために、単一の DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-105">In the **Microsoft 365 Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, Teams, and now Endpoint Devices.</span></span> <span data-ttu-id="cfd5b-106">ここで DLP ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-106">We recommend that you create a DLP policy here.</span></span> <span data-ttu-id="cfd5b-107">詳細については、「データ損失防止 [リファレンス」を参照してください](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="cfd5b-108">管理センター **Exchangeで**、DLP ポリシーを作成して、コンテンツの保護をサポートExchange。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="cfd5b-109">このポリシーでは、Exchangeフロー ルール (トランスポート ルールとも呼ばれる) を使用できます。そのため、メールの処理に固有のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="cfd5b-110">詳細については、管理センターの[DLP をExchangeしてください](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="cfd5b-111">これらの管理センターで作成された DLP ポリシーは、サイド バイ サイドで機能します。このトピックでは、方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![セキュリティとコンプライアンス センターと管理センターの DLP Exchangeページ](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="cfd5b-113">セキュリティ コンプライアンス センターの DLP &管理センターの DLP およびメール フロー ルールExchangeする方法</span><span class="sxs-lookup"><span data-stu-id="cfd5b-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="cfd5b-114">セキュリティ & コンプライアンス センターで DLP ポリシーを作成すると、ポリシーに含まれるすべての場所にポリシーが展開されます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="cfd5b-115">ポリシーにポリシーに Exchange Onlineが含まれる場合、ポリシーはそこに同期され、Exchange 管理センターで作成された DLP ポリシーとまったく同じ方法で適用されます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="cfd5b-116">Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは引き続きセキュリティ & コンプライアンス センターで作成した電子メールのポリシーと並べて機能します。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="cfd5b-117">ただし、管理センターで作成されたExchangeが優先されます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="cfd5b-118">すべてのExchangeフロー ルールが最初に処理され、次にセキュリティ ポリシー コンプライアンス センター& DLP ルールが処理されます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="cfd5b-119">これは、次の意味を持つ。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-119">This means that:</span></span>
  
- <span data-ttu-id="cfd5b-120">メール フロー ルールによってブロックExchangeメッセージは、セキュリティ コンプライアンス センターで作成された DLP ルール&されません。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>

- <span data-ttu-id="cfd5b-121">DLP が DLP によってスキャンExchange前に、メール フロー ルールまたは他のフィルターによって検疫されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="cfd5b-121">Messages that are quarantined by Exchange mail flow rules or any other filters run before DLP will not be scanned by DLP</span></span>
    
- <span data-ttu-id="cfd5b-122">Exchange メール フロー ルールが、セキュリティ & コンプライアンス センターの DLP ポリシー (外部ユーザーの追加など) に一致する方法でメッセージを変更した場合、DLP ルールはこれを検出し、必要に応じてポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-122">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="cfd5b-123">また、「処理Exchange停止」アクションを使用するメール フロー ルールは、セキュリティ & コンプライアンス センターでの DLP ルールの処理には影響を与え、引き続き処理されます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-123">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="cfd5b-124">コンプライアンス センターとセキュリティ &管理センターのExchangeヒント</span><span class="sxs-lookup"><span data-stu-id="cfd5b-124">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="cfd5b-125">ポリシー ヒントは、Exchange 管理センターで作成された DLP ポリシーとメール フロー ルール、またはセキュリティ & コンプライアンス センターで作成された DLP ポリシーを使用して動作できますが、両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-125">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="cfd5b-126">これは、これらのポリシーは異なる場所に保存されますが、ポリシー ヒントは 1 つの場所からのみ描画できるためです。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-126">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="cfd5b-127">Exchange 管理センターでポリシー ヒントを構成した場合、セキュリティ & コンプライアンス センターで構成したポリシー ヒントは、Exchange 管理センターでヒントをオフにするまで、Outlook on the web および Outlook 2013 以降のユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-127">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="cfd5b-128">これにより、セキュリティ Exchangeコンプライアンス センターに切り替えるまで、現在のメール フロー ルールが&されます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-128">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="cfd5b-129">ポリシー ヒントは 1 つの場所からしか描画されませんが、セキュリティ & コンプライアンス センターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されます。</span><span class="sxs-lookup"><span data-stu-id="cfd5b-129">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
