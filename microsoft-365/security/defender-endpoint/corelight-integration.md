---
title: Microsoft Defender for Endpoint で Corelight 統合を有効にする
description: Corelight 統合を有効にして、MDE が展開されていないネットワークの領域で IoT/OT デバイスに焦点を当てた可視性を得る
keywords: SIEM コネクタ、SIEM、コネクタ、セキュリティ情報、イベントを有効にする
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
ms.openlocfilehash: 51762f9a2273817f926a55f8fef630cbfd7d2df1
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61372518"
---
# <a name="enable-corelight-data-integration"></a>Corelight データ統合

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft は、業界をリードするオープン ネットワーク検出および応答 (NDR) プラットフォームのプロバイダーである [Corelight](https://corelight.com/integrations/iot-security)と提携し、組織全体で IoT/OT デバイスを検出するのに役立ちます。 Corelight ネットワーク アプライアンスから送信されるデータを使用すると、Microsoft 365 Defender は、他の管理されていないデバイスや外部ネットワークとの通信など、管理されていないデバイスのネットワーク アクティビティの可視性を高めます。

このデータ ソースを有効にすると、Corelight ネットワーク アプライアンスからのすべてのイベントがネットワーク にMicrosoft 365 Defender。 これらのアクティビティは、Microsoft Defender for Endpoint デバイス インベントリで使用できる管理されていないデバイスのタイムラインで表示できます。 詳細については、「デバイスの検出 [」を参照してください](device-discovery.md)。

## <a name="enabling-the-corelight-integration"></a>Corelight 統合の有効化

Corelight 統合を有効にするには、次の手順を実行する必要があります。

[手順 1: Corelight をデータ ソースとして有効にする](#step-1-turn-on-corelight-as-a-data-source)<br>
[手順 2: Corelight にイベントを送信するアクセス許可を付与Microsoft 365 Defender](#step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender)<br>
[手順 3: Corelight アプライアンスを構成して、データをサーバーに送信Microsoft 365 Defender](#step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender)

### <a name="step-1-turn-on-corelight-as-a-data-source"></a>手順 1: Corelight をデータ ソースとして有効にする

1. ポータルのナビゲーション ウィンドウで、[ [https://security.microsoft.com](https://security.microsoft.com/) デバイス検出データ ソース]**設定** \> **を** \> **選択します**。

    ![データ ソースのイメージ](images/enable-corelight.png)

2. [ **コアライト データを M365D に送信する] を選択し、[保存** ] を **選択します**。

### <a name="step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender"></a>手順 2: Corelight にイベントを送信するアクセス許可を付与Microsoft 365 Defender

> [!NOTE]
> 組織内のリソースにアクセスするための Corelight アクセス許可を付与するには、グローバル管理者である必要があります。

1. テナント グローバル管理者として、このリンクに移動 [してアクセス許可](<https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=d8be544e-9d1a-4825-a5cb-fb447457f692&response_type=code&sso_reload=true>) を付与します。
2. ポータルに [https://security.microsoft.com](https://security.microsoft.com/) 移動し **、[設定Microsoft 365 Defender]** \> **を** 選択し、テナント ID を **メモします**。 Corelight アプライアンスを構成する場合は、この情報が必要です。

### <a name="step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender"></a>手順 3: Corelight アプライアンスを構成して、データをサーバーに送信Microsoft 365 Defender

**適用対象**: Corelight Sensor ソフトウェア v23.2 以降

> [!NOTE]
> データの送信をサポートする以前のリリースで有効にするには、最初に次のコマンドを実行する必要があります `corelight-client configuration update --enable.adfiot 1` 。

> [!NOTE]
> ソリューションを動作するには、センサーが Defender クラウド サービスと Corelight クラウド サービスの両方に到達するためにインターネット接続が必要です。

#### <a name="enabling-in-the-corelight-sensor-gui"></a>Corelight センサー GUI での有効化

1. [Corelight Sensor GUI 構成] セクションで、[センサーのエクスポート] **を** \> **選択します**。
2. 一覧から **[EXPORT TO KAFKA]** に移動し、スイッチを選択してオンにします。

   ![kafka エクスポートのイメージ](images/exporttokafka.png)

3. 次に **、[IOT** 用 AZURE DEFENDER にエクスポート] をオンにし、[テナント ID] フィールドに手順 1 で説明されているテナント ID を入力します。

   ![iot エクスポートのイメージ](images/exporttodiot.png)

4. **[Apply Changes]\(変更の適用\)** を選択します。

   ![イメージの適用 ](images/corelightapply.png)

> [!NOTE]
> Kafka の構成オプション (ログの除外とフィルターを除く) は変更できません。 行われた変更は無視されます。

#### <a name="enabling-in-the-corelight-client"></a>corelight-client での有効化

コアライト クライアントで次のコマンドを使用して **、KAFKA** へのエクスポートと **IOT** 用 AZURE DEFENDER へのエクスポートを有効にできます。

`corelight-client configuration update --bro.export.kafka.defender.enable true --bro.export.kafka.defender.tenant\_id <your tenant>`.

> [!IMPORTANT]
> Kafka エクスポートを既に使用している場合は、別の構成について Corelight サポートに問い合わせください。

最小限のログ セットの送信のみを構成するには、次の手順を実行します。

1. Corelight センサー GUI で、[Kafka] セクションに移動します。
2. Zeek ログ **に移動して除外する**
3. [すべて選択 **]**
4. 次に、次のログの横にある **[x]** を選択して、Microsoft に引き続き流れる必要があります。  
    `dns  conn  files  http  ssl  ssh  x509  snmp  smtp  ftp  sip  dhcp  notice`
5. [変更 **の適用] を選択します。**

Microsoft に流れるログの一覧は、時間の流れによって拡張される可能性があります。

## <a name="see-also"></a>関連項目

- [デバイス検出に関する FAQ](device-discovery-faq.md)
