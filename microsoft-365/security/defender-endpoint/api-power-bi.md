---
title: Power BI への Microsoft Defender ATP API 接続
ms.reviewer: ''
description: Microsoft Defender for Endpoint API の上に Power Business Intelligence (BI) レポートを作成します。
keywords: apis、サポートされている API、Power BI、レポート
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 696782ca03e5494c3fc5ca08943d1079c5d78f8a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167032"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="6d325-104">Power BI を使用してカスタム レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="6d325-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6d325-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6d325-105">**Applies to:**</span></span>
- [<span data-ttu-id="6d325-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6d325-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6d325-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d325-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="6d325-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6d325-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6d325-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6d325-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="6d325-110">このセクションでは、Defender for Endpoint API の上に Power BI レポートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d325-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="6d325-111">最初の例は、Power BI を Advanced Hunting API に接続する方法を示し、2 番目の例では、マシン アクションやアラートなどの OData API への接続を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d325-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="6d325-112">Power BI を高度なハンティング API に接続する</span><span class="sxs-lookup"><span data-stu-id="6d325-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="6d325-113">Microsoft Power BI を開く</span><span class="sxs-lookup"><span data-stu-id="6d325-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="6d325-114">[データ **の空のクエリ**  >  **の取得] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="6d325-114">Click **Get Data** > **Blank Query**</span></span>

    ![空のクエリを作成するイメージ](images/power-bi-create-blank-query.png)

- <span data-ttu-id="6d325-116">[高度 **なエディター] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="6d325-116">Click **Advanced Editor**</span></span>

    ![開いている高度なエディターのイメージ](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="6d325-118">以下をコピーし、エディターに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6d325-118">Copy the below and paste it in the editor:</span></span>

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- <span data-ttu-id="6d325-119">[完了] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="6d325-119">Click **Done**</span></span>

- <span data-ttu-id="6d325-120">[資格情報 **の編集] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="6d325-120">Click **Edit Credentials**</span></span>

    ![編集資格情報のイメージ0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="6d325-122">[**組織アカウント]**  >  **[サインイン] の選択**</span><span class="sxs-lookup"><span data-stu-id="6d325-122">Select **Organizational account** > **Sign in**</span></span>

    ![set credentials1 のイメージ](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="6d325-124">資格情報を入力し、サインインを待つ</span><span class="sxs-lookup"><span data-stu-id="6d325-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="6d325-125">[接続 **] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="6d325-125">Click **Connect**</span></span>

    ![set credentials2 のイメージ](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="6d325-127">これでクエリの結果がテーブルとして表示され、その上にビジュアライゼーションのビルドを開始できます。</span><span class="sxs-lookup"><span data-stu-id="6d325-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="6d325-128">このテーブルを複製し、名前を変更し、高度な検索クエリを内部で編集して、必要なデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6d325-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="6d325-129">Power BI を OData API に接続する</span><span class="sxs-lookup"><span data-stu-id="6d325-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="6d325-130">上記の例との唯一の違いは、エディター内のクエリです。</span><span class="sxs-lookup"><span data-stu-id="6d325-130">The only difference from the above example is the query inside the editor.</span></span> 

- <span data-ttu-id="6d325-131">以下をコピーしてエディターに貼り付け、組織から **すべての Machine Actions** をプルします。</span><span class="sxs-lookup"><span data-stu-id="6d325-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- <span data-ttu-id="6d325-132">アラートとコンピューターでも同 **じ操作** を **実行できます**。</span><span class="sxs-lookup"><span data-stu-id="6d325-132">You can do the same for **Alerts** and **Machines**.</span></span>

- <span data-ttu-id="6d325-133">クエリ フィルターに OData クエリを使用することもできます [。「Using OData Queries」を参照してください。](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="6d325-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>


## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="6d325-134">GitHub の Power BI ダッシュボードのサンプル</span><span class="sxs-lookup"><span data-stu-id="6d325-134">Power BI dashboard samples in GitHub</span></span>
<span data-ttu-id="6d325-135">詳細については、「Power BI レポート テンプレート [」を参照してください](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)。</span><span class="sxs-lookup"><span data-stu-id="6d325-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="6d325-136">サンプル レポート</span><span class="sxs-lookup"><span data-stu-id="6d325-136">Sample reports</span></span>
<span data-ttu-id="6d325-137">Microsoft Defender ATP Power BI レポートサンプルを表示します。</span><span class="sxs-lookup"><span data-stu-id="6d325-137">View the Microsoft Defender ATP Power BI report samples.</span></span> <span data-ttu-id="6d325-138">詳細については、「Browse [code samples 」を参照してください](https://docs.microsoft.com/samples/browse/?products=mdatp)。</span><span class="sxs-lookup"><span data-stu-id="6d325-138">For more information, see [Browse code samples](https://docs.microsoft.com/samples/browse/?products=mdatp).</span></span>


## <a name="related-topic"></a><span data-ttu-id="6d325-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6d325-139">Related topic</span></span>
- [<span data-ttu-id="6d325-140">エンドポイント API の Defender</span><span class="sxs-lookup"><span data-stu-id="6d325-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="6d325-141">高度な追及 API</span><span class="sxs-lookup"><span data-stu-id="6d325-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="6d325-142">OData クエリの使用</span><span class="sxs-lookup"><span data-stu-id="6d325-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)
