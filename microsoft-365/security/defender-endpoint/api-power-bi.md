---
title: Microsoft Defender for Endpoint API 接続とエンドポイント API Power BI
ms.reviewer: ''
description: Microsoft Defender for Endpoint API の上に Power Business Intelligence (BI) レポートを作成します。
keywords: apis、サポートされている api、Power BI、レポート
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 5c76784d78837c324922ffc25539746a4921e426
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769715"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="e44b4-104">ユーザー設定を使用してカスタム レポートをPower BI</span><span class="sxs-lookup"><span data-stu-id="e44b4-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e44b4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e44b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="e44b4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e44b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e44b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e44b4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="e44b4-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="e44b4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e44b4-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e44b4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="e44b4-110">このセクションでは、Defender for Endpoint API の上にPower BIレポートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e44b4-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="e44b4-111">最初の例は、Power BI を Advanced Hunting API に接続する方法を示し、2 番目の例では、マシン アクションやアラートなどの OData API への接続を示しています。</span><span class="sxs-lookup"><span data-stu-id="e44b4-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="e44b4-112">Connect Power BI高度なハンティング API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="e44b4-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="e44b4-113">Microsoft ファイルを開Power BI</span><span class="sxs-lookup"><span data-stu-id="e44b4-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="e44b4-114">[データ **の空のクエリ**  >  **の取得] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="e44b4-114">Click **Get Data** > **Blank Query**</span></span>

    ![空のクエリを作成するイメージ](images/power-bi-create-blank-query.png)

- <span data-ttu-id="e44b4-116">[高度 **なエディター] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="e44b4-116">Click **Advanced Editor**</span></span>

    ![開いている高度なエディターのイメージ](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="e44b4-118">以下をコピーし、エディターに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e44b4-118">Copy the below and paste it in the editor:</span></span>

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

- <span data-ttu-id="e44b4-119">[完了] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="e44b4-119">Click **Done**</span></span>

- <span data-ttu-id="e44b4-120">[資格情報 **の編集] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="e44b4-120">Click **Edit Credentials**</span></span>

    ![編集資格情報のイメージ0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="e44b4-122">[**組織アカウント]**  >  **[サインイン] の選択**</span><span class="sxs-lookup"><span data-stu-id="e44b4-122">Select **Organizational account** > **Sign in**</span></span>

    ![set credentials1 のイメージ](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="e44b4-124">資格情報を入力し、サインインを待つ</span><span class="sxs-lookup"><span data-stu-id="e44b4-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="e44b4-125">[次 **Connect**</span><span class="sxs-lookup"><span data-stu-id="e44b4-125">Click **Connect**</span></span>

    ![set credentials2 のイメージ](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="e44b4-127">これでクエリの結果がテーブルとして表示され、その上にビジュアライゼーションのビルドを開始できます。</span><span class="sxs-lookup"><span data-stu-id="e44b4-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="e44b4-128">このテーブルを複製し、名前を変更し、高度な検索クエリを内部で編集して、必要なデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="e44b4-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="e44b4-129">Connect Power BI OData API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="e44b4-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="e44b4-130">上記の例との唯一の違いは、エディター内のクエリです。</span><span class="sxs-lookup"><span data-stu-id="e44b4-130">The only difference from the above example is the query inside the editor.</span></span> 

- <span data-ttu-id="e44b4-131">以下をコピーしてエディターに貼り付け、組織から **すべての Machine Actions** をプルします。</span><span class="sxs-lookup"><span data-stu-id="e44b4-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- <span data-ttu-id="e44b4-132">アラートとコンピューターでも同 **じ操作** を **実行できます**。</span><span class="sxs-lookup"><span data-stu-id="e44b4-132">You can do the same for **Alerts** and **Machines**.</span></span>

- <span data-ttu-id="e44b4-133">クエリ フィルターに OData クエリを使用することもできます [。「Using OData Queries」を参照してください。](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="e44b4-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>


## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="e44b4-134">Power BIダッシュボードのサンプルをGitHub</span><span class="sxs-lookup"><span data-stu-id="e44b4-134">Power BI dashboard samples in GitHub</span></span>
<span data-ttu-id="e44b4-135">詳細については、「レポート テンプレートのPower BI[を参照してください](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)。</span><span class="sxs-lookup"><span data-stu-id="e44b4-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="e44b4-136">サンプル レポート</span><span class="sxs-lookup"><span data-stu-id="e44b4-136">Sample reports</span></span>
<span data-ttu-id="e44b4-137">レポート サンプルの Microsoft Defender for Endpoint Power BI表示します。</span><span class="sxs-lookup"><span data-stu-id="e44b4-137">View the Microsoft Defender for Endpoint Power BI report samples.</span></span> <span data-ttu-id="e44b4-138">詳細については、「Browse [code samples 」を参照してください](https://docs.microsoft.com/samples/browse/?products=mdatp)。</span><span class="sxs-lookup"><span data-stu-id="e44b4-138">For more information, see [Browse code samples](https://docs.microsoft.com/samples/browse/?products=mdatp).</span></span>


## <a name="related-topic"></a><span data-ttu-id="e44b4-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e44b4-139">Related topic</span></span>
- [<span data-ttu-id="e44b4-140">エンドポイント API の Defender</span><span class="sxs-lookup"><span data-stu-id="e44b4-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="e44b4-141">高度な追及 API</span><span class="sxs-lookup"><span data-stu-id="e44b4-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="e44b4-142">OData クエリの使用</span><span class="sxs-lookup"><span data-stu-id="e44b4-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)
