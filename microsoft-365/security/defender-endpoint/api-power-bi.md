---
title: Power BI への API 接続をMicrosoft Defender for Endpointする
ms.reviewer: ''
description: Microsoft Defender for Endpoint API の上に Power Business Intelligence (BI) レポートを作成します。
keywords: apis、サポートされている API、Power BI、レポート
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 086579f6923f59c12c5ef9f7494b539f24c19210
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328125"
---
# <a name="create-custom-reports-using-power-bi"></a>Power BI を使用してカスタム レポートを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

このセクションでは、Defender for Endpoint API の上に Power BI レポートを作成する方法について説明します。

最初の例では Power BI を Advanced Hunting API に接続する方法を示し、2 番目の例では、マシン アクションやアラートなどの OData API への接続を示します。

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Power BI を Advanced Hunting API に接続する

- Microsoft Power BI を開きます。

- [データ **の空のクエリ****の**\>取得] をクリックします。

  :::image type="content" source="images/power-bi-create-blank-query.png" alt-text="[データの取得] メニュー項目の下にある [空白のクエリ] オプション" lightbox="images/power-bi-create-blank-query.png":::

- **[詳細エディター**] をクリックします。

  :::image type="content" source="images/power-bi-open-advanced-editor.png" alt-text="詳細エディターメニュー項目" lightbox="images/power-bi-open-advanced-editor.png":::

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

- **[完了]** をクリックします。

- [ **資格情報の編集]** をクリックします。

    :::image type="content" source="images/power-bi-edit-credentials.png" alt-text="[資格情報の編集] メニュー項目" lightbox="images/power-bi-edit-credentials.png":::
    

- [ **組織アカウント** \> **のサインイン**] を選択します。

    :::image type="content" source="images/power-bi-set-credentials-organizational.png" alt-text="[組織アカウント] メニュー項目の [サインイン] オプション" lightbox="images/power-bi-set-credentials-organizational.png":::

- 資格情報を入力し、サインインするまで待ちます。

- **[接続]** をクリックします。

    :::image type="content" source="images/power-bi-set-credentials-organizational-cont.png" alt-text="[組織アカウント] メニュー項目のサインイン確認メッセージ" lightbox="images/power-bi-set-credentials-organizational-cont.png":::

- これで、クエリの結果がテーブルとして表示され、その上に視覚化を作成できるようになります。

- このテーブルを複製し、名前を変更し、内部の Advanced Hunting クエリを編集して、必要なデータを取得できます。

## <a name="connect-power-bi-to-odata-apis"></a>Power BI を OData API に接続する

- 上記の例との唯一の違いは、エディター内のクエリです。

- 以下をコピーし、エディターに貼り付けて、組織からすべての **マシン アクション** をプルします。

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source
```

- **アラート** と **マシン** でも同じ操作を行うことができます。
- クエリ フィルターに OData クエリを使用することもできます。「 [OData クエリの使用](exposed-apis-odata-samples.md)」を参照してください。

## <a name="power-bi-dashboard-samples-in-github"></a>GitHub の Power BI ダッシュボードサンプル

詳細については、 [Power BI レポート テンプレート](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)を参照してください。

## <a name="sample-reports"></a>サンプル レポート

Microsoft Defender for Endpoint Power BI レポートのサンプルを表示します。 詳細については、「 [コード サンプルを参照する」を](/samples/browse/?products=mdatp)参照してください。

## <a name="related-topics"></a>関連項目

- [Defender for Endpoint API](apis-intro.md)
- [高度な追求 API](run-advanced-query-api.md)
- [OData クエリの使用](exposed-apis-odata-samples.md)
