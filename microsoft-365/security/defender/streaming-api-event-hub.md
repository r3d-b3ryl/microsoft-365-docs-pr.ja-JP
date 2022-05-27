---
title: Microsoft 365 Defender イベントをAzure Event Hubsにストリーミングする
description: Advanced Hunting イベントを Event Hubs にストリーミングするようにMicrosoft 365 Defenderを構成する方法について説明します。
keywords: 生データのエクスポート, ストリーミング API, API, Azure Event Hubs, Azure Storage, ストレージ アカウント, Advanced Hunting, 生データ共有
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9cae28cc69d67bb18058e2c81cd8235ffce79997
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65754402"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>高度なハンティング イベントを Azure Event Hub にストリーミングするようにMicrosoft 365 Defenderを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="prerequisites"></a>前提条件

Event Hubs にデータをストリーミングするようにMicrosoft 365 Defenderを構成する前に、次の前提条件が満たされていることを確認してください。

1. Event Hubs を作成します (詳細については、「 [Event Hubs のセットアップ](configure-event-hub.md#set-up-event-hubs)」を参照してください)。

2. Event Hubs 名前空間の作成 (詳細については、「 [Event Hubs 名前空間のセットアップ](configure-event-hub.md#set-up-event-hubs-namespace)」を参照してください)。

3. このエンティティが Event Hubs にデータをエクスポートできるように、 **共同作成者** の特権を持つエンティティにアクセス許可を追加します。 アクセス許可の追加の詳細については、「[アクセス許可の追加](configure-event-hub.md#add-permissions)」を参照してください。

> [!NOTE]
> ストリーミング API は、Event Hubs または Azure Storage アカウントを使用して統合できます。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. ***Global Administrator** _ または _*_Security Administrator_** として <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>にログオンします。

2. [[ストリーミング API の設定] ページ](https://security.microsoft.com/settings/mtp_settings/raw_data_export)に移動します。

3. [**追加**] をクリックします。

4. 新しい設定の名前を選択します。

5. [ **Azure Event Hub にイベントを転送する]** を選択します。

6. イベント データを 1 つの Event Hub にエクスポートするか、Event Hubs 名前空間内の別の Event Hubs に各イベント テーブルをエクスポートするかを選択できます。

7. イベント データを 1 つの Event Hub にエクスポートするには、 **Event Hub 名** と **Event Hub リソース ID を** 入力します。

   **Event Hub リソース ID を** 取得するには、[Azure](https://ms.portal.azure.com/) > **の [プロパティ**] タブの [Azure Event Hubs名前空間] ページに移動>、[**リソース ID**] の下にテキストをコピーします。

   :::image type="content" source="../defender-endpoint/images/event-hub-resource-id.png" alt-text="Event Hub リソース ID" lightbox="../defender-endpoint/images/event-hub-resource-id.png":::

8. [イベント ストリーミング API でサポートされているMicrosoft 365 Defender イベントの種類に](supported-event-types.md)移動し、Microsoft 365 Streaming API のイベントの種類のサポート状態を確認します。

9. ストリーミングするイベントを選択し、[ **保存]** をクリックします。

## <a name="the-schema-of-the-events-in-azure-event-hub"></a>Azure Event Hub のイベントのスキーマ

```JSON
{
   "records": [
               {
                  "time": "<The time Microsoft 365 Defender received the event>"
                  "tenantId": "<The Id of the tenant that the event belongs to>"
                  "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                  "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
               }
               ...
            ]
}
```

- Azure Event Hubsの各 Event Hubs メッセージには、レコードの一覧が含まれています。

- 各レコードには、イベント名、イベントMicrosoft 365 Defender受信した時刻、それが属するテナント (テナントからイベントのみを取得します)、"**properties**" というプロパティの JSON 形式のイベントが含まれます。

- Microsoft 365 Defender イベントのスキーマの詳細については、「[高度なハンティングの概要](advanced-hunting-overview.md)」を参照してください。

- Advanced Hunting では、 **DeviceInfo** テーブルには、デバイスのグループを含む **MachineGroup** という名前の列があります。 ここでは、すべてのイベントもこの列で装飾されます。

## <a name="data-types-mapping"></a>データ型のマッピング

イベント プロパティのデータ型を取得するには、次の手順に従います。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にログオンし、[[高度なハンティング] ページ](https://security.microsoft.com/hunting-package)に移動します。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Device Info イベントの例を次に示します。

  :::image type="content" source="../defender-endpoint/images/machine-info-datatype-example.png" alt-text="デバイス情報のクエリの例" lightbox="../defender-endpoint/images/machine-info-datatype-example.png":::

## <a name="related-topics"></a>関連項目

- [高度なハンティングの概要](advanced-hunting-overview.md)
- [Microsoft 365 Defender ストリーミング API](streaming-api.md)
- [イベント ストリーミング API でサポートされているMicrosoft 365 Defenderイベントの種類](supported-event-types.md)
- [Microsoft 365 Defender イベントを Azure ストレージ アカウントにストリーミングする](streaming-api-storage.md)
- [Azure Event Hubsドキュメント](/azure/event-hubs/)
- [接続の問題のトラブルシューティング - Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
