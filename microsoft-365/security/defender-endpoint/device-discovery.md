---
title: デバイス検出の概要
description: ネットワーク内の管理されていないデバイスをMicrosoft 365 Defenderエンドポイントの検出を活用する方法について説明します。
keywords: デバイスの検出、検出、パッシブ、プロアクティブ、ネットワーク、可視性、サーバー、ワークステーション、オンボード、管理されていないデバイス
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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 75b47d9d7c95bd2e1f0c2654e59c3d24e7e838fc6a4d1d543976829e9c96c149
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53834134"
---
# <a name="device-discovery-overview"></a>デバイス検出の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


環境を保護するには、ネットワーク内のデバイスのインベントリを取得する必要があります。 ただし、ネットワーク内のマッピング デバイスは、多くの場合、コストがかかり、困難で、時間がかかる場合があります。

Microsoft Defender for Endpoint は、デバイス検出機能を提供し、追加のアプライアンスや面倒なプロセス変更を必要とせずに、企業ネットワークに接続されている管理されていないデバイスを見つけるのに役立ちます。

デバイス検出機能を使用すると、次の機能を使用できます。

- **企業ネットワークに接続されているエンタープライズ エンドポイントを検出する**

  基本的な検出オプションまたは標準検出オプションを使用すると、Microsoft Defender for Endpoint にまだオンボードされていないワークステーション、サーバー、およびモバイル エンドポイントを検出できます。

- **オンボードで検出されたエンドポイント**

  ネットワーク内の管理されていないエンドポイントは、ネットワークに脆弱性とリスクを導入します。 サービスにオンボーディングすると、セキュリティの可視性が向上します。

この機能と組み合わせて、Microsoft Defender for Endpoint にデバイスをオンボードする新しいセキュリティ推奨事項は、既存の脅威と脆弱性管理エクスペリエンスの一環として利用できます。

## <a name="discovery-methods"></a>探索メソッド

検出には 2 つのモードがあります。

- 基本的な検出
- 標準検出 (推奨)

> [!IMPORTANT]
> 検出は基本モードに設定されます。 この構成は、[設定] ページから保持できます。 2021 年 7 月 19 日から始まるすべてのお客様の既定のモードは、この日付より前の設定ページで変更されていない限り、標準検出です。

### <a name="basic-discovery"></a>基本的な検出

このモードでは、エンドポイントはネットワーク内のイベントを受動的に収集し、そこからデバイス情報を抽出します。 基本的な検出では、SenseNDR.exeネットワーク データ収集にバイナリを使用し、ネットワーク トラフィックは開始されません。 エンドポイントは、オンボードデバイスで見られるすべてのネットワーク トラフィックからデータを抽出するだけで構成されます。

### <a name="standard-discovery"></a>標準検出

このモードにより、エンドポイントはネットワーク内の観測されたデバイスをアクティブにプローブして収集されたデータを強化し、信頼性の高い一貫性のあるデバイス インベントリを構築できます。 標準モードでは、スマートでアクティブなプロブを使用して、観測されたデバイスに関するさらに多くの情報を検出し、既存のデバイス情報を強化します。

Standard モードを有効にすると、検出センサーによって生成される最小限のごくわずかのネットワーク アクティビティが、組織内のネットワーク監視ツールによって観察される場合があります。

 このモードを有効にしない場合は、ネットワーク内の管理されていないエンドポイントの表示が制限されます。

標準検出では、さまざまな PowerShell スクリプトを使用して、ネットワーク内のデバイスをアクティブにプローブします。 これらの PowerShell スクリプトは Microsoft 署名済みで、次の場所から実行されます `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` 。 たとえば、`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1` などです。

詳細については、「デバイス検出の構成」を参照[してください。](configure-device-discovery.md)

> [!NOTE]
> 検出エンジンは、企業ネットワークで受信されるネットワーク イベントと企業ネットワーク外のネットワーク イベントを区別します。 企業ネットワークに接続されていないデバイスは、デバイス インベントリで検出または一覧表示されません。

## <a name="device-inventory"></a>デバイス インベントリ

Microsoft Defender for Endpoint によって検出されたが、まだオンボードおよびセキュリティ保護されていないデバイスは、[エンドポイント] タブの [デバイス インベントリ] に表示されます。これで、次の値を持つ可能性があるオンボード状態と呼ばれるデバイス インベントリ リストで新しいフィルターを使用できます。

- オンボード: エンドポイントは Microsoft Defender for Endpoint にオンボードされます。
- オンボード可能: ネットワークでエンドポイントが検出され、オペレーティング システムは Microsoft Defender for Endpoint でサポートされているエンドポイントとして識別されましたが、現在オンボードされていません。 これらのデバイスのオンボーディングを強くお勧めします。
- サポートされていません: エンドポイントはネットワークで検出されましたが、Microsoft Defender for Endpoint ではサポートされていません。
- 不十分な情報: システムは、デバイスのサポート可能性を判断する必要があります。 ネットワーク内のより多くのデバイスで標準検出を有効にすると、検出された属性を強化できます。

![デバイス インベントリ ダッシュボードのイメージ](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> フィルターをいつでも適用して、デバイス インベントリ リストから管理されていないデバイスを除外できます。 また、API クエリのオンボーディング状態列を使用して、管理されていないデバイスをフィルター処理することもできます。

## <a name="vulnerability-assessment-on-discovered-devices"></a>検出されたデバイスの脆弱性評価

デバイスの脆弱性とリスク、およびネットワーク内で検出された他の管理されていないデバイスは、"セキュリティ推奨事項" の下にある現在の TVM フローの一部であり、ポータル全体のエンティティ ページに表示されます。
"SSH" 関連のセキュリティ推奨事項を検索して、管理されていないデバイスと管理対象デバイスに関連する SSH の脆弱性を検索します。

![セキュリティ推奨事項ダッシュボードのイメージ](images/1156c82ffadd356ce329d1cf551e806c.png)

## <a name="use-advanced-hunting-on-discovered-devices"></a>検出されたデバイスで高度なハンティングを使用する

高度な検索クエリを使用すると、検出されたデバイスを表示できます。
検出されたエンドポイントの詳細については、DeviceInfo テーブル、または DeviceNetworkInfo テーブルのこれらのデバイスに関するネットワーク関連の情報を参照してください。

![高度なハンティングの使用イメージ](images/f48ba1779eddee9872f167453c24e5c9.png)

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

次のセクションでは、この機能が有効になっているときに Microsoft Defender for Endpoint または Microsoft 365 セキュリティ センターで確認する変更点を示します。

1. Microsoft Defender to Endpoint にオンボードされていないデバイスは、デバイス インベントリ、高度なハンティング、API クエリに表示される必要があります。 これにより、クエリ結果のサイズが大幅に増加する可能性があります。
    1. Advanced Hunting の "DeviceInfo" テーブルと "DeviceNetworkInfo" テーブルには、検出されたデバイスが保持されます。 "OnboardingStatus" 属性を使用して、これらのデバイスをフィルター処理できます。
    2. 検出されたデバイスは、ストリーミング API クエリ結果に表示される予定です。 これらのデバイスは、クエリでフィルターを使用 `OnboardingStatus` してフィルター処理できます。
2. 管理されていないデバイスは、定義された条件に基づいて既存のデバイス グループに割り当てられます。
3. まれに、標準検出によってネットワーク モニターやセキュリティ ツールでアラートがトリガーされる場合があります。 このようなイベントが発生した場合は、これらの問題が繰り返されるのを防ぐためのフィードバックをお寄せください。 特定のターゲットまたはサブネット全体が Standard Discovery によってアクティブにプローブされるのを明示的に除外できます。

## <a name="next-steps"></a>次の手順

- [デバイス検出の構成](configure-device-discovery.md)
- [デバイスの検出に関するよくある質問](device-discovery-faq.md)
