---
title: ユーザー Microsoft 365 Defenderアカウントにイベントをストレージする
description: 詳細ハンティング イベントを Microsoft 365 Defenderアカウントにストリーミングする方法をストレージします。
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
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028897"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>高度Microsoft 365 Defenderイベントを自分のアカウントにストリーミングするストレージ構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a>開始する前に:

1. テナントに[ストレージアカウント](/azure/storage/common/storage-account-overview)を作成します。

2. Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[サブスクリプション] > サブスクリプション > リソース プロバイダー> **Microsoft.インサイト** に登録します。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする:

1. セキュリティ センターに [Microsoft 365 Defender](https://security.microsoft.com) ***グローバル管理者** _ または _* セキュリティ管理者 **_としてログイン_ します。

2. [データの[エクスポート設定] ページに移動](https://security.microsoft.com/settings/mtp_settings/raw_data_export)Microsoft Defender セキュリティ センター。

3. [データエクスポート **設定の追加] をクリックします**。

4. 新しい設定の名前を選択します。

5. [**イベントを転送する] をAzure Storage** します。

6. アカウント リソース **ID ストレージ入力します**。 ストレージ アカウント リソース **ID を** 取得するには [、Azure portal](https://ms.portal.azure.com/) > プロパティ タブの ストレージ アカウント ページに移動し、> アカウント リソース ID の下のテキストストレージ **コピーします**。

   ![イベント ハブ リソース ID1 のイメージ](../defender-endpoint/images/storage-account-resource-id.png)

7. ストリーミングするイベントを選択し、[保存] を **クリックします**。

## <a name="the-schema-of-the-events-in-the-storage-account"></a>アカウント内のイベントのスキーマストレージします。

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

- イベントのスキーマの詳細については、「高度なMicrosoft 365 Defender概要[」を参照してください](../defender/advanced-hunting-overview.md)。


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
- [Microsoft 365 Defenderストリーミング API](streaming-api.md)
- [Azure Microsoft 365 Defenderアカウントにイベントをストリーミングする](streaming-api-storage.md)
- [Azure Storageアカウントのドキュメント](/azure/storage/common/storage-account-overview)
