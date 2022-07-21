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
ms.openlocfilehash: 1a9e899c1f3292dd0a665c7cbf7ccfd5e561c2aa
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66943298"
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

## <a name="prerequisites"></a>前提条件

1. Corelight データ統合を設定するには、ユーザーに次のロールが必要です。
   - Azure Active Directory のテナント グローバル管理者
   - Microsoft Defender for IoT 統合に使用される Azure サブスクリプションのセキュリティ管理者
2. オンボードされた Defender for IoT プラン。 詳細については、「Microsoft Defender for Endpointを[使用した Microsoft Defender for IoT のオンボード](enable-microsoft-defender-for-iot-integration.md)」を参照してください。

## <a name="enabling-the-corelight-integration"></a>Corelight 統合を有効にする

Corelight 統合を有効にするには、次の手順を実行する必要があります。

[手順 1: Corelight をデータ ソースとして有効にする](#step-1-turn-on-corelight-as-a-data-source)<br>
[手順 2: Corelight がMicrosoft 365 Defenderにイベントを送信するためのアクセス許可を指定する](#step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender)<br>
[手順 3: データをMicrosoft 365 Defenderに送信するように Corelight アプライアンスを構成する](#step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender)

### <a name="step-1-turn-on-corelight-as-a-data-source"></a>手順 1: Corelight をデータ ソースとして有効にする

1. ポータルの [https://security.microsoft.com](https://security.microsoft.com/)ナビゲーション ウィンドウで、[**デバイス検出** \> **データ ソース** の **設定]** \> を選択します。

   :::image type="content" source="../../media/defender-endpoint/enable-corelight.png" alt-text="Microsoft 365 Defender ポータルの [データ ソース] ページ" lightbox="../../media/defender-endpoint/enable-corelight.png":::

2. [ **Corelight データを M365D に送信** ] を選択し、[ **保存]** を選択します。

### <a name="step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender"></a>手順 2: Corelight がMicrosoft 365 Defenderにイベントを送信するためのアクセス許可を指定する

> [!NOTE]
> 組織内のリソースにアクセスするためのアクセス許可を Corelight に付与するには、グローバル管理者である必要があります。

1. テナント グローバル管理者として、この [リンク](<https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=d8be544e-9d1a-4825-a5cb-fb447457f692&response_type=code&sso_reload=true>) にアクセスしてアクセス許可を付与します。
2. ポータルに移動し [https://security.microsoft.com](https://security.microsoft.com/)、[**設定]** \> **Microsoft 365 Defender** を選択し、**テナント ID** を書き留めます。 Corelight アプライアンスを構成するときは、この情報が必要です。

### <a name="step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender"></a>手順 3: データをMicrosoft 365 Defenderに送信するように Corelight アプライアンスを構成する

> [!NOTE]
> この統合は、Corelight Sensor ソフトウェア v25 以降で利用できます。
> 
> ソリューションを機能させるには、センサーが Defender クラウド サービスと Corelight クラウド サービスの両方に到達するには、インターネット接続が必要です。

#### <a name="enable-the-integration-in-the-corelight-web-interface"></a>Corelight Web インターフェイスで統合を有効にする

1. Corelight Web インターフェイスで、 **センサー** \> **のエクスポート** に移動します。

   :::image type="content" source="images/exporttodefender.png" alt-text="kafka エクスポート" lightbox="images/exporttodefender.png":::

2. **Microsoft Defender へのエクスポートを** 有効にします。
3. Microsoft 356 Defender テナント ID を入力します。
4. 必要に応じて、次のことも行えます。
    - **Zeek ログを除外に設定します**。 含める必要があるログの最小セットは、dns、conn、files、http、ssl、ssh、x509、snmp、smtp、ftp、sip、dhcp、および通知です。
    - **Microsoft Defender ログ フィルター** を作成することを選択します。
5. **[Apply Changes]\(変更の適用\)** を選択します。

#### <a name="enable-the-integration-in-the-corelight-client"></a>corelight-client で統合を有効にする

1. corelight-client で次のコマンドを使用して **Microsoft Defender へのエクスポート** を有効にします。

    ``` command
    corelight-client configuration update \
    --bro.export.defender.enable True
    ```

2. テナント ID を設定する

3. 必要に応じて、次のコマンドを使用して特定のログを除外したり、Microsoft Defender ログ フィルターを作成したりできます。 含める必要があるログの最小セットは、dns、conn、files、http、ssl、ssh、x509、snmp、smtp、ftp、sip、dhcp、および通知です。

   ``` command
     corelight-client configuration update \
    --bro.export.defender.exclude=<logs_to_exclude> \
    --bro.export.defender.filter=<logs_to_filter>
   ```

## <a name="see-also"></a>関連項目

- [デバイス検出に関する FAQ](device-discovery-faq.md)
