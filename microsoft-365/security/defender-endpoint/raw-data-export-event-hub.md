---
title: Microsoft Defender for Endpoint イベントをAzure Event Hubsにストリーミングする
description: Advanced Hunting イベントを Event Hub にストリーミングするようにMicrosoft Defender for Endpointを構成する方法について説明します。
keywords: 生データのエクスポート, ストリーミング API, API, Azure Event Hubs, Azure Storage, ストレージ アカウント, Advanced Hunting, 生データ共有
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
ms.openlocfilehash: eb58e21ee9dc2cf7c1eaf89c8fa9d06edfbbe050
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467909"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>高度なハンティング イベントをAzure Event HubsにストリーミングするようにMicrosoft Defender for Endpointを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>開始する前に

1. テナントに [イベント ハブ](/azure/event-hubs/) を作成します。

2. [Azure テナント](https://ms.portal.azure.com/)にログインし、[**サブスクリプション] > [サブスクリプション] > [リソース プロバイダー] > Microsoft.insights に登録します**。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. ***Global Administrator** _ または _*_Security Administrator_** として [Microsoft 365 Defender](https://security.microsoft.com)にログインします。

2. Microsoft Defender ポータルの [[データエクスポート設定] ページ](https://security.microsoft.com/interoperability/dataexport) に移動します。

3. [ **データエクスポート設定の追加]** をクリックします。

4. 新しい設定の名前を選択します。

5. **[イベントをAzure Event Hubsに転送する**] を選択します。

6. **Event Hubs 名** と **Event Hubs リソース ID を** 入力します。

   **Event Hubs リソース ID を** 取得するには、[Azure](https://ms.portal.azure.com/) > プロパティ タブの [Azure Event Hubs 名前空間] ページに移動し、[**リソース ID**] の下のテキストをコピーします\>。

   :::image type="content" source="images/event-hub-resource-id.png" alt-text="Event Hubs リソース ID-1" lightbox="images/event-hub-resource-id.png":::

7. ストリーミングするイベントを選択し、[ **保存]** をクリックします。

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure Event Hubsのイベントのスキーマ

```json
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Azure Event Hubsの各イベント ハブ メッセージには、レコードの一覧が含まれています。

- 各レコードには、イベント名、イベントMicrosoft Defender for Endpoint受信した時刻、それが属するテナント (テナントからイベントのみを取得します)、"**properties**" というプロパティの JSON 形式のイベントが含まれます。

- Microsoft Defender for Endpoint イベントのスキーマの詳細については、「[高度なハンティングの概要](advanced-hunting-overview.md)」を参照してください。

- Advanced Hunting では、 **DeviceInfo** テーブルには、デバイスのグループを含む **MachineGroup** という名前の列があります。 ここでは、すべてのイベントもこの列で装飾されます。 詳細については、「 [デバイス グループ](machine-groups.md) 」を参照してください。

## <a name="data-types-mapping"></a>データ型のマッピング

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. [Microsoft 365 Defender](https://security.microsoft.com)にログインし、[[高度なハンティング] ページ](https://security.microsoft.com/hunting-package)に移動します。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Device Info イベントの例を次に示します。

  :::image type="content" source="images/machine-info-datatype-example.png" alt-text="Event Hubs リソース ID-2" lightbox="images/machine-info-datatype-example.png":::

## <a name="related-topics"></a>関連項目

- [高度なハンティングの概要](advanced-hunting-overview.md)
- [Microsoft Defender for Endpoint ストリーミング API](raw-data-export.md)
- [Microsoft Defender for Endpoint イベントを Azure ストレージ アカウントにストリーミングする](raw-data-export-storage.md)
- [Azure Event Hubsドキュメント](/azure/event-hubs/)
- [接続の問題のトラブルシューティング - Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
