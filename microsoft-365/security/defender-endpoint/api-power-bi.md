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
ms.openlocfilehash: 0e64ccef09af6a8ab9ff3f798a0754a605a7f122
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58507748"
---
# <a name="create-custom-reports-using-power-bi"></a>ユーザー設定を使用してカスタム レポートをPower BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

このセクションでは、Defender for Endpoint API の上にPower BIレポートを作成する方法について説明します。

最初の例は、Power BI を Advanced Hunting API に接続する方法を示し、2 番目の例では、マシン アクションやアラートなどの OData API への接続を示しています。

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Connect Power BI高度なハンティング API へのアクセス

- Microsoft ファイルを開Power BI

- [データ **の空のクエリ** \> **の取得] をクリックします。**

  ![空のクエリを作成するイメージ](images/power-bi-create-blank-query.png)

- [高度 **なエディター] をクリックします。**

  ![開いている高度なエディターのイメージ](images/power-bi-open-advanced-editor.png)

- 以下をコピーし、エディターに貼り付けます。

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

- [完了] を **クリックします。**

- [資格情報 **の編集] をクリックします。**

    ![編集資格情報のイメージ0](images/power-bi-edit-credentials.png)

- [ **組織アカウント]** \> **[サインイン] の選択**

    ![set credentials1 のイメージ](images/power-bi-set-credentials-organizational.png)

- 資格情報を入力し、サインインを待つ

- [次 **Connect**

    ![set credentials2 のイメージ](images/power-bi-set-credentials-organizational-cont.png)

- これでクエリの結果がテーブルとして表示され、その上にビジュアライゼーションのビルドを開始できます。

- このテーブルを複製し、名前を変更し、高度な検索クエリを内部で編集して、必要なデータを取得できます。

## <a name="connect-power-bi-to-odata-apis"></a>Connect Power BI OData API へのアクセス

- 上記の例との唯一の違いは、エディター内のクエリです。

- 以下をコピーしてエディターに貼り付け、組織から **すべての Machine Actions** をプルします。

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source
```

- アラートとコンピューターでも同 **じ操作** を **実行できます**。
- クエリ フィルターに OData クエリを使用することもできます [。「Using OData Queries」を参照してください。](exposed-apis-odata-samples.md)

## <a name="power-bi-dashboard-samples-in-github"></a>Power BIダッシュボードのサンプルをGitHub

詳細については、「レポート テンプレートのPower BI[を参照してください](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)。

## <a name="sample-reports"></a>サンプル レポート

レポート サンプルの Microsoft Defender for Endpoint Power BI表示します。 詳細については、「Browse [code samples 」を参照してください](/samples/browse/?products=mdatp)。

## <a name="related-topics"></a>関連項目

- [エンドポイント API の Defender](apis-intro.md)
- [高度な追求 API](run-advanced-query-api.md)
- [OData クエリの使用](exposed-apis-odata-samples.md)
