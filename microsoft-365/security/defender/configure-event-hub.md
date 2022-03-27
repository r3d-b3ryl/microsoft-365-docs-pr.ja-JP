---
title: イベント ハブを構成する
description: イベント ハブを構成する方法の詳細
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
ms.openlocfilehash: a842f9161aa823203354917326653b583e5fddb9
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754302"
---
# <a name="configure-your-event-hub"></a>イベント ハブを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

イベント ハブがイベントをデバイスから取り込むMicrosoft 365 Defender。

## <a name="set-up-the-required-resource-provider-in-the-event-hub-subscription"></a>Event Hub サブスクリプションで必要なリソース プロバイダーを設定する

1. [Azure portal](https://portal.azure.com) にサインインします。
1. [**サブスクリプション]** >  **を選択します。イベント** ハブが }Resource プロバイダーに展開されるサブスクリプション > **を選択します**。
1. **Microsoft.インサイト** プロバイダーが登録されています。 それ以外の場合は、登録します。

:::image type="content" source="../../media/f893db7a7b1f7aa520e8b9257cc72562.png" alt-text="[サービス プロバイダー] ページの一覧 (Microsoft Azureポータル)" lightbox="../../media/f893db7a7b1f7aa520e8b9257cc72562.png":::

## <a name="set-up-azure-active-directory-app-registration"></a>アプリ登録Azure Active Directory設定する

> ![メモ]管理者以外のユーザーがアプリを登録Azure Active Directory許可AAD管理者ロールまたは管理者 (AAD) を設定する必要があります。 サービス プリンシパルに役割を割り当てるには、所有者またはユーザー アクセス管理者の役割も必要です。 詳細については、「ポータルでアプリ Azure ADサービス &を作成する [- Microsoft \| Docs Microsoft ID プラットフォーム参照してください](/azure/active-directory/develop/howto-create-service-principal-portal)。

1. [アプリの登録] [新しい登録] で新しい登録 (本質的に **サービス プリンシパル**\>をAzure Active Directory **作成** \> **します。**

1. [名前] だけでフォームに入力します (リダイレクト URI は必要ありません)。

    :::image type="content" source="../../media/336bc84e6be23900c43232b4ef0c253c.png" alt-text="[アプリケーション名] ポータルの [アプリケーション名Microsoft Azure]" lightbox="../../media/336bc84e6be23900c43232b4ef0c253c.png":::


    :::image type="content" source="../../media/06ac04c4ff713c2065cec2ef2f99a294.png" alt-text="ポータルの [概要] Microsoft Azureセクション" lightbox="../../media/06ac04c4ff713c2065cec2ef2f99a294.png":::

1. [証明書] をクリックしてシークレットを作成 **&新しいクライアント** \> **シークレットを作成します**。

    :::image type="content" source="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png" alt-text="[クライアント シークレット] セクション (Microsoft Azure ポータル)" lightbox="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png":::
    

> [!WARNING]
> **クライアント シークレットに再度** アクセスできないので、必ず保存してください。

## <a name="set-up-event-hub-namespace"></a>Event Hub 名前空間のセットアップ

1. イベント ハブ名前空間を作成します。

    [**イベント ハブの追加] \>** に移動し、予想される負荷に適した価格レベル、スループット単位、自動インフレート (標準の価格と機能が必要) を選択します。 詳細については、「Pricing [- Event Hub \| Microsoft Azure](https://azure.microsoft.com/pricing/details/event-hubs/)

    > [!NOTE]
    > 既存のイベント ハブを使用できますが、スループットとスケーリングは名前空間レベルで設定され、イベント ハブを独自の名前空間に配置する必要があります。

   :::image type="content" source="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png" alt-text="[イベント ハブ] セクション (Microsoft Azure ポータル)" lightbox="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png":::

1. また、このイベント ハブ名前空間のリソース ID も必要です。 Azure Event Hub 名前空間ページの [プロパティ] に移動 \> します。 [リソース ID] の下のテキストをコピーし、以下の [構成] セクションで使用Microsoft 365記録します。

    :::image type="content" source="../../media/759498162a4e93cbf17c4130d704d164.png" alt-text="[イベント ハブのプロパティ] セクション (Microsoft Azure ポータル)" lightbox="../../media/759498162a4e93cbf17c4130d704d164.png":::


1. イベント ハブ名前空間を作成したら、App Registration Service Principal を Reader、Azure Event Hub Data Receiver、および Microsoft 365 Defender に投稿者としてログインするユーザーを追加する必要があります (リソース グループまたはサブスクリプション レベルでも実行できます)。

    この手順は、 **Event Hub 名前空間** \> **アクセス制御 (IAM)** の [役割の割り当て] \> **で** 追加および **確認します**。

    :::image type="content" source="../../media/9c9c29137b90d5858920202d87680d16.png" alt-text="ポータルのアプリケーション登録サービス プリンシパル セクションMicrosoft Azureします。" lightbox="../../media/9c9c29137b90d5858920202d87680d16.png":::

## <a name="set-up-event-hub"></a>イベント ハブのセットアップ

**オプション 1:**

名前空間内にイベント ハブを作成し、エクスポートするために選択したイベントの種類 (テーブル) はすべて、この 1 つのイベント **ハブに** 書き込まれます。

**オプション 2:**

すべてのイベントの種類 (テーブル) を 1 つのイベント ハブにエクスポートする代わりに、各テーブルをイベント ハブ名前空間内の異なるイベント ハブ (イベントの種類ごとに 1 つのイベント ハブ) にエクスポートできます。

このオプションでは、Microsoft 365 Defenderイベント ハブを作成します。

> [!NOTE]
> イベント ハブ クラスターの一部ではないイベント ハブ名前空間を使用している場合は、Azure のイベント ハブ名前空間あたり 10 イベント ハブの制限により、定義した各エクスポート 設定 でエクスポートするイベント の種類 (テーブル) を最大 10 つまで選択できます。

次に例を示します。

:::image type="content" source="../../media/005c1f6c10c34420d387f594987f9ffe.png" alt-text="ポータルのイベント ハブ セクションMicrosoft Azureします。" lightbox="../../media/005c1f6c10c34420d387f594987f9ffe.png":::

このオプションを選択した場合は、[電子メール テーブルを送信する[Microsoft 365 Defenderの構成] セクションにスキップ](#configure-microsoft-365-defender-to-send-email-tables)できます。

[イベント ハブ] + [イベント ハブ] を選択して、名前空間内に **イベント** \> **ハブを作成します**。

パーティション数を使用すると、並列処理によるスループットが増えるので、予想される負荷に基づいてこの数を増やしてください。 既定のメッセージの保持とキャプチャの値は 1 とオフをお勧めします。

:::image type="content" source="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png" alt-text="イベント ハブ作成セクション (Microsoft Azure ポータル)" lightbox="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png":::
 

これらのイベント ハブ (名前空間ではない) では、送信、リッスンクレームを使用して共有アクセス ポリシーを構成する必要があります。 [イベント ハブの **共有** \> **アクセス** \> ポリシー] **+ [** 追加] をクリックし、ポリシー名 (他の場所では使用されません) を指定し、[送信とリッスン] **を** オン **にしてください**。

:::image type="content" source="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png" alt-text="[共有アクセス ポリシー] ページ (Microsoft Azure ポータル)" lightbox="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png":::

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>電子メール Microsoft 365 Defender送信する方法を構成する

### <a name="set-up-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>イベント ハブをMicrosoft 365 Defender Splunk に電子メール テーブルを送信する方法を設定する

1. 次のすべての役割要件<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>を満たすアカウントを使用して、ログインしてアカウントにアクセスします。

    - エクスポートするイベント ハブの Event Hub *名前空間* リソース レベル以上の共同作成者ロール。 このアクセス許可がない場合は、設定を保存しようとするときにエクスポート エラーが発生します。

    - テナントのグローバル管理者またはセキュリティ管理者の役割は、Microsoft 365 Defender Azure に関連付けされます。

      :::image type="content" source="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png" alt-text="ポータル設定の [Microsoft 365 Defender] ページ" lightbox="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png":::

1. [Raw Data **Export + Add] \> をクリックします**。

    これで、上記で記録したデータを使用します。

    **名前**: この値はローカルであり、環境で動作する値である必要があります。

    **イベント をイベント ハブに転送する**: このチェック ボックスをオンにします。

    **Event-Hub リソース ID**: この値は、イベント ハブのセットアップ時に記録したイベント ハブ名前空間リソース ID です。

    **イベント ハブ名**: イベント ハブ名前空間内にイベント ハブを作成した場合は、上記で記録したイベント ハブ名を貼り付けます。

    イベント の種類 (テーブル) Microsoft 365 Defenderイベント ハブを作成する場合は、このフィールドを空のままにします。

    **イベントの種類**: イベント ハブに転送し、カスタム アプリに転送する高度なハンティング テーブルを選択します。 アラート テーブルは Microsoft 365 Defender から、デバイス テーブルは Microsoft Defender for Endpoint (EDR) から、電子メール テーブルは Microsoft Defender から提供Office 365。 電子メール イベントは、すべての電子メール トランザクションを記録します。 URL (セーフ リンク)、添付ファイル (セーフ 添付ファイル)、および配信後イベント (ZAP) も記録され、[NetworkMessageId] フィールドの [電子メール イベント] に参加できます。

    :::image type="content" source="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png" alt-text="ポータルの [ストリーミング API 設定] ページMicrosoft Azureページ" lightbox="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png":::

1. [送信] をクリック **してください**。

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>イベントがイベント ハブにエクスポートされるのを確認する

イベントがイベント ハブに送信されるのを確認するには、基本的な高度なハンティング クエリを実行します。 [ハン **ティング** \> **の高度な検索クエリ** \> **] を** 選択し、次のクエリを入力します。

```console
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

これにより、他のすべてのテーブルに参加した過去 1 時間に受信されたメールの数が表示されます。 また、イベント ハブにエクスポートできるイベントが表示される場合も表示されます。 この数に 0 が表示されている場合、イベント ハブにデータが表示されません。

:::image type="content" source="../../media/c305e57dc6f72fa9eb035943f244738e.png" alt-text="ポータルの高度なMicrosoft Azureページ" lightbox="../../media/c305e57dc6f72fa9eb035943f244738e.png":::

エクスポートするデータが確認された後、イベント ハブ ページを表示して、メッセージが受信されるのを確認できます。 これには最大 1 時間かかる場合があります。

1. Azure で、[イベント ハブ] [名前空間イベント  \> \> **ハブ**\>] [イベント **ハブ] の** [クリック] に **移動します**。
1. [ **概要]** で下にスクロールし、[メッセージ] グラフに [受信メッセージ] と表示されます。 結果が表示されていない場合、カスタム アプリが取り込むメッセージは表示されません。

:::image type="content" source="../../media/e88060e315d76e74269a3fc866df047f.png" alt-text="Azure portal の [概要] Microsoft 365ページ" lightbox="../../media/e88060e315d76e74269a3fc866df047f.png":::
