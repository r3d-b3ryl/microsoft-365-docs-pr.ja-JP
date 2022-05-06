---
title: Event Hub を構成する
description: Event Hub を構成する方法について説明します
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
ms.openlocfilehash: 40211d37b8b036f93b826a383d9d0aa87f44fc68
ms.sourcegitcommit: 292de1a7e5ecc2e9e6187126aebba6d3b9416dff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2022
ms.locfileid: "65243076"
---
# <a name="configure-your-event-hub"></a>Event Hub を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft 365 Defenderからイベントを取り込むことができるように Event Hub を構成する方法について説明します。

## <a name="set-up-the-required-resource-provider-in-the-event-hub-subscription"></a>Event Hub サブスクリプションで必要なリソース プロバイダーを設定する

1. [Azure portal](https://portal.azure.com)にサインインします。
1. **[サブスクリプションの** > **選択] { イベント ハブを }** > **リソース プロバイダー** にデプロイするサブスクリプションを選択します。
1. **Microsoft.インサイト** を確認するプロバイダーが登録されています。 それ以外の場合は、登録します。

:::image type="content" source="../../media/f893db7a7b1f7aa520e8b9257cc72562.png" alt-text="Microsoft Azure ポータルの [サービス プロバイダー] ページの一覧" lightbox="../../media/f893db7a7b1f7aa520e8b9257cc72562.png":::

## <a name="set-up-azure-active-directory-app-registration"></a>アプリの登録Azure Active Directory設定する

> ![注]管理者以外のユーザーがアプリを登録できるようにするには、管理者ロールまたはAzure Active Directory (AAD) を設定する必要があります。 サービス プリンシパルにロールを割り当てるには、所有者またはユーザー アクセス管理者ロールも必要です。 詳細については、「[ポータルでAzure AD アプリ & サービス プリンシパルを作成する - Microsoft Docs Microsoft ID プラットフォーム\|](/azure/active-directory/develop/howto-create-service-principal-portal)する」を参照してください。

1. Azure Active Directory アプリの登録新しい登録 **で**\>新しい登録 (本質的にサービス プリンシパルを作成する) **を** \> **作成します。**

1. 名前だけでフォームに入力します (リダイレクト URI は必要ありません)。

    :::image type="content" source="../../media/336bc84e6be23900c43232b4ef0c253c.png" alt-text="Microsoft Azure ポータルのアプリケーション名表示セクション" lightbox="../../media/336bc84e6be23900c43232b4ef0c253c.png":::


    :::image type="content" source="../../media/06ac04c4ff713c2065cec2ef2f99a294.png" alt-text="Microsoft Azure ポータルの [概要情報] セクション" lightbox="../../media/06ac04c4ff713c2065cec2ef2f99a294.png":::

1. [証明書] &シークレットの **[新しいクライアント シークレット**] をクリックして **シークレットを**\>作成します。

    :::image type="content" source="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png" alt-text="Microsoft Azure ポータルの [クライアント シークレット] セクション" lightbox="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png":::
    

> [!WARNING]
> **クライアント シークレットに再度アクセスすることはできないため、必ず保存してください**。

## <a name="set-up-event-hub-namespace"></a>Event Hub 名前空間を設定する

1. Event Hub 名前空間を作成する:

    **Event Hub \> Add に** 移動し、予想される負荷に適した価格レベル、スループット ユニット、および Auto-Inflate (標準の価格と機能が必要) を選択します。 詳細については、「[価格 - Event Hub \| Microsoft Azure](https://azure.microsoft.com/pricing/details/event-hubs/)」を参照してください。

    > [!NOTE]
    > 既存のイベント ハブを使用できますが、スループットとスケーリングは名前空間レベルで設定されるため、イベント ハブを独自の名前空間に配置することをお勧めします。

   :::image type="content" source="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png" alt-text="Microsoft Azure ポータルの Event Hubs セクション" lightbox="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png":::

1. この Event Hub 名前空間のリソース ID も必要です。 Azure Event Hub 名前空間ページの [プロパティ] に \> 移動します。 リソース ID の下にテキストをコピーし、以下のMicrosoft 365構成セクションで使用するために記録します。

    :::image type="content" source="../../media/759498162a4e93cbf17c4130d704d164.png" alt-text="Microsoft Azure ポータルのイベント ハブのプロパティ セクション" lightbox="../../media/759498162a4e93cbf17c4130d704d164.png":::


1. Event Hub 名前空間を作成したら、アプリ登録サービス プリンシパルを閲覧者、Azure Event Hubs データ レシーバー、および共同作成者としてMicrosoft 365 Defenderにログインするユーザーを追加する必要があります (リソース グループまたはサブスクリプション レベルでこれを行うこともできます)。

    この手順は **、Event Hub 名前空間** \> **Access Control (IAM)** \> の [**ロールの割り当て****] で追加** および確認します。

    :::image type="content" source="../../media/9c9c29137b90d5858920202d87680d16.png" alt-text="Microsoft Azure ポータルのアプリケーション登録サービス プリンシパル セクション" lightbox="../../media/9c9c29137b90d5858920202d87680d16.png":::

## <a name="set-up-event-hub"></a>Event Hub を設定する

**オプション 1:**

名前空間内に Event Hub を作成すると、エクスポートするために選択 **したすべての** イベントの種類 (テーブル) がこの **1 つの** Event Hub に書き込まれます。

**オプション 2:**

すべてのイベントの種類 (テーブル) を 1 つのイベント ハブにエクスポートする代わりに、Event Hub 名前空間内の異なる Event Hub に各テーブルをエクスポートできます (イベントの種類ごとに 1 つのイベント ハブ)。

このオプションでは、Microsoft 365 Defenderが Event Hub を作成します。

> [!NOTE]
> Event Hub クラスターの一部 **ではない** Event Hub 名前空間を使用している場合は、Event Hub 名前空間あたり 10 イベント ハブの Azure 制限があるため、定義した各エクスポート 設定でエクスポートするイベントの種類 (テーブル) を最大 10 個まで選択できます。

次に、例を示します。

:::image type="content" source="../../media/005c1f6c10c34420d387f594987f9ffe.png" alt-text="Microsoft Azure ポータルのイベント ハブ セクション" lightbox="../../media/005c1f6c10c34420d387f594987f9ffe.png":::

このオプションを選択した場合は、[[電子メール テーブルを送信するMicrosoft 365 Defenderの構成] セクションに](#configure-microsoft-365-defender-to-send-email-tables)進むことができます。

Event Hub + Event Hub を選択して、名前空間内 **に Event Hub** \> を作成 **します**。

パーティション数を使用すると、並列処理によるスループットの増加が可能になるため、予想される負荷に基づいてこの数を増やすことをお勧めします。 既定のメッセージの保持期間とキャプチャの値は 1 とオフにすることをお勧めします。

:::image type="content" source="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png" alt-text="Microsoft Azure ポータルのイベント ハブ作成セクション" lightbox="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png":::
 

これらの Event Hub (名前空間ではない) の場合は、要求の送信、リッスンを使用して共有アクセス ポリシーを構成する必要があります。 **Event Hub** \> **共有アクセス ポリシー** \> **と追加** をクリックし、ポリシー名 (他の場所では使用されません) を指定して **、[送信** と **リッスン**] をオンにします。

:::image type="content" source="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png" alt-text="Microsoft Azure ポータルの [共有アクセス ポリシー] ページ" lightbox="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png":::

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>電子メール テーブルを送信するようにMicrosoft 365 Defenderを構成する

### <a name="set-up-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Event Hub を使用してメール テーブルを Splunk に送信Microsoft 365 Defender設定する

1. 次のすべてのロール要件を満たすアカウントで<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にログインします。

    - エクスポート先の Event Hub の Event Hub *名前空間* リソース レベル以上の共同作成者ロール。 このアクセス許可がないと、設定を保存しようとするとエクスポート エラーが発生します。

    - Microsoft 365 Defenderと Azure に関連付けられているテナントのグローバル管理者ロールまたはセキュリティ管理者ロール。

      :::image type="content" source="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png" alt-text="Microsoft 365 Defender ポータルの [設定] ページ" lightbox="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png":::

1. **[未加工データのエクスポート\>] + [追加]** をクリックします。

    これで、上記で記録したデータが使用されます。

    **名前**: この値はローカルであり、環境内で動作するものは何でも指定する必要があります。

    **イベント ハブにイベントを転送する**: このチェック ボックスをオンにします。

    **Event-Hub リソース ID**: この値は、Event Hub のセットアップ時に記録した Event Hub 名前空間リソース ID です。

    **Event-Hub 名**: Event Hub 名前空間内に Event Hub を作成した場合は、上記で記録した Event Hub 名を貼り付けます。

    イベントの種類 (テーブル) ごとに Event Hub を作成するMicrosoft 365 Defenderを許可する場合は、このフィールドは空のままにします。

    **イベントの種類: Event** Hub に転送し、カスタム アプリに転送する高度なハンティング テーブルを選択します。 アラート テーブルはMicrosoft 365 Defenderから、デバイス テーブルはMicrosoft Defender for Endpoint (EDR)、電子メール テーブルはMicrosoft Defender for Office 365から取得されます。 電子メール イベントでは、すべての電子メール トランザクションが記録されます。 URL (セーフ リンク)、添付ファイル (セーフ添付ファイル)、および配信後イベント (ZAP) も記録され、NetworkMessageId フィールドの電子メール イベントに参加できます。

    :::image type="content" source="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png" alt-text="Microsoft Azure ポータルの [ストリーミング API の設定] ページ" lightbox="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png":::

1. [ **送信**] をクリックしてください。

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>イベントが Event Hub にエクスポートされていることを確認する

基本的な高度なハンティング クエリを実行して、イベントが Event Hub に送信されていることを確認できます。 [ **ハンティング** \> **の詳細な検索** \> **クエリ]** を選択し、次のクエリを入力します。

```console
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

これにより、他のすべてのテーブルに参加した過去 1 時間に受信したメールの数が表示されます。 また、イベント ハブにエクスポートできるイベントが表示される場合も表示されます。 このカウントに 0 が表示されている場合、Event Hub に出力されるデータは表示されません。

:::image type="content" source="../../media/c305e57dc6f72fa9eb035943f244738e.png" alt-text="Microsoft Azure ポータルの高度なハンティング ページ" lightbox="../../media/c305e57dc6f72fa9eb035943f244738e.png":::

エクスポートするデータがあることを確認したら、Event Hub ページを表示してメッセージが受信していることを確認できます。 これには最大 1 時間かかる場合があります。

1. Azure で、Event Hub に移動し、**Event Hub** \> の **名前空間** \> **イベント ハブ**\>をクリック **します。**
1. [ **概要**] で下にスクロールし、[メッセージ] グラフに [受信メッセージ] が表示されます。 結果が表示されない場合は、カスタム アプリが取り込むメッセージはありません。

:::image type="content" source="../../media/e88060e315d76e74269a3fc866df047f.png" alt-text="Microsoft 365 Azure portalの [概要] ページ" lightbox="../../media/e88060e315d76e74269a3fc866df047f.png":::
