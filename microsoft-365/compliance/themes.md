---
title: テーマ-データ調査
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
description: データの調査時に、テーマを使用して、一般的なアイデアや概念を検索してドキュメントを整理します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 249d0739e7d83665f3d2a30d544886c43f89e07d
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285523"
---
# <a name="themes-in-data-investigations-preview"></a><span data-ttu-id="88da0-103">データ調査でのテーマ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="88da0-103">Themes in Data Investigations (preview)</span></span>

<span data-ttu-id="88da0-104">ユーザーがドキュメントを合成するときに、ランダムに単語を選択することはありません。これらのユーザーは、いくつかのアイデアや概念を伝えるようにしており、それに応じて単語が選択されます。</span><span class="sxs-lookup"><span data-stu-id="88da0-104">When someone composes a document, they do not choose words randomly; they are trying to convey some ideas or concepts, and the words are chosen accordingly.</span></span> <span data-ttu-id="88da0-105">Themes モジュールは、同じような主題について議論するドキュメントをクラスター化し、校閲者がドキュメントをより効率的に進めることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="88da0-105">Themes modules clusters documents that discuss similar subject matters so that reviewers can be more efficient in going through documents.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="88da0-106">テーマはどのように機能しますか?</span><span class="sxs-lookup"><span data-stu-id="88da0-106">How does Themes work?</span></span>

<span data-ttu-id="88da0-107">テーマは、ドキュメント全体にわたって表示される共通のテーマを解析するために、作業セット内のテキストが含まれるドキュメントを分析します。</span><span class="sxs-lookup"><span data-stu-id="88da0-107">Themes analyzes documents with text in a working set to parse out common themes that appear across the documents.</span></span> <span data-ttu-id="88da0-108">その後、それらのテーマが表示されるドキュメントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="88da0-108">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="88da0-109">また、それぞれのテーマの代表的なドキュメントで使用されている単語にラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="88da0-109">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="88da0-110">ドキュメントには複数の件名が含まれることがあるため、多くの場合、ドキュメントには複数のテーマが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="88da0-110">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="88da0-111">ドキュメントで最も目立つテーマは、その主要なテーマとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="88da0-111">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
