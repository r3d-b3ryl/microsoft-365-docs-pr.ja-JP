---
title: iOSのMicrosoft Defender for Endpointに関連する FAQ に関する問題のトラブルシューティングと回答の検索
description: トラブルシューティングと FAQ - iOSのMicrosoft Defender for Endpoint
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, トラブルシューティング, FAQ, 方法
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ae6e65d99a82bdf4a9c0adbb740c6e5b969f4b68
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016330"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>iOS 上の Microsoft Defender for Endpoint で問題のトラブルシューティングを行い、FAQ に対する回答を見つける

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、iOSでMicrosoft Defender for Endpointを使用するときに発生する可能性がある問題に対処するために役立つトラブルシューティング情報を提供します。

> [!NOTE]
> iOS上の Defender for Endpoint では、Web 保護機能を提供するために VPN が使用されます。 これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカル/セルフループ VPN です。

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>VPN が有効になっているとアプリが機能しない
アクティブな VPN が検出されたときに機能を停止するアプリがいくつかあります。 このようなアプリを使用している間は、VPN を無効にすることができます。

既定では、iOS上の Defender for Endpoint には Web 保護機能が含まれており、有効になっています。 [Web 保護](web-protection-overview.md)は、Web の脅威からデバイスを保護し、フィッシング攻撃からユーザーを保護するのに役立ちます。 iOS上の Defender for Endpoint では、この保護を提供するために VPN が使用されます。 これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されないことに注意してください。

既定では有効になっていますが、VPN を無効にする必要がある場合があります。 たとえば、VPN が構成されているときに動作しないアプリを実行するとします。 このような場合は、Defender for Endpoint アプリから直接 VPN を無効にするか、次の手順を使用するかを選択できます。

1. iOS デバイスで、**設定** アプリを開き、[**全般**] をクリックまたはタップして、[**VPN**] をクリックまたはタップします。
1. Microsoft Defender for Endpointの [i] ボタンをクリックまたはタップします。
1. オンデマンド **Connect** オフに切り替えて VPN を無効にします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-vpn-config.png" alt-text="オンデマンド オプションのConnect" lightbox="images/ios-vpn-config.png":::

> [!NOTE]
> VPN が無効になっている場合、Web Protection は使用できません。 Web Protection を再度有効にするには、デバイスでMicrosoft Defender for Endpoint アプリを開き、Web 保護を有効にします。

## <a name="coexistence-with-multiple-vpn-profiles"></a>複数の VPN プロファイルとの共存

Apple iOSでは、複数の **デバイス全体の** VPN を同時にアクティブにすることはできません。 デバイスに複数の VPN プロファイルを存在させることができますが、一度にアクティブにできる VPN は 1 つだけです。 デバイスで別の VPN を使用する必要がある場合は、他の VPN を使用している間に Defender for Endpoint VPN を無効にすることができます。

## <a name="battery-consumption"></a>バッテリ消費量

Web ベースの脅威から常に保護するために、Microsoft Defender for Endpointは常にバックグラウンドで実行する必要があります。 これにより、デバイスの全体的なバッテリ消費量が若干増加する可能性があります。 バッテリの大幅な消耗が発生した場合は、 [フィードバックをお送](ios-troubleshoot.md#send-in-app-feedback) りください。調査を行います。

また、設定 アプリでは、iOS特定の期間、ユーザーに表示されるアプリのバッテリ使用量のみが表示されます。 画面に表示されるアプリのバッテリ使用量は、その期間のみであり、CPU やネットワークの使用状況など、さまざまな要因に基づいてiOSによって計算されます。 Microsoft Defender for Endpointでは、バックグラウンドでローカル/ループバック VPN を使用して、悪意のある Web サイトや接続の Web トラフィックをチェックします。 アプリからのネットワーク パケットはこのチェックを通過し、Microsoft Defender for Endpointのバッテリ使用量が不正確に計算されます。 Microsoft Defender for Endpointの実際のバッテリ消費量は、デバイスの [バッテリの設定] ページに表示される値より小さくなります。

使用される VPN はローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されないことに注意してください。

## <a name="data-usage"></a>データ使用量

Microsoft Defender for Endpointでは、ローカル/ループバック VPN を使用して、悪意のある Web サイトまたは接続の Web トラフィックを確認します。 このため、Microsoft Defender for Endpointデータの使用状況は不正確に考慮される可能性があります。 また、デバイスが携帯ネットワーク上にある場合、サービス プロバイダーによって報告されるデータ使用量は実際の消費量に非常に近いことがわかりますが、設定 アプリでは数値が不正確になる可能性があります。

他の VPN サービスでも同様の観察があります。

さらに、Microsoft Defender for Endpointがバックエンド サービスを最新の状態に保ち、より優れた保護を提供することが重要です。

## <a name="report-unsafe-site"></a>安全でないサイトを報告する

フィッシング Web サイトは、お客様の個人情報または財務情報を取得するために信頼できる Web サイトを偽装します。 フィッシング サイトである可能性がある Web サイトを報告するには、 [ネットワーク保護に関するフィードバックの提供](https://www.microsoft.com/wdsi/support/report-unsafe-site) ページにアクセスします。

## <a name="malicious-site-detected"></a>悪意のあるサイトが検出されました

Microsoft Defender for Endpointは、フィッシングやその他の Web ベースの攻撃から保護します。 悪意のあるサイトが検出されると、接続がブロックされ、アラートが組織のMicrosoft 365 Defender ポータルに送信されます。 アラートには、接続のドメイン名、リモート IP アドレス、デバイスの詳細が含まれます。

さらに、iOS デバイスに通知が表示されます。 通知をタップすると、次の画面が開き、ユーザーは詳細を確認できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/ios-phish-alert.png" alt-text="安全でない通知として報告されたサイト" lightbox="images/ios-phish-alert.png":::

## <a name="device-not-seen-on-the-defender-for-endpoint-console-after-onboarding"></a>オンボード後に Defender for Endpoint コンソールにデバイスが表示されない

オンボード後、Defender for Endpoint セキュリティ コンソールのデバイス インベントリにデバイスが表示されるまでに数時間かかります。 また、デバイスがAzure Active Directoryに正しく登録されていて、デバイスにインターネット接続があることを確認します。 オンボードに成功するには、デバイスをMicrosoft AuthenticatorまたはIntune ポータル サイト経由で登録する必要があります。ユーザーは、デバイスが Azure AD に登録されているのと同じアカウントを使用してサインインする必要があります。

> [!NOTE]
> 場合によっては、デバイス名がMicrosoft エンドポイント マネージャー (Intune) コンソールの名前と一致しない場合があります。 Defender for Endpoint コンソールのデバイス名は、モデル><username_iPhone/iPad形式です。 Azure AD デバイス ID を使用して、Defender for Endpoint コンソールでデバイスを識別することもできます。

## <a name="data-and-privacy"></a>データとプライバシー

収集されたデータとプライバシーの詳細については、「[プライバシー情報 - iOSのMicrosoft Defender for Endpoint」を](ios-privacy.md)参照してください。

## <a name="connectivity-issue-on-cellular-network"></a>携帯ネットワークでの接続の問題

携帯ネットワークでインターネット接続の問題が発生している場合は、Microsoft Defender for Endpoint携帯データネットワークが有効になっているかどうかを確認します。ms Defender >アプリ設定開>、MS Defender に対して "携帯データネットワーク" が有効になっていることを確認します。

接続に関する問題が解決していない場合は、飛行機モードをオン/オフにすることで問題を解決できるかどうかを確認してください。 問題が解決しない場合は、 [ログを送信してください](ios-troubleshoot.md#send-in-app-feedback)。

## <a name="issues-on-supervised-devices-with-content-filter-profile-installed"></a>コンテンツ フィルター プロファイルがインストールされている監視対象デバイスに関する問題

Defender for Endpoint コンテンツ フィルターがインストールされている監視対象デバイスに問題があります。 このようなデバイスでのインターネット接続の速度低下または待機時間が発生した場合は、デバイスからコンテンツ フィルター プロファイルをアンインストールまたは削除します。 この問題の解決に取り組んでおり、解決したらこの場所を更新します。 

## <a name="issues-during-app-updates-from-the-app-store"></a>アプリ ストアからのアプリの更新中の問題

アプリ ストアを介してアプリが更新されたときに問題が発生した場合 (自動更新または手動更新)、デバイスの再起動が必要になる場合があります。 それでも問題が解決しない場合は、Defender VPN を無効にしてアプリの更新を実行できます。 この問題を報告するために、アプリ内のフィードバックを提供することもできます。

## <a name="send-in-app-feedback"></a>アプリ内フィードバックを送信する

ユーザーが上記のセクションでまだ対処されていない問題に直面している場合、または一覧表示されている手順を使用して解決できない場合、ユーザーは診断データと共にアプリ内フィードバックを提供できます。 その後、チームはログを調査して適切なソリューションを提供します。 ユーザーは、次の手順を使用してフィードバックを送信できます。

- iOS/iPadOS デバイスで MSDefender アプリを開きます。
- 左上隅にあるメニュー (プロファイル アイコン) をタップします。
- [ **フィードバックの送信]** をタップします。
- 指定したオプションから選択します。 問題を報告するには、[ **気に入らない**] を選択します。
- 発生している問題の詳細を入力し、[ **診断データの送信]** をオンにします。 チームがソリューションまたはフォローアップのために連絡できるように、メール アドレスを含めてお勧めします。
- [ **送信] を** タップして、フィードバックを正常に送信します。
