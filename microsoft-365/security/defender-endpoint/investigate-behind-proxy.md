---
title: 転送プロキシの背後で発生する接続イベントの調査
description: プロキシの代わりに実際のターゲットを示すMicrosoft Defender for Endpointのネットワーク保護を通じて高度な HTTP レベルの監視を使用する方法について説明します。
keywords: プロキシ, ネットワーク保護, 転送プロキシ, ネットワーク イベント, 監査, ブロック, ドメイン名, ドメイン
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 580f41c24d6d78fb9e5ac7e20eb80e6ae78a505b
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469803"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>転送プロキシの背後で発生する接続イベントの調査

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Defender for Endpoint では、ネットワーク スタックのさまざまなレベルからのネットワーク接続の監視がサポートされます。 困難なケースは、ネットワークがインターネットへのゲートウェイとしてフォワード プロキシを使用する場合です。

プロキシは、それがターゲット エンドポイントであるかのように動作します。 このような場合、単純なネットワーク接続モニターは、正しいが調査値が低いプロキシとの接続を監査します。

Defender for Endpoint では、ネットワーク保護による高度な HTTP レベルの監視がサポートされています。 オンにすると、実際のターゲット ドメイン名を公開する新しい種類のイベントが表示されます。

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>ネットワーク保護を使用してファイアウォールの内側のネットワーク接続を監視する

転送プロキシの背後にあるネットワーク接続を監視することは、ネットワーク保護から発生する他のネットワーク イベントが原因で発生する可能性があります。 デバイスのタイムラインに表示するには、ネットワーク保護を有効にします (監査モードでは少なくとも)。

ネットワーク保護は、次のモードを使用して制御できます。

- **ブロック**: ユーザーまたはアプリは、危険なドメインへの接続をブロックされます。 このアクティビティは、Microsoft 365 Defenderで確認できます。
- **監査**: ユーザーまたはアプリが危険なドメインへの接続をブロックされることはありません。 ただし、このアクティビティはMicrosoft 365 Defenderに引き続き表示されます。


ネットワーク保護を無効にすると、ユーザーまたはアプリが危険なドメインへの接続をブロックされることはありません。 Microsoft 365 Defenderにネットワーク アクティビティは表示されません。

構成しない場合、ネットワークブロックは既定で無効になります。

詳細については、「 [ネットワーク保護を有効にする」を](enable-network-protection.md)参照してください。

## <a name="investigation-impact"></a>調査の影響

ネットワーク保護がオンになっていると、デバイスのタイムラインで IP アドレスがプロキシを表し続け、実際のターゲット アドレスが表示されます。

:::image type="content" source="images/atp-proxy-investigation.png" alt-text="デバイスのタイムライン上のネットワーク イベント" lightbox="images/atp-proxy-investigation.png":::

ネットワーク保護レイヤーによってトリガーされるその他のイベントは、プロキシの背後でも実際のドメイン名を表示するために使用できるようになりました。

イベントの情報:

:::image type="content" source="images/atp-proxy-investigation-event.png" alt-text="1 つのネットワーク イベントの URL" lightbox="images/atp-proxy-investigation-event.png":::

## <a name="hunt-for-connection-events-using-advanced-hunting"></a>高度なハンティングを使用して接続イベントを検出する

すべての新しい接続イベントを利用して、高度な捜索を行うこともできます。 これらのイベントは接続イベントであるため、DeviceNetworkEvents テーブルのアクションの種類の `ConnecionSuccess` 下にあります。

この単純なクエリを使用すると、関連するすべてのイベントが表示されます。

```console
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess"
| take 10
```

:::image type="content" source="images/atp-proxy-investigation-ah.png" alt-text="高度なハンティング クエリ" lightbox="images/atp-proxy-investigation-ah.png":::

プロキシ自体への接続に関連するイベントを除外することもできます。

次のクエリを使用して、プロキシへの接続を除外します。

```console
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"
| take 10
```

## <a name="related-topics"></a>関連項目

- [GP を使用したネットワーク保護の適用 - ポリシー CSP](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
