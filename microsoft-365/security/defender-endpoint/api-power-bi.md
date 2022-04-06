---
title: Microsoft Defender for Endpoint API からエンドポイント API への接続Power BI
ms.reviewer: ''
description: Microsoft Defender for Endpoint API の上に Power Business Intelligence (BI) レポートを作成します。
keywords: apis、サポートされている api、Power BI、レポート
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4cad6fd5188745773ce561d1db697989598a1dc5
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472157"
---
# <a name="create-custom-reports-using-power-bi"></a>ユーザー設定を使用してカスタム レポートをPower BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

このセクションでは、Defender for Endpoint API の上にPower BIレポートを作成する方法について説明します。

最初の例は、Power BIを Advanced Hunting API に接続する方法を示し、2 番目の例では、マシン アクションやアラートなどの OData API への接続を示しています。

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Connect Power BI高度なハンティング API へのアクセス

- Microsoft ファイルを開Power BI。

- [データ **の空のクエリの** \> **取得] をクリックします**。

  :::image type="content" source="images/power-bi-create-blank-query.png" alt-text="[データの取得] メニュー項目の [空のクエリ] オプション" lightbox="images/power-bi-create-blank-query.png":::

- [高度 **なエディター] をクリックします**。

  :::image type="content" source="images/power-bi-open-advanced-editor.png" alt-text="[高度なエディター] メニュー項目" lightbox="images/power-bi-open-advanced-editor.png":::

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

- [資格情報 **の編集] をクリックします**。

    :::image type="content" source="images/power-bi-edit-credentials.png" alt-text="[資格情報の編集] メニュー項目" lightbox="images/power-bi-edit-credentials.png":::
    

- [ **組織アカウント] [** \> **サインイン] を選択します**。

    :::image type="content" source="images/power-bi-set-credentials-organizational.png" alt-text="[組織アカウント] メニュー項目の [サインイン] オプション" lightbox="images/power-bi-set-credentials-organizational.png":::

- 資格情報を入力し、サインインするのを待ちます。

- **[接続]** をクリックします。

    :::image type="content" source="images/power-bi-set-credentials-organizational-cont.png" alt-text="[組織アカウント] メニュー項目のサインイン確認メッセージ" lightbox="images/power-bi-set-credentials-organizational-cont.png":::

- これでクエリの結果が表として表示され、その上に視覚化を作成できます。

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

- アラートとコンピューターでも同 **じ操作を****実行できます**。
- また、クエリ フィルターに OData クエリを使用することもできます。「 [Using OData Queries」を参照してください](exposed-apis-odata-samples.md)。

## <a name="power-bi-dashboard-samples-in-github"></a>Power BIダッシュボードのサンプルのGitHub

詳細については、「レポート テンプレートPower BI[参照してください](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)。

## <a name="sample-reports"></a>サンプル レポート

レポート サンプルの Microsoft Defender for Endpoint Power BI表示します。 詳細については、「Browse [code samples」を参照してください](/samples/browse/?products=mdatp)。

## <a name="related-topics"></a>関連項目

- [エンドポイント API の Defender](apis-intro.md)
- [高度な追求 API](run-advanced-query-api.md)
- [OData クエリの使用](exposed-apis-odata-samples.md)
