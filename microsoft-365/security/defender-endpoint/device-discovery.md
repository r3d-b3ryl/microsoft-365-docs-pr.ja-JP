---
title: デバイス検出の概要
description: Microsoft 365 Defenderでエンドポイント検出を利用して、ネットワーク内のアンマネージド デバイスを見つける方法について説明します
keywords: デバイス検出, 検出, パッシブ, プロアクティブ, ネットワーク, 可視性, サーバー, ワークステーション, オンボード, アンマネージド デバイス
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: siosulli
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365-initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 53a23751fd53b05b51bf1125dcca98c23f4ba73c
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65418250"
---
# <a name="device-discovery-overview"></a>デバイス検出の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

環境を保護するには、ネットワーク内にあるデバイスのインベントリを取得する必要があります。 ただし、ネットワーク内のマッピング デバイスは、多くの場合、コストが高く、困難で、時間がかかる場合があります。

Microsoft Defender for Endpointは、余分なアプライアンスや煩雑なプロセス変更を必要とせずに、企業ネットワークに接続されているアンマネージド デバイスを見つけるのに役立つデバイス検出機能を提供します。 デバイス検出では、オンボードされたエンドポイントをネットワーク内で使用して、ネットワークを収集、プローブ、またはスキャンして、管理されていないデバイスを検出します。 デバイス検出機能を使用すると、次を検出できます。

- Microsoft Defender for EndpointにまだオンボードされていないEnterprise エンドポイント (ワークステーション、サーバー、モバイル デバイス)
- ルーターやスイッチなどのネットワーク デバイス
- プリンターやカメラなどの IoT デバイス

不明なデバイスと管理されていないデバイスは、パッチが適用されていないプリンター、セキュリティ構成が弱いネットワーク デバイス、セキュリティ制御のないサーバーなど、ネットワークに重大なリスクを生じます。 デバイスが検出されたら、次のことができます。

- アンマネージド エンドポイントをサービスにオンボードし、セキュリティの可視性を高める。
- 脆弱性を特定して評価し、構成のギャップを検出することで、攻撃対象を減らします。

デバイスの検出方法の概要については、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWORdQ]

この機能と組み合わせて、デバイスをMicrosoft Defender for Endpointにオンボードするためのセキュリティに関する推奨事項は、既存の脅威と脆弱性の管理 エクスペリエンスの一部として利用できます。

## <a name="discovery-methods"></a>検出方法

オンボードデバイスで使用する検出モードを選択できます。 このモードは、企業ネットワーク内のアンマネージド デバイスに対して取得できる可視性のレベルを制御します。

検出には、次の 2 つのモードがあります。

- **基本的な検出**: このモードでは、エンドポイントはネットワーク内のイベントをパッシブに収集し、そこからデバイス情報を抽出します。 基本的な検出では、パッシブ ネットワーク データ収集に SenseNDR.exe バイナリが使用され、ネットワーク トラフィックは開始されません。 エンドポイントは、オンボードされたデバイスによって見られるすべてのネットワーク トラフィックからデータを抽出するだけです。 基本的な検出では、ネットワーク内のアンマネージド エンドポイントの可視性が制限されます。

- **標準検出** (推奨): このモードでは、エンドポイントがネットワーク内のデバイスを積極的に検索して、収集されたデータを強化し、より多くのデバイスを検出できます。信頼できる一貫性のあるデバイス インベントリを構築するのに役立ちます。 パッシブメソッドを使用して観察されたデバイスに加えて、標準モードでは、ネットワーク内のマルチキャスト クエリを使用してさらに多くのデバイスを検索する一般的な検出プロトコルも利用されます。 Standard モードでは、スマートでアクティブなプローブを使用して、観察されたデバイスに関する追加情報を検出して、既存のデバイス情報を強化します。 Standard モードが有効になっている場合、検出センサーによって生成される最小限のネットワーク アクティビティと無視できるネットワーク アクティビティは、組織内のネットワーク監視ツールによって観察される可能性があります。

検出設定を変更してカスタマイズできます。詳細については、「 [デバイス検出の構成」を](configure-device-discovery.md)参照してください。

> [!IMPORTANT]
> Standard Discovery は、2021 年 7 月 19 日からのすべてのお客様の既定のモードです。 この構成は、[設定] ページから [基本] に変更できます。 基本モードを選択した場合、ネットワーク内のアンマネージド エンドポイントの可視性が制限されます。

> [!NOTE]
> 探索エンジンは、企業ネットワークで受信されるネットワーク イベントと、企業ネットワークの外部で受信されるネットワーク イベントを区別します。 企業ネットワークに接続されていないデバイスは、検出されず、デバイス インベントリに一覧表示されません。

## <a name="device-inventory"></a>デバイス一覧

検出されたが、Microsoft Defender for Endpointによってまだオンボードおよびセキュリティで保護されていないデバイスは、[コンピューターとモバイル] タブのデバイス インベントリに一覧表示されます。

これらのデバイスを評価するには、オンボード状態と呼ばれるデバイス インベントリの一覧でフィルターを使用できます。これには、次のいずれかの値を指定できます。

- オンボード済み: エンドポイントはMicrosoft Defender for Endpointにオンボードされます。
- オンボードできます。エンドポイントはネットワークで検出され、オペレーティング システムはMicrosoft Defender for Endpointでサポートされているものとして識別されましたが、現在オンボードされていません。 これらのデバイスのオンボードを非常に推奨します。
- サポートされていない: エンドポイントはネットワークで検出されましたが、Microsoft Defender for Endpointではサポートされていません。
- 情報が不十分です。システムはデバイスのサポート可能性を判断できませんでした。 ネットワーク内のより多くのデバイスで標準検出を有効にすると、検出された属性を強化できます。

:::image type="content" source="images/2b62255cd3a9dd42f3219e437b956fb9.png" alt-text="デバイス インベントリ ダッシュボード" lightbox="images/2b62255cd3a9dd42f3219e437b956fb9.png":::

> [!TIP]
> デバイス インベントリリストから管理されていないデバイスを除外するには、常にフィルターを適用できます。 また、API クエリのオンボード状態列を使用して、管理されていないデバイスを除外することもできます。

詳細については、「 [デバイス インベントリ」を参照してください](machines-view-overview.md)。

## <a name="network-device-discovery"></a>ネットワーク デバイスの検出

組織に展開されているアンマネージド ネットワーク デバイスの数が多い場合、攻撃領域が大きく、企業全体に大きなリスクが生じます。 Microsoft Defender for Endpointネットワーク検出機能は、ネットワーク デバイスが検出され、正確に分類され、資産インベントリに追加されるようにするのに役立ちます。

Defender for Endpoint にはネットワーク デバイス自体にセンサーが組み込まれていないので、ネットワーク デバイスは標準エンドポイントとして管理されません。 このような種類のデバイスでは、リモート スキャンでデバイスから必要な情報を取得するエージェントレス アプローチが必要です。 これを行うには、構成済みネットワーク デバイスの定期的な認証スキャンを実行するために、各ネットワーク セグメントで指定されたMicrosoft Defender for Endpoint デバイスが使用されます。 検出されると、Defender for Endpoint の脅威と脆弱性の管理機能により、検出されたスイッチ、ルーター、WLAN コントローラー、ファイアウォール、VPN ゲートウェイをセキュリティで保護するための統合ワークフローが提供されます。

詳細については、「 [ネットワーク デバイス](network-devices.md)」を参照してください。

## <a name="device-discovery-integrations"></a>デバイス検出の統合

完全な OT/IOT 資産インベントリを見つけ、特定し、セキュリティで保護するのに十分な可視性を得るという課題に対処するために、Microsoft Defender for Endpoint次の統合がサポートされるようになりました。

- **Corelight**: Microsoft は Corelight と提携し、Corelight ネットワーク アプライアンスからデータを受信しています。 これにより、他の非管理対象デバイスや外部ネットワークとの通信など、アンマネージド デバイスのネットワーク アクティビティの可視性が向上するMicrosoft 365 Defenderが提供されます。 詳細については、「 [Corelight データ統合を有効にする」を](corelight-integration.md)参照してください。

- **Microsoft Defender for IoT**: この統合は、Microsoft Defender for Endpointのデバイス検出機能と Microsoft Defender for IoT のエージェントレス監視機能を組み合わせて、IT ネットワークに接続されたエンタープライズ IoT デバイス (Voice over Internet Protocol (VoIP)、プリンター、スマート テレビなど) をセキュリティで保護します。 詳細については、「 [Microsoft Defender for IoT 統合を有効にする](enable-microsoft-defender-for-iot-integration.md)」を参照してください。

## <a name="vulnerability-assessment-on-discovered-devices"></a>検出されたデバイスの脆弱性評価

デバイスの脆弱性とリスク、およびネットワーク内の他の検出されたアンマネージド デバイスは、"セキュリティ おすすめ" の下の現在の TVM フローの一部であり、ポータル全体のエンティティ ページに表示されます。
"SSH" 関連のセキュリティに関する推奨事項を検索して、管理されていないデバイスと管理対象デバイスに関連する SSH の脆弱性を見つけます。

:::image type="content" source="images/1156c82ffadd356ce329d1cf551e806c.png" alt-text="セキュリティに関する推奨事項ダッシュボード" lightbox="images/1156c82ffadd356ce329d1cf551e806c.png":::

## <a name="use-advanced-hunting-on-discovered-devices"></a>検出されたデバイスで高度なハンティングを使用する

高度なハンティング クエリを使用して、検出されたデバイスの可視性を得ることができます。 検出されたデバイスの詳細は DeviceInfo テーブルで確認するか、DeviceNetworkInfo テーブルでそれらのデバイスに関するネットワーク関連情報を確認します。

:::image type="content" source="images/f48ba1779eddee9872f167453c24e5c9.png" alt-text="クエリを使用できる高度なハンティング ページ" lightbox="images/f48ba1779eddee9872f167453c24e5c9.png":::

### <a name="query-discovered-devices-details"></a>検出されたデバイスの詳細を照会する

次のクエリを DeviceInfo テーブルで実行して、検出されたすべてのデバイスと、各デバイスの詳細までを返します。

```query
DeviceInfo
| summarize arg_max(Timestamp, *) by DeviceId  // Get latest known good per device Id
| where isempty(MergedToDeviceId) // Remove invalidated/merged devices
| where OnboardingStatus != "Onboarded"
```

**SeenBy** 関数を呼び出すと、高度なハンティング クエリで、検出されたデバイスがどのオンボードデバイスによって検出されたかの詳細を取得できます。 この情報は、検出された各デバイスのネットワークの場所を特定するのに役立ち、その後、ネットワーク内のデバイスを識別するのに役立ちます。

```query
DeviceInfo
| where OnboardingStatus != "Onboarded"
| summarize arg_max(Timestamp, *) by DeviceId 
| where isempty(MergedToDeviceId) 
| limit 100
| invoke SeenBy()
| project DeviceId, DeviceName, DeviceType, SeenBy
```

詳細については、 [SeenBy()](/microsoft-365/security/defender/advanced-hunting-seenby-function) 関数を参照してください。

### <a name="query-network-related-information"></a>クエリ ネットワーク関連情報

デバイス検出では、オンボードされたデバイスMicrosoft Defender for Endpointをネットワーク データ ソースとして利用し、アクティビティを非オンボード デバイスに属性付けします。 Microsoft Defender for Endpointオンボードデバイスのネットワーク センサーは、次の 2 つの新しい接続の種類を識別します。

- ConnectionAttempt - TCP 接続を確立する試み (syn)
- ConnectionAcknowledged - TCP 接続が受け入れられたことを確認する (syn\ack)

つまり、オンボードされていないデバイスがオンボードされたMicrosoft Defender for Endpoint デバイスと通信しようとすると、その試行によって DeviceNetworkEvent が生成され、オンボードされたデバイスタイムラインと高度なハンティング DeviceNetworkEvents テーブルで非オンボードデバイス アクティビティを確認できます。

次のクエリ例を試すことができます。

```text
DeviceNetworkEvents
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"
| take 10
```

## <a name="next-steps"></a>次の手順

- [デバイス検出の構成](configure-device-discovery.md)
- [デバイス検出に関する FAQ](device-discovery-faq.md)
