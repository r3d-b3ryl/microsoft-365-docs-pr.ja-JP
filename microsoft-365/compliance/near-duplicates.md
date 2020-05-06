---
title: ほぼ重複した検出-データの調査
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
description: データ調査を管理するときは、大文字と小文字を区別したドキュメントをグループ化するために近い重複検出を使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa451051c008f7a1614661d3bd66129cac6bb4ad
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036432"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="5714d-103">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="5714d-103">Near duplicate detection</span></span>

<span data-ttu-id="5714d-104">サブセットが同じテンプレートを基にしていて、ほとんど同じ定型表現を持っており、ここではいくつかの違いがある、ドキュメントのセットをレビューすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5714d-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="5714d-105">レビュー担当者がこのサブセットを特定し、そのうちの1つを徹底的に確認して、残りの相違点を確認した場合は、すべてのドキュメントカバーの読み取りにかかる時間が限られているため、固有の情報が失われることはありません。</span><span class="sxs-lookup"><span data-stu-id="5714d-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="5714d-106">ほぼ重複した検出グループでは、よく似たドキュメントが一緒に表示され、レビュープロセスの効率を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="5714d-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="5714d-107">どのような仕組みなのか。</span><span class="sxs-lookup"><span data-stu-id="5714d-107">How does it work?</span></span>

<span data-ttu-id="5714d-108">近い重複検出が実行されると、システムによってすべてのドキュメントがテキストで解析されます。</span><span class="sxs-lookup"><span data-stu-id="5714d-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="5714d-109">次に、すべてのドキュメントを比較して、類似性が設定されたしきい値より大きいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5714d-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="5714d-110">その場合、ドキュメントはグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="5714d-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="5714d-111">すべてのドキュメントを比較してグループ化すると、各グループのドキュメントが "pivot" としてマークされます。ドキュメントを確認するには、ピボットを最初に確認して、同じ付近にある重複セット内の他のドキュメントを確認して、ピボットとレビュー中のドキュメントの違いに焦点を合わせます。</span><span class="sxs-lookup"><span data-stu-id="5714d-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
