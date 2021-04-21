---
title: iOS の機能で Microsoft Defender for Endpoint を構成する
description: iOS 機能に Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: microsoft、 defender, atp, ios, configure, features, ios
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
ms.openlocfilehash: f5f7345f92b3ac76aa647a9caed63e5684be9c30
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903312"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>iOS の機能で Microsoft Defender for Endpoint を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> IOS 用エンドポイントの Defender は、Web Protection 機能を提供するために VPN を使用します。 これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a>iOS 用エンドポイントの Defender を使用した条件付きアクセス  
Microsoft Defender for Endpoint on iOS、Microsoft Intune、Azure Active Directory を使用すると、デバイスのリスク レベルに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。 Defender for Endpoint は、Intune を介してこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。

IOS 用 Defender for Endpoint を使用して条件付きアクセスを設定する方法の詳細については [、「Defender for Endpoint and Intune」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。

## <a name="web-protection-and-vpn"></a>Web 保護と VPN

既定では、Defender for Endpoint for iOS には Web 保護機能が含まれています。 [Web 保護は](web-protection-overview.md) 、Web の脅威からデバイスを保護し、ユーザーをフィッシング攻撃から保護するのに役立ちます。 IOS 用エンドポイントの Defender は、この保護を提供するために VPN を使用します。 これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。

既定で有効になっている場合は、VPN を無効にする必要がある場合があります。 たとえば、VPN が構成されているときに動作しないアプリを実行する場合です。 このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にできます。

1. iOS デバイスで、[設定]**アプリを開** き、[全般] をクリックまたはタップ **し****、[VPN] をタップします**。
1. Microsoft Defender for Endpoint の "i" ボタンをクリックまたはタップします。
1. [オンデマンド接続 **] をオフにして** VPN を無効にします。

    > [!div class="mx-imgBorder"]
    > ![VPN 構成はオンデマンドで接続します](images/ios-vpn-config.png)

> [!NOTE]
> VPN が無効になっている場合、Web 保護は使用できません。 Web Protection を再び有効にするには、デバイスで Microsoft Defender for Endpoint アプリを開き、[VPN の開始] をクリックまたは **タップします**。

## <a name="co-existence-of-multiple-vpn-profiles"></a>複数の VPN プロファイルの共存在

Apple iOS では、同時にアクティブになる複数のデバイス全体の VPN はサポートされていません。 デバイスに複数の VPN プロファイルを存在することができますが、一度にアクティブにできる VPN は 1 つのみです。


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>脱獄されたデバイスに対するコンプライアンス ポリシーの構成

企業データが脱獄された iOS デバイスでアクセスされるのを保護するには、Intune で次のコンプライアンス ポリシーを設定することをお勧めします。

> [!NOTE]
> 現時点では、Microsoft Defender for Endpoint on iOS では、脱獄シナリオに対する保護は提供されません。 脱獄されたデバイスで使用する場合、特定のシナリオで、企業の電子メール ID や企業プロファイル画像 (利用可能な場合) など、アプリケーションで使用されるデータをローカルで公開できます

以下の手順に従って、脱獄されたデバイスに対するコンプライアンス ポリシーを作成します。

1. [Microsoft Endpoint Manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)デバイス コンプライアンス ポリシー  ->  **の作成ポリシー**  ->  **] に移動します**。 プラットフォームとして [iOS/iPadOS] を選択し、[作成] を **クリックします**。

    > [!div class="mx-imgBorder"]
    > ![ポリシーの作成](images/ios-jb-policy.png)

2. ポリシーの名前を指定します 。たとえば、「脱獄のコンプライアンス ポリシー」などです。
3. [コンプライアンス設定] ページで、[デバイスの正常性] セクションをクリック **し、[脱** 獄デバイスのブロック **] フィールドをクリック** します。

    > [!div class="mx-imgBorder"]
    > ![ポリシー設定](images/ios-jb-settings.png)

4. [非 *準拠のアクション] セクションで* 、要件に従ってアクションを選択し、[次へ] を選択 **します**。

    > [!div class="mx-imgBorder"]
    > ![ポリシーアクション](images/ios-jb-actions.png)

5. [割 *り当て* ] セクションで、このポリシーに含めるユーザー グループを選択し、[次へ] を **選択します**。
6. [レビュー **+ 作成] セクション** で、入力した情報が正しいか確認し、[作成] を **選択します**。

## <a name="configure-custom-indicators"></a>カスタム インジケーターの構成

Defender for Endpoint for iOS を使用すると、管理者は iOS デバイスでもカスタム インジケーターを構成できます。 カスタム インジケーターを構成する方法の詳細については、「指標の管理」 [を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)。

> [!NOTE]
> Defender for Endpoint for iOS では、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみをサポートしています。

## <a name="report-unsafe-site"></a>安全でないサイトを報告する

フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で信頼できる Web サイトになりすます。 フィッシング サイト [の可能性がある Web サイトを報告](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) する場合は、[ネットワーク保護に関するフィードバックを提供する] ページをご覧ください。

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a>Microsoft Defender for Endpoint がインストールされている場合の iOS でのバッテリー消費の問題

アプリによるバッテリー使用量は、CPU やネットワークの使用状況など、さまざまな要因に基づいて Apple によって計算されます。 Microsoft Defender for Endpoint では、バックグラウンドでローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックを確認します。 任意のアプリからのネットワーク パケットは、このチェックを通過し、Microsoft Defender for Endpoint のバッテリー使用量が不正確に計算される原因になります。 これは、ユーザーに誤った印象を与えます。 Microsoft Defender for Endpoint の実際のバッテリー消費量は、デバイスの [バッテリーの設定] ページに表示される値よりも少ない値です。 これは、バッテリー消費を理解するために Microsoft Defender for Endpoint アプリで実施されたテストに基づいて行われます。

また、使用される VPN はローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。
