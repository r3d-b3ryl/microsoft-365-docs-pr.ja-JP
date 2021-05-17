---
title: テーマ - 電子情報開示
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 各ドキュメントで主なAdvanced eDiscoveryを見つけることで、レビュー セットを整理するには、ページの [テーマ] を使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285533"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="a32d8-103">[テーマ] Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a32d8-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="a32d8-104">ユーザーがドキュメントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="a32d8-104">How does a person write a document?</span></span> <span data-ttu-id="a32d8-105">通常、ドキュメントで伝えたい 1 つ以上のアイデアから始め、アイデアに合った単語を使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="a32d8-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="a32d8-106">一般的なアイデアは、そのアイデアに関連する単語の頻度が高くなる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="a32d8-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="a32d8-107">これにより、ユーザーがドキュメントを使用する方法も通知されます。</span><span class="sxs-lookup"><span data-stu-id="a32d8-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="a32d8-108">ドキュメントを読んで理解する重要な点は、ドキュメントが伝えようとしているアイデア、どこに表示されるアイデア、アイデア間の関係を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a32d8-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="a32d8-109">これは、ユーザーが一連のドキュメントを使用する方法まで拡張できます。</span><span class="sxs-lookup"><span data-stu-id="a32d8-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="a32d8-110">セットにどのアイデアが存在し、どのドキュメントがそれらのアイデアについて話しているのか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a32d8-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="a32d8-111">また、関心のある特定のドキュメントを見つけた場合は、同様のアイデアを議論するドキュメントを見る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a32d8-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="a32d8-112">Advanced eDiscovery のテーマ機能は、レビュー セットで説明されているテーマを分析し、レビュー セット内のドキュメントにテーマを割り当て、ドキュメントに関する人間の理由を模倣します。</span><span class="sxs-lookup"><span data-stu-id="a32d8-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="a32d8-113">このAdvanced eDiscoveryテーマはさらに一歩進み、各ドキュメントの主要 *なテーマ* を識別します。</span><span class="sxs-lookup"><span data-stu-id="a32d8-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="a32d8-114">主なテーマは、ドキュメント内で最も頻繁に表示されるテーマです。</span><span class="sxs-lookup"><span data-stu-id="a32d8-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="a32d8-115">テーマの動作</span><span class="sxs-lookup"><span data-stu-id="a32d8-115">How does Themes work?</span></span>

<span data-ttu-id="a32d8-116">テーマ機能は、レビューセット内のテキストを含むドキュメントを分析して、レビューセット内のすべてのドキュメントにわたって表示される共通のテーマを解析します。</span><span class="sxs-lookup"><span data-stu-id="a32d8-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="a32d8-117">Advanced eDiscovery は、テーマを、それらが表示されるドキュメントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a32d8-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="a32d8-118">また、テーマには、テーマを表すドキュメントで使用されている単語を各テーマにラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="a32d8-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="a32d8-119">ドキュメントにはさまざまな種類の主題が含まれる可能性があるため、Advanced eDiscovery は複数のテーマをドキュメントに割り当てることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="a32d8-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="a32d8-120">ドキュメントで最も目立つテーマは、その主要なテーマとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="a32d8-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
