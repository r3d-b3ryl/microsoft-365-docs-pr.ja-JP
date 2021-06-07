---
title: Defender Microsoft 365 Azure イベント ハブへのストリーム配信
description: 詳細ハンティング イベントをイベント Microsoft 365にストリームする Defender を構成する方法について学習します。
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
ms.openlocfilehash: b96ae78b0f2decfe7b2c6f695a4456ac93919c35
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772509"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Azure イベント Microsoft 365に高度なハンティング イベントをストリーミングするように Defender を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>開始する前に:

1. テナントに [イベント ハブ](/azure/event-hubs/) を作成します。

2. Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[サブスクリプション] >[サブスクリプション>プロバイダー> **Microsoft.Insights** に登録する] に移動します。

3. イベント ハブ名前空間を作成し、[イベント ハブ] **>[** 追加] に移動し、予想される負荷に適した価格レベル、スループット単位、自動インフレートを選択します。 詳細については[、「Pricing - Event Hubs |Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

4. イベント ハブの名前空間が作成されると、App Registration Service Principal を Reader、Azure Event Hubs Data Receiver、および投稿者として Microsoft 365 Defender にログインするユーザーを追加する必要があります (これは、リソース グループまたはサブスクリプション レベルでも実行できます)。 [役割の **割り当て] の下>アクセス制御 (IAM)** > [イベント ハブの名前空間 **] に移動します**。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする:

1. Defender セキュリティ センター [にMicrosoft 365 *](https://security.microsoft.com) **グローバル** 管理者 _ または _* セキュリティ管理者 **_としてログイン_ します。

2. [データエクスポート設定 [] ページに移動します](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。

3. [**追加**] をクリックします。

4. 新しい設定の名前を選択します。

5. [ **イベントを Azure イベント ハブに転送する] を選択します**。

6. イベント データを 1 つのイベント ハブにエクスポートするか、イベント ハブの名前空間内の別のハブに各イベント テーブルをエクスポートするか選択できます。 

7. イベント データを 1 つのイベント ハブにエクスポートするには、イベント ハブ名と Event **Hub** リソース **ID を入力します**。

   Event **Hubs リソース ID を** 取得するには [、[Azure](https://ms.portal.azure.com/)プロパティ] タブの [Azure Event Hubs 名前空間] ページに移動し> [リソース ID] の下のテキストを  >  **コピーします**。

   ![イベント ハブ リソース Id1 のイメージ](../defender-endpoint/images/event-hub-resource-id.png)

8. ストリーミングするイベントを選択し、[保存] を **クリックします**。

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure Event Hubs のイベントのスキーマ:

```
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

- Azure Event Hubs の各イベント ハブ メッセージには、レコードの一覧が含まれます。

- 各レコードには、イベント名、Microsoft 365 Defender がイベントを受け取った時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが **"properties"** というプロパティで含まれる。

- Defender イベントのスキーマの詳細についてはMicrosoft 365高度なハンティング[の概要を参照してください](advanced-hunting-overview.md)。

- Advanced Hunting では **、DeviceInfo** テーブルに **MachineGroup** という名前の列が含まれるので、デバイスのグループが含まれる。 ここでは、すべてのイベントもこの列で装飾されます。 

9. 各イベント テーブルを別のイベント ハブにエクスポートするには、イベント ハブ名を空のままにしMicrosoft 365 Defender が実行します。


## <a name="data-types-mapping"></a>データ型マッピング:

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. セキュリティ センターにMicrosoft 365[し、[](https://security.microsoft.com)高度な検索][ページに移動します](https://security.microsoft.com/hunting-package)。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- デバイス情報イベントの例を次に示します。 

  ![イベント ハブ リソース Id2 のイメージ](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>関連項目
- [高度なハンティングの概要](advanced-hunting-overview.md)
- [Microsoft 365Defender ストリーミング API](streaming-api.md)
- [Defender Microsoft 365を Azure ストレージ アカウントにストリーミングする](streaming-api-storage.md)
- [Azure Event Hubs のドキュメント](/azure/event-hubs/)
- [接続の問題のトラブルシューティング - Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
