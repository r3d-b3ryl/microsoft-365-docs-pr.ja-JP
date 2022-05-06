---
title: Microsoft 365 Defender イベントを Azure Event Hub にストリーミングする
description: Advanced Hunting イベントを Event Hub にストリーミングするようにMicrosoft 365 Defenderを構成する方法について説明します。
keywords: 生データのエクスポート, ストリーミング API, API, Azure Event Hub, Azure Storage, ストレージ アカウント, Advanced Hunting, 生データ共有
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
ms.openlocfilehash: 064ce5f796d59994b9d7ec4c3403711b1d683e56
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500477"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>高度なハンティング イベントを Azure Event Hub にストリーミングするようにMicrosoft 365 Defenderを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>はじめに

1. テナントに [イベント ハブ](/azure/event-hubs/) を作成します。

2. [Azure テナント](https://ms.portal.azure.com/)にログインし、[**サブスクリプション] > [サブスクリプション] > [リソース プロバイダー] > Microsoft.インサイトに登録します**。

3. Event Hub 名前空間を作成し、[ **Event Hub >追加]** に移動し、予想される負荷に適した価格レベル、スループット ユニット、自動インフレを選択します。 詳細については、 [Event Hubs の価格に関するページを](https://azure.microsoft.com/pricing/details/event-hubs/)参照してください。

### <a name="add-contributor-permissions"></a>共同作成者のアクセス許可を追加する

Event Hub 名前空間が作成されたら、次の手順を実行する必要があります。

1. 共同作成者としてMicrosoft 365 Defenderにログインするユーザーを定義します。

2. アプリケーションに接続する場合は、アプリ登録サービス プリンシパルを閲覧者、Azure Event Hub データ レシーバーとして追加します (これは、リソース グループまたはサブスクリプション レベルでも実行できます)。

    **[Event hubs 名前空間] > [アクセス制御 (IAM)] > [****ロールの割り当て**] で追加と確認を行います。

## <a name="enable-raw-data-streaming"></a>生データ ストリーミングを有効にする

1. ***Global Administrator** _ または _*_Security Administrator_** として <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>にログインします。

2. [[ストリーミング API の設定] ページ](https://security.microsoft.com/settings/mtp_settings/raw_data_export)に移動します。

3. [**追加**] をクリックします。

4. 新しい設定の名前を選択します。

5. [ **Azure Event Hub にイベントを転送する]** を選択します。

6. イベント データを 1 つの Event Hub にエクスポートするか、Event Hub 名前空間内の別のイベント ハブに各イベント テーブルをエクスポートするかを選択できます。

7. イベント データを 1 つの Event Hub にエクスポートするには、 **Event Hub 名** と **Event Hub リソース ID を** 入力します。

   **Event Hub リソース ID を** 取得するには、**AzureProperties** [タブの Azure](https://ms.portal.azure.com/) Event Hub 名前空間ページに > 移動>**、リソース ID** の下にテキストをコピーします。

   :::image type="content" source="../defender-endpoint/images/event-hub-resource-id.png" alt-text="Event Hub リソース ID" lightbox="../defender-endpoint/images/event-hub-resource-id.png":::

8. [イベント ストリーミング API でサポートされているMicrosoft 365 Defender イベントの種類に](supported-event-types.md)移動し、Microsoft 365 Streaming API のイベントの種類のサポート状態を確認します。

9. ストリーミングするイベントを選択し、[ **保存]** をクリックします。

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

- Azure Event Hub の各 Event Hub メッセージには、レコードの一覧が含まれています。

- 各レコードには、イベント名、イベントMicrosoft 365 Defender受信した時刻、それが属するテナント (テナントからイベントのみを取得します)、"**properties**" というプロパティの JSON 形式のイベントが含まれます。

- Microsoft 365 Defender イベントのスキーマの詳細については、「[高度なハンティングの概要](advanced-hunting-overview.md)」を参照してください。

- Advanced Hunting では、 **DeviceInfo** テーブルには、デバイスのグループを含む **MachineGroup** という名前の列があります。 ここでは、すべてのイベントもこの列で装飾されます。

## <a name="data-types-mapping"></a>データ型のマッピング

イベント プロパティのデータ型を取得するには、次の操作を行います。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にログインし、[[高度なハンティング] ページ](https://security.microsoft.com/hunting-package)に移動します。

2. 次のクエリを実行して、各イベントのデータ型マッピングを取得します。

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Device Info イベントの例を次に示します。

  :::image type="content" source="../defender-endpoint/images/machine-info-datatype-example.png" alt-text="デバイス情報のクエリの例" lightbox="../defender-endpoint/images/machine-info-datatype-example.png":::

## <a name="related-topics"></a>関連項目

- [高度なハンティングの概要](advanced-hunting-overview.md)
- [Microsoft 365 Defender ストリーミング API](streaming-api.md)
- [イベント ストリーミング API でサポートされているMicrosoft 365 Defenderイベントの種類](supported-event-types.md)
- [Microsoft 365 Defender イベントを Azure ストレージ アカウントにストリーミングする](streaming-api-storage.md)
- [Azure Event Hub のドキュメント](/azure/event-hubs/)
- [接続の問題のトラブルシューティング - Azure Event Hub](/azure/event-hubs/troubleshooting-guide)
