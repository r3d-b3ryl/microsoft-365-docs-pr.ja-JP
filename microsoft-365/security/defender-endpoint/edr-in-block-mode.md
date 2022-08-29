---
title: ブロック モードでのエンドポイントの検出と応答
description: ブロック モードでのエンドポイントの検出と応答について学習する
keywords: Microsoft Defender for Endpoint、mde、ブロック モードの EDR、パッシブ モードのブロック
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
ms.date: 08/19/2022
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: bc15acb2a78350cff367e33f26f47e283c8b07b8
ms.sourcegitcommit: c81f6c39ed39d017f9d7c5f13148cd8d17b25c3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2022
ms.locfileid: "67392738"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>ブロック モードのエンドポイントでの検出と対応 (EDR)

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**

- Windows

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>ブロック モードの EDR とは

ブロック モードの[エンドポイント検出と応答](overview-endpoint-detection-response.md) (EDR) は、Microsoft Defender ウイルス対策 (MDAV) がプライマリウイルス対策製品ではなくパッシブ モードで実行されている場合に、悪意のある成果物からの保護を強化します。 ブロック モードの EDR は、EDR 機能によって検出された悪意のあるアーティファクトを修復するためにバックグラウンドで機能します。 このような成果物は、Microsoft 以外のプライマリウイルス対策製品によって見逃されている可能性があります。 ブロック モードの EDR を使用すると、Microsoft Defender ウイルス対策は違反後の動作 EDR 検出に対してアクションを実行できます。 「よく寄せられる質問」セクション [の「Microsoft Defender ウイルス対策をお持ちであれば、ブロック モードで EDR を有効にする必要がありますか](#do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices) ?」セクション **を** 参照してください。

> [!IMPORTANT]
> ブロック モードの EDR では、Microsoft Defender ウイルス対策のリアルタイム保護が有効になっている場合に使用できるすべての保護が提供されるわけではありません。 次の例のように、Microsoft Defender ウイルス対策に依存してアクティブなウイルス対策ソリューションに依存する一部の機能は機能しません。
>
> - Microsoft Defender ウイルス対策がパッシブ モードの場合、オンアクセス スキャンを含むリアルタイム保護は使用できません。 リアルタイム保護ポリシー設定の詳細については、「 **[Microsoft Defender ウイルス対策の常時オン保護を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)**」を参照してください。
> - **[ネットワーク保護](network-protection.md)** や **[攻撃面の縮小ルール](attack-surface-reduction.md)** などの機能は、Microsoft Defender ウイルス対策がアクティブ モードで実行されている場合にのみ使用できます。
>
> Microsoft 以外のウイルス対策ソリューションには、これらの機能が含まれていることが予想されます。

ブロック モードの EDR は、 [脅威&脆弱性管理機能](next-gen-threat-and-vuln-mgt.md) と統合されています。 組織のセキュリティ チームは、まだ有効になっていない場合は、ブロック モードで EDR を有効にするための [セキュリティに関する推奨事項](tvm-security-recommendation.md) を取得します。 この推奨事項は、主にアクティブな Microsoft 以外のウイルス対策ソリューション (パッシブ モードの Microsoft Defender ウイルス対策を使用) を使用するデバイスに対するものです。 Microsoft Defender ウイルス対策がデバイスの主要なウイルス対策ソリューションである場合、ブロック モードで EDR を有効にすることには利点はほとんどありません。

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="ブロック モードで EDR を有効にするための推奨事項" lightbox="images/edrblockmode-TVMrecommendation.png":::

> [!TIP]
> 最適な保護を得るには、必ず **[Microsoft Defender for Endpointベースラインをデプロイ](configure-machines-security-baseline.md)** してください。

このビデオでは、ブロック モードでエンドポイントの検出と応答 (EDR) を有効にし、違反前から違反後までの各段階で動作ブロックと包含を有効にする理由と方法について説明します。
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HjW2]

## <a name="what-happens-when-something-is-detected"></a>何かが検出されるとどうなりますか?

ブロック モードの EDR がオンになっていて、悪意のあるアーティファクトが検出されると、Defender for Endpoint はそのアーティファクトを修復します。 セキュリティ運用チームは、[アクション センター](respond-machine-alerts.md#check-activity-details-in-action-center)で検出状態が **ブロック** または **禁止と表示され**、完了したアクションとして一覧表示されます。 次の図は、ブロック モードで EDR を介して検出され修復された不要なソフトウェアのインスタンスを示しています。

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="ブロック モードでの EDR による検出" lightbox="images/edr-in-block-mode-detection.png":::

## <a name="enable-edr-in-block-mode"></a>ブロック モードで EDR を有効にする

> [!IMPORTANT]
> プラットフォーム バージョン 4.18.2202.X 以降では、Intune CSP を使用して特定のデバイス グループをターゲットにするようにブロック モードで EDR を設定できるようになりました。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>では、引き続きブロック モードのテナント全体で EDR を設定できます。 ブロック モードの EDR は、主に、パッシブ モードで Microsoft Defender ウイルス対策を実行しているデバイス (Microsoft 以外のウイルス対策ソリューションがデバイスにインストールされ、アクティブ) に推奨されます。

> [!TIP]
> ブロック モードで EDR を有効にする前に [、要件](#requirements-for-edr-in-block-mode) が満たされていることを確認します。

### <a name="security-portal"></a>セキュリティ ポータル

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) に移動してサインインします。
1. [Settings Endpoints General Advanced features **]\(設定** \> **エンドポイントの** \> **一般的** \> **な高度な機能\**) を選択します。
1. 下にスクロールし、 **ブロック モードで EDR を有効にします**。

### <a name="intune"></a>Intune

Intuneでカスタム ポリシーを作成するには、「[Intuneを介して CSP をターゲットにするOMA-URIsをデプロイする」とオンプレミスとの比較に関するページを参照してください](/troubleshoot/mem/intune/deploy-oma-uris-to-target-csp-via-intune)。

ブロック モードで EDR に使用される Defender CSP の詳細については、 [Defender CSP](/windows/client-management/mdm/defender-csp) の「Configuration/PassiveRemediation」を参照してください。

## <a name="requirements-for-edr-in-block-mode"></a>ブロック モードでの EDR の要件

次の表に、ブロック モードでの EDR の要件を示します。

|要件|詳細|
|---|---|
|アクセス許可|[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) にグローバル管理者ロールまたはセキュリティ管理者ロールが割り当てられている必要があります。 詳細については、「 [基本的なアクセス許可](basic-permissions.md)」を参照してください。|
|オペレーティング システム|デバイスは、次のいずれかのバージョンの Windows を実行している必要があります。 <ul><li>Windows 11</li><li>Windows 10 (すべてのリリース)</li><li>Windows Server 2019 以降。</li><li>Windows Server バージョン 1803 以降</li><li>[新しい統合クライアント ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)を使用した R2 \(のWindows Server 2016とWindows Server 2012\)</li></ul>|
|Microsoft Defender for Endpoint|デバイスは Defender for Endpoint にオンボードする必要があります。 次の記事をご覧ください。 <br/>- [Microsoft Defender for Endpointの最小要件](minimum-requirements.md)<br/>- [デバイスのオンボードとMicrosoft Defender for Endpoint機能の構成](onboard-configure.md)<br/>- [Defender for Endpoint サービスへの Windows サーバーのオンボード](configure-server-endpoints.md)<br/>- [最新の統合ソリューションの新しいWindows Server 2012 R2 および 2016 機能 (プレビュー)](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) |
|Microsoft Defender ウイルス対策|デバイスには、Microsoft Defender ウイルス対策がインストールされ、アクティブ モードまたはパッシブ モードで実行されている必要があります。 [Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードであることを確認します](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。|
|クラウドによる保護|[クラウド配信](enable-cloud-protection-microsoft-defender-antivirus.md)保護が有効になるように、Microsoft Defender ウイルス対策を構成する必要があります。|
|Microsoft Defender ウイルス対策プラットフォーム|デバイスは最新の状態である必要があります。 PowerShell を使用して確認するには、管理者として [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを実行します。 **AMProductVersion** 行には、**4.18.2001.10** 以降が表示されます。 <p> 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。|
|Microsoft Defender ウイルス対策エンジン|デバイスは最新の状態である必要があります。 PowerShell を使用して確認するには、管理者として [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを実行します。 **AMEngineVersion** 行には、**1.1.16700.2** 以降が表示されます。 <p> 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。|

(<a id="fn1">1</a>) Windows Server 2016[および Windows Server 2012 R2 で EDR がブロック モードでサポートされているか](#is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2)を参照してください。

> [!IMPORTANT]
> 最適な保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成されていること、および [除外が構成されていることを](configure-exclusions-microsoft-defender-antivirus.md)確認します。 ブロック モードの EDR では、Microsoft Defender ウイルス対策用に定義されている除外は尊重されますが、Microsoft Defender for Endpointに対して定義された[インジケーター](manage-indicators.md)は対象としません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="can-i-specify-exclusions-for-edr-in-block-mode"></a>ブロック モードで EDR の除外を指定できますか?

誤検知を受け取った場合は、[Microsoft セキュリティ インテリジェンス送信サイト](https://www.microsoft.com/en-us/wdsi/filesubmission)で分析用にファイルを送信できます。

Microsoft Defender ウイルス対策の除外を定義することもできます。 「[Microsoft Defender ウイルス対策のスキャンの除外を構成および検証する](configure-exclusions-microsoft-defender-antivirus.md)」を参照してください。

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>デバイスで Microsoft Defender ウイルス対策を実行している場合、ブロック モードで EDR を有効にする必要がありますか?

ブロック モードでの EDR の主な目的は、Microsoft 以外のウイルス対策製品によって見逃された違反後の検出を修復することです。 Microsoft Defender ウイルス対策がアクティブ モードの場合、ブロック モードで EDR を有効にすることには最小限の利点があります。これは、リアルタイム保護が最初に検出をキャッチして修復することが期待されるためです。 Microsoft Defender for Antivirus がパッシブ モードで実行されているエンドポイントでは、ブロック モードで EDR を有効にすることをお勧めします。 EDR 検出は、 [PUA 保護](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) またはブロック モードでの [自動調査&修復機能](automated-investigations.md) によって自動的に修復できます。

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>ブロック モードの EDR は、ユーザーのウイルス対策保護に影響しますか?

ブロック モードの EDR は、ユーザーのデバイスで実行されているサードパーティのウイルス対策保護には影響しません。 ブロック モードの EDR は、プライマリウイルス対策ソリューションが何かを見逃した場合、または違反後の検出がある場合に機能します。 ブロック モードの EDR は、パッシブ モードの Microsoft Defender ウイルス対策と同様に機能します。ただし、ブロック モードの EDR では、検出された悪意のあるアーティファクトや動作もブロックおよび修復されます。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Microsoft Defender ウイルス対策を最新の状態に保つ必要があるのはなぜですか?

Microsoft Defender ウイルス対策は悪意のあるアイテムを検出して修復するため、最新の状態に保つことが重要です。 ブロック モードの EDR を有効にするには、最新のデバイスラーニング モデル、動作検出、ヒューリスティックを使用します。 [Defender for Endpoint](microsoft-defender-endpoint.md) スタックの機能は、統合された方法で機能します。 最適な保護値を取得するには、Microsoft Defender ウイルス対策を最新の状態に保つ必要があります。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。

### <a name="why-do-we-need-cloud-protection-maps-on"></a>クラウド保護 (MAPS) が必要な理由

デバイスで機能を有効にするには、クラウド保護が必要です。 クラウド保護により [、Defender for Endpoint](microsoft-defender-endpoint.md) は、幅広さと深いセキュリティ インテリジェンスに基づいて、最新かつ最大の保護を、行動学習モデルとデバイスラーニング モデルと共に提供できます。

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>アクティブ モードとパッシブ モードの違いは何ですか?

Windows 10、Windows 11、Windows Server、バージョン 1803 以降、Windows Server 2019、または Windows Server 2022 を実行しているエンドポイントの場合、Microsoft Defender ウイルス対策がアクティブ モードの場合は、デバイスのプライマリ ウイルス対策として使用されます。 パッシブ モードで実行している場合、Microsoft Defender ウイルス対策はプライマリウイルス対策製品ではありません。 この場合、脅威は Microsoft Defender ウイルス対策によってリアルタイムで修復されません。

> [!NOTE]
> Microsoft Defender ウイルス対策は、デバイスがMicrosoft Defender for Endpointにオンボードされている場合にのみパッシブ モードで実行できます。

詳細については、「[Microsoft Defender ウイルス対策の互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードであることを確認操作方法。

Microsoft Defender ウイルス対策がアクティブ モードまたはパッシブ モードで実行されているかどうかを確認するには、Windows を実行しているデバイスでコマンド プロンプトまたは PowerShell を使用します。

|Method|プロシージャ|
|---|---|
|PowerShell|1. [スタート] メニューを選択し、入力`PowerShell`を開始し、結果のWindows PowerShellを開きます。<br/><br/>2. 「. 」と入力します `Get-MpComputerStatus`。<br/><br/>3. 結果の一覧の **AMRunningMode** 行で、次のいずれかの値を探します。<br/>- `Normal`<br/>- `Passive Mode`<br/><br/>詳細については、「 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)」を参照してください。|
|コマンド プロンプト|<ol><li>[スタート] メニューを選択し、入力 `Command Prompt`を開始し、結果で Windows コマンド プロンプトを開きます。</li><li>種類 `sc query windefend`。</li><li>結果の一覧の **STATE** 行で、サービスが実行されていることを確認します。</li></ol>|

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>ブロック モードの EDR がパッシブ モードで Microsoft Defender ウイルス対策で有効になっていることを確認操作方法。

PowerShell を使用すると、Microsoft Defender ウイルス対策がパッシブ モードで実行されている場合に、ブロック モードの EDR が有効になっていることを確認できます。

1. [スタート] メニューを選択し、入力`PowerShell`を開始し、結果のWindows PowerShellを開きます。

2. 種類 `Get-MPComputerStatus|select AMRunningMode`。

3. 結果 `EDR Block Mode`が表示されていることを確認します。

   > [!TIP]
   > Microsoft Defender ウイルス対策がアクティブ モードの場合は`Normal``EDR Block Mode`、 . 詳細については、「 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)」を参照してください。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2"></a>Windows Server 2016および Windows Server 2012 R2 では、ブロック モードの EDR はサポートされていますか?

Microsoft Defender ウイルス対策がアクティブ モードまたはパッシブ モードで実行されている場合、ブロック モードの EDR は、次のバージョンの Windows でサポートされます。

- Windows 11
- Windows 10 (すべてのリリース)
- Windows Server バージョン 1803 以降
- Windows Server 2022
- Windows Server 2019
- R2 のWindows Server 2016とWindows Server 2012 ([新しい統合クライアント ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)を使用)

Windows Server 2016およびWindows Server 2012 R2 用の[新しい統合クライアント ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)を使用すると、パッシブ モードまたはアクティブ モードでブロック モードで EDR を実行できます。

> [!NOTE]
> この機能を機能させるには、「[Windows サーバーのオンボード](configure-server-endpoints.md)」の手順に従って、Windows Server 2016とWindows Server 2012 R2 をオンボードする必要があります。

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>ブロック モードの EDR を無効にするにはどのくらいの時間がかかりますか?

ブロック モードで EDR を無効にすることを選択した場合、システムがこの機能を無効にするには最大で 30 分かかることがあります。

## <a name="see-also"></a>関連項目

- [Tech Community ブログ: ブロック モードでの EDR の導入: トラック内での攻撃の停止](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)

- [動作ブロックと封じ込め](behavioral-blocking-containment.md)
