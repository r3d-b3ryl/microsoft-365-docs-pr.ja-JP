---
title: iOS 上の Microsoft Defender for Endpoint の問題のトラブルシューティング
description: トラブルシューティングと FAQ - Microsoft Defender for Endpoint on iOS
keywords: microsoft、defender、Microsoft Defender for Endpoint、ios、トラブルシューティング、FAQ、方法
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 82a3fcc58b97f53f584befae77c86e8a18952a23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539325"
---
# <a name="troubleshoot-issues-on-microsoft-defender-for-endpoint-on-ios"></a>iOS 上の Microsoft Defender for Endpoint の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

このトピックでは、iOS で Microsoft Defender for Endpoint を使用する際に発生する可能性のある問題に対処するためのトラブルシューティング情報を提供します。



> [!NOTE]
> iOS 上のエンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。 これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>VPN が有効になっているとアプリが動作しない
アクティブな VPN が検出されると、機能を停止するアプリがあります。 このようなアプリを使用している間は、VPN を無効にできます。 

既定では、Defender for Endpoint on iOS には Web 保護機能が含まれています。 [Web 保護は](web-protection-overview.md) 、Web の脅威からデバイスを保護し、ユーザーをフィッシング攻撃から保護するのに役立ちます。 iOS のエンドポイントの Defender は、この保護を提供するために VPN を使用します。 これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。

既定で有効になっている場合は、VPN を無効にする必要がある場合があります。 たとえば、VPN が構成されているときに動作しないアプリを実行する場合です。 このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にできます。

1. iOS デバイスで、アプリを開き **設定[全般**] をクリック **またはタップ** し **、[VPN] をタップします**。
1. Microsoft Defender for Endpoint の "i" ボタンをクリックまたはタップします。
1. VPN を無効 **にするにはConnectをオフ** にします。

    > [!div class="mx-imgBorder"]
    > ![VPN 構成はオンデマンドで接続します](images/ios-vpn-config.png)

> [!NOTE]
> VPN が無効になっている場合、Web 保護は使用できません。 Web Protection を再び有効にするには、デバイスで Microsoft Defender for Endpoint アプリを開き、[VPN の開始] をクリックまたは **タップします**。

## <a name="issues-with-multiple-vpn-profiles"></a>複数の VPN プロファイルに関する問題

Apple iOS では、同時にアクティブになる複数のデバイス全体の VPN はサポートされていません。 デバイスに複数の VPN プロファイルを存在することができますが、一度にアクティブにできる VPN は 1 つのみです。


## <a name="battery-consumption"></a>バッテリー消費

アプリによるバッテリー使用量は、CPU やネットワークの使用状況など、さまざまな要因に基づいて Apple によって計算されます。 Microsoft Defender for Endpoint では、バックグラウンドでローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックを確認します。 任意のアプリからのネットワーク パケットは、このチェックを通過し、Microsoft Defender for Endpoint のバッテリー使用量が不正確に計算される原因になります。 これは、ユーザーに誤った印象を与えます。 Microsoft Defender for Endpoint の実際のバッテリー消費量は、デバイスの [バッテリー] ページに表示設定より小さいです。 これは、バッテリー消費を理解するために Microsoft Defender for Endpoint アプリで実施されたテストに基づいて行われます。

また、使用される VPN はローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。

## <a name="data-usage"></a>データの使用状況

Microsoft Defender for Endpoint では、ローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックを確認します。 このため、Apple は Microsoft Defender for Endpoint へのデータ使用量を不正確にアカウントします。 Microsoft Defender for Endpoint による実際のデータ使用量は、デバイス上のデータ使用量のデータ使用量に表示されるデータ使用量設定はるかに小さい値です。

## <a name="report-unsafe-site"></a>安全でないサイトを報告する

フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で信頼できる Web サイトになりすます。 [ネットワーク [保護に関するフィードバックを提供する](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) ] ページにアクセスして、フィッシング サイトになる可能性のある Web サイトを報告します。

## <a name="malicious-site-detected"></a>悪意のあるサイトが検出されました

Microsoft Defender for Endpoint は、フィッシングなどの Web ベースの攻撃からユーザーを保護します。 悪意のあるサイトが検出されると、接続がブロックされ、組織のセキュリティ センター ポータルにアラートが送信されます。 アラートには、接続のドメイン名、リモート IP アドレス、デバイスの詳細が含まれます。

さらに、iOS デバイスに通知が表示されます。 通知をタップすると、ユーザーが詳細を確認する次の画面が開きます。

> [!div class="mx-imgBorder"]
> ![安全でない通知として報告されたサイトの画像](images/ios-phish-alert.png)

## <a name="data-and-privacy"></a>データとプライバシー

収集されたデータとプライバシーの詳細については、「プライバシー情報 [- Microsoft Defender for Endpoint on iOS」を参照してください](ios-privacy.md)。

