---
title: ブロック モードでのエンドポイントの検出と応答
description: ブロック モードでのエンドポイントでの検出と対応の詳細
keywords: Microsoft Defender for Endpoint、mde、ブロック モードでのEDR、パッシブ モードのブロック
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
- admindeeplinkDEFENDER
ms.date: 04/04/2022
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: 5a9441a41db2dfbe53bfb280152c038e9dbc383e
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789846"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>ブロック モードのエンドポイントでの検出と対応 (EDR)

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>ブロック モードでEDRとは何ですか?

ブロック モードの[エンドポイントの検出と応答](overview-endpoint-detection-response.md) (EDR) は、プライマリウイルス対策製品ではなくパッシブ モードで実行されている場合に、悪意のある成果物からの保護を追加Microsoft Defender ウイルス対策提供します。 ブロック モードのEDRは、EDR機能によって検出された悪意のあるアーティファクトを修復するためにバックグラウンドで機能します。 このような成果物は、Microsoft 以外のプライマリウイルス対策製品によって見逃されている可能性があります。 Microsoft Defender ウイルス対策をプライマリ ウイルス対策として実行しているデバイスの場合、ブロック モードのEDRは、違反後の動作EDR検出に対してMicrosoft Defender ウイルス対策が自動アクションを実行できるようにすることで、防御の追加レイヤーを提供します。

> [!IMPORTANT]
> ブロック モードのEDRでは、リアルタイム保護が有効になっている場合に使用可能なすべての保護Microsoft Defender ウイルス対策提供されるわけではありません。 次の主要な例を含め、アクティブなウイルス対策ソリューションであるMicrosoft Defender ウイルス対策に依存するすべての機能は機能しません。
>
> - オンアクセス スキャンを含むリアルタイム保護は、Microsoft Defender ウイルス対策がパッシブ モードの場合は使用できません。 リアルタイム保護ポリシー設定の詳細については、「**[常時オン保護Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)**」を参照してください。
>
> - **[ネットワーク保護](network-protection.md)** や **[攻撃面の縮小ルール](attack-surface-reduction.md)** などの機能は、Microsoft Defender ウイルス対策がアクティブ モードで実行されている場合にのみ使用できます。
>
> Microsoft 以外のウイルス対策ソリューションでは、これらの機能が提供されることが予想されます。

ブロック モードのEDRは、[脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)と統合されます。 組織のセキュリティ チームは、EDRがまだ有効になっていない場合は、ブロック モードで有効にする[セキュリティに関する推奨事項](tvm-security-recommendation.md)を取得します。

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="ブロック モードでEDRを有効にするための推奨事項" lightbox="images/edrblockmode-TVMrecommendation.png":::

> [!TIP]
> 最適な保護を得るには、必ず **[Microsoft Defender for Endpointベースラインをデプロイ](configure-machines-security-baseline.md)** してください。

## <a name="what-happens-when-something-is-detected"></a>何かが検出されるとどうなりますか?

ブロック モードのEDRがオンになっていて、悪意のあるアーティファクトが検出されると、そのアーティファクトをブロックして修復Microsoft Defender for Endpoint。 セキュリティ運用チームは、[アクション センター](respond-machine-alerts.md#check-activity-details-in-action-center)で検出状態が **ブロック** または **禁止と表示され**、完了したアクションとして一覧表示されます。

次の図は、ブロック モードでEDRによって検出され、ブロックされた不要なソフトウェアのインスタンスを示しています。

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="ブロック モードでのEDRによる検出" lightbox="images/edr-in-block-mode-detection.png":::


## <a name="enable-edr-in-block-mode"></a>ブロック モードでEDRを有効にする

> [!IMPORTANT]
> プラットフォーム バージョン 4.18.2202.X 以降では、Intune CSP を使用して特定のデバイス グループをターゲットにするようにブロック モードでEDRを設定できるようになりました。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>では、引き続きブロック モードのテナント全体でEDRを設定できます。 ブロック モードのEDRは、主にパッシブ モードでMicrosoft Defender ウイルス対策を実行しているデバイス (Microsoft 以外のウイルス対策ソリューションがデバイスにインストールされ、アクティブ) に推奨されます。 

> [!TIP]
> ブロック モードでEDRを有効にする前に[、要件](#requirements-for-edr-in-block-mode)が満たされていることを確認します。

### <a name="security-portal"></a>セキュリティ ポータル 

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) に移動してサインインします。

2. [エンドポイント **の一般的** \> **な高度な機能****設定**\>選択 **します**\>。

3. 下にスクロールし、**ブロック モードで [EDRを有効にする]** をオンにします。

### <a name="intune"></a>Intune

Intuneでカスタム ポリシーを作成するには、「[Intuneを介して CSP をターゲットにするOMA-URIsをデプロイする」とオンプレミスとの比較に関するページを参照してください](/troubleshoot/mem/intune/deploy-oma-uris-to-target-csp-via-intune)。

ブロック モードでEDRに使用される Defender CSP の詳細については、「[Defender CSP](/windows/client-management/mdm/defender-csp)」の「Configuration/PassiveRemediation」を参照してください。


## <a name="requirements-for-edr-in-block-mode"></a>ブロック モードでのEDRの要件

次の表に、ブロック モードでのEDRの要件を示します。

|要件|詳細|
|---|---|
|アクセス許可|[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)には、グローバル管理者ロールまたはセキュリティ管理者ロールが割り当てられている必要があります。 詳細については、「 [基本的なアクセス許可](basic-permissions.md)」を参照してください。|
|オペレーティング システム|デバイスは、次のいずれかのバージョンのWindowsを実行している必要があります。 <br/>- Windows 11 <br/>- Windows 10 (すべてのリリース)<br/>- Windows Server 2022 <br/>- Windows Server 2019<br/>- Windows Server バージョン 1803 以降<br/>- Windows Server 2016とWindows Server 2012 R2 ([新しい統合クライアント ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)を使用)<sup>[[1](#fn1)]</sup>  |
|Microsoft Defender for Endpoint|デバイスは Defender for Endpoint にオンボードする必要があります。 次の記事をご覧ください。 <br/>- [Microsoft Defender for Endpointの最小要件](minimum-requirements.md)<br/>- [デバイスのオンボードとMicrosoft Defender for Endpoint機能の構成](onboard-configure.md)<br/>- [Windows サーバーを Defender for Endpoint サービスにオンボードする](configure-server-endpoints.md)<br/>- [最新の統合ソリューションの新しいWindows Server 2012 R2 および 2016 機能 (プレビュー)](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) |
|Microsoft Defender ウイルス対策|デバイスはMicrosoft Defender ウイルス対策アクティブ モードまたはパッシブ モードでインストールおよび実行されている必要があります。 [Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードになっていることを確認](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)します。|
|クラウドによる保護|[クラウド配信](enable-cloud-protection-microsoft-defender-antivirus.md)保護が有効になるようにMicrosoft Defender ウイルス対策を構成する必要があります。|
|Microsoft Defender ウイルス対策 プラットフォーム|デバイスは最新の状態である必要があります。 PowerShell を使用して確認するには、管理者として [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを実行します。 **AMProductVersion** 行には、**4.18.2001.10** 以降が表示されます。 <p> 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。|
|Microsoft Defender ウイルス対策 エンジン|デバイスは最新の状態である必要があります。 PowerShell を使用して確認するには、管理者として [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを実行します。 **AMEngineVersion** 行には、**1.1.16700.2** 以降が表示されます。 <p> 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。|

(<a id="fn1">1</a>) [Windows Server 2016および Windows Server 2012 R2 でブロック モードでEDRがサポートされているか](#is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2)を参照してください。

> [!IMPORTANT]
> 最適な保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成されていること、および [除外が構成されていることを](configure-exclusions-microsoft-defender-antivirus.md)確認します。 ブロック モードのEDRでは、Microsoft Defender ウイルス対策に対して定義されているが、Microsoft Defender for Endpointに対して定義されている[インジケーター](manage-indicators.md)には定義されていない除外が適用されます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="can-i-specify-exclusions-for-edr-in-block-mode"></a>ブロック モードでEDRの除外を指定できますか?

誤検知を受け取った場合は、[Microsoft セキュリティ インテリジェンス送信サイト](https://www.microsoft.com/en-us/wdsi/filesubmission)で分析用にファイルを送信できます。

Microsoft Defender ウイルス対策の除外を定義することもできます。 「[Microsoft Defender ウイルス対策のスキャンの除外を構成および検証する](configure-exclusions-microsoft-defender-antivirus.md)」を参照してください。

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>デバイスでMicrosoft Defender ウイルス対策を実行している場合、ブロック モードでEDRを有効にする必要がありますか?

ブロック モードでのEDRの主な目的は、Microsoft 以外のウイルス対策製品によって見逃された違反後の検出を修復することです。 Microsoft Defender ウイルス対策がアクティブ モードの場合にブロック モードでEDRを有効にすることには最小限の利点があります。リアルタイム保護は検出を最初にキャッチして修復することが期待されるためです。 Microsoft Defender for Antivirus がパッシブ モードで実行されているエンドポイントでは、ブロック モードでEDRを有効にすることをお勧めします。 EDR検出は、[PUA 保護](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)またはブロック モードでの[自動調査&修復機能](automated-investigations.md)によって自動的に修復できます。

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>ブロック モードのEDRは、ユーザーのウイルス対策保護に影響しますか?

ブロック モードのEDRは、ユーザーのデバイスで実行されているサードパーティのウイルス対策保護には影響しません。 ブロック モードのEDRは、プライマリウイルス対策ソリューションが何かを見逃した場合、または違反後の検出がある場合に機能します。 ブロック モードのEDRは、パッシブ モードのMicrosoft Defender ウイルス対策と同様に機能します。ただし、ブロック モードのEDRでは、検出された悪意のあるアーティファクトや動作もブロックおよび修復されます。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Microsoft Defender ウイルス対策を最新の状態に保つ必要があるのはなぜですか?

Microsoft Defender ウイルス対策は悪意のあるアイテムを検出して修復するため、最新の状態に保つことが重要です。 ブロック モードのEDRを有効にするには、最新のデバイスラーニング モデル、動作検出、ヒューリスティックを使用します。 [Defender for Endpoint](microsoft-defender-endpoint.md) スタックの機能は、統合された方法で機能します。 最適な保護値を取得するには、Microsoft Defender ウイルス対策を最新の状態に保つ必要があります。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。

### <a name="why-do-we-need-cloud-protection-maps-on"></a>クラウド保護 (MAPS) が必要な理由

デバイスで機能を有効にするには、クラウド保護が必要です。 クラウド保護により [、Defender for Endpoint](microsoft-defender-endpoint.md) は、幅広さと深いセキュリティ インテリジェンスに基づいて、最新かつ最大の保護を、行動学習モデルとデバイスラーニング モデルと共に提供できます。

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>アクティブ モードとパッシブ モードの違いは何ですか?

Windows 10、Windows 11、Windows Server バージョン 1803 以降、Windows Server 2019、またはWindows Server 2022 を実行しているエンドポイントの場合、Microsoft Defender ウイルス対策がアクティブ モードになっている場合は、デバイスのプライマリ ウイルス対策として使用されます。 パッシブ モードで実行している場合、Microsoft Defender ウイルス対策はプライマリウイルス対策製品ではありません。 この場合、脅威はリアルタイムでMicrosoft Defender ウイルス対策によって修復されません。

> [!NOTE]
> Microsoft Defender ウイルス対策は、デバイスがMicrosoft Defender for Endpointにオンボードされている場合にのみパッシブ モードで実行できます。

詳細については、「[Microsoft Defender ウイルス対策の互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードになっていることを確認操作方法。

Microsoft Defender ウイルス対策がアクティブ モードまたはパッシブ モードで実行されているかどうかを確認するには、Windowsを実行しているデバイスでコマンド プロンプトまたは PowerShell を使用します。

|Method|プロシージャ|
|---|---|
|PowerShell|1. スタート メニューを選択し、入力`PowerShell`を開始し、結果のWindows PowerShellを開きます。<br/><br/>2. 「. 」と入力します `Get-MpComputerStatus`。<br/><br/>3. 結果の一覧の **AMRunningMode** 行で、次のいずれかの値を探します。<br/>- `Normal`<br/>- `Passive Mode`<br/><br/>詳細については、「 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)」を参照してください。|
|コマンド プロンプト|1. スタート メニューを選択し、入力`Command Prompt`を開始し、結果Windowsコマンド プロンプトを開きます。<br/><br/>2. 「. 」と入力します `sc query windefend`。<br/><br/>3. 結果の一覧の **STATE** 行で、サービスが実行されていることを確認します。 |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>ブロック モードのEDRがパッシブ モードのMicrosoft Defender ウイルス対策でオンになっていることを確認操作方法。

PowerShell を使用すると、Microsoft Defender ウイルス対策がパッシブ モードで実行されているブロック モードのEDRがオンになっていることを確認できます。

1. スタート メニューを選択し、入力`PowerShell`を開始し、結果のWindows PowerShellを開きます。

2. 種類 `Get-MPComputerStatus|select AMRunningMode`。

3. 結果 `EDR Block Mode`が表示されていることを確認します。

   > [!TIP]
   > Microsoft Defender ウイルス対策がアクティブ モードの場合は`Normal``EDR Block Mode`、 . 詳細については、「 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)」を参照してください。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2"></a>EDRは、Windows Server 2016および Windows Server 2012 R2 でブロック モードでサポートされていますか?

Microsoft Defender ウイルス対策がアクティブ モードまたはパッシブ モードで実行されている場合、ブロック モードのEDRは、次のバージョンのWindowsでサポートされます。

- Windows 11
- Windows 10 (すべてのリリース)
- Windows Server バージョン 1803 以降 
- Windows Server 2022
- Windows Server 2019 
- R2 のWindows Server 2016とWindows Server 2012 ([新しい統合クライアント ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)を使用)

Windows Server 2016およびWindows Server 2012 R2 用の[新しい統合クライアント ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)を使用すると、パッシブ モードまたはアクティブ モードでブロック モードでEDRを実行できます。

> [!NOTE]
> この機能を機能させるには、「オンボード Windows サーバー」の手順に従って[、Windows Server 2016およびWindows Server 2012](configure-server-endpoints.md) R2 をオンボードする必要があります。 

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>ブロック モードのEDRが無効になるのにどのくらいの時間がかかりますか?

ブロック モードでEDRを無効にすることを選択した場合、システムがこの機能を無効にするには最大で 30 分かかることがあります。

## <a name="see-also"></a>関連項目

- [Tech Community ブログ: ブロック モードでのEDRの概要: トラックでの攻撃の停止](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)

- [動作ブロックと封じ込め](behavioral-blocking-containment.md)
