---
title: Microsoft Defender for Endpoint イベントをストレージ アカウントにストリーミングする
description: Advanced Hunting イベントをストレージ アカウントにストリーミングするようにMicrosoft Defender for Endpointを構成する方法について説明します。
keywords: 生データエクスポート, ストリーミング API, API, Event Hubs, Azure Storage, ストレージ アカウント, Advanced Hunting, 生データ共有
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
ms.openlocfilehash: c94830e4f9dbfe16a8dfafba35aecb5a36efddf5
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66493445"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>高度なハンティング イベントをストレージ アカウントにストリーミングするようにMicrosoft Defender for Endpointを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>はじめに

1. テナントに [ストレージ アカウント](/azure/storage/common/storage-account-overview) を作成します。

2. [Azure テナント](https://ms.portal.azure.com/)にログインし、[**サブスクリプション] > [サブスクリプション] > [リソース プロバイダー] > Microsoft.insights に登録します**。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. ***Global Administrator** _ または _*_Security Administrator_** として [Microsoft 365 Defender](https://security.microsoft.com)にログインします。

2. Microsoft 365 Defenderの [[データエクスポート設定] ページ](https://security.microsoft.com/settings/mtp_settings/raw_data_export)に移動します。

3. [ **データエクスポート設定の追加]** をクリックします。

4. 新しい設定の名前を選択します。

5. [ **Azure Storage にイベントを転送する**] を選択します。

6. **ストレージ アカウント リソース ID を入力します**。 **ストレージ アカウント リソース ID を取得するには、ストレージ アカウント リソース ID** の下のテキストをコピー [Azure portal](https://ms.portal.azure.com/)\>プロパティ タブ\>の **[ストレージ アカウント**] ページに移動します。

   :::image type="content" source="images/storage-account-resource-id.png" alt-text="リソース ID1 を持つ Event Hubs" lightbox="images/storage-account-resource-id.png":::

7. ストリーミングするイベントを選択し、[ **保存]** をクリックします。

## <a name="the-schema-of-the-events-in-the-storage-account"></a>ストレージ アカウント内のイベントのスキーマ

- イベントの種類ごとに BLOB コンテナーが作成されます。

  :::image type="content" source="images/storage-account-event-schema.png" alt-text="リソース ID 2 を持つ Event Hubs" lightbox="images/storage-account-event-schema.png":::

- BLOB 内の各行のスキーマは、次の JSON です。

  ```json
  {
    "time": "<The time WDATP received the event>"
    "tenantId": "<Your tenant ID>"
    "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
    "properties": { <WDATP Advanced Hunting event as Json> }
  }
  ```

- 各 BLOB には複数の行が含まれています。

- 各行には、イベント名、Defender for Endpoint がイベントを受信した時刻、それが属するテナント (テナントからイベントのみを取得します)、"properties" というプロパティの JSON 形式のイベントが含まれます。

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

  :::image type="content" source="images/data-types-mapping-query.png" alt-text="リソース ID 3 を持つ Event Hubs" lightbox="images/data-types-mapping-query.png":::

## <a name="related-topics"></a>関連項目

- [高度なハンティングの概要](advanced-hunting-overview.md)
- [Microsoft Defender for Endpoint ストリーミング API](raw-data-export.md)
- [Microsoft Defender for Endpoint イベントを Azure ストレージ アカウントにストリーミングする](raw-data-export-storage.md)
- [Azure Storage アカウントのドキュメント](/azure/storage/common/storage-account-overview)
