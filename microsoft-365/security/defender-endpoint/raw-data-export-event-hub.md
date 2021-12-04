---
title: エンドポイント イベントの Microsoft Defender を Azure イベント ハブにストリーミングする
description: Microsoft Defender for Endpoint を構成して、高度なハンティング イベントをイベント ハブにストリーミングする方法について説明します。
keywords: raw data export, Streaming API, API, Azure Event Hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: 0dddebc27f776e317090ac3424c27f01f26126ed
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300191"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Azure イベント ハブに高度なハンティング イベントをストリーミングするように Microsoft Defender for Endpoint を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>始める前に

1. テナントに [イベント ハブ](/azure/event-hubs/) を作成します。

2. Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[**Subscriptions > サブスクリプション > リソース プロバイダー> **Microsoft.insights**** に登録します。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. * Global **Administrator** _ [または](https://securitycenter.windows.com)_* セキュリティ管理者 **として、Microsoft Defender セキュリティ センターに _ログイン_ します。

2. [データのエクスポート[設定] ページに移動Microsoft Defender セキュリティ センター。](https://securitycenter.windows.com/interoperability/dataexport)

3. [データエクスポート **設定の追加] をクリックします**。

4. 新しい設定の名前を選択します。

5. [ **イベントを Azure イベント ハブに転送する] を選択します**。

6. イベント ハブ **名とイベント** ハブ **リソース ID を入力します**。

   Event Hubs リソース ID を取得するには、Azure の [プロパティ] タブの [[Azure](https://ms.portal.azure.com/) Event **Hubs** 名前空間] ページ>[リソース ID] の下のテキストを \> **コピーします**。

   :::image type="content" alt-text="イベント ハブ リソース Id1 のイメージ。" source="images/event-hub-resource-id.png" lightbox="images/event-hub-resource-id.png":::

7. ストリーミングするイベントを選択し、[保存] を **クリックします**。

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure Event Hubs のイベントのスキーマ

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

- Azure Event Hubs の各イベント ハブ メッセージには、レコードの一覧が含まれます。

- 各レコードには、イベント名、Microsoft Defender for Endpoint がイベントを受信した時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが **"properties"** というプロパティで含まれる。

- Microsoft Defender for Endpoint イベントのスキーマの詳細については、「Advanced Hunting [overview」を参照してください](advanced-hunting-overview.md)。

- Advanced Hunting では **、DeviceInfo** テーブルに **MachineGroup** という名前の列が含まれるので、デバイスのグループが含まれる。 ここでは、すべてのイベントもこの列で装飾されます。 詳細については [、「デバイス グループ](machine-groups.md) 」を参照してください。

## <a name="data-types-mapping"></a>データ型マッピング

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. ログイン[して[詳細](https://securitycenter.windows.com)Microsoft Defender セキュリティ センター]ページ[に移動します](https://securitycenter.windows.com/hunting-package)。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- デバイス情報イベントの例を次に示します。

  ![イベント ハブ リソース Id2 のイメージ。](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>関連トピック

- [高度なハンティングの概要](advanced-hunting-overview.md)
- [エンドポイント ストリーミング API 用 Microsoft Defender](raw-data-export.md)
- [Microsoft Defender for Endpoint イベントを Azure ストレージ アカウントにストリーミングする](raw-data-export-storage.md)
- [Azure Event Hubs のドキュメント](/azure/event-hubs/)
- [接続の問題のトラブルシューティング - Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
