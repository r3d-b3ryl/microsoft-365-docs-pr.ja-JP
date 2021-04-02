---
title: 高度な捜索で共有クエリを使用する
description: 定義済みおよび共有クエリを使用して、脅威の捜索をすぐに開始します。 クエリを公開または組織に共有します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、github リポジトリ、自分のクエリ、共有クエリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 78a532167e4256e3453803f1a0b4a9e4875771cf
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499422"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="de03b-105">高度な捜索で共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="de03b-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="de03b-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="de03b-106">**Applies to:**</span></span>
- [<span data-ttu-id="de03b-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="de03b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="de03b-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="de03b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="de03b-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="de03b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="de03b-110">[高度な捜索](advanced-hunting-overview.md)クエリは、同じ組織内のユーザー間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="de03b-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="de03b-111">また、GitHub で公開されているクエリも検索できます。</span><span class="sxs-lookup"><span data-stu-id="de03b-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="de03b-112">これらのクエリを使用すると、クエリを最初から作成することなく、特定の脅威の捜索シナリオを迅速に実行できます。</span><span class="sxs-lookup"><span data-stu-id="de03b-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![共有クエリの画像](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="de03b-114">クエリを保存、変更、共有する</span><span class="sxs-lookup"><span data-stu-id="de03b-114">Save, modify, and share a query</span></span>
<span data-ttu-id="de03b-115">新規または既存のクエリを保存して、自分のみアクセスできるようにしたり、組織内の他のユーザーと共有したりできます。</span><span class="sxs-lookup"><span data-stu-id="de03b-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="de03b-116">[共有クエリ] または [マイ クエリ]の下から、新しいクエリを入力するか、既存のクエリ **を読み込む。**</span><span class="sxs-lookup"><span data-stu-id="de03b-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="de03b-117">保存 **オプションから [** 保存 **] または [** 名前を付けて保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de03b-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="de03b-118">既存のクエリを上書きしないようにするには、[名前を付けて保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="de03b-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="de03b-119">クエリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="de03b-119">Enter a name for the query.</span></span>

   ![クエリの保存の画像](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="de03b-121">クエリを保存するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="de03b-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="de03b-122">**共有クエリ** - 組織内のすべてのユーザーに共有される</span><span class="sxs-lookup"><span data-stu-id="de03b-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="de03b-123">[**マイ クエリ**] — 自分のみアクセス可能</span><span class="sxs-lookup"><span data-stu-id="de03b-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="de03b-124">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de03b-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="de03b-125">クエリを削除または名前を変更する</span><span class="sxs-lookup"><span data-stu-id="de03b-125">Delete or rename a query</span></span>
1. <span data-ttu-id="de03b-126">名前を変更または削除するクエリを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="de03b-126">Right-click on a query you want to rename or delete.</span></span>

    ![削除するクエリの画像](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="de03b-128">[**削除**] を選択して、削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="de03b-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="de03b-129">または、[**名前の変更**] を選択して、クエリに新しい名前を入力ます。</span><span class="sxs-lookup"><span data-stu-id="de03b-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="de03b-130">クエリへの直接リンクを作成する</span><span class="sxs-lookup"><span data-stu-id="de03b-130">Create a direct link to a query</span></span>
<span data-ttu-id="de03b-131">高度な検索クエリ エディターでクエリを直接開くリンクを生成するには、クエリを最終処理し、[リンクの共有] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="de03b-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="de03b-132">GitHub リポジトリ内のクエリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="de03b-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="de03b-133">Microsoft のセキュリティ調査員は、[GitHub の指定された公開リポジトリ](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)で高度な捜索クエリを定期的に共有しています。</span><span class="sxs-lookup"><span data-stu-id="de03b-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="de03b-134">このリポジトリは投稿できます。</span><span class="sxs-lookup"><span data-stu-id="de03b-134">This repository is open to contributions.</span></span> <span data-ttu-id="de03b-135">投稿するには、[GitHub に無料で参加](https://github.com/)してください。</span><span class="sxs-lookup"><span data-stu-id="de03b-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="de03b-136">また、Microsoft のセキュリティ調査員は高度な捜索クエリも提供しています。これを使用して、新たな脅威に関連するアクティビティやインジケータを特定できます。</span><span class="sxs-lookup"><span data-stu-id="de03b-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="de03b-137">これらのクエリは、Microsoft Defender セキュリティ センターの[脅威の分析](threat-analytics.md)レポートの一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="de03b-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="de03b-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="de03b-138">Related topics</span></span>
- [<span data-ttu-id="de03b-139">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="de03b-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="de03b-140">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="de03b-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="de03b-141">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="de03b-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="de03b-142">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="de03b-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="de03b-143">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="de03b-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="de03b-144">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="de03b-144">Custom detections overview</span></span>](overview-custom-detections.md)
