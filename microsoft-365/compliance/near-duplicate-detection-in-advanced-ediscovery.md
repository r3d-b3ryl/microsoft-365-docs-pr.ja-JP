---
title: 重複検出に近い - 電子情報開示
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: データのケース データを分析する場合は、ほぼ重複した検出を使用して、テキスト的に類似したドキュメントをグループ化Advanced eDiscovery。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286023"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="1c39d-103">データの重複検出に近いAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1c39d-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="1c39d-104">サブセットが同じテンプレートに基づいており、ほとんど同じ定型言語を持つ一連のドキュメントを検討します。ここではいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="1c39d-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="1c39d-105">レビュー者がこのサブセットを特定し、そのうちの 1 つを徹底的に確認し、残りの部分の違いを確認できる場合、一意の情報を見逃す必要はありません。一方で、すべてのドキュメントを読み取る時間はほんの一部です。</span><span class="sxs-lookup"><span data-stu-id="1c39d-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="1c39d-106">準重複の検出グループは、テキスト的に類似したドキュメントをまとめてグループ化し、レビュープロセスをより効率的にします。</span><span class="sxs-lookup"><span data-stu-id="1c39d-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="1c39d-107">どのような仕組みなのか。</span><span class="sxs-lookup"><span data-stu-id="1c39d-107">How does it work?</span></span>

<span data-ttu-id="1c39d-108">準重複の検出が実行されると、システムはテキストを含むすべてのドキュメントを解析します。</span><span class="sxs-lookup"><span data-stu-id="1c39d-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="1c39d-109">次に、すべてのドキュメントを互いに比較して、それらの類似度を設定したしきい値よりも大きいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1c39d-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="1c39d-110">大きい場合は、ドキュメントはグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="1c39d-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="1c39d-111">すべてのドキュメントが比較およびグループ化されると、各グループのドキュメントが「ピボット」としてマークされます。ドキュメントのレビューでは、最初にピボットをレビューし、同じ準重複セット内の他のドキュメントをレビューして、ピボットとレビュー中のドキュメントの違いに焦点を合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="1c39d-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
