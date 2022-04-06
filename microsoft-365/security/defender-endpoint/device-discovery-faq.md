---
title: デバイス検出に関してよく寄せられる質問
description: デバイスの検出に関してよく寄せられる質問 (FAQ) に対する回答を見つける
keywords: デバイス検出, 検出, パッシブ, プロアクティブ, ネットワーク, 可視性, サーバー, ワークステーション, オンボード, アンマネージド デバイス
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
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 54a1b816f3d1322cab5558e5bd09d5d9b4285ae8
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665010"
---
# <a name="device-discovery-frequently-asked-questions"></a>デバイス検出に関してよく寄せられる質問

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- - [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

デバイスの検出に関してよく寄せられる質問 (FAQ) に対する回答を見つけます。

## <a name="what-is-basic-discovery-mode"></a>Basic 検出モードとは何ですか?

このモードでは、オンボードされているすべてのデバイスMicrosoft Defender for Endpointネットワーク データを収集し、近隣のデバイスを検出できます。 オンボードエンドポイントは、ネットワーク内のイベントをパッシブに収集し、そこからデバイス情報を抽出します。 ネットワーク トラフィックは開始されません。 オンボードエンドポイントは、オンボードされたデバイスによって見られるすべてのネットワーク トラフィックからデータを抽出するだけです。 ネットワーク内のアンマネージド デバイスを一覧表示するために使用されるこのデータ。

## <a name="can-i-disable-basic-discovery"></a>Basic Discovery を無効にできますか?

[ [高度な機能](advanced-features.md) ] ページでデバイス検出を無効にするオプションがあります。 ただし、ネットワーク内のアンマネージド デバイスの可視性は失われます。 SenseNDR.exeは、検出がオフになっているかどうかにかかわらず、オンボードされたデバイスで引き続き実行されることに注意してください。 

## <a name="what-is-standard-discovery-mode"></a>Standard 検出モードとは何ですか?

このモードでは、Microsoft Defender for Endpointにオンボードされたエンドポイントは、収集されたデータを強化するために、ネットワーク内の観察されたデバイスを積極的にプローブできます (ネットワーク トラフィックの量はごくわずかです)。 基本検出モードで観察されたデバイスのみが、標準モードでアクティブにプローブされます。 このモードは、信頼性が高くコヒーレントなデバイス インベントリを構築するために強くお勧めします。 このモードを無効にし、[基本探索モード] を選択した場合、ネットワーク内のアンマネージド エンドポイントの可視性は限られている可能性があります。

 標準モードでは、パッシブメソッドを使用して観察されたデバイスに加えて、ネットワーク内のマルチキャスト クエリを使用してさらに多くのデバイスを検索する一般的な検出プロトコルも利用されます。

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>Standard 検出を実行するデバイスを制御できますか?

Standard 検出の実行に使用されるデバイスの一覧をカスタマイズできます。 この機能もサポートしているすべてのオンボード デバイスで Standard Discovery を有効にするか (現在Windows 10以降およびサーバー 2019 以降のデバイスのみをWindows)、デバイス タグを指定してデバイスのサブセットまたはサブセットを選択します。 この場合、他のすべてのデバイスは、Basic Discovery のみを実行するように構成されます。 構成は、[デバイス検出の設定] ページで使用できます。

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>デバイス インベントリリストから管理されていないデバイスを除外できますか?

はい。フィルターを適用して、デバイス インベントリリストから管理されていないデバイスを除外できます。 また、API クエリのオンボード状態列を使用して、管理されていないデバイスを除外することもできます。

## <a name="which-onboarded-devices-can-perform-discovery"></a>検出を実行できるオンボードデバイスはどれですか?

Windows 10 バージョン 1809 以降、Windows 11、Windows Server 2019、またはWindows Server 2022 で実行されているオンボード デバイスは、検出を実行できます。

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>オンボードされたデバイスがホーム ネットワークまたはパブリック アクセス ポイントに接続されている場合はどうなりますか?

探索エンジンは、企業ネットワークで受信されるネットワーク イベントと、企業ネットワークの外部で受信されるネットワーク イベントを区別します。 すべてのテナントのクライアント間でネットワーク識別子を関連付けることで、イベントはプライベート ネットワークと企業ネットワークから受信されたものの間で区別されます。 たとえば、組織内のデバイスの大半が、同じ既定のゲートウェイと DHCP サーバー アドレスを持つ同じネットワーク名に接続されていることを報告する場合、このネットワークが企業ネットワークである可能性が高いと見なすことができます。 プライベート ネットワーク デバイスはインベントリに一覧表示されず、積極的にプローブされません。

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>キャプチャおよび分析するプロトコルは何ですか?

既定では、Windows 10 バージョン 1809 以降、Windows 11、Windows Server 2019、またはWindows Server 2022 で実行されているすべてのオンボード デバイスは、ARP、CDP、DHCP、DHCPv6、IP (ヘッダー)、LLDP、LLMNR、mDNS、MNDP、NBNS、SSDP、TCP (SYN ヘッダー)、WSD (ヘッダー)、WSD (ヘッダー)、WSD (ヘッダー) のプロトコルをキャプチャして分析しています。

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Standard Discovery でアクティブなプローブに使用するプロトコルはどれですか?
デバイスが Standard Discovery を実行するように構成されている場合、公開されたサービスは、ARP、FTP、HTTP、HTTPS、ICMP、LLMNR、NBNS、RDP、SIP、SMTP、SNMP、SSH、Telnet、UPNP、WSD、SMB、NBSS、IPP、PJJ、RPC、mDNS、DHCP、AFP、アセンシップ、IphoneSync、WinRM、VNC、SLP、LDAP


## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>Standard 検出でターゲットをプローブから除外するにはどうすればよいですか?

アクティブにプローブすべきでないデバイスがネットワーク上に存在する場合は、除外の一覧を定義してスキャンされないようにすることもできます。 構成は、[デバイス検出の設定] ページで使用できます。

> [!NOTE]
> デバイスは、ネットワーク内のマルチキャスト検出試行に応答する可能性があります。 これらのデバイスは検出されますが、積極的にプローブされることはありません。 

## <a name="can-i-exclude-devices-from-being-discovered"></a>デバイスの検出を除外できますか?

デバイス検出ではパッシブメソッドを使用してネットワーク内のデバイスを検出するため、企業ネットワーク内のオンボードデバイスと通信するすべてのデバイスを検出し、インベントリに一覧表示できます。 デバイスをアクティブなプローブから除外できるのは、デバイスのみです。

## <a name="how-frequent-is-the-active-probing"></a>アクティブプローブの頻度はどのくらいですか?

デバイス特性の変化が観察されると、デバイスがアクティブにプローブされ、既存の情報が最新であることが確認されます (通常、デバイスは 3 週間に 1 回以上プローブされません)。

## <a name="my-security-tool-raised-alert-on-unicastscannerps1--psscript_guidps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>セキュリティ ツールによって開始されたUnicastScanner.ps1/PSScript_{GUID}.ps1またはポート スキャン アクティビティでアラートが発生しました。どうすればよいですか?

アクティブなプローブ スクリプトは Microsoft によって署名され、安全です。 除外リストに次のパスを追加できます。 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps1`

## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Standard 検出アクティブ プローブによって生成されるトラフィックの量はどのくらいですか?

アクティブプローブでは、オンボードされたデバイスとプローブされたデバイスの間で最大 50 Kb のトラフィックを生成できます。プローブの試行ごとに

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>デバイス インベントリ内の "オンボードできる" デバイスと、ダッシュボード タイルの "オンボードするデバイス" の数に不一致があるのはなぜですか?

デバイス インベントリの [オンボードできる] の下に表示されるデバイスの数と、"オンボードからMicrosoft Defender for Endpoint" のセキュリティに関する推奨事項、および "オンボードするデバイス" ダッシュボード ウィジェットの数の違いに気付く場合があります。

 セキュリティに関する推奨事項とダッシュボード ウィジェットは、ネットワーク内で安定しているデバイス用です。エフェメラル デバイス、ゲスト デバイス、その他を除く。 このアイデアは、永続的なデバイスで推奨することです。これは、組織の全体的なセキュリティ スコアにも影響します。

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>見つかったアンマネージド デバイスをオンボードできますか?

はい。 アンマネージド デバイスは手動でオンボードできます。 ネットワーク内のアンマネージド エンドポイントは、ネットワークに脆弱性とリスクを発生させます。 サービスにオンボードすると、セキュリティの可視性が向上する可能性があります。

## <a name="ive-noticed-that-unmanaged-device-health-state-is-always-active-why-is-that"></a>アンマネージド デバイスの正常性状態が常に "アクティブ" であることがわかります。なぜですか?

一時的に、非管理対象デバイスの正常性状態は、実際の状態に関係なく、デバイス インベントリの標準保有期間中に "アクティブ" になります。

## <a name="does-standard-discovery-look-like-malicious-network-activity"></a>標準検出は悪意のあるネットワーク アクティビティのように見えますか?

Standard の検出を検討する場合は、プローブの影響、特にセキュリティ ツールが悪意のあるアクティビティを疑う可能性があるかどうかについて疑問に思うかもしれません。 次のサブセクションでは、ほとんどの場合、組織が Standard 検出を有効にすることに関する懸念がない理由について説明します。  

### <a name="probing-is-distributed-across-all-windows-devices-on-the-network"></a>プローブは、ネットワーク上のすべてのWindows デバイスに分散されます

通常、侵害された少数のデバイスからネットワーク全体をスキャンする悪意のあるアクティビティとは対照的に、Microsoft Defender for Endpointの Standard Discovery プローブは、オンボードされているすべてのWindows デバイスから開始され、アクティビティが無害で異常ではない状態になります。 プローブは、ネットワーク内でサポートされているすべてのオンボード デバイス間でプローブ試行のバランスを取るために、クラウドから一元的に管理されます。  

### <a name="active-probing-generates-negligible-amount-of-extra-traffic"></a>アクティブなプローブでは、余分なトラフィックの量がごくわずかです

アンマネージド デバイスは通常、3 週間に 1 回以上プローブされ、50 KB 未満のトラフィックが生成されます。 通常、悪意のあるアクティビティには、高い反復的なプローブ試行が含まれ、場合によっては、ネットワーク監視ツールによって異常として識別できる大量のネットワーク トラフィックを生成するデータ流出が含まれます。

### <a name="your-windows-device-already-runs-active-discovery"></a>Windows デバイスで既にアクティブな検出が実行されている

アクティブ検出機能は常にWindows オペレーティング システムに埋め込まれており、近くのデバイス、エンドポイント、プリンターを見つけて、ネットワーク内のエンドポイント間での"プラグ アンド プレイ" エクスペリエンスとファイル共有を簡単に行うことができます。 同様の機能は、いくつかの名前を付けるだけで、モバイル デバイス、ネットワーク機器、インベントリ アプリケーションに実装されています。  

Standard Discovery では、同じ検出方法を使用してデバイスを識別し、Microsoft 365 Defender デバイス インベントリ内のネットワーク内のすべてのデバイスの統一された可視性を実現します。 たとえば、Standard Discovery では、ネットワーク内の使用可能なプリンターを一覧表示するのと同じ方法で、ネットワーク内の近くのエンドポイントWindows識別します。 

ネットワーク のセキュリティと監視ツールは、ネットワーク上のデバイスによって実行されるこのようなアクティビティに無関心です。 

### <a name="only-unmanaged-devices-are-being-probed"></a>アンマネージド デバイスのみがプローブされている

デバイス検出機能は、ネットワーク上の管理されていないデバイスのみを検出して識別するように構築されています。 つまり、Microsoft Defender for Endpointで既にオンボードされている以前に検出されたデバイスはプローブされません。

### <a name="you-can-exclude-network-lures-from-active-probing"></a>アクティブなプローブからネットワーク ルアーを除外できます

Standard Discovery では、アクティブなプローブからのデバイスまたは範囲 (サブネット) の除外がサポートされます。 ネットワーク ルアーが配置されている場合は、デバイス検出設定を使用して、IP アドレスまたはサブネット (IP アドレスの範囲) に基づいて除外を定義できます。 これらの除外を定義すると、これらのデバイスが積極的にプローブされず、アラートが表示されなくなります。 これらのデバイスは、パッシブ メソッドのみを使用して検出されます (基本的な検出モードと同様)。
