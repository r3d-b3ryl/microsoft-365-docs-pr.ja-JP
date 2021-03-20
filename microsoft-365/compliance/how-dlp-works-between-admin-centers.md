---
title: EXCHANGE 管理センターでのセキュリティ &コンプライアンス センター& DLP の動作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
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
description: セキュリティ コンプライアンス センターの DLP & Exchange 管理センターの DLP およびメール フロー ルール (トランスポート ルール) を使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd8a3eb0e7bb859ab9e10551fadd22cc7dcb2a39
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905939"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="5bfb9-103">セキュリティ/コンプライアンス センターと Exchange 管理センターでの DLP の動作</span><span class="sxs-lookup"><span data-stu-id="5bfb9-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="5bfb9-104">365 Officeでは、次の 2 つの異なる管理センターにデータ損失防止 (DLP) ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="5bfb9-105">セキュリティ & **コンプライアンス** センターで、SharePoint、OneDrive、Exchange、および現在の Microsoft Teams でコンテンツを保護するのに役立つ単一の DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="5bfb9-106">可能であれば、ここで DLP ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="5bfb9-107">詳細については [、「Security & コンプライアンス センター」の「DLP」を参照してください](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="5bfb9-108">Exchange 管理 **センターで、Exchange** でのみコンテンツを保護するための DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="5bfb9-109">このポリシーでは、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を使用できます。そのため、メールの処理に固有のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="5bfb9-110">詳細については [、「Exchange 管理センターの DLP」を参照してください](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="5bfb9-111">これらの管理センターで作成された DLP ポリシーは、サイド バイ サイドで機能します。このトピックでは、方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![セキュリティとコンプライアンス センターと Exchange 管理センターの DLP ページ](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="5bfb9-113">セキュリティ コンプライアンス センターの DLP & Exchange 管理センターの DLP およびメール フロー ルールを使用する方法</span><span class="sxs-lookup"><span data-stu-id="5bfb9-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="5bfb9-114">セキュリティ & コンプライアンス センターで DLP ポリシーを作成すると、ポリシーに含まれるすべての場所にポリシーが展開されます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="5bfb9-115">ポリシーに Exchange Online が含まれる場合、ポリシーはそこに同期され、Exchange 管理センターで作成された DLP ポリシーとまったく同じ方法で適用されます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="5bfb9-116">Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは引き続きセキュリティ & コンプライアンス センターで作成した電子メールのポリシーと並べて機能します。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="5bfb9-117">ただし、Exchange 管理センターで作成されたルールが優先されます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="5bfb9-118">すべての Exchange メール フロー ルールが最初に処理され、次にセキュリティ ポリシーコンプライアンス センター& DLP ルールが処理されます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="5bfb9-119">これは、次の意味を持つ。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-119">This means that:</span></span>
  
- <span data-ttu-id="5bfb9-120">Exchange メール フロー ルールによってブロックされたメッセージは、セキュリティ コンプライアンス センターで作成された DLP ルール&されません。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="5bfb9-121">Exchange メール フロー ルールが、セキュリティ & コンプライアンス センターの DLP ポリシー (外部ユーザーの追加など) に一致する方法でメッセージを変更した場合、DLP ルールはこれを検出し、必要に応じてポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="5bfb9-122">また、「処理の停止」アクションを使用する Exchange メール フロー ルールは、セキュリティ & コンプライアンス センターでの DLP ルールの処理には影響を与え、引き続き処理されます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="5bfb9-123">コンプライアンス センターと Exchange 管理センター&セキュリティ センターのポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="5bfb9-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="5bfb9-124">ポリシー ヒントは、Exchange 管理センターで作成された DLP ポリシーとメール フロー ルール、またはセキュリティ & コンプライアンス センターで作成された DLP ポリシーで動作できますが、両方は使用できません。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="5bfb9-125">これは、これらのポリシーは異なる場所に保存されますが、ポリシー ヒントは 1 つの場所からのみ描画できるためです。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="5bfb9-126">Exchange 管理センターでポリシー ヒントを構成した場合、Exchange 管理センターでヒントをオフにするまで、セキュリティ & コンプライアンス センターで構成したポリシー ヒントは、Outlook on the web および Outlook 2013 以降のユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="5bfb9-127">これにより、現在の Exchange メール フロー ルールが引き続き動作し、セキュリティ コンプライアンス センターに切り替&されます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="5bfb9-128">ポリシー ヒントは 1 つの場所からしか描画されませんが、セキュリティ & コンプライアンス センターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されます。</span><span class="sxs-lookup"><span data-stu-id="5bfb9-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
