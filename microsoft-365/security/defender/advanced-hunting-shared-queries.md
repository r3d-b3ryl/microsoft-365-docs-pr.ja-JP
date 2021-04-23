---
title: Microsoft 365 Defender Advanced Hunting で共有クエリを使用する
description: 定義済みおよび共有クエリを使用して、脅威の捜索をすぐに開始します。 クエリを公開または組織に共有します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、github リポジトリ、自分のクエリ、共有クエリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952586"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="f3ce9-105">高度な捜索で共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="f3ce9-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f3ce9-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f3ce9-106">**Applies to:**</span></span>
- <span data-ttu-id="f3ce9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3ce9-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="f3ce9-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f3ce9-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="f3ce9-109">[高度な捜索](advanced-hunting-overview.md)クエリは、同じ組織内のユーザー間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-109">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="f3ce9-110">また、GitHub で公開されているクエリも検索できます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-110">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="f3ce9-111">これらのクエリを使用すると、クエリを最初から作成することなく、特定の脅威の捜索シナリオを迅速に実行できます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-111">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![共有クエリの画像](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="f3ce9-113">クエリを保存、変更、共有する</span><span class="sxs-lookup"><span data-stu-id="f3ce9-113">Save, modify, and share a query</span></span>
<span data-ttu-id="f3ce9-114">新規または既存のクエリを保存して、自分のみアクセスできるようにしたり、組織内の他のユーザーと共有したりできます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-114">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="f3ce9-115">クエリを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-115">Create or modify a query.</span></span> 

2. <span data-ttu-id="f3ce9-116">[**クエリの保存**] ドロップダウン ボタンをクリックし、[**名前を付けて保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-116">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="f3ce9-117">クエリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-117">Enter a name for the query.</span></span> 

   ![クエリの保存の画像](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="f3ce9-119">クエリを保存するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-119">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="f3ce9-120">[**共有クエリ**] — 組織のすべてのユーザーに共有する</span><span class="sxs-lookup"><span data-stu-id="f3ce9-120">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="f3ce9-121">[**マイ クエリ**] — 自分のみアクセス可能</span><span class="sxs-lookup"><span data-stu-id="f3ce9-121">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="f3ce9-122">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-122">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="f3ce9-123">クエリを削除または名前を変更する</span><span class="sxs-lookup"><span data-stu-id="f3ce9-123">Delete or rename a query</span></span>
1. <span data-ttu-id="f3ce9-124">名前を変更または削除するクエリを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-124">Right-click on a query you want to rename or delete.</span></span>

    ![削除するクエリの画像](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="f3ce9-126">[**削除**] を選択して、削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-126">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="f3ce9-127">または、[**名前の変更**] を選択して、クエリに新しい名前を入力ます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-127">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="f3ce9-128">クエリへの直接リンクを作成する</span><span class="sxs-lookup"><span data-stu-id="f3ce9-128">Create a direct link to a query</span></span>
<span data-ttu-id="f3ce9-129">高度な検索クエリ エディターでクエリを直接開くリンクを生成するには、クエリを最終処理し、[リンクの共有] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-129">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="f3ce9-130">GitHub リポジトリ内のクエリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f3ce9-130">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="f3ce9-131">Microsoft のセキュリティ調査員は、[GitHub の指定された公開リポジトリ](https://aka.ms/hunting-queries)で高度な捜索クエリを定期的に共有しています。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-131">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="f3ce9-132">このリポジトリは投稿できます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-132">This repository is open to contributions.</span></span> <span data-ttu-id="f3ce9-133">投稿するには、[GitHub に無料で参加](https://github.com/)してください。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-133">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="f3ce9-134">また、Microsoft のセキュリティ調査員は高度な捜索クエリも提供しています。これを使用して、新たな脅威に関連するアクティビティやインジケータを特定できます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-134">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="f3ce9-135">これらのクエリは、Microsoft Defender セキュリティ センターの[脅威の分析](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)レポートの一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-135">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

>[!NOTE]
><span data-ttu-id="f3ce9-136">この記事の一部のテーブルは、Microsoft Defender for Endpoint では使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-136">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f3ce9-137">[Microsoft 365 Defender をオンに](m365d-enable.md) し、より多くのデータ ソースを使用して脅威を検出します。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-137">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="f3ce9-138">「Advanced [Hunting queries](advanced-hunting-migrate-from-mde.md)from Microsoft Defender for Endpoint 」 の手順に従って、高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defender に移動できます。</span><span class="sxs-lookup"><span data-stu-id="f3ce9-138">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3ce9-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3ce9-139">Related topics</span></span>
- [<span data-ttu-id="f3ce9-140">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="f3ce9-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f3ce9-141">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="f3ce9-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f3ce9-142">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="f3ce9-142">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="f3ce9-143">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="f3ce9-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f3ce9-144">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="f3ce9-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f3ce9-145">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="f3ce9-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)