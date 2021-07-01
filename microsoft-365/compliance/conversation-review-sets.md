---
title: '[チャット] で会話をAdvanced eDiscovery'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery グループでのチャット会話の再構築、レビュー、エクスポートを行う Advanced eDiscovery での会話の再構築機能についてMicrosoft TeamsおよびYammerします。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9848280a7d6dbcbd6128fff06f150c8458f09701
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227189"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="f3eca-103">スレッド内のスレッドAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f3eca-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="f3eca-104">インスタント メッセージングは、質問をしたり、アイデアを共有したり、大規模なユーザー間ですばやくコミュニケーションを取る便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="f3eca-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="f3eca-105">Microsoft Teams グループや Yammer グループなどのインスタント メッセージング プラットフォームがエンタープライズ コラボレーションの中核となる中、組織は電子情報開示ワークフローがこれらの新しい形式のコミュニケーションとコラボレーションにどう対応するのか評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3eca-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="f3eca-106">コンテキスト コンテンツを特定し、Advanced eDiscoveryの会話ビューを作成するのに役立つ、会話の再構成機能です。</span><span class="sxs-lookup"><span data-stu-id="f3eca-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="f3eca-107">この機能により、Microsoft Teams のようなプラットフォームで生成される完全なインスタント メッセージ会話 (スレッド *会話とも呼* ばれる) を効率的かつ迅速に確認Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="f3eca-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="f3eca-108">Conversation Reconstruction を使用すると、組み込みの機能を使用してスレッド会話を再構築、レビュー、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="f3eca-109">スレッドのAdvanced eDiscoveryを使用して、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="f3eca-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="f3eca-110">会話内のすべてのメッセージに対して一意のメッセージ レベルのメタデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="f3eca-111">検索結果に関するコンテキスト メッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="f3eca-112">スレッドスレッドの会話の確認、注釈付け、やり直しを行います。</span><span class="sxs-lookup"><span data-stu-id="f3eca-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="f3eca-113">個々のメッセージまたはスレッドスレッドの会話をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f3eca-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="f3eca-114">用語</span><span class="sxs-lookup"><span data-stu-id="f3eca-114">Terminology</span></span>

<span data-ttu-id="f3eca-115">会話の再構築の使用を始めるのに役立ついくつかの定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="f3eca-116">**メッセージ:** 会話の最小単位を表します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="f3eca-117">メッセージのサイズ、構造、およびメタデータは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3eca-117">Messages may vary in size, structure, and metadata.</span></span>

- <span data-ttu-id="f3eca-118">**会話:** 1 つ以上のメッセージのグループ化を表します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="f3eca-119">異なるアプリケーション間で、会話はさまざまな方法で表される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3eca-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="f3eca-120">一部のアプリケーションでは、既存のメッセージに返信する明示的なアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="f3eca-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="f3eca-121">会話は、このユーザー操作の結果として明示的に形成されます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="f3eca-122">たとえば、次に、チャネル会話のスクリーンショットを示Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="f3eca-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teamsチャネルの会話](../media/threadedchat.png)

   <span data-ttu-id="f3eca-124">他のアプリ (Teams の 1xN チャット メッセージなど) では、正式な返信チェーンが用意されていないので、メッセージは単一スレッド内の "平らなメッセージの川" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="f3eca-125">これらの種類のアプリでは、会話は、特定の時間内に発生するメッセージのグループから推測されます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="f3eca-126">このメッセージの "ソフト グループ化" は、(返信チェーンではなく) 特定のトピックに関する "前後" の会話を表します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="f3eca-127">手順 1: 下書きコレクションを作成する</span><span class="sxs-lookup"><span data-stu-id="f3eca-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="f3eca-128">関連する保管担当者とコンテンツの場所を特定した後、検索を作成して関連性の高いコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="f3eca-129">このケース **の [** コレクション] タブAdvanced eDiscovery、[新しいコレクション] をクリックしてウィザードに従ってコレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="f3eca-130">コレクションを作成し、検索クエリを作成し、検索結果をプレビューする方法については、「下書きコレクションを作成 [する」を参照してください](create-draft-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="f3eca-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="f3eca-131">手順 2: 下書きコレクションをレビュー セットにコミットする</span><span class="sxs-lookup"><span data-stu-id="f3eca-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="f3eca-132">コレクション内の検索クエリを確認して終了したら、検索結果をレビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="f3eca-133">検索結果をレビュー セットに追加すると、元のデータは、レビューおよび分析プロセスを容易にするために、Azure Storage領域にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="f3eca-134">レビュー セットに検索結果を追加する方法の詳細については、「レビュー セットに下書きコレクションをコミット [する」を参照してください](commit-draft-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="f3eca-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="f3eca-135">会話からレビュー セットにアイテムを追加する場合は、スレッド会話オプションを使用して、コレクションの検索条件に一致するアイテムを含む会話からコンテキスト メッセージを収集できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="f3eca-136">スレッドの会話オプションを選択すると、次のことが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3eca-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![会話の取得](../media/messagesandconversations.png)

1. <span data-ttu-id="f3eca-138">キーワードと日付範囲のクエリを使用して、検索でメッセージ 3 のヒット *が返されました*。</span><span class="sxs-lookup"><span data-stu-id="f3eca-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="f3eca-139">このメッセージは *、CRC1* によって示される、より大きな会話の一部でした。</span><span class="sxs-lookup"><span data-stu-id="f3eca-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>

2. <span data-ttu-id="f3eca-140">レビュー セットにデータを追加し、会話の取得オプションを有効にした場合、Advanced eDiscovery *CRC1* の他のアイテムを収集します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>

3. <span data-ttu-id="f3eca-141">アイテムがレビュー セットに追加された後 *、CRC1* からのすべての個々のメッセージを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="f3eca-142">スレッド会話オプションを有効にするには、「下書きコレクションをレビュー セットにコミット [する」を参照してください](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)。</span><span class="sxs-lookup"><span data-stu-id="f3eca-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>

## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="f3eca-143">手順 3: スレッド会話の確認とエクスポート</span><span class="sxs-lookup"><span data-stu-id="f3eca-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="f3eca-144">コンテンツが処理され、レビュー セットに追加された後、レビュー セットのデータの確認を開始できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="f3eca-145">レビュー機能は、コンテンツが標準のレビュー セットまたは会話レビュー セットに追加されたかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f3eca-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="f3eca-146">標準レビュー セットでの会話の確認</span><span class="sxs-lookup"><span data-stu-id="f3eca-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="f3eca-147">標準のレビュー セットでは、メッセージはメールボックス フォルダーに格納される方法と同様に、個々のアイテムとして処理および表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="f3eca-148">このワークフローでは、各メッセージは個別のアイテムとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="f3eca-149">そのため、スレッド化された概要とエクスポートのオプションは、標準のレビュー セットでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f3eca-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![標準レビュー セット](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="f3eca-151">会話レビュー セットでの会話の確認</span><span class="sxs-lookup"><span data-stu-id="f3eca-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="f3eca-152">会話レビュー セットでは、個々のメッセージがスレッド化され、会話として表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="f3eca-153">これにより、コンテキスト会話を確認およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-153">This lets you review and export contextual conversations.</span></span>

  ![会話レビュー セット](../media/ConversationRSOptions.PNG)

<span data-ttu-id="f3eca-155">次のセクションでは、会話レビュー セット内の会話の確認とエクスポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="f3eca-156">会話の確認</span><span class="sxs-lookup"><span data-stu-id="f3eca-156">Reviewing conversations</span></span>

<span data-ttu-id="f3eca-157">会話レビュー セットでは、次のオプションを使用してレビュー プロセスを容易にできます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="f3eca-158">**会話によるグループ化:** 同じ会話内のメッセージをグループ化して、ユーザーがレビュー プロセスを簡素化し、迅速に行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="f3eca-159">**概要ビュー:** スレッドスレッドの会話を表示します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="f3eca-160">このビューでは、会話全体を確認し、個々のメッセージのメタデータにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>

   - <span data-ttu-id="f3eca-161">個々のメッセージのメタデータを表示する</span><span class="sxs-lookup"><span data-stu-id="f3eca-161">View metadata for individual messages</span></span>

   - <span data-ttu-id="f3eca-162">個々のメッセージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f3eca-162">Download individual messages</span></span>

- <span data-ttu-id="f3eca-163">**テキスト ビュー:** 会話全体の抽出されたテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="f3eca-164">**注釈ビュー:** スレッドビューをマークアップできます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="f3eca-165">会話内のすべてのメッセージは、同じ注釈付きドキュメントを共有します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="f3eca-166">**タグ付け:** レビュー セットで会話を表示する場合は、[コーディング] パネルの[タグ付け] パネルをクリックしてタグを表示および適用できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="f3eca-167">**会話の変換を再実行する:** メッセージを会話レビュー セットに追加すると、変換ジョブが自動的に実行され、スレッド化された概要が作成され、ビューに注釈が付きます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="f3eca-168">会話の再構築ジョブが失敗した場合は、[アクション] をクリックしてこのジョブを再実行し>で会話 **PDF を** 作成します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="f3eca-169">会話のエクスポート</span><span class="sxs-lookup"><span data-stu-id="f3eca-169">Exporting conversations</span></span>

<span data-ttu-id="f3eca-170">会話レビュー セットでは、次のオプションを設定して会話をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![会話のエクスポート オプション](../media/export.png)

1. <span data-ttu-id="f3eca-172">メタデータ オプション:</span><span class="sxs-lookup"><span data-stu-id="f3eca-172">Metadata options:</span></span>
   - <span data-ttu-id="f3eca-173">**ファイルの読み込み:** メタデータは、個々のメッセージ、電子メール、およびドキュメントごとに含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-173">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="f3eca-174">会話内のメッセージごとに 1 行があります。</span><span class="sxs-lookup"><span data-stu-id="f3eca-174">There is one row for each message in a conversation.</span></span>
   - <span data-ttu-id="f3eca-175">**タグ:** レビュー プロセスのタグがメタデータ ファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-175">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="f3eca-176">会話内のメッセージは同じタグを共有します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-176">Messages in a conversation share the same tags.</span></span>

2. <span data-ttu-id="f3eca-177">会話のオプション:</span><span class="sxs-lookup"><span data-stu-id="f3eca-177">Conversation options:</span></span>
   - <span data-ttu-id="f3eca-178">**会話ファイル:** 会話ファイルをエクスポートすると、注釈付きビューが PDF ファイルに変換され、エクスポート フォルダーにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-178">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="f3eca-179">1 つの会話ファイル内のメッセージは、同じ会話ファイルの PDF バージョンを指します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-179">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>
   - <span data-ttu-id="f3eca-180">**個々のチャット メッセージ:** 個々のメッセージをエクスポートすると、会話内の各一意のメッセージがスタンドアロン アイテムとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-180">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="f3eca-181">ファイルは、メールボックスと同じ形式でエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-181">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="f3eca-182">特定の会話では、複数の .msg ファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-182">For a specific conversation, you receive multiple .msg files.</span></span>

     > [!NOTE]
     > <span data-ttu-id="f3eca-183">会話ファイルに注釈を適用した場合、これらの注釈は個々のメッセージに転送されません。</span><span class="sxs-lookup"><span data-stu-id="f3eca-183">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

3. <span data-ttu-id="f3eca-184">その他のオプション:</span><span class="sxs-lookup"><span data-stu-id="f3eca-184">Other options:</span></span>
   - <span data-ttu-id="f3eca-185">**エクスポートされたコンテンツのテキスト ファイルを生成します。** レビュー セットからエクスポートされた会話ごとにテキスト ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="f3eca-185">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>
   - <span data-ttu-id="f3eca-186">**エクスポートされたコンテンツを、変更された PDF に置き換える:** 編集された会話ファイルがレビュー プロセス中に生成された場合、エクスポート時にこれらのファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-186">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="f3eca-187">(このオプションを選択しない) ネイティブ ファイルのみをエクスポートするか、ネイティブ ファイルを PDF ファイルとしてエクスポートする (このオプションを選択して) 元のバージョンのネイティブ ファイルに置き換えるかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="f3eca-187">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="f3eca-188">詳細</span><span class="sxs-lookup"><span data-stu-id="f3eca-188">More information</span></span>

<span data-ttu-id="f3eca-189">ケース データを確認する方法の詳細については、Advanced eDiscovery記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3eca-189">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="f3eca-190">ケース データの表示</span><span class="sxs-lookup"><span data-stu-id="f3eca-190">View case data</span></span>](view-documents-in-review-set.md)
- [<span data-ttu-id="f3eca-191">ケース データを分析する</span><span class="sxs-lookup"><span data-stu-id="f3eca-191">Analyze case data</span></span>](analyzing-data-in-review-set.md)
- [<span data-ttu-id="f3eca-192">ケース データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f3eca-192">Export case data</span></span>](exporting-data-ediscover20.md)
