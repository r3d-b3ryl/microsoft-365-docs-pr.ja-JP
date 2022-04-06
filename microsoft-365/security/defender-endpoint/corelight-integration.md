---
title: Microsoft Defender for Endpointで Corelight 統合を有効にする
description: Corelight 統合を有効にして、MDE がデプロイされていないネットワークの領域で IoT/OT デバイスに焦点を当てた可視性を得る
keywords: siem コネクタ、siem、コネクタ、セキュリティ情報、イベントを有効にする
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bf3095b9178b4ff2e71d4ee5f652d9316f233746
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664592"
---
# <a name="enable-corelight-data-integration"></a>Corelight データ統合

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft は、業界をリードするオープン ネットワーク検出および応答 (NDR) プラットフォームのプロバイダーである [Corelight](https://corelight.com/integrations/iot-security) と提携し、組織全体の IoT/OT デバイスの検出を支援しています。 Corelight ネットワーク アプライアンスから送信されたデータを使用Microsoft 365 Defender、他の非管理対象デバイスや外部ネットワークとの通信など、アンマネージド デバイスのネットワーク アクティビティの可視性が向上します。

このデータ ソースを有効にすると、Corelight ネットワーク アプライアンスのすべてのイベントがMicrosoft 365 Defenderに送信されます。 これらのアクティビティは、Microsoft Defender for Endpointデバイス インベントリで利用できるアンマネージド デバイスタイムラインで確認できます。 詳細については、「 [デバイスの検出」を](device-discovery.md)参照してください。

## <a name="enabling-the-corelight-integration"></a>Corelight 統合を有効にする

Corelight 統合を有効にするには、次の手順を実行する必要があります。

[手順 1: Corelight をデータ ソースとして有効にする](#step-1-turn-on-corelight-as-a-data-source)<br>
[手順 2: Corelight がMicrosoft 365 Defenderにイベントを送信するためのアクセス許可を指定する](#step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender)<br>
[手順 3: データをMicrosoft 365 Defenderに送信するように Corelight アプライアンスを構成する](#step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender)

### <a name="step-1-turn-on-corelight-as-a-data-source"></a>手順 1: Corelight をデータ ソースとして有効にする

1. ポータルの [https://security.microsoft.com](https://security.microsoft.com/)ナビゲーション ウィンドウで、**デバイス検出** \> **データ ソース****設定**\>選択します。

   :::image type="content" source="images/enable-corelight.png" alt-text="Microsoft 365 Defender ポータルの [データ ソース] ページ" lightbox="images/enable-corelight.png":::

2. [ **Corelight データを M365D に送信** ] を選択し、[ **保存]** を選択します。

### <a name="step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender"></a>手順 2: Corelight がMicrosoft 365 Defenderにイベントを送信するためのアクセス許可を指定する

> [!NOTE]
> 組織内のリソースにアクセスするためのアクセス許可を Corelight に付与するには、グローバル管理者である必要があります。

1. テナント グローバル管理者として、この [リンク](<https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=d8be544e-9d1a-4825-a5cb-fb447457f692&response_type=code&sso_reload=true>) にアクセスしてアクセス許可を付与します。
2. ポータルに移動し [https://security.microsoft.com](https://security.microsoft.com/)、**設定 Microsoft 365 Defender**\>を選択し、**テナント ID** をメモします。 Corelight アプライアンスを構成するときは、この情報が必要です。

### <a name="step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender"></a>手順 3: データをMicrosoft 365 Defenderに送信するように Corelight アプライアンスを構成する

> [!NOTE]
>  この統合は、Corelight Sensor ソフトウェア v24 以降で公開されます。 

v23 または v22.1 でプレビューするには、GUI で構成セクションを有効にするために実行 `corelight-client configuration update --enable.adfiot 1` する必要があります。

これに加えて、GUI 検証では、ブローカーがすべての v23 リリースの構成セクションで構成されている必要があります。  指定したブローカーは必須ですが、実際には使用されません。 次の手順に従ってMicrosoft 365 Defenderにデータを送信できるようにする前に _、kafka ブローカー_ フィールドに入力`127.0.0.1:1234`して検証を成功させます。

> [!NOTE]
> ソリューションを機能させるには、センサーが Defender クラウド サービスと Corelight クラウド サービスの両方に到達するには、インターネット接続が必要です。

#### <a name="enabling-in-the-corelight-sensor-gui"></a>Corelight センサー GUI での有効化

1. [Corelight Sensor GUI の構成] セクションで、[ **センサー** \> **のエクスポート**] を選択します。
2. 一覧から **[KAFKA にエクスポート] に** 移動し、スイッチを選択してオンにします。

   :::image type="content" source="images/exporttokafka.png" alt-text="kafka エクスポート" lightbox="images/exporttokafka.png":::

3. 次 **に、AZURE DEFENDER FOR IOT へのエクスポートを** 有効にし、手順 1 で説明されているテナント ID を [TENANT ID] フィールドに入力します。

   :::image type="content" source="images/exporttodiot.png" alt-text="iot エクスポート" lightbox="images/exporttodiot.png":::

4. **[Apply Changes]\(変更の適用\)** を選択します。

   :::image type="content" source="images/corelightapply.png" alt-text="[変更の適用] アイコン" lightbox="images/corelightapply.png":::

> [!NOTE]
> Kafka の構成オプション (ログの除外とフィルターを除く) は変更しないでください。 加えられた変更は無視されます。

#### <a name="enabling-in-the-corelight-client"></a>corelight-client での有効化

CORElight-client で次のコマンドを使用して **、KAFKA へのエクスポート** と **AZURE DEFENDER FOR IOT へのエクスポート** を有効にすることができます。

`corelight-client configuration update --bro.export.kafka.defender.enable true --bro.export.kafka.defender.tenant\_id <your tenant>`.

> [!IMPORTANT]
> Kafka エクスポートを既に使用している場合は、Corelight サポートに連絡して別の構成を行います。

最小限のログセットのみを送信するように構成するには:

1. Corelight Sensor GUI で、Kafka セクションに移動します。
2. 除外する **Zeek ログに移動する**
3. **すべて** 選択
4. 次に、次のログの横にある **[x** ] を選択して、Microsoft に引き続きフローされるようにします。  
    `dns  conn  files  http  ssl  ssh  x509  snmp  smtp  ftp  sip  dhcp  notice`
5. **[変更の適用**] を選択する

Microsoft にフローするログの一覧は、時間の経過と共に拡張される可能性があります。

## <a name="see-also"></a>関連項目

- [デバイス検出に関する FAQ](device-discovery-faq.md)
