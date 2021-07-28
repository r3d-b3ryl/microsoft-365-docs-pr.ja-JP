---
title: デバイスの検出に関するよく寄せられる質問
description: デバイスの検出に関するよく寄せられる質問 (FAQ) に対する回答を検索する
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
ms.openlocfilehash: ac2643adaa2e0a30e94434a0fe34e4d6ec2b3b1d
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53542971"
---
# <a name="device-discovery-frequently-asked-questions"></a>デバイスの検出に関するよく寄せられる質問

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

デバイスの検出に関するよく寄せられる質問 (FAQ) に対する回答を検索します。

## <a name="what-is-basic-discovery-mode"></a>基本検出モードとは
このモードでは、すべての Microsoft Defender for Endpoint オンボード デバイスがネットワーク データを収集し、隣接するデバイスを検出できます。 オンボードエンドポイントは、ネットワーク内のイベントをパッシブに収集し、そこからデバイス情報を抽出します。 ネットワーク トラフィックは開始されません。 オンボードエンドポイントは、オンボードされたデバイスで見られるすべてのネットワーク トラフィックからデータを抽出するだけで構成されます。 ネットワーク内の管理されていないデバイスを一覧表示するために使用されるこのデータ。

## <a name="can-i-disable-basic-discovery"></a>基本検出を無効にできますか?
[高度な機能] ページでデバイスの検出を [無効にするオプション](advanced-features.md) があります。 ただし、ネットワーク内の管理されていないデバイスの表示が失われる可能性があります。 

## <a name="what-is-standard-discovery-mode"></a>標準検出モードとは
 このモードでは、Microsoft Defender for Endpoint にオンボードされたエンドポイントは、ネットワーク内の監視されたデバイスをアクティブにプローブして、収集されたデータを強化できます (ネットワーク トラフィックの量はごくわずかです)。 このモードは、信頼性の高い一貫性のあるデバイス インベントリを構築する場合に強くお勧めします。 このモードを無効にし、[基本検出モード] を選択すると、ネットワーク内の管理されていないエンドポイントの表示が制限される可能性があります。

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>標準検出を実行するデバイスを制御できますか?
 Standard Discovery の実行に使用されるデバイスの一覧をカスタマイズできます。 この機能をサポートしているすべてのオンボード デバイス (現在の Windows 10 デバイスのみ) で Standard Discovery を有効にするか、デバイス タグを指定してデバイスのサブセットまたはサブセットを選択できます。 この場合、他のすべてのデバイスは基本検出のみを実行するように構成されます。 構成は、[デバイスの検出設定] ページで使用できます。

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>管理されていないデバイスをデバイス インベントリ リストから除外できますか?
はい、フィルターを適用すると、デバイス インベントリ リストから管理されていないデバイスを除外できます。 また、API クエリのオンボーディング状態列を使用して、管理されていないデバイスをフィルター処理することもできます。 


## <a name="which-onboarded-devices-can-perform-discovery"></a>検出を実行できるオンボード デバイス
 バージョン 1809 以降Windows 10オンボーディングされたデバイスは、検出を実行できます。

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>オンボード デバイスがホーム ネットワークまたはパブリック アクセス ポイントに接続されている場合は、どうなるでしょうか。
 検出エンジンは、企業ネットワークで受信されるネットワーク イベントと企業ネットワーク外のネットワーク イベントを区別します。 すべてのテナントのクライアント間でネットワーク識別子を関連付け、プライベート ネットワークから受信したイベントと企業ネットワークの間でイベントが区別されます。 たとえば、ネットワーク内のデバイスの大部分が、同じ既定のゲートウェイと DHCP サーバー アドレスを持つ同じネットワーク名に接続されていることを報告する場合、このネットワークは企業ネットワークである可能性が高いとみなされます。 プライベート ネットワーク デバイスはインベントリに表示され、アクティブにプローブされません。

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>キャプチャと分析を行うプロトコルは何ですか?
 既定では、Windows 10 バージョン 1809 以降で実行されているオンボード デバイスはすべて、ARP、CDP、DHCP、DHCPv6、IP (ヘッダー)、LLDP、LLMNR、mDNS、MNDP、NBNS、SSDP、TCP (ヘッダー)、UDP (ヘッダー)、WSD のプロトコルをキャプチャおよび分析しています。

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Standard Discovery でアクティブなプロビリングに使用するプロトコルは何ですか?
 デバイスが標準検出を実行するように構成されている場合、公開されたサービスは、ARP、FTP、HTTP、HTTPS、ICMP、LLMNR、NBNS、RDP、SIP、SMTP、SSH、Telnet、UPNP、WSD、SMB、NBSS、IPP、PJL、RPC、mDNS、DHCP、AFP、CrestonCIP、IphoneSyncR のプロトコルを使用してプローブされます。

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>標準検出でターゲットをプローブから除外する方法を説明します。
 ネットワーク上にアクティブにプローブしないデバイスがある場合は、除外リストを定義してスキャンを防止することもできます。 構成は、[デバイスの検出設定] ページで使用できます。

## <a name="can-i-exclude-devices-from-being-discovered"></a>デバイスを検出から除外できますか?
 デバイス検出ではパッシブ メソッドを使用してネットワーク内のデバイスを検出します。企業ネットワーク内のオンボード デバイスと通信するデバイスは、インベントリ内で検出および一覧表示されます。 アクティブなプロビリングからのみデバイスを除外できます。

## <a name="how-frequent-is-the-active-probing"></a>アクティブなプロブの頻度はどのくらいですか?
 デバイスの特性の変化が観察された場合 (1 ~ 3 週間ごとに) デバイスがアクティブに調査され、既存の情報が最新の状態に更新されます。

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>セキュリティ ツールによって開始されたUnicastScanner.ps1スキャン アクティビティに関するアラートが発生しました。何を行う必要がありますか?
 アクティブなプロブ スクリプトは Microsoft によって署名され、安全です。 除外リストに次のパスを追加できます。 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Standard Discovery アクティブ プローブによって生成されるトラフィックの量は何ですか?
 アクティブプローブは、オンボードデバイスとプローブされたデバイスの間で最大 50Kb のトラフィックを生成できます。すべてのプローブ試行

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>デバイス インベントリ内の "オンボード可能" デバイスと、ダッシュボード タイル内の "オンボードするデバイス" の数との間に不一致がある理由
デバイス インベントリの [オンボード可能] の下にリストされているデバイスの数、"Microsoft Defender for Endpoint にオンボード" セキュリティ推奨事項、および "オンボードするデバイス" ダッシュボード ウィジェットの数の違いがあります。

 セキュリティの推奨事項とダッシュボード ウィジェットは、ネットワーク内で安定しているデバイス用です。一時的なデバイス、ゲスト デバイス、その他を除く。 このアイデアは、組織の全体的なセキュリティ スコアを示す永続的なデバイスで推奨する方法です。

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>検出された管理されていないデバイスをオンボードできますか?
 はい。 ネットワーク内の管理されていないエンドポイントは、ネットワークに脆弱性とリスクを導入します。 サービスにオンボーディングすると、セキュリティの可視性が向上します。 

## <a name="ive-noticed-that-unmanaged-device-health-state-is-always-active-why-is-that"></a>管理されていないデバイスの正常性状態が常に "Active" であるのに気付いたのですが、なぜですか?
一時的に、管理されていないデバイスの正常性状態は、実際の状態に関係なく、デバイス インベントリの標準保持期間中に "Active" になります。
