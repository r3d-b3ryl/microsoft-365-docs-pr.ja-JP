---
title: アナリティクスを使用して、より速い調査を実行する
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
description: ほぼ重複検出、電子メールスレッド、テーマなどの分析ツールを使用して、調査を高速化する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e7c5103adabadf88028351f0314bcdfaa2cd4d0f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035849"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="a8917-103">アナリティクスを使用して、より速い調査を実行する</span><span class="sxs-lookup"><span data-stu-id="a8917-103">Run analytics to investigate faster</span></span>

<span data-ttu-id="a8917-104">証拠のコレクションが大きい場合、それらをすべて確認するのは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8917-104">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="a8917-105">多くの場合、証拠のセットには、同じまたは類似の電子メールメッセージまたはドキュメントの複数のコピーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8917-105">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="a8917-106">データ調査 (プレビュー) には、情報が失われないように、確認が必要なドキュメントのボリュームを減らすために役立つ分析ツールが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="a8917-106">Data Investigations (Preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="a8917-107">これらの機能の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8917-107">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="a8917-108">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="a8917-108">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="a8917-109">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="a8917-109">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="a8917-110">テーマ</span><span class="sxs-lookup"><span data-stu-id="a8917-110">Themes</span></span>](themes.md)

<span data-ttu-id="a8917-111">証拠セット内のデータを分析するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a8917-111">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="a8917-112">調査のための分析設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a8917-112">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="a8917-113">詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8917-113">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="a8917-114">証拠セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="a8917-114">Open the evidence set.</span></span>

3. <span data-ttu-id="a8917-115">[**証明の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8917-115">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="a8917-116">[**分析**] の [**分析**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8917-116">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="a8917-117">調査中に [**ジョブ**] タブで分析の進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a8917-117">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="a8917-118">トリガーされるジョブの種類は、 **analytics の実行**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a8917-118">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="a8917-119">分析が完了すると、右側のパネルに表示されている、確認しているドキュメントの完全に重複またはほぼ重複したリストが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a8917-119">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="a8917-120">表示しているドキュメントのすべての複製を選択するには、このパネルを使用して簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="a8917-120">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="a8917-121">このパネルの他の機能の詳細については、「[証拠データのレビュー](review-data-in-evidence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8917-121">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="a8917-122">また、テーマなどの分析の出力を使用して、証拠内で追加のクエリを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a8917-122">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="a8917-123">詳細については、「[証拠でデータを照会する](evidence-query.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8917-123">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="a8917-124">分析レポート</span><span class="sxs-lookup"><span data-stu-id="a8917-124">Analytics report</span></span>

<span data-ttu-id="a8917-125">証拠の分析レポートを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a8917-125">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="a8917-126">証拠セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="a8917-126">Open the evidence set.</span></span>

2. <span data-ttu-id="a8917-127">[**証明の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8917-127">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="a8917-128">[**分析**] の [**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8917-128">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="a8917-129">レポートには、分析の4つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="a8917-129">The report has four components from analysis:</span></span>

- <span data-ttu-id="a8917-130">[**内訳**]-証拠セットに含まれる生の電子メール、添付ファイル、およびドキュメントの数。</span><span class="sxs-lookup"><span data-stu-id="a8917-130">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="a8917-131">**電子メール**-inclusives で使用される eamil メッセージの数、包括的なコピー、または上記に該当しないものがあります。</span><span class="sxs-lookup"><span data-stu-id="a8917-131">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="a8917-132">Inclusives: 以前のすべての履歴を含む電子メールスレッドの最後のメッセージ。レビューが必要です。</span><span class="sxs-lookup"><span data-stu-id="a8917-132">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="a8917-133">包括的な使用法: 確認が必要な1つ以上の異なる添付ファイルが含まれているスレッド内のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="a8917-133">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="a8917-134">包括的コピー: 別の包括的または包括的なマイナスメッセージのコピーであるメッセージ (件名と本文)。</span><span class="sxs-lookup"><span data-stu-id="a8917-134">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="a8917-135">**添付ファイル**-同じ証拠に含まれる異なる電子メール添付ファイルの一意の数または重複した電子メール添付ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="a8917-135">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="a8917-136">**ドキュメント (電子メール添付ファイルを除く)** : 校閲を必要とする一意のドキュメントの数。たとえば、ほぼ重複したセットの代表的なドキュメント、または別のドキュメントの完全な重複があります。</span><span class="sxs-lookup"><span data-stu-id="a8917-136">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>
