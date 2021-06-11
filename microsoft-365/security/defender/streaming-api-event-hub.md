---
title: Defender Microsoft 365 Azure イベント ハブにストリーム配信する
description: 詳細ハンティング イベントをイベント Microsoft 365にストリームする Defender を構成する方法について学習します。
keywords: raw data export, Streaming API, API, Azure Event Hub, Azure Storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: 6f5d04d35c8c4fec18e1a689c51ecbc32d416adf
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903818"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>Azure イベント Microsoft 365高度なハンティング イベントをストリーミングするように Defender を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>はじめに

1. テナントに [イベント ハブ](/azure/event-hubs/) を作成します。

2. Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[サブスクリプション] >[サブスクリプション>プロバイダー> **Microsoft.Insights** に登録する] に移動します。

3. イベント ハブ名前空間を作成し、[イベント ハブ] **>[** 追加] に移動し、予想される負荷に適した価格レベル、スループット単位、自動インフレートを選択します。 詳細については、「価格 - イベント ハブ[」を参照|Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

### <a name="add-contributor-permissions"></a>共同作成者のアクセス許可を追加する 
Event Hub 名前空間が作成されると、次の処理が必要になります。
1. Defender にログインするユーザーを投稿者Microsoft 365定義します。

2. アプリケーションに接続する場合は、アプリ登録サービス プリンシパルを Reader、Azure Event Hub Data Receiver として追加します (これは、リソース グループまたはサブスクリプション レベルでも実行できます)。 

    [役割の **割り当て] > [追加と確認]** >アクセス制御 (IAM) のイベント ハブ名前空間 **に移動します**。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. Defender セキュリティ センター [にMicrosoft 365 *](https://security.microsoft.com) **グローバル** 管理者 _ または _* セキュリティ管理者 **_としてログイン_ します。

2. [ストリーミング [API の設定] ページに移動します](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。

3. [**追加**] をクリックします。

4. 新しい設定の名前を選択します。

5. [イベント **を Azure Event Hub に転送する] を選択します**。

6. イベント データを 1 つのイベント ハブにエクスポートするか、イベント ハブ名前空間内の別のイベント ハブに各イベント テーブルをエクスポートするか選択できます。 

7. イベント データを 1 つのイベント ハブにエクスポートするには、イベント ハブ名とイベント ハブ **リソース ID を入力します**。

   Event Hub リソース **ID を取得するには**、[Azure プロパティ] タブの [[Azure](https://ms.portal.azure.com/)Event Hub 名前空間] ページに移動し> [リソース ID] の下のテキストを  >  **コピーします**。

   ![イベント ハブ リソース Id1 のイメージ](../defender-endpoint/images/event-hub-resource-id.png)

8. ストリーミングするイベントを選択し、[保存] を **クリックします**。

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

- Azure Event Hub の各イベント ハブ メッセージには、レコードの一覧が含まれます。

- 各レコードには、イベント名、Microsoft 365 Defender がイベントを受け取った時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが **"properties"** というプロパティで含まれる。

- Defender イベントのスキーマの詳細についてはMicrosoft 365高度なハンティング[の概要を参照してください](advanced-hunting-overview.md)。

- Advanced Hunting では **、DeviceInfo** テーブルに **MachineGroup** という名前の列が含まれるので、デバイスのグループが含まれる。 ここでは、すべてのイベントもこの列で装飾されます。 




## <a name="data-types-mapping"></a>データ型マッピング

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. セキュリティ センターにMicrosoft 365[し、[](https://security.microsoft.com)高度な検索][ページに移動します](https://security.microsoft.com/hunting-package)。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。
 
   ```kusto
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
- [Azure Event Hub のドキュメント](/azure/event-hubs/)
- [接続の問題のトラブルシューティング - Azure Event Hub](/azure/event-hubs/troubleshooting-guide)
