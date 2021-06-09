---
title: iOS の機能で Microsoft Defender for Endpoint を構成する
description: iOS 機能に Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.openlocfilehash: d32d40ac8ce086caedd53e0a69aac2a3025dc702
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842256"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>iOS の機能で Microsoft Defender for Endpoint を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> iOS 上のエンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。 これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>iOS 上のエンドポイント用 Defender を使用した条件付きアクセス  
Microsoft Defender for Endpoint on iOS および Microsoft Intune および Azure Active Directory を使用すると、デバイス のリスク スコアに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。 Defender for Endpoint は、Intune を介してこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。

iOS 上の Defender for Endpoint で条件付きアクセスを設定する方法の詳細については [、「Defender for Endpoint and Intune」を参照してください](/mem/intune/protect/advanced-threat-protection)。

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint による脱獄の検出
Microsoft Defender for Endpoint には、脱獄された管理されていないデバイスと管理対象デバイスを検出する機能があります。 デバイスが脱獄されたと検出された場合、危険度の高いアラートがセキュリティ センターに報告され、条件付きアクセスがデバイス リスク スコアに基づいてセットアップされている場合、デバイスは企業データへのアクセスをブロックされます。

## <a name="web-protection-and-vpn"></a>Web 保護と VPN

既定では、Defender for Endpoint on iOS には Web 保護機能が含まれています。 [Web 保護は](web-protection-overview.md) 、Web の脅威からデバイスを保護し、ユーザーをフィッシング攻撃から保護するのに役立ちます。 iOS のエンドポイントの Defender は、この保護を提供するために VPN を使用します。 これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されません。

既定で有効になっている場合は、VPN を無効にする必要がある場合があります。 たとえば、VPN が構成されているときに動作しないアプリを実行する場合です。 このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にできます。

1. iOS デバイスで、アプリを開き **設定[全般**] をクリック **またはタップ** し **、[VPN] をタップします**。
1. Microsoft Defender for Endpoint の "i" ボタンをクリックまたはタップします。
1. VPN を無効 **にするにはConnectをオフ** にします。

    > [!div class="mx-imgBorder"]
    > ![VPN 構成はオンデマンドで接続します](images/ios-vpn-config.png)

> [!NOTE]
> VPN が無効になっている場合、Web 保護は使用できません。 Web Protection を再び有効にするには、デバイスで Microsoft Defender for Endpoint アプリを開き、[VPN の開始] をクリックまたは **タップします**。

## <a name="co-existence-of-multiple-vpn-profiles"></a>複数の VPN プロファイルの共存在

Apple iOS では、同時にアクティブになる複数のデバイス全体の VPN はサポートされていません。 デバイスに複数の VPN プロファイルを存在することができますが、一度にアクティブにできる VPN は 1 つのみです。


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>脱獄されたデバイスに対するコンプライアンス ポリシーの構成

企業データが脱獄された iOS デバイスでアクセスされるのを保護するには、Intune で次のコンプライアンス ポリシーを設定することをお勧めします。

> [!NOTE]
> 脱獄検出は、iOS 上の Microsoft Defender for Endpoint によって提供される機能です。 ただし、脱獄シナリオに対する追加の防御層としてこのポリシーをセットアップすることをお勧めします。

以下の手順に従って、脱獄されたデバイスに対するコンプライアンス ポリシーを作成します。

1. 管理 [Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)デバイス コンプライアンス ポリシー  ->  **の作成ポリシー**]  ->  **に移動します**。 プラットフォームとして [iOS/iPadOS] を選択し、[作成] を **クリックします**。

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

iOS のエンドポイントの Defender を使用すると、管理者は iOS デバイス上のカスタム インジケーターも構成できます。 カスタム インジケーターを構成する方法の詳細については、「指標の管理」 [を参照してください](/microsoft-365/security/defender-endpoint/manage-indicators)。

> [!NOTE]
> IOS のエンドポイントの Defender は、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみをサポートしています。

## <a name="report-unsafe-site"></a>安全でないサイトを報告する

フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で信頼できる Web サイトになりすます。 フィッシング サイト [の可能性がある Web サイトを報告](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) する場合は、[ネットワーク保護に関するフィードバックを提供する] ページをご覧ください。

