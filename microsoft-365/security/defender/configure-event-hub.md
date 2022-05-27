---
title: Event Hubs を構成する
description: Event Hubs を構成する方法について説明します
keywords: イベント ハブ、構成、分析情報
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
MS.technology: mde
ms.openlocfilehash: 569f51eda2f2ee61286c661548fe73e793928294
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65754844"
---
# <a name="configure-your-event-hubs"></a>Event Hubs を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft 365 Defenderからイベントを取り込むことができるように Event Hubs を構成する方法について説明します。

## <a name="set-up-the-required-resource-provider-in-the-event-hubs-subscription"></a>Event Hubs サブスクリプションで必要なリソース プロバイダーを設定する

1. [Azure portal](https://portal.azure.com)にサインインします。
1. **[サブスクリプションの** > **選択] { イベント ハブを }** > **リソース プロバイダー** にデプロイするサブスクリプションを選択します。
1. **Microsoft.インサイト** かどうかを確認するプロバイダーが登録されています。 それ以外の場合は、登録します。

:::image type="content" source="../../media/f893db7a7b1f7aa520e8b9257cc72562.png" alt-text="Microsoft Azure ポータルの [サービス プロバイダー] ページの一覧" lightbox="../../media/f893db7a7b1f7aa520e8b9257cc72562.png":::

## <a name="set-up-azure-active-directory-app-registration"></a>アプリの登録Azure Active Directory設定する

> [!NOTE]
> 管理者以外のユーザーがアプリを登録できるようにするには、管理者ロールまたはAzure Active Directory (AAD) を設定する必要があります。 サービス プリンシパルにロールを割り当てるには、所有者またはユーザー アクセス管理者ロールも必要です。 詳細については、「[ポータルで Azure AD アプリ & サービス プリンシパルを作成する - Microsoft Docs Microsoft ID プラットフォーム\|](/azure/active-directory/develop/howto-create-service-principal-portal)」を参照してください。

1. Azure Active Directory アプリの登録新しい登録 **で**\>新しい登録 (本質的にサービス プリンシパルを作成する) **を** \> **作成します。**

1. 名前だけでフォームに入力します (リダイレクト URI は必要ありません)。

    :::image type="content" source="../../media/336bc84e6be23900c43232b4ef0c253c.png" alt-text="Microsoft Azure ポータルのアプリケーション名表示セクション" lightbox="../../media/336bc84e6be23900c43232b4ef0c253c.png":::


    :::image type="content" source="../../media/06ac04c4ff713c2065cec2ef2f99a294.png" alt-text="Microsoft Azure ポータルの [概要情報] セクション" lightbox="../../media/06ac04c4ff713c2065cec2ef2f99a294.png":::

1. [証明書] &シークレットの **[新しいクライアント シークレット**] をクリックして **シークレットを**\>作成します。

    :::image type="content" source="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png" alt-text="Microsoft Azure ポータルの [クライアント シークレット] セクション" lightbox="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png":::

このクライアント シークレット値は、登録されているこのアプリケーションを認証するために Microsoft Graph API によって使用されます。

> [!WARNING]
> **クライアント シークレットに再度アクセスすることはできないため、必ず保存してください**。

## <a name="set-up-event-hubs-namespace"></a>Event Hubs 名前空間を設定する

1. Event Hubs 名前空間を作成します。

    **Event Hub \> Add に** 移動し、予想される負荷に適した価格レベル、スループット ユニット、自動インフレ (標準価格と機能が必要) を選択します。 詳細については、「[価格 - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/pricing/details/event-hubs/)」を参照してください。

    > [!NOTE]
    > 既存のイベント ハブを使用できますが、スループットとスケーリングは名前空間レベルで設定されるため、イベント ハブを独自の名前空間に配置することをお勧めします。

   :::image type="content" source="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png" alt-text="Microsoft Azure ポータルの Event Hubs セクション" lightbox="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png":::

1. この Event Hubs 名前空間のリソース ID も必要です。 Azure Event Hubs名前空間ページ\>のプロパティに移動します。 リソース ID の下にテキストをコピーし、以下のMicrosoft 365構成セクションで使用するために記録します。

    :::image type="content" source="../../media/759498162a4e93cbf17c4130d704d164.png" alt-text="Microsoft Azure ポータルのイベント ハブのプロパティ セクション" lightbox="../../media/759498162a4e93cbf17c4130d704d164.png":::

### <a name="add-permissions"></a>アクセス許可を追加する

Event Hubs データ管理に関連するエンティティに、次のロールにアクセス許可を追加する必要があります。

- **共同作成者**: このロールに関連するアクセス許可は、Microsoft 365 Defender ポータルにログインするエンティティに追加されます。
- **閲覧者** と **Azure Event Hub データ レシーバー**: これらのロールに関連するアクセス許可は、**サービス プリンシパル** のロールが既に割り当てられているエンティティに割り当てられ、Azure Active Directory アプリケーションにログインします。

これらのロールが確実に追加されるようにするには、次の手順に従います。

**Event Hub 名前空間** \> **Access Control (IAM)** \> に移動し、[**ロールの割り当て**] で **追加** して確認します。

:::image type="content" source="../../media/9c9c29137b90d5858920202d87680d16.png" alt-text="Microsoft Azure ポータルのアプリケーション登録サービス プリンシパル セクション" lightbox="../../media/9c9c29137b90d5858920202d87680d16.png":::

## <a name="set-up-event-hubs"></a>Event Hubs を設定する

**オプション 1:**

名前空間内に Event Hubs を作成できます。エクスポートするために選択 **したすべての** イベントの種類 (テーブル) は、この **1 つの** Event Hub に書き込まれます。

**オプション 2:**

すべてのイベントの種類 (テーブル) を 1 つのイベント ハブにエクスポートする代わりに、Event Hubs 名前空間内の異なる Event Hubs に各テーブルをエクスポートできます (イベントの種類ごとに 1 つの Event Hub)。

このオプションでは、Microsoft 365 Defenderが Event Hubs を作成します。

> [!NOTE]
> Event Hub クラスターの一部 **ではない** Event Hub 名前空間を使用している場合は、Event Hub 名前空間あたり 10 イベント ハブの Azure 制限があるため、定義した各エクスポート 設定でエクスポートするイベントの種類 (テーブル) を最大 10 個まで選択できます。

次に例を示します。

:::image type="content" source="../../media/005c1f6c10c34420d387f594987f9ffe.png" alt-text="Microsoft Azure ポータルのイベント ハブ セクション" lightbox="../../media/005c1f6c10c34420d387f594987f9ffe.png":::

このオプションを選択した場合は、[[電子メール テーブルを送信するMicrosoft 365 Defenderの構成] セクションに](#configure-microsoft-365-defender-to-send-email-tables)進むことができます。

Event Hub + Event Hub を選択して、名前空間内 **に Event Hubs** \> を作成 **します**。

パーティション数を使用すると、並列処理によるスループットの増加が可能になるため、予想される負荷に基づいてこの数を増やすことをお勧めします。 既定のメッセージの保持期間とキャプチャの値は 1 とオフにすることをお勧めします。

:::image type="content" source="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png" alt-text="Microsoft Azure ポータルのイベント ハブ作成セクション" lightbox="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png":::

これらの Event Hubs (名前空間ではない) の場合は、要求の送信、リッスンを使用して共有アクセス ポリシーを構成する必要があります。 **Event Hub** \> **共有アクセス ポリシー** \> **と追加** をクリックし、ポリシー名 (他の場所では使用されません) を指定して **、[送信** と **リッスン**] をオンにします。

:::image type="content" source="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png" alt-text="Microsoft Azure ポータルの [共有アクセス ポリシー] ページ" lightbox="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png":::

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>電子メール テーブルを送信するようにMicrosoft 365 Defenderを構成する

### <a name="set-up-microsoft-365-defender-send-email-tables-to-splunk-via-event-hubs"></a>Event Hubs を使用してメール テーブルを Splunk に送信Microsoft 365 Defender設定する

1. 次のすべてのロール要件を満たすアカウントで<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にサインインします。

    - エクスポート先の Event Hubs の Event Hubs *名前空間* リソース レベル以上の共同作成者ロール。 このアクセス許可がない場合、設定を保存しようとするとエクスポート エラーが発生します。

    - Microsoft 365 Defenderと Azure に関連付けられているテナントのグローバル 管理ロールまたはセキュリティ 管理 ロール。

      :::image type="content" source="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png" alt-text="Microsoft 365 Defender ポータルの [設定] ページ" lightbox="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png":::

1. **[未加工データのエクスポート\>] + [追加]** をクリックします。

    これで、上記で記録したデータを使用します。

    **名前**: この値はローカルであり、環境内で動作するものは何でも指定する必要があります。

    **イベント ハブにイベントを転送する**: このチェック ボックスをオンにします。

    **Event-Hub リソース ID**: この値は、Event Hubs のセットアップ時に記録した Event Hubs 名前空間リソース ID です。

    **Event-Hub 名**: Event Hubs 名前空間内に Event Hubs を作成した場合は、上記で記録した Event Hubs 名を貼り付けます。

    Microsoft 365 Defenderがイベントの種類 (テーブル) ごとに Event Hubs を作成できるようにする場合は、このフィールドは空のままにします。

    **イベントの種類: Event** Hubs に転送し、カスタム アプリに転送する高度なハンティング テーブルを選択します。 アラート テーブルはMicrosoft 365 Defenderから、デバイス テーブルはMicrosoft Defender for Endpoint (EDR)、電子メール テーブルはMicrosoft Defender for Office 365から取得されます。 電子メール イベントでは、すべての電子メール トランザクションが記録されます。 URL (セーフ リンク)、添付ファイル (セーフ添付ファイル)、および配信後イベント (ZAP) も記録され、NetworkMessageId フィールドの電子メール イベントに参加できます。

    :::image type="content" source="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png" alt-text="Microsoft Azure ポータルの [ストリーミング API の設定] ページ" lightbox="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png":::

1. [ **送信**] をクリックしてください。

### <a name="verify-that-the-events-are-being-exported-to-the-event-hubs"></a>イベントが Event Hubs にエクスポートされていることを確認する

基本的な高度なハンティング クエリを実行して、イベントが Event Hubs に送信されていることを確認できます。 [ **ハンティング** \> **の詳細な検索** \> **クエリ]** を選択し、次のクエリを入力します。

```console
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

このクエリでは、他のすべてのテーブルで結合された過去 1 時間に受信したメールの数が表示されます。 また、イベント ハブにエクスポートできるイベントが表示される場合も表示されます。 このカウントに 0 が表示されている場合、Event Hubs に送信されるデータは表示されません。

:::image type="content" source="../../media/c305e57dc6f72fa9eb035943f244738e.png" alt-text="Microsoft Azure ポータルの高度なハンティング ページ" lightbox="../../media/c305e57dc6f72fa9eb035943f244738e.png":::

エクスポートするデータがあることを確認したら、Event Hubs ページを表示して、メッセージが受信していることを確認できます。 このプロセスには最大 1 時間かかる場合があります。

1. Azure で、Event Hub に移動し、**Event Hub** \> の **名前空間** \> **イベント ハブ**\>をクリック **します。**
1. [ **概要**] で下にスクロールし、[メッセージ] グラフに [受信メッセージ] が表示されます。 結果が表示されない場合は、カスタム アプリが取り込むメッセージはありません。

:::image type="content" source="../../media/e88060e315d76e74269a3fc866df047f.png" alt-text="Microsoft 365 Azure portalの [概要] ページ" lightbox="../../media/e88060e315d76e74269a3fc866df047f.png":::
