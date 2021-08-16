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
ms.openlocfilehash: d4ae05517583a8368ba7936a942e5ec06a9414f7
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58257326"
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
 デバイスの特性の変化が観察された場合、デバイスはアクティブにプローブされ、既存の情報が最新の状態に更新されます (通常、デバイスは 3 週間に 1 回までプローブされます)

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


## <a name="does-standard-discovery-look-like-malicious-network-activity"></a>標準の検出は、悪意のあるネットワーク アクティビティのように見えるでしょうか。
Standard discovery を検討する場合は、プロブの影響、特にセキュリティ ツールが悪意のあるアクティビティを疑う可能性があるかどうかについて疑問に思う場合があります。 次のサブセクションでは、ほとんどの場合、組織が Standard Discovery を有効にするための懸念を持つ必要がない理由について説明します。  

### <a name="probing-is-distributed-across-all-windows-devices-on-the-network"></a>Probing は、ネットワーク上のすべてのWindowsデバイスに分散されます。
通常、侵害されたデバイスの数が少ないネットワーク全体をスキャンする悪意のあるアクティビティとは対照的に、Microsoft Defender for Endpoint の Standard Discovery probing は、オンボードのすべての Windows デバイスから開始され、アクティビティは無害で異常ではありません。 プロブは、ネットワークでサポートされているオンボード デバイス間の試みをバランスを取るクラウドから一中心に管理されます。  

### <a name="active-probing-generates-negligible-amount-of-extra-traffic"></a>アクティブなプロブは、余分なトラフィックのごくわずかの量を生成します
非管理対象デバイスは通常、3 週間に 1 回までプローブを受け取り、50 KB 未満のトラフィックを生成します。 悪意のあるアクティビティには、通常、繰り返しの多い試み、場合によっては、ネットワーク監視ツールによって異常を特定できる大量のネットワーク トラフィックを生成するデータの侵入が含まれます。 

### <a name="your-windows-device-already-runs-active-discovery"></a>デバイスWindowsアクティブな検出が既に実行されている
アクティブな検出機能は、Windows オペレーティング システムに常に埋め込まれているので、近くのデバイス、エンドポイント、プリンターを検索して、ネットワーク内のエンドポイント間での "プラグ アンド プレイ" エクスペリエンスとファイル共有を容易にします。 同様の機能は、モバイル デバイス、ネットワーク機器、インベントリ アプリケーションにも実装されています。  

標準検出では、同じ検出方法を使用してデバイスを識別し、デバイス インベントリ内のネットワーク内のすべてのデバイスを統合Microsoft 365 Defenderします。 たとえば、標準検出では、ネットワーク内の利用可能なプリンターをリストする場合と同Windows近くのエンドポイントを識別します。 

ネットワーク セキュリティおよび監視ツールは、ネットワーク上のデバイスによって実行されるこのようなアクティビティに対して無関心です。 

### <a name="only-unmanaged-devices-are-being-probed"></a>プローブされているのは管理されていないデバイスのみです
デバイス検出機能は、ネットワーク上の管理されていないデバイスのみを検出して識別するために構築されています。 つまり、Microsoft Defender for Endpoint で既にオンボードされている以前に検出されたデバイスはプローブされません。 

### <a name="you-can-exclude-network-lures-from-active-probing"></a>アクティブなプロビリングからネットワーク ルアーを除外できます
標準検出では、アクティブなプロブからのデバイスまたは範囲 (サブネット) の除外がサポートされています。 ネットワーク ルアーが展開されている場合は、Device Discovery 設定を使用して、IP アドレスまたはサブネット (IP アドレスの範囲) に基づいて除外を定義できます。 これらの除外を定義すると、これらのデバイスがアクティブにプローブされ、通知されません。 これらのデバイスはパッシブ メソッドのみを使用して検出されます (基本検出モードと同様)。
