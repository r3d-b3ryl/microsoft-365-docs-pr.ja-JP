---
title: Microsoft 365 Defender イベントをストレージ アカウントにストリーミングする
description: Advanced Hunting イベントをストレージ アカウントにストリーミングするようにMicrosoft 365 Defenderを構成する方法について説明します。
keywords: 生データエクスポート, ストリーミング API, API, Event Hubs, Azure Storage, ストレージ アカウント, Advanced Hunting, 生データ共有
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
ms.openlocfilehash: 0f5195e5a74395073267fd4df87f077c6a1d5f20
ms.sourcegitcommit: c6f1486617b39565bfd8f662ee6ad65a9cefd3e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66530578"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Advanced Hunting イベントをストレージ アカウントにストリーミングするようにMicrosoft 365 Defenderを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>はじめに

1. テナントに [ストレージ アカウント](/azure/storage/common/storage-account-overview) を作成します。

2. [Azure テナント](https://ms.portal.azure.com/)にログインし、[**サブスクリプション] > [サブスクリプション] > [リソース プロバイダー] > Microsoft.Insights に登録します**。

### <a name="add-contributor-permissions"></a>共同作成者のアクセス許可を追加する

ストレージ アカウントが作成されたら、次の手順を実行する必要があります。

1. 共同作成者としてMicrosoft 365 Defenderにログインするユーザーを定義します。

    **[ストレージ アカウント > アクセス制御 (IAM)] > [****ロールの割り当て**] で [追加と確認] に移動します。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. ***Global Administrator** _ または _*_Security Administrator_** として <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にログインします。

2. **[設定]** **Microsoft 365 Defender** \> **[ストリーミング API] に** 移動します\>。 **ストリーミング API** ページに直接移動するには、<https://security.microsoft.com/settings/mtp_settings/raw_data_export>.

3. **[追加]** をクリックします。

4. 表示される [ **新しいストリーミング API 設定の追加]** ポップアップで、次の設定を構成します。
   1. **名前**: 新しい設定の名前を選択します。
   2. [ **Azure Storage にイベントを転送する**] を選択します。
   3. 表示された **[ストレージ アカウント リソース ID** ] ボックスに、 **ストレージ アカウント リソース ID を** 入力します。 **ストレージ アカウント リソース ID を** 取得するには、Azure portal<https://portal.azure.com>を開き、[**ストレージ アカウント**\>] をクリックして [プロパティ] タブに移動し、[\>**ストレージ アカウント リソース ID**] の下のテキストをコピーします。

      :::image type="content" source="../defender-endpoint/images/storage-account-resource-id.png" alt-text="ストレージ アカウント リソース ID" lightbox="../defender-endpoint/images/storage-account-resource-id.png":::

   4. **[新しいストリーミング API 設定の追加]** ポップアップに戻り、ストリーミングする **イベントの種類** を選択します。

   完了したら、**[送信]** をクリックします。

## <a name="the-schema-of-the-events-in-the-storage-account"></a>ストレージ アカウント内のイベントのスキーマ

- イベントの種類ごとに BLOB コンテナーが作成されます。

  :::image type="content" source="../defender-endpoint/images/storage-account-event-schema.png" alt-text="BLOB コンテナーの例" lightbox="../defender-endpoint/images/storage-account-event-schema.png":::

- BLOB 内の各行のスキーマは、次の JSON です。

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- 各 BLOB には複数の行が含まれています。

- 各行には、イベント名、Defender for Endpoint がイベントを受信した時刻、それが属するテナント (テナントからイベントのみを取得します)、"properties" というプロパティの JSON 形式のイベントが含まれます。

- Microsoft 365 Defender イベントのスキーマの詳細については、「[高度なハンティングの概要](../defender/advanced-hunting-overview.md)」を参照してください。

## <a name="data-types-mapping"></a>データ型のマッピング

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にログインし、**Hunting** \> **Advanced hunting** に移動します。 **[高度な検索**] ページに直接移動するには、<security.microsoft.com/advanced-hunting>を使用します。

2. [ **クエリ** ] タブで、次のクエリを実行して、各イベントのデータ型マッピングを取得します。

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Device Info イベントの例を次に示します。

  :::image type="content" source="../defender-endpoint/images/machine-info-datatype-example.png" alt-text="デバイス情報クエリの例" lightbox="../defender-endpoint/images/machine-info-datatype-example.png":::

## <a name="monitoring-created-resources"></a>作成されたリソースの監視

**Azure Monitor** を使用して、ストリーミング API によって作成されたリソースを監視できます。 詳細については、「[ターゲットの監視 - Azure Monitor |」を参照してください。Microsoft Docs](/azure/azure-monitor/logs/logs-data-export?tabs=portal#monitor-destinations)。

## <a name="related-topics"></a>関連項目

- [高度なハンティングの概要](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender ストリーミング API](streaming-api.md)
- [Microsoft 365 Defender イベントを Azure ストレージ アカウントにストリーミングする](streaming-api-storage.md)
- [Azure Storage アカウントのドキュメント](/azure/storage/common/storage-account-overview)
