---
title: iOS 機能用 Microsoft Defender for Endpoint を構成する
description: iOS 機能にMicrosoft Defender for Endpointをデプロイする方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.openlocfilehash: c52fac7c5680d8e5f814098410dc2e1993328d2f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476909"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>iOS 機能用 Microsoft Defender for Endpoint を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> iOS 上の Defender for Endpoint では、Web 保護機能を提供するために VPN が使用されます。 これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカル/セルフループ VPN です。

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>iOS 上の Defender for Endpoint を使用した条件付きアクセス

iOS でのMicrosoft Defender for EndpointとMicrosoft IntuneとAzure Active Directoryにより、デバイスリスク スコアに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。 Defender for Endpoint は、Intuneを介してこの機能を活用するためにデプロイできる Mobile Threat Defense (MTD) ソリューションです。

iOS で Defender for Endpoint を使用して条件付きアクセスを設定する方法の詳細については、「[Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection)」を参照してください。

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointによる脱獄検出

Microsoft Defender for Endpointには、脱獄されたアンマネージド デバイスとマネージド デバイスを検出する機能があります。 デバイスが脱獄されていることが検出された場合、**危険度の高い** アラートがMicrosoft 365 Defender ポータルに報告され、デバイス リスク スコアに基づいて条件付きアクセスが設定されている場合、デバイスは企業データへのアクセスをブロックされます。

## <a name="web-protection-and-vpn"></a>Web Protection と VPN

既定では、iOS 上の Defender for Endpoint には Web 保護機能が含まれており、有効になっています。 [Web 保護](web-protection-overview.md)は、Web の脅威からデバイスを保護し、フィッシング攻撃からユーザーを保護するのに役立ちます。 フィッシング対策とカスタム インジケーター (URL と IP アドレス) は、Web Protection の一部としてサポートされていることに注意してください。 現在、Web コンテンツ フィルターは iOS ではサポートされていません。

iOS 上の Defender for Endpoint では、この機能を提供するために VPN を使用します。 これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されないことに注意してください。

既定では有効になっていますが、VPN を無効にする必要がある場合があります。 たとえば、VPN が構成されているときに動作しないアプリを実行するとします。 このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にすることができます。

1. iOS デバイスで **、設定** アプリを開き、[**全般]**、[**VPN**] の順にクリックまたはタップします。
1. Microsoft Defender for Endpointの [i] ボタンをクリックまたはタップします。
1. オンデマンド **Connect** オフに切り替えて VPN を無効にします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-vpn-config.png" alt-text="VPN 構成Connectオンデマンド オプションのトグル ボタン" lightbox="images/ios-vpn-config.png":::

> [!NOTE]
> VPN が無効になっている場合、Web Protection は使用できません。 Web Protection を再度有効にするには、デバイスでMicrosoft Defender for Endpoint アプリを開き、[**VPN の開始**] をクリックまたはタップします。

## <a name="co-existence-of-multiple-vpn-profiles"></a>複数の VPN プロファイルの共存

Apple iOS では、同時にアクティブにする複数のデバイス全体の VPN はサポートされていません。 デバイスに複数の VPN プロファイルを存在させることができますが、一度にアクティブにできる VPN は 1 つだけです。

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>アプリ保護ポリシー (MAM) でMicrosoft Defender for Endpointリスクシグナルを構成する

Microsoft Defender for Endpointは、iOS/iPadOS 上の App Protection Policyes (MAM とも呼ばれる) で使用される脅威信号を送信するように構成できます。 この機能を使用すると、Microsoft Defender for Endpointを使用して、登録されていないデバイスから企業データへのアクセスを保護することもできます。

Microsoft Defender for Endpointを使用してアプリ保護ポリシーを設定する手順は次のとおりです。

1. Microsoft エンドポイント マネージャー テナントからMicrosoft Defender for Endpointへの接続を設定します。 [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**テナント管理** \> **コネクタとトークン** \> **Microsoft Defender for Endpoint** (クロス プラットフォームの下) または **Endpoint Security** \> **Microsoft Defender for Endpoint** ([セットアップ] の下) に移動し **、iOS 用の App Protection Policy 設定**。
1. [保存] を選択します。 **[接続の状態**] が **[有効]** に設定されていることがわかります。
1. アプリ保護ポリシーの作成: Microsoft Defender for Endpoint コネクタのセットアップが完了したら、[**アプリ** \> **アプリ保護 ポリシー**] ([ポリシー] の下) に移動して新しいポリシーを作成するか、既存のポリシーを更新します。
1. 組織がポリシーに必要とするプラットフォーム、 **アプリ、データ保護、アクセス要件** の設定を選択します。
1. **条件付き起動** \> **デバイスの条件** で、[**許可されるデバイスの最大脅威レベル**] の設定が表示されます。 これは、低、中、高、またはセキュリティで保護されるように構成する必要があります。 使用可能なアクションは、[アクセスを **ブロック]** または [ **データのワイプ]** になります。 この設定が有効になる前に、コネクタが設定されていることを確認する情報ダイアログが表示される場合があります。 コネクタが既に設定されている場合は、このダイアログを無視できます。
1. 割り当てを完了し、ポリシーを保存します。

MAM またはアプリ保護ポリシーの詳細については、「 [iOS アプリ保護ポリシーの設定](/mem/intune/apps/app-protection-policy-settings-ios)」を参照してください。

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>MAM または登録されていないデバイスにMicrosoft Defender for Endpointを展開する

iOS のMicrosoft Defender for Endpointは、App Protection Policy シナリオを有効にし、Apple アプリ ストアで使用できます。

エンド ユーザーは、Apple アプリ ストアから直接最新バージョンのアプリをインストールする必要があります。

## <a name="privacy-controls"></a>プライバシー コントロール

> [!IMPORTANT]
> iOS でのMicrosoft Defender for Endpointのプライバシー コントロールはプレビュー段階です。 次の情報は、市販される前に大幅に変更される可能性のあるプレリリース済み製品に関連しています。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

### <a name="configure-privacy-in-phish-alert-report"></a>フィッシング アラート レポートでプライバシーを構成する

お客様は、iOS でMicrosoft Defender for Endpointから送信されたフィッシング レポートのプライバシー制御を有効にできるようになりました。 これにより、フィッシング Web サイトが検出され、Microsoft Defender for Endpointによってブロックされるたびに、ドメイン名がフィッシング アラートの一部として送信されなくなります。

次の手順を使用してプライバシーを有効にし、フィッシング アラート レポートの一部としてドメイン名を収集しません。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**AppsApp** >  **構成****ポリシーAddManaged** >  >  デバイスに移動 **します**。
1. ポリシーに名前を付けます **。プラットフォーム > iOS/iPadOS**、プロファイルの種類を選択します。
1. ターゲット アプリとして **Microsoft Defender for Endpoint** を選択します。
1. 設定 ページで、[**構成デザイナーを使用** する] を選択し、キーとして **DefenderExcludeURLInReport** を追加し、値の型を **ブール型** として追加します。
   - プライバシーを有効にし、ドメイン名を収集しないようにするには、値を `true` 入力し、このポリシーをユーザーに割り当てます。 既定では、この値は `false`.
   - キーが設定されている `true`ユーザーの場合、Defender for Endpoint によって悪意のあるサイトが検出されてブロックされるたびに、フィッシング アラートにドメイン名情報は含まれません。
1. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

上記のプライバシー制御をオンまたはオフにしても、デバイスコンプライアンスチェックや条件付きアクセスには影響しません。

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>脱獄されたデバイスに対するコンプライアンス ポリシーを構成する

脱獄された iOS デバイスで企業データにアクセスできないようにするには、Intuneに次のコンプライアンス ポリシーを設定することをお勧めします。

> [!NOTE]
> 脱獄検出は、iOS 上のMicrosoft Defender for Endpointによって提供される機能です。 ただし、脱獄シナリオに対する防御の追加レイヤーとしてこのポリシーを設定することをお勧めします。

脱獄されたデバイスに対するコンプライアンス ポリシーを作成するには、次の手順に従います。

1. [管理センター Microsoft エンドポイント マネージャー](https://go.microsoft.com/fwlink/?linkid=2109431)**、****DevicesCompliance** ->  **policyesCreate** ->  Policy に移動します。 プラットフォームとして [iOS/iPadOS] を選択し、[ **作成**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-jb-policy.png" alt-text="[ポリシーの作成] タブ" lightbox="images/ios-jb-policy.png":::

2. ポリシーの名前 ("脱獄のコンプライアンス ポリシー" など) を指定します。
3. [コンプライアンス設定] ページで、[**デバイスの正常性**] セクションをクリックして展開し、[**脱獄されたデバイス** の **ブロック**] フィールドをクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-jb-settings.png" alt-text="[コンプライアンス設定] タブ" lightbox="images/ios-jb-settings.png":::

4. [ **非準拠のアクション]** セクションで、要件に従ってアクションを選択し、[ **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-jb-actions.png" alt-text="[非準拠のアクション] タブ" lightbox="images/ios-jb-actions.png":::

5. [ **割り当て** ] セクションで、このポリシーに含めるユーザー グループを選択し、[ **次へ**] を選択します。
6. [ **確認と作成** ] セクションで、入力されたすべての情報が正しいことを確認し、[ **作成**] を選択します。

## <a name="configure-custom-indicators"></a>カスタム インジケーターを構成する

iOS 上の Defender for Endpoint を使用すると、管理者は iOS デバイスでもカスタム インジケーターを構成できます。 カスタム インジケーターを構成する方法の詳細については、「インジケーターの [管理](/microsoft-365/security/defender-endpoint/manage-indicators)」を参照してください。

> [!NOTE]
> iOS 上の Defender for Endpoint では、IP アドレスと URL/ドメインに対してのみカスタム インジケーターを作成できます。

## <a name="configure-option-to-send-in-app-feedback"></a>アプリ内フィードバックを送信するオプションを構成する 

お客様は、Defender for Endpoint アプリ内で Microsoft にフィードバック データを送信する機能を構成できるようになりました。 フィードバック データは、Microsoft が製品を改善し、問題のトラブルシューティングを行うのに役立ちます。

> [!NOTE]
> 米国政府機関のクラウドのお客様の場合、フィードバック データ収集は既定で **無効になっています** 。 

次の手順に従って、フィードバック データを Microsoft に送信するオプションを構成します。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**AppsApp** >  **構成****ポリシーAddManaged** >  >  デバイスに移動 **します**。
1. ポリシーに名前を付けます **。プラットフォーム > iOS/iPadOS**、プロファイルの種類を選択します。
1. ターゲット アプリとして **Microsoft Defender for Endpoint** を選択します。
1. 設定 ページで、[**構成デザイナーを使用** する] を選択し、キーとして **DefenderSendFeedback** を追加し、値の型を **ブール型** として追加します。
   - エンド ユーザーがフィードバックを提供する機能を削除するには、値を設定 `false` し、このポリシーをユーザーに割り当てます。 既定では、この値は `true`. 米国政府機関のお客様の場合、既定値は "false" に設定されます。
   - キーが `true`設定されているユーザーの場合は、アプリ内でフィードバック データを Microsoft に送信するオプションがあります (メニュー > ヘルプ & フィードバック> Microsoft にフィードバックを送信する)
1. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。


## <a name="report-unsafe-site"></a>安全でないサイトを報告する

フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で、信頼できる Web サイトを偽装します。 フィッシング サイトである可能性がある Web サイトを報告する場合は、 [ネットワーク保護に関するフィードバックを提供](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) するページにアクセスしてください。
