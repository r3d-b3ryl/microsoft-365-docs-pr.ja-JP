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
ms.openlocfilehash: 0e1971ba9b2c65dd02411d237ab3886c58fa7003
ms.sourcegitcommit: e4882e3c66166ea7b834ad2e8fafeab42293e07d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67099285"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>iOS 機能用 Microsoft Defender for Endpoint を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> iOS 上の Defender for Endpoint では、Web 保護機能を提供するために VPN が使用されます。 これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカル/セルフループ VPN です。

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>iOS 上の Defender for Endpoint を使用した条件付きアクセス

iOS 上のMicrosoft Defender for Endpoint、Microsoft Intune、Azure Active Directory を使用すると、デバイス リスク スコアに基づいてデバイス コンプライアンスと条件付きアクセス ポリシーを適用できます。 Defender for Endpoint は、Intuneを介してこの機能を活用するためにデプロイできる Mobile Threat Defense (MTD) ソリューションです。

iOS で Defender for Endpoint を使用して条件付きアクセスを設定する方法の詳細については、「[Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection)」を参照してください。

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointによる脱獄検出

Microsoft Defender for Endpointには、脱獄されたアンマネージド デバイスとマネージド デバイスを検出する機能があります。 デバイスが脱獄されていることが検出された場合、**危険度の高い** アラートがMicrosoft 365 Defender ポータルに報告され、デバイス リスク スコアに基づいて条件付きアクセスが設定されている場合、デバイスは企業データへのアクセスをブロックされます。

## <a name="web-protection-and-vpn"></a>Web Protection と VPN

既定では、iOS 上の Defender for Endpoint には Web 保護機能が含まれており、有効になっています。 [Web 保護](web-protection-overview.md)は、Web の脅威からデバイスを保護し、フィッシング攻撃からユーザーを保護するのに役立ちます。 フィッシング対策とカスタム インジケーター (URL と IP アドレス) は、Web Protection の一部としてサポートされていることに注意してください。 現在、Web コンテンツ フィルターはモバイル プラットフォームではサポートされていません。

iOS 上の Defender for Endpoint では、この機能を提供するために VPN を使用します。 これはローカル VPN であり、従来の VPN とは異なり、ネットワーク トラフィックはデバイスの外部に送信されないことに注意してください。

既定では有効になっていますが、VPN を無効にする必要がある場合があります。 たとえば、VPN が構成されているときに動作しないアプリを実行するとします。 このような場合は、次の手順に従って、デバイス上のアプリから VPN を無効にすることができます。

1. iOS デバイスで **、[設定]** アプリを開き、[ **全般]** をクリックまたはタップして、[ **VPN**] をクリックまたはタップします。

2. Microsoft Defender for Endpointの [i] ボタンをクリックまたはタップします。

3. Vpn を無効にするには **、[オンデマンド接続]** をオフにします。 

   :::image type="content" source="images/ios-vpn-config.png" alt-text="VPN 構成の [オンデマンド接続] オプションのトグル ボタン" lightbox="images/ios-vpn-config.png":::

> [!NOTE]
> VPN が無効になっている場合、Web Protection は使用できません。 Web Protection を再度有効にするには、デバイスでMicrosoft Defender for Endpoint アプリを開き、[**VPN の開始**] をクリックまたはタップします。

## <a name="disable-web-protection"></a>Web 保護を無効にする

Web Protection は Defender for Endpoint の主要な機能の 1 つであり、その機能を提供するために VPN が必要です。 使用される VPN はローカル/ループバック VPN であり、従来の VPN ではありません。ただし、お客様が VPN を好まない理由はいくつかあります。 VPN を設定したくないお客様は、 **Web Protection** を無効にし、その機能なしで Defender for Endpoint をデプロイするオプションがあります。 その他の Defender for Endpoint 機能は引き続き機能します。

この構成は、登録済み (MDM) デバイスと登録されていない (MAM) デバイスの両方で使用できます。 MDM をお持ちのお客様の場合、管理者は App Config でマネージド デバイスを使用して **Web Protection** を構成できます。MAM を使用して登録していないお客様の場合、管理者は App Config でマネージド アプリを使用して **Web Protection** を構成できます。

### <a name="configure-web-protection"></a>Web Protection を構成する

1. **Web Protection(MDM) を無効にする** 登録済みデバイスの **Web Protection** を無効にするには、次の手順に従います。

    - [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**アプリ** > **アプリ構成ポリシー** >  [**管理対象デバイス** の **追加]** >  に移動します。
    - ポリシーに、 **プラットフォーム > iOS/iPadOS** という名前を付けます。
    - ターゲット アプリとしてMicrosoft Defender for Endpointを選択します。
    - [設定] ページで、[構成デザイナーの使用] を選択し、キーとして **WebProtection** を追加し、値の型を **ブール値** として追加します。
        - 既定では、 **WebProtection= true です**。
        - 管理 Web 保護をオフにするには **、WebProtection = false** にする必要があります。
        - Defender は、ユーザーがアプリを開くたびに、Microsoft 365 Defender ポータルにハートビートを送信します。
        - [次へ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

1. **Web Protection(MAM) を無効にする** 登録されていないデバイスの **Web Protection** を無効にするには、次の手順に従います。

    - [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、[**アプリ** > **アプリの構成ポリシー** > ]**[管理** アプリの **追加]** >  に移動します。
    - ポリシーに名前を付けます。
    - [パブリック アプリの選択] で、ターゲット アプリとして [Microsoft Defender for Endpoint] を選択します。
    - [設定] ページの [全般構成設定] で、キーとして **WebProtection** を追加し、 **値を false** として追加します。
        - 既定では、 **WebProtection= true です**。
        - 管理 Web 保護をオフにするには **、WebProtection = false** にする必要があります。
        - Defender は、ユーザーがアプリを開くたびに、Microsoft 365 Defender ポータルにハートビートを送信します。
        - [次へ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

## <a name="configure-network-protection"></a>Network Protection を構成する

>[!NOTE]
>Microsoft Defender for Endpointの Network Protection はパブリック プレビュー段階になりました。 次の情報は、製品が商用リリースされる前に大幅に変更される可能性がある製品のプレリリースに関連しています。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft Defender for endpoint のネットワーク保護は、既定で有効になっています。 管理者は、次の手順を使用して、iOS デバイスでのネットワーク保護の MAM サポートを構成できます。

1. Microsoft エンドポイント マネージャー 管理で、[アプリ> アプリ構成ポリシー] に移動します。 新しいアプリ構成ポリシーを作成します。
   :::image type="content" source="images/addiosconfig.png" alt-text="構成ポリシーを追加します。" lightbox="images/addiosconfig.png":::

2. ポリシーを一意に識別するための名前と説明を入力します。 次に、[パブリック アプリの選択] をクリックし、プラットフォーム iOS/IPadOS の [Microsoft Defender] を選択して :::image type="content" source="images/nameiosconfig.png" alt-text="構成を指定します。" lightbox="images/nameiosconfig.png":::

3. [設定] ページで、キーとして 'DefenderNetworkProtectionEnable' を追加し、値を "false" として追加してネットワーク保護を無効にします。 (ネットワーク保護は既定で有効になっています) :::image type="content" source="images/addiosconfigvalue.png" alt-text="構成値を追加します。" lightbox="images/addiosconfigvalue.png":::

4. ネットワーク保護に関連するその他の構成については、次のキーと適切な対応する値を追加します。

    |キー| 既定値 (true-enable、false-disable)|説明|
    |---|---|---|
    |DefenderEndUserTrustFlowEnable| false | ユーザーがネットワークと証明書を信頼できるようにする|
    |DefenderNetworkProtectionAutoRemediation| true |この設定は、IT 管理者が、より安全な WIFI アクセス ポイントへの切り替えや Defender によって検出された疑わしい証明書の削除などの修復アクティビティをユーザーが実行したときに送信される修復アラートを有効または無効にするために使用されます。|
    |DefenderNetworkProtectionPrivacy| true |この設定は、IT 管理者がネットワーク保護でプライバシーを有効または無効にするように管理されます。|
  
5. [割り当て] セクションで、管理者はポリシーに含めるユーザーと除外するユーザーのグループを選択できます。
   :::image type="content" source="images/assigniosconfig.png" alt-text="構成を割り当てます。" lightbox="images/assigniosconfig.png":::

6. 構成ポリシーを確認して作成します。

## <a name="co-existence-of-multiple-vpn-profiles"></a>複数の VPN プロファイルの共存

Apple iOS では、同時にアクティブにする複数のデバイス全体の VPN はサポートされていません。 デバイスに複数の VPN プロファイルを存在させることができますが、一度にアクティブにできる VPN は 1 つだけです。

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>アプリ保護ポリシー (MAM) でMicrosoft Defender for Endpointリスクシグナルを構成する

Microsoft Defender for Endpointは、iOS/iPadOS 上の App Protection Policyes (MAM とも呼ばれる) で使用される脅威信号を送信するように構成できます。 この機能を使用すると、Microsoft Defender for Endpointを使用して、登録されていないデバイスから企業データへのアクセスを保護することもできます。

Microsoft Defender for Endpointを使用してアプリ保護ポリシーを設定する手順は次のとおりです。

1. Microsoft エンドポイント マネージャー テナントからMicrosoft Defender for Endpointへの接続を設定します。 [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**テナント管理** \> **コネクタとトークン** \> **Microsoft Defender for Endpoint** (クロス プラットフォームの下) または **Endpoint Security** \> **Microsoft Defender for Endpoint** ([セットアップ] の下) に移動し **、iOS の App Protection ポリシー設定**。

2. [保存] を選択します。 **[接続の状態**] が **[有効]** に設定されていることがわかります。

3. アプリ保護ポリシーの作成: Microsoft Defender for Endpoint コネクタのセットアップが完了したら、[**アプリ** \> **アプリ保護 ポリシー**] ([ポリシー] の下) に移動して新しいポリシーを作成するか、既存のポリシーを更新します。

4. 組織がポリシーに必要とするプラットフォーム、 **アプリ、データ保護、アクセス要件** の設定を選択します。

5. **条件付き起動** \> **デバイスの条件** で、[**許可されるデバイスの最大脅威レベル**] の設定が表示されます。 これは、低、中、高、またはセキュリティで保護されるように構成する必要があります。 使用可能なアクションは、[アクセスを **ブロック]** または [ **データのワイプ]** になります。 この設定が有効になる前に、コネクタが設定されていることを確認する情報ダイアログが表示される場合があります。 コネクタが既に設定されている場合は、このダイアログを無視できます。

6. 割り当てを完了し、ポリシーを保存します。

MAM またはアプリ保護ポリシーの詳細については、「 [iOS アプリ保護ポリシーの設定](/mem/intune/apps/app-protection-policy-settings-ios)」を参照してください。

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>MAM または登録されていないデバイスにMicrosoft Defender for Endpointを展開する

iOS のMicrosoft Defender for Endpointは、App Protection Policy シナリオを有効にし、Apple アプリ ストアで使用できます。 エンド ユーザーは、Apple アプリ ストアから直接最新バージョンのアプリをインストールする必要があります。

## <a name="privacy-controls"></a>プライバシー コントロール

iOS のMicrosoft Defender for Endpointでは、管理者とエンド ユーザーの両方のプライバシー 制御が有効になります。 これには、登録された (MDM) デバイスと登録されていない (MAM) デバイスのコントロールが含まれます。
MDM をお持ちのお客様の場合、管理者は App Config でマネージド デバイスを介してプライバシー コントロールを構成できます。登録していないお客様の場合は、MAM を使用して、管理者は App Config でマネージド アプリを使用してプライバシー コントロールを構成できます。エンド ユーザーは、Defender アプリの設定からプライバシー設定を構成することもできます。

### <a name="configure-privacy-in-phish-alert-report"></a>フィッシング アラート レポートでプライバシーを構成する

お客様は、iOS でMicrosoft Defender for Endpointから送信されたフィッシング レポートのプライバシー制御を有効にできるようになりました。 これにより、フィッシング Web サイトが検出され、Microsoft Defender for Endpointによってブロックされるたびに、ドメイン名がフィッシング アラートの一部として送信されなくなります。

1. **管理 プライバシー制御 (MDM)** 次の手順を使用してプライバシーを有効にし、登録済みデバイスのフィッシング アラート レポートの一部としてドメイン名を収集しません。

    - [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**アプリ** > **アプリ構成ポリシー** >  [**管理対象デバイス** の **追加]** >  に移動します。

    - ポリシーに名前を付けます **。プラットフォーム > iOS/iPadOS**、プロファイルの種類を選択します。

    - ターゲット アプリとして **Microsoft Defender for Endpoint** を選択します。

    - [設定] ページで、[ **構成デザイナーの使用** ] を選択し、キーとして **DefenderExcludeURLInReport** を追加し、値の型を **ブール型** として追加します。

      - プライバシーを有効にし、ドメイン名を収集しないようにするには、値を `true` 入力し、このポリシーをユーザーに割り当てます。 既定では、この値は `false`.

      - キーが設定されている `true`ユーザーの場合、Defender for Endpoint によって悪意のあるサイトが検出されてブロックされるたびに、フィッシング アラートにドメイン名情報は含まれません。

    - [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

1. **管理 プライバシー制御 (MAM)** 次の手順を使用してプライバシーを有効にし、登録されていないデバイスのフィッシング アラート レポートの一部としてドメイン名を収集しません。

    - [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、[**アプリ** > **アプリの構成ポリシー** > ]**[管理** アプリの **追加]** >  に移動します。

    - ポリシーに名前を付けます。

    - [パブリック アプリの選択] で、ターゲット アプリとして **[Microsoft Defender for Endpoint**] を選択します。

    - [設定] ページの [  **全般構成設定]** で、 **DefenderExcludeURLInReport** をキーとして追加し、 **値を true** として追加します。

      - プライバシーを有効にし、ドメイン名を収集しないようにするには、値を `true` 入力し、このポリシーをユーザーに割り当てます。 既定では、この値は `false`.

      - キーが設定されている `true`ユーザーの場合、Defender for Endpoint によって悪意のあるサイトが検出されてブロックされるたびに、フィッシング アラートにドメイン名情報は含まれません。

    - [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

1. **エンド ユーザーのプライバシー制御** これらのコントロールは、エンド ユーザーが組織と共有する情報を構成するのに役立ちます。
    - 監視対象デバイスの場合、エンド ユーザー コントロールは表示されません。 管理は設定を決定し、制御します。
    - ただし、教師なしデバイスの場合は、[**設定] > [プライバシー]** の下にコントロールが表示されます。
        - ユーザーには **、安全でないサイト情報** の切り替えが表示されます。
        - このトグルは、**管理が DefenderExcludeURLInReport = true** を設定している場合にのみ表示されます
        - 管理によって有効になっている場合、ユーザーは安全でないサイト情報を組織に送信するかどうかを決定できます。
        - 既定では、安全 `true`でないサイト情報が送信されます。
        - ユーザーがユーザーに `false`切り替えると、安全でないサイトの詳細は送信されません。

上記のプライバシー制御をオンまたはオフにしても、デバイスコンプライアンスチェックや条件付きアクセスには影響しません。

## <a name="optional-permissions"></a>オプションのアクセス許可

iOS のMicrosoft Defender for Endpointでは、オンボード フローで **オプションのアクセス許可** が有効になります。 現在、MDE で必要なアクセス許可は、オンボード フローで必須です。 この機能を使用すると、管理者は、オンボード中に必須の **VPN アクセス許可** を強制することなく、BYOD デバイスに MDE をデプロイできます。 エンド ユーザーは、必須のアクセス許可なしでアプリをオンボードでき、後でこれらのアクセス許可を確認できます。 この機能は現在、登録済みデバイス (MDM) にのみ存在します。

### <a name="configure-optional-permission"></a>省略可能なアクセス許可を構成する

1. **管理 フロー (MDM)** 次の手順を使用して、登録済みデバイスに **対するオプションの VPN** アクセス許可を有効にします。

    - [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**アプリ** > **アプリ構成ポリシー** >  [**管理対象デバイス** の **追加]** >  に移動します。

    - ポリシーに名前を付け、[ **プラットフォーム > iOS/iPadOS**] を選択します。

    - ターゲット アプリとして **Microsoft Defender for Endpoint** を選択します。

    - [設定] ページで、[ **構成デザイナーの使用** ] を選択し、キーとして **DefenderOptionalVPN** を追加し、値の型を **ブール値** として追加します。

      - オプションの VPN アクセス許可を有効にするには、値を `true` 入力し、このポリシーをユーザーに割り当てます。 既定では、この値は `false`.
      - キーが設定されている `true`ユーザーの場合、ユーザーは VPN アクセス許可を付与せずにアプリをオンボードできます。

    - [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。
1. **エンド ユーザー フロー** - ユーザーがアプリをインストールして開き、オンボードを開始します。
    - 管理者がオプションのアクセス許可を設定している場合、ユーザーは VPN アクセス許可を **スキップ** してオンボードを完了できます。
    - ユーザーが VPN をスキップした場合でも、デバイスはオンボードでき、ハートビートが送信されます。
    - 無効になっているため `VPN` 、 `Web Protection` アクティブになりません。
    - 後で、ユーザーはアプリ内で From を `Web Protection` 有効にすることができます。 これにより、デバイスに VPN 構成がインストールされます。

> [!NOTE]
>**省略可能なアクセス許可** は、 **Web 保護の無効化** とは異なります。 オプションの VPN アクセス許可は、オンボード中にアクセス許可をスキップする場合にのみ役立ちますが、エンド ユーザーが後で確認して有効にできます。 **Web Protection を無効にすると**、ユーザーは Web Protection なしで MDE アプリをオンボードできます。 後で有効にすることはできません。

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>脱獄されたデバイスに対するコンプライアンス ポリシーを構成する

脱獄された iOS デバイスで企業データにアクセスできないようにするには、Intuneに次のコンプライアンス ポリシーを設定することをお勧めします。

> [!NOTE]
> 脱獄検出は、iOS 上のMicrosoft Defender for Endpointによって提供される機能です。 ただし、脱獄シナリオに対する防御の追加レイヤーとしてこのポリシーを設定することをお勧めします。

脱獄されたデバイスに対するコンプライアンス ポリシーを作成するには、次の手順に従います。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、[**デバイス** -> **コンプライアンス ポリシー** の **作成ポリシー** -> ] に移動します。 プラットフォームとして [iOS/iPadOS] を選択し、[ **作成**] をクリックします。

   :::image type="content" source="images/ios-jb-policy.png" alt-text="[ポリシーの作成] タブ" lightbox="images/ios-jb-policy.png":::

1. ポリシーの名前 ("脱獄のコンプライアンス ポリシー" など) を指定します。

1. [コンプライアンス設定] ページで、[**デバイスの正常性**] セクションをクリックして展開し、[**脱獄されたデバイス** の **ブロック**] フィールドをクリックします。

   :::image type="content" source="images/ios-jb-settings.png" alt-text="[コンプライアンス設定] タブ" lightbox="images/ios-jb-settings.png":::

1. [ **非準拠のアクション]** セクションで、要件に従ってアクションを選択し、[ **次へ**] を選択します。

   :::image type="content" source="images/ios-jb-actions.png" alt-text="[非準拠のアクション] タブ" lightbox="images/ios-jb-actions.png":::

1. [ **割り当て** ] セクションで、このポリシーに含めるユーザー グループを選択し、[ **次へ**] を選択します。

1. [ **確認と作成** ] セクションで、入力されたすべての情報が正しいことを確認し、[ **作成**] を選択します。

## <a name="configure-custom-indicators"></a>カスタム インジケーターを構成する

iOS 上の Defender for Endpoint を使用すると、管理者は iOS デバイスでもカスタム インジケーターを構成できます。 カスタム インジケーターを構成する方法の詳細については、「インジケーターの [管理](/microsoft-365/security/defender-endpoint/manage-indicators)」を参照してください。

> [!NOTE]
> iOS 上の Defender for Endpoint では、IP アドレスと URL/ドメインに対してのみカスタム インジケーターを作成できます。

## <a name="configure-option-to-send-in-app-feedback"></a>アプリ内フィードバックを送信するオプションを構成する

お客様は、Defender for Endpoint アプリ内で Microsoft にフィードバック データを送信する機能を構成できるようになりました。 フィードバック データは、Microsoft が製品を改善し、問題のトラブルシューティングを行うのに役立ちます。

> [!NOTE]
> 米国政府機関のクラウドのお客様の場合、フィードバック データ収集は既定で **無効になっています** 。

次の手順に従って、フィードバック データを Microsoft に送信するオプションを構成します。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**Apps** > **App 構成ポリシー** > の **[管理対象デバイス****の追加]** >  に移動します。

1. ポリシーに名前を付けます **。プラットフォーム > iOS/iPadOS**、プロファイルの種類を選択します。

1. ターゲット アプリとして **Microsoft Defender for Endpoint** を選択します。

1. [設定] ページで、[ **構成デザイナーの使用** ] を選択し、キーとして **DefenderSendFeedback** を追加し、値の型を **ブール型** として追加します。
   
   - エンド ユーザーがフィードバックを提供する機能を削除するには、値を設定 `false` し、このポリシーをユーザーに割り当てます。 既定では、この値は `true`. 米国政府機関のお客様の場合、既定値は "false" に設定されます。
   
   - キーが `true`設定されているユーザーの場合は、アプリ内でフィードバック データを Microsoft に送信するオプションがあります (メニュー > ヘルプ & フィードバック> Microsoft にフィードバックを送信する)

1. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

## <a name="report-unsafe-site"></a>安全でないサイトを報告する

フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で、信頼できる Web サイトを偽装します。 フィッシング サイトである可能性がある Web サイトを報告する場合は、 [ネットワーク保護に関するフィードバックを提供](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) するページにアクセスしてください。
