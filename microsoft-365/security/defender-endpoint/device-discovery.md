---
title: デバイス検出の概要
description: ネットワーク内の管理されていないデバイスをMicrosoft 365 Defenderエンドポイントの検出を活用する方法について説明します。
keywords: デバイスの検出、検出、パッシブ、プロアクティブ、ネットワーク、可視性、サーバー、ワークステーション、オンボード、管理されていないデバイス
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e32880b46b04ce9ee755c09b6cbff2e3e484f4ff
ms.sourcegitcommit: 6b24f65c987e5ca06e6d5f4fc10804cdbe68b034
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2021
ms.locfileid: "61320853"
---
# <a name="device-discovery-overview"></a>デバイス検出の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

環境を保護するには、ネットワーク内のデバイスのインベントリを取得する必要があります。 ただし、ネットワーク内のマッピング デバイスは、多くの場合、コストがかかり、困難で、時間がかかる場合があります。

Microsoft Defender for Endpoint は、デバイス検出機能を提供し、追加のアプライアンスや面倒なプロセス変更を必要とせずに、企業ネットワークに接続されている管理されていないデバイスを見つけるのに役立ちます。 デバイス検出では、ネットワーク内のオンボード エンドポイントを使用して、ネットワークを収集、プローブ、またはスキャンして管理されていないデバイスを検出します。 デバイス検出機能を使用すると、次の情報を検出できます。

- Enterprise Microsoft Defender for Endpoint にまだオンボードされていないエンドポイント (ワークステーション、サーバー、およびモバイル デバイス)
- ルーターやスイッチのようなネットワーク デバイス
- プリンターやカメラのような IoT デバイス

不明なデバイスと管理されていないデバイスは、パッチが適用されていないプリンター、セキュリティ構成が弱いネットワーク デバイス、セキュリティ制御のないサーバーなど、ネットワークに重大なリスクを伴います。 デバイスが検出された後は、次の方法を実行できます。

- アンマネージ エンドポイントをサービスにオンボードし、セキュリティの可視性を高くします。
- 脆弱性を特定して評価し、構成のギャップを検出することで、攻撃の表面を減らします。

デバイスの検出方法の概要については、次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWORdQ]

この機能と組み合わせて、Microsoft Defender for Endpoint にデバイスをオンボードするセキュリティ推奨事項は、既存の脅威と脆弱性の管理エクスペリエンスの一環として利用できます。

## <a name="discovery-methods"></a>探索メソッド

オンボード デバイスで使用する検出モードを選択できます。 このモードは、企業ネットワーク内の管理されていないデバイスに対して取得できる可視性のレベルを制御します。

次の 2 つの検出モードを使用できます。

- **基本的な検出**: このモードでは、エンドポイントはネットワーク内のイベントを受動的に収集し、そこからデバイス情報を抽出します。 基本的な検出では、SenseNDR.exeネットワーク データ収集にバイナリを使用し、ネットワーク トラフィックは開始されません。 エンドポイントは、オンボードデバイスで見られるすべてのネットワーク トラフィックからデータを抽出するだけで構成されます。 基本的な検出では、ネットワーク内の管理されていないエンドポイントの表示が制限されます。

- **標準検出** (推奨): このモードを使用すると、エンドポイントはネットワーク内のデバイスをアクティブに検索して、収集されたデータを強化し、より多くのデバイスを検出し、信頼性の高い一貫性のあるデバイス インベントリを構築できます。 パッシブ方式を使用して観測されたデバイスに加えて、標準モードでは、ネットワークでマルチキャスト クエリを使用する一般的な検出プロトコルも利用して、さらに多くのデバイスを検索します。 標準モードでは、スマートでアクティブなプロブを使用して、観測されたデバイスに関する追加情報を検出し、既存のデバイス情報を強化します。 Standard モードを有効にすると、検出センサーによって生成される最小限のごくわずかのネットワーク アクティビティが、組織内のネットワーク監視ツールによって観察される可能性があります。

検出設定を変更およびカスタマイズできます。詳細については、「デバイス検出の構成 [」を参照してください](configure-device-discovery.md)。

> [!IMPORTANT]
> 標準検出は、2021 年 7 月 19 日からすべてのユーザーの既定のモードです。 この構成を基本に変更するには、設定ページを使用します。 基本モードを選択すると、ネットワーク内の管理されていないエンドポイントの表示が制限されます。

> [!NOTE]
> 検出エンジンは、企業ネットワークで受信されるネットワーク イベントと企業ネットワーク外のネットワーク イベントを区別します。 企業ネットワークに接続されていないデバイスは、デバイス インベントリで検出または一覧表示されません。

## <a name="device-inventory"></a>デバイス インベントリ

Microsoft Defender for Endpoint によって検出されたが、まだオンボードおよびセキュリティ保護されていないデバイスは、[エンドポイント] タブの [デバイス インベントリ] に表示されます。

[オンボーディングの状態] と呼ばれるデバイス インベントリ リストでフィルターを使用できます。これは、次の値を持つ場合があります。

- オンボード: エンドポイントは Microsoft Defender for Endpoint にオンボードされます。
- オンボード可能: ネットワークでエンドポイントが検出され、オペレーティング システムは Microsoft Defender for Endpoint でサポートされているエンドポイントとして識別されましたが、現在オンボードされていません。 これらのデバイスのオンボーディングを強くお勧めします。
- サポートされていません: エンドポイントはネットワークで検出されましたが、Microsoft Defender for Endpoint ではサポートされていません。
- 不十分な情報: システムは、デバイスのサポート可能性を判断する必要があります。 ネットワーク内のより多くのデバイスで標準検出を有効にすると、検出された属性を強化できます。

![デバイス インベントリ ダッシュボードのイメージ。](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> フィルターをいつでも適用して、デバイス インベントリ リストから管理されていないデバイスを除外できます。 また、API クエリのオンボーディング状態列を使用して、管理されていないデバイスをフィルター処理することもできます。

## <a name="network-device-discovery"></a>ネットワーク デバイスの検出

組織に展開されている管理されていないネットワーク デバイスの数が多い場合、攻撃の領域が大きく、企業全体にとって大きなリスクになります。 Microsoft Defender for Endpoint ネットワーク検出機能を使用すると、ネットワーク デバイスが検出され、正確に分類され、資産インベントリに追加されます。

Defender for Endpoint にはネットワーク デバイス自体にセンサーが組み込かされていないので、ネットワーク デバイスは標準エンドポイントとして管理されません。 これらの種類のデバイスでは、リモート スキャンがデバイスから必要な情報を取得するエージェントレスアプローチが必要です。 これを行うには、指定された Microsoft Defender for Endpoint デバイスを各ネットワーク セグメントで使用して、事前構成済みネットワーク デバイスの定期的な認証スキャンを実行します。 検出された Defender for Endpoint の 脅威と脆弱性の管理 機能は、検出されたスイッチ、ルーター、WLAN コントローラー、ファイアウォール、VPN ゲートウェイを保護するための統合ワークフローを提供します。

詳細については、「ネットワーク デバイス [」を参照してください](network-devices.md)。

## <a name="device-discovery-integrations"></a>デバイス検出の統合

完全な OT/IOT アセット インベントリ Microsoft Defender for Endpoint を見つけ、特定し、セキュリティ保護するのに十分な可視性を得るという課題に対処するために、次の統合がサポートされています。

- **Corelight**: Microsoft は Corelight と提携して、Corelight ネットワーク アプライアンスからデータを受信しました。 これにより、Microsoft 365 Defenderデバイスや外部ネットワークとの通信など、管理されていないデバイスのネットワーク アクティビティの可視性が向上します。 詳細については、「Enable [Corelight data integration 」を参照してください](corelight-integration.md)。

- **Microsoft Defender for IoT:** この統合は、Microsoft Defender for Endpoint のデバイス検出機能と、Microsoft Defender for IoT のエージェントレス監視機能を組み合わせ、IT ネットワークに接続されているエンタープライズ IoT デバイス (VoIP、プリンター、スマートテレビなど) をセキュリティで保護します。 詳細については [、「Enable Microsoft Defender for IoT integration」を参照してください](enable-microsoft-defender-for-iot-integration.md)。

## <a name="vulnerability-assessment-on-discovered-devices"></a>検出されたデバイスの脆弱性評価

デバイスの脆弱性とリスク、およびネットワーク内で検出された他の管理されていないデバイスは、"セキュリティ推奨事項" の下にある現在の TVM フローの一部であり、ポータル全体のエンティティ ページに表示されます。
"SSH" 関連のセキュリティ推奨事項を検索して、管理されていないデバイスと管理対象デバイスに関連する SSH の脆弱性を検索します。

![セキュリティ推奨事項ダッシュボードのイメージ。](images/1156c82ffadd356ce329d1cf551e806c.png)

## <a name="use-advanced-hunting-on-discovered-devices"></a>検出されたデバイスで高度なハンティングを使用する

高度な検索クエリを使用すると、検出されたデバイスを表示できます。
検出されたエンドポイントの詳細については、DeviceInfo テーブル、または DeviceNetworkInfo テーブルのこれらのデバイスに関するネットワーク関連の情報を参照してください。

![高度な狩猟の使用のイメージ。](images/f48ba1779eddee9872f167453c24e5c9.png)

デバイス検出では、Microsoft Defender for Endpoint オンボード デバイスをネットワーク データ ソースとして活用して、オンボードされていないデバイスにアクティビティを属性付けします。 つまり、Microsoft Defender for Endpoint オンボード デバイスがオンボードされていないデバイスと通信した場合、オンボードされていないデバイス上のアクティビティは、タイムライン上および高度なハンティング DeviceNetworkEvents テーブルで確認できます。

新しいイベントは、伝送制御プロトコル (TCP) 接続ベースであり、現在の DeviceNetworkEvents スキームに適合します。 エンドポイントが有効な Microsoft Defender 以外からの Microsoft Defender for Endpoint 対応デバイスへの TCP 入力。

次のアクションの種類も追加されています。

- ConnectionAttempt - TCP 接続を確立する試み (syn)
- ConnectionAcknowledged - TCP 接続が受け入れられたという確認応答 (syn\ack)

次のクエリ例を試してみてください。

```text
DeviceNetworkEvents
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"
| take 10
```

## <a name="changed-behavior"></a>変更された動作

次のセクションでは、この機能が有効になっているときに Microsoft Defender for Endpoint および Microsoft 365 Defenderポータルで確認<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">する</a>変更を示します。

1. Microsoft Defender for Endpoint にオンボードされていないデバイスは、デバイス インベントリ、高度な検索、API クエリに表示される必要があります。 これにより、クエリ結果のサイズが大幅に増加する可能性があります。
    1. Advanced Hunting の "DeviceInfo" テーブルと "DeviceNetworkInfo" テーブルには、検出されたデバイスが保持されます。 "OnboardingStatus" 属性を使用して、これらのデバイスをフィルター処理できます。
    2. 検出されたデバイスは、ストリーミング API クエリ結果に表示される予定です。 これらのデバイスは、クエリでフィルターを使用 `OnboardingStatus` してフィルター処理できます。
2. 管理されていないデバイスは、定義された条件に基づいて既存のデバイス グループに割り当てられます。
3. まれに、標準検出によってネットワーク モニターやセキュリティ ツールでアラートがトリガーされる場合があります。 このようなイベントが発生した場合は、これらの問題が繰り返されるのを防ぐためのフィードバックをお寄せください。 特定のターゲットまたはサブネット全体が Standard Discovery によってアクティブにプローブされるのを明示的に除外できます。

## <a name="next-steps"></a>次の手順

- [デバイス検出の構成](configure-device-discovery.md)
- [デバイスの検出に関するよくある質問](device-discovery-faq.md)
