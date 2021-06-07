---
title: Defender Microsoft 365を自分のアカウントにStorageする
description: 詳細ハンティング イベントを Microsoft 365アカウントにストリームする Defender を構成するStorageします。
keywords: raw data export, Streaming API, API, Event Hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: a4e706bbb2246bd0629db721373ffcd4164d123d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772502"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>高度なMicrosoft 365を自分のアカウントにストリーミングする Defender Storage構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a>開始する前に:

1. テナントに[Storageアカウント](/azure/storage/common/storage-account-overview)を作成します。

2. Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[サブスクリプション] >[サブスクリプション>プロバイダー> **Microsoft.Insights** に登録する] に移動します。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする:

1. Defender セキュリティ センター [Microsoft 365 *](https://security.microsoft.com) **グローバル** 管理者 _ または _* セキュリティ管理者 **_としてログイン_ します。

2. [データの[エクスポート設定] ページに移動](https://security.microsoft.com/settings/mtp_settings/raw_data_export)Microsoft Defender セキュリティ センター。

3. [データエクスポート **設定の追加] をクリックします**。

4. 新しい設定の名前を選択します。

5. [**イベントを転送する] をAzure Storage** します。

6. アカウント リソース **ID Storage入力します**。 Storage アカウント リソース **ID** を取得するには [、Azure portal](https://ms.portal.azure.com/) > プロパティ タブの Storage アカウント ページに移動し、> アカウント リソース ID の下Storage **コピーします**。

   ![イベント ハブ リソース ID1 のイメージ](../defender-endpoint/images/storage-account-resource-id.png)

7. ストリーミングするイベントを選択し、[保存] を **クリックします**。

## <a name="the-schema-of-the-events-in-the-storage-account"></a>アカウント内のイベントのスキーマStorageします。

- BLOB コンテナーは、イベントの種類ごとに作成されます。 

  ![イベント ハブ リソース ID2 のイメージ](../defender-endpoint/images/storage-account-event-schema.png)

- BLOB 内の各行のスキーマは、次の JSON です。 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- 各 BLOB には複数の行が含まれます。

- 各行には、イベント名、Defender for Endpoint がイベントを受信した時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが "properties" と呼ばれるプロパティで含まれる。

- Defender イベントのスキーマの詳細についてはMicrosoft 365高度なハンティング[の概要を参照してください](../defender/advanced-hunting-overview.md)。


## <a name="data-types-mapping"></a>データ型マッピング

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. セキュリティ センターにMicrosoft 365[し、[](https://security.microsoft.com)高度な検索][ページに移動します](https://security.microsoft.com/hunting-package)。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- デバイス情報イベントの例を次に示します。 

  ![イベント ハブ リソース ID3 のイメージ](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>関連項目
- [高度なハンティングの概要](../defender/advanced-hunting-overview.md)
- [Microsoft 365Defender ストリーミング API](streaming-api.md)
- [Defender Microsoft 365を Azure ストレージ アカウントにストリーミングする](streaming-api-storage.md)
- [Azure Storageアカウントのドキュメント](/azure/storage/common/storage-account-overview)
