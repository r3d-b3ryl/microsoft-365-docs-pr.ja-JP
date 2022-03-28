---
title: Microsoft Defender for Endpoint イベントを自分のアカウントStorageする
description: Microsoft Defender for Endpoint を構成して、高度なハンティング イベントを自分のアカウントStorageします。
keywords: raw data export, Streaming API, API, Event Hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: 77220c8e34cfcbcdb6b1ca527786696bb67e5d79
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465782"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Microsoft Defender for Endpoint を構成して、高度なハンティング イベントを自分のアカウントStorageする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>はじめに

1. テナントに[Storageアカウント](/azure/storage/common/storage-account-overview)を作成します。

2. Azure テナントにログインし、[ [サブスクリプション](https://ms.portal.azure.com/)] >[リソース プロバイダー> **Microsoft.insights >に登録** する] に移動します。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. *Global Administrator_ [Microsoft 365 Defender](https://security.microsoft.com) _*_Security_ **Administrator****としてログインします。

2. [データの[エクスポート設定] ページに移動](https://security.microsoft.com/interoperability/dataexport)Microsoft 365 Defender。

3. [データエクスポート **設定の追加] をクリックします**。

4. 新しい設定の名前を選択します。

5. [**イベントを転送する] をAzure Storage**。

6. アカウント リソース **ID Storage入力します**。 アカウント リソース **ID** を取得Storage、[Azure portal](https://ms.portal.azure.com/) \> の [プロパティ] タブの [Storage アカウント] ページに移動し\>、[アカウント リソース ID] の下Storage **コピーします**。

   :::image type="content" source="images/storage-account-resource-id.png" alt-text="リソース ID 1 のイベント ハブ" lightbox="images/storage-account-resource-id.png":::

7. ストリーミングするイベントを選択し、[保存] を **クリックします**。

## <a name="the-schema-of-the-events-in-the-storage-account"></a>アカウント内のイベントのスキーマStorageします。

- BLOB コンテナーは、イベントの種類ごとに作成されます。

  :::image type="content" source="images/storage-account-event-schema.png" alt-text="リソース ID 2 を持つイベント ハブ" lightbox="images/storage-account-event-schema.png":::

- BLOB 内の各行のスキーマは、次の JSON です。

  ```json
  {
      "time": "<The time WDATP received the event>"
      "tenantId": "<Your tenant ID>"
      "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
      "properties": { <WDATP Advanced Hunting event as Json> }
  }
  ```

- 各 BLOB には複数の行が含まれます。

- 各行には、イベント名、Defender for Endpoint がイベントを受信した時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが "properties" と呼ばれるプロパティで含まれる。

- Microsoft Defender for Endpoint イベントのスキーマの詳細については、「Advanced Hunting overview [」を参照してください](advanced-hunting-overview.md)。

- Advanced Hunting では、 **DeviceInfo** テーブルに **MachineGroup** という名前の列が含まれるので、デバイスのグループが含まれる。 ここでは、すべてのイベントもこの列で装飾されます。 詳細については [、「デバイス グループ](machine-groups.md) 」を参照してください。

## <a name="data-types-mapping"></a>データ型マッピング

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. ログインして[詳細[Microsoft 365 Defender](https://security.microsoft.com)]ページ[に移動します](https://security.microsoft.com/hunting-package)。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- デバイス情報イベントの例を次に示します。

  :::image type="content" source="images/data-types-mapping-query.png" alt-text="リソース ID 3 のイベント ハブ" lightbox="images/data-types-mapping-query.png":::

## <a name="related-topics"></a>関連項目

- [高度なハンティングの概要](advanced-hunting-overview.md)
- [エンドポイント ストリーミング API 用 Microsoft Defender](raw-data-export.md)
- [Microsoft Defender for Endpoint イベントを Azure ストレージ アカウントにストリーミングする](raw-data-export-storage.md)
- [Azure Storageアカウントのドキュメント](/azure/storage/common/storage-account-overview)
