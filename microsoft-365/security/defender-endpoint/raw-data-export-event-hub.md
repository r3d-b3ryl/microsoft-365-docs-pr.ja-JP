---
title: エンドポイント イベントの Microsoft Defender を Azure イベント ハブにストリーミングする
description: 高度なハンティング イベントをイベント ハブにストリーミングするために Microsoft Defender ATP を構成する方法について説明します。
keywords: raw data export, Streaming API, API, Azure Event Hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 231ba79e1d66eee263b6c1a4335f0a7b54eeb75d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063868"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Azure イベント ハブに高度なハンティング イベントをストリーミングするように Microsoft Defender for Endpoint を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>開始する前に:

1. テナントに [イベント ハブ](https://docs.microsoft.com/azure/event-hubs/) を作成します。

2. Azure テナントに [ログインし、[**Subscriptions](https://ms.portal.azure.com/)> サブスクリプション >リソース プロバイダー> **Microsoft.insights** に登録する] に移動します。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする:

1. [Microsoft Defender](https://securitycenter.windows.com)セキュリティ センターに ***グローバル** 管理者 _ または _* セキュリティ管理者 **_としてログイン_ します。

2. Microsoft Defender セキュリティ [センターの [データエクスポート設定]](https://securitycenter.windows.com/interoperability/dataexport) ページに移動します。

3. [データエクスポート **設定の追加] をクリックします**。

4. 新しい設定の名前を選択します。

5. [ **イベントを Azure イベント ハブに転送する] を選択します**。

6. イベント ハブ **名とイベント** ハブ **リソース ID を入力します**。

   Event Hubs リソース ID を取得するには [、Azure](https://ms.portal.azure.com/) > プロパティ タブの Azure Event **Hubs** 名前空間ページに移動し、[リソース ID] >を **コピーします**。

   ![イベント ハブ リソース Id1 のイメージ](images/event-hub-resource-id.png)

7. ストリーミングするイベントを選択し、[保存] を **クリックします**。

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure Event Hubs のイベントのスキーマ:

```
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

## <a name="data-types-mapping"></a>データ型マッピング:

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. Microsoft Defender セキュリティ センター [にログインし、[](https://securitycenter.windows.com) 高度な検索] [ページに移動します](https://securitycenter.windows.com/hunting-package)。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- デバイス情報イベントの例を次に示します。 

  ![イベント ハブ リソース Id2 のイメージ](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>関連項目
- [高度なハンティングの概要](advanced-hunting-overview.md)
- [エンドポイント ストリーミング API 用 Microsoft Defender](raw-data-export.md)
- [Microsoft Defender for Endpoint イベントを Azure ストレージ アカウントにストリーミングする](raw-data-export-storage.md)
- [Azure Event Hubs のドキュメント](https://docs.microsoft.com/azure/event-hubs/)
- [接続の問題のトラブルシューティング - Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
