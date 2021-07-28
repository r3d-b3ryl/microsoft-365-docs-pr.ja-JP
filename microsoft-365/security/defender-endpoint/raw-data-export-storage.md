---
title: Microsoft Defender for Endpoint イベントを自分のアカウントStorageする
description: Microsoft Defender for Endpoint を構成して、高度なハンティング イベントを自分のアカウントStorageします。
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
ms.custom: api
ms.openlocfilehash: b914f0db277f92d56b651aa23f840865f029fd7e
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623098"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Microsoft Defender for Endpoint を構成して、高度なハンティング イベントを自分のアカウントStorageする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>はじめに

1. テナントに[Storageアカウント](/azure/storage/common/storage-account-overview)を作成します。

2. Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[サブスクリプション] >[リソース プロバイダー> **Microsoft.insights >に登録** する] に移動します。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. [Microsoft Defender for Endpoint ポータルに](https://securitycenter.windows.com)***グローバル** 管理者 _ または _* セキュリティ管理者 **_としてログイン_ します。

2. [データの[エクスポート設定] ページに移動](https://securitycenter.windows.com/interoperability/dataexport)Microsoft Defender セキュリティ センター。

3. [データエクスポート **設定の追加] をクリックします**。

4. 新しい設定の名前を選択します。

5. [**イベントを転送する] をAzure Storage** します。

6. アカウント リソース **ID Storage入力します**。 Storage アカウント リソース **ID を** 取得するには [、Azure portal](https://ms.portal.azure.com/) > プロパティ タブの Storage アカウント ページに移動し、> アカウント リソース ID の下のStorage **をコピーします**。

   ![イベント ハブ リソース ID1 のイメージ](images/storage-account-resource-id.png)

7. ストリーミングするイベントを選択し、[保存] を **クリックします**。

## <a name="the-schema-of-the-events-in-the-storage-account"></a>アカウント内のイベントのスキーマStorageします。

- BLOB コンテナーは、イベントの種類ごとに作成されます。 

  ![イベント ハブ リソース ID2 のイメージ](images/storage-account-event-schema.png)

- BLOB 内の各行のスキーマは、次の JSON です。 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- 各 BLOB には複数の行が含まれます。

- 各行には、イベント名、Defender for Endpoint がイベントを受信した時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが "properties" と呼ばれるプロパティで含まれる。

- Microsoft Defender for Endpoint イベントのスキーマの詳細については、「Advanced Hunting [overview」を参照してください](advanced-hunting-overview.md)。

- Advanced Hunting では **、DeviceInfo** テーブルに **MachineGroup** という名前の列が含まれるので、デバイスのグループが含まれる。 ここでは、すべてのイベントもこの列で装飾されます。 詳細については [、「デバイス グループ](machine-groups.md) 」を参照してください。

## <a name="data-types-mapping"></a>データ型マッピング

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. ログイン[して[詳細](https://securitycenter.windows.com)Microsoft Defender セキュリティ センター]ページ[に移動します](https://securitycenter.windows.com/hunting-package)。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- デバイス情報イベントの例を次に示します。 

  ![イベント ハブ リソース ID3 のイメージ](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>関連項目
- [高度なハンティングの概要](advanced-hunting-overview.md)
- [エンドポイント ストリーミング API 用 Microsoft Defender](raw-data-export.md)
- [Microsoft Defender for Endpoint イベントを Azure ストレージ アカウントにストリーミングする](raw-data-export-storage.md)
- [Azure Storageアカウントのドキュメント](/azure/storage/common/storage-account-overview)