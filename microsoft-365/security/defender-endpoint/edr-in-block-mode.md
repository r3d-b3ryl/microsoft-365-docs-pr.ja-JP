---
title: ブロック モードでのエンドポイントの検出と応答
description: ブロック モードでのエンドポイントでの検出と対応の詳細
keywords: Microsoft Defender for Endpoint、mde、EDRモード、パッシブ モードのブロック
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
ms.openlocfilehash: eb40eaee9043e81331eca98c85f1467111cc37e4
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64638358"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>ブロック モードのエンドポイントでの検出と対応 (EDR)

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>ブロック モードEDR機能とは

[ブロック モードの](overview-endpoint-detection-response.md)エンドポイント検出と応答 (EDR) は、Microsoft Defender ウイルス対策 がプライマリ ウイルス対策製品ではなく、パッシブ モードで実行されている場合に、悪意のあるアーティファクトからの保護を強化します。 EDRモードでは、悪意のあるアーティファクトを修復するために、ブロック モードの機能によって検出された悪意のあるEDRします。 このようなアーティファクトは、Microsoft 以外のプライマリ ウイルス対策製品によって見逃されている可能性があります。 Microsoft Defender ウイルス対策 をプライマリ ウイルス対策として実行しているデバイスの場合、ブロック モードの EDR は、Microsoft Defender ウイルス対策 が侵害後の行動EDR検出に対して自動アクションを実行できるようにして、追加の防御層を提供します。

> [!IMPORTANT]
> EDRモードの場合、リアルタイム保護が有効になっている場合に使用可能Microsoft Defender ウイルス対策保護が提供されるとは言えな アクティブなウイルス対策Microsoft Defender ウイルス対策に依存しているすべての機能は、次の主要な例を含めて機能しません。
>
> - パッシブ モードの場合、オンアクセス スキャンを含むMicrosoft Defender ウイルス対策保護は使用できません。 リアルタイム保護ポリシー設定の詳細については、「常に保護を有効にして構成 **[するMicrosoft Defender ウイルス対策」を参照してください](configure-real-time-protection-microsoft-defender-antivirus.md)**。
>
> - ネットワーク保護 **[や攻撃表面](network-protection.md)****[の](attack-surface-reduction.md)** 縮小ルールのような機能は、アクティブ モードでMicrosoft Defender ウイルス対策場合にのみ使用できます。
>
> Microsoft 以外のウイルス対策ソリューションがこれらの機能を提供する必要があります。

EDRモードのデータは、脅威の検出[と統合& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)。 組織のセキュリティ チームは、まだ有効になっていない[](tvm-security-recommendation.md)場合、ブロック モードEDR有効にするセキュリティの推奨事項を受け取ります。

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="ブロック モードでEDRする推奨事項" lightbox="images/edrblockmode-TVMrecommendation.png":::

> [!TIP]
> 最適な保護を得る場合は、必ずベースライン **[をMicrosoft Defender for Endpointしてください](configure-machines-security-baseline.md)**。

## <a name="what-happens-when-something-is-detected"></a>何かが検出されると何が起こりますか?

ブロック EDRがオンになっていて、悪意のあるアーティファクトが検出されると、そのアーティファクトMicrosoft Defender for Endpointブロックして修復します。 セキュリティ運用チームは、アクション センターで検出状態を [ブロック] または [[](respond-machine-alerts.md#check-activity-details-in-action-center)防止済み] と表示し、完了したアクションとして一覧表示されます。

次の図は、ブロック モードで検出され、ブロックされたソフトウェアのインスタンスEDR示しています。

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="ブロック モードでのEDR検出" lightbox="images/edr-in-block-mode-detection.png":::


## <a name="enable-edr-in-block-mode"></a>ブロック モードでEDRを有効にする

> [!IMPORTANT]
> プラットフォーム バージョン 4.18.2202.X から、EDR をブロック モードで設定して、INTUNE CSP を使用して特定のデバイス グループをターゲットにできます。 引き続き、EDRポータルでブロック モードのテナント全体でMicrosoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">できます</a>。 EDRモードの場合は、パッシブ モードで Microsoft Defender ウイルス対策 を実行しているデバイス (Microsoft 以外のウイルス対策ソリューションがデバイスにインストールされ、アクティブ) に主に推奨されます。 

> [!TIP]
> ブロック モードで[オンにする前](#requirements-for-edr-in-block-mode)に、要件EDR確認してください。

### <a name="security-portal"></a>セキュリティ ポータル 

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) に移動してサインインします。

2. [エンドポイント **設定** \> **高度な機能** \> **] を** \> **選択します**。

3. 下にスクロールし、[ブロック モードでEDR **を有効にする] をオンにします**。

### <a name="intune"></a>Intune

カスタム ポリシーを Intune作成するには、「OMA-URIsを使用して CSP をターゲットIntune展開する」および「オンプレミスとの比較」[を参照してください](/troubleshoot/mem/intune/deploy-oma-uris-to-target-csp-via-intune)。

ブロック モードで使用する Defender CSP のEDR詳細については、「Defender CSP」の「Configuration/PassiveRemediation」[を参照してください](/windows/client-management/mdm/defender-csp)。


## <a name="requirements-for-edr-in-block-mode"></a>ブロック モードでのEDR要件

次の表に、ブロック モードでのEDR要件を示します。

|要件|詳細|
|---|---|
|アクセス許可|グローバル管理者またはセキュリティ管理者の役割が管理者に割り当てられている必要[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。 詳細については、「基本アクセス許可 [」を参照してください](basic-permissions.md)。|
|オペレーティング システム|デバイスは、次のいずれかのバージョンのデバイスを実行している必要Windows。 <br/>- Windows 11 <br/>- Windows 10 (すべてのリリース)<br/>- Windows Server 2022 <br/>- Windows Server 2019<br/>- Windows Server バージョン 1803 以降<br/>- Windows Server 2016とWindows Server 2012 R2 (新しい統合クライアント ソリューションを[使用](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview))<sup>[[1](#fn1)]</sup>  |
|Microsoft Defender for Endpoint|デバイスは Defender for Endpoint にオンボードされている必要があります。 次の記事をご覧ください。 <br/>- [ユーザーの最小要件Microsoft Defender for Endpoint](minimum-requirements.md)<br/>- [デバイスをオンボードし、Microsoft Defender for Endpoint機能を構成する](onboard-configure.md)<br/>- [Defender Windowsサービスへのオンボード サーバー](configure-server-endpoints.md)<br/>- [最新Windows Server 2012ソリューションの R2 および 2016 の新機能 (プレビュー)](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) |
|Microsoft Defender ウイルス対策|デバイスには、アクティブ Microsoft Defender ウイルス対策パッシブ モードでインストールおよび実行されている必要があります。 [アクティブMicrosoft Defender ウイルス対策モードまたはパッシブ モードの状態を確認します](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。|
|クラウドによる保護|Microsoft Defender ウイルス対策保護を有効にするように[構成する必要があります](enable-cloud-protection-microsoft-defender-antivirus.md)。|
|Microsoft Defender ウイルス対策プラットフォーム|デバイスは最新である必要があります。 PowerShell を使用して確認するには、 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを管理者として実行します。 **AMProductVersion 行** に **4.18.2001.10 以上** が表示されます。 <p> 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。|
|Microsoft Defender ウイルス対策 エンジン|デバイスは最新である必要があります。 PowerShell を使用して確認するには、 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを管理者として実行します。 **AMEngineVersion 行に** **1.1.16700.2** 以上が表示されます。 <p> 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。|

(<a id="fn1">1</a>) [「ブロック モードEDR R2 でサポートされているWindows Server 2016」をWindows Server 2012してください。](#is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2)

> [!IMPORTANT]
> 最適な保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成され、除外が構成 [されていることを確認します](configure-exclusions-microsoft-defender-antivirus.md)。 EDRモードでは、ブロック モードに対して定義されている除外Microsoft Defender ウイルス対策、ブロック モードに対して定義されているインジケーター[](manage-indicators.md)はMicrosoft Defender for Endpoint。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="can-i-specify-exclusions-for-edr-in-block-mode"></a>ブロック モードで、EDR除外を指定できますか?

誤検知を受け取った場合は、ファイルを提出する際に、そのファイルを提出サイトのMicrosoft セキュリティ インテリジェンス[できます](https://www.microsoft.com/en-us/wdsi/filesubmission)。

また、ユーザーの除外を定義Microsoft Defender ウイルス対策。 「[Microsoft Defender ウイルス対策のスキャンの除外を構成および検証する](configure-exclusions-microsoft-defender-antivirus.md)」を参照してください。

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>デバイスで実行しているEDRブロック モードでMicrosoft Defender ウイルス対策する必要がありますか?

ブロック モードでEDRの主な目的は、Microsoft 以外のウイルス対策製品によって見逃された侵害後の検出を修復する方法です。 Microsoft Defender ウイルス対策 がアクティブ モードのときにブロック モードで EDR を有効にすることで、リアルタイムの保護が検出を最初にキャッチして修復する必要があるため、最小限のメリットがあります。 Microsoft Defender for Antivirus EDRパッシブ モードで実行されているエンドポイントで、ブロック モードでアクティブ化を有効にすることをお勧めします。 EDR検出は[、PUA](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) 保護またはブロック モードでの修復機能の&調査によって[自動的に修復](automated-investigations.md)できます。

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>ブロック モードEDRユーザーのウイルス対策保護に影響しますか?

EDRモードの場合、ユーザーのデバイスで実行されているサードパーティのウイルス対策保護には影響しません。 EDRウイルス対策ソリューションで何かが見つからない場合、または侵害後の検出がある場合は、ブロック モードで動作します。 EDRモードの場合はパッシブ モードの Microsoft Defender ウイルス対策 と同様に動作しますが、ブロック モードの EDR は、検出された悪意のあるアーティファクトや動作もブロックおよび修復します。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>最新の状態を維持Microsoft Defender ウイルス対策する必要がある理由

悪意のあるMicrosoft Defender ウイルス対策を検出して修復するために、最新の状態に保つ必要があります。 ブロック EDRを有効にするために、最新のデバイス学習モデル、動作検出、ヒューリスティックを使用します。 Defender [for Endpoint の機能](microsoft-defender-endpoint.md) スタックは、統合された方法で動作します。 最適な保護値を取得するには、最新のMicrosoft Defender ウイルス対策する必要があります。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。

### <a name="why-do-we-need-cloud-protection-maps-on"></a>クラウド保護 (MAPS) が必要な理由

デバイスの機能を有効にするには、クラウド保護が必要です。 クラウド保護により [、Defender for Endpoint](microsoft-defender-endpoint.md) は、セキュリティ インテリジェンスの幅と深さに基づいて、行動モデルとデバイス学習モデルに基づいて、最新の最大の保護を提供できます。

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>アクティブ モードとパッシブ モードの違いは何ですか?

Windows 10、Windows 11、Windows Server、バージョン 1803 以降、Windows Server 2019、Windows Server 2022 を実行しているエンドポイントの場合、Microsoft Defender ウイルス対策 がアクティブ モードの場合は、デバイス上のプライマリ ウイルス対策として使用されます。 パッシブ モードで実行する場合、Microsoft Defender ウイルス対策ウイルス対策製品ではありません。 この場合、脅威はリアルタイムでMicrosoft Defender ウイルス対策修復されない。

> [!NOTE]
> Microsoft Defender ウイルス対策がパッシブ モードで実行できるのは、デバイスがデバイスにオンボードされている場合Microsoft Defender for Endpoint。

詳細については、「[Microsoft Defender ウイルス対策の互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>操作方法モードMicrosoft Defender ウイルス対策モードかパッシブ モードか確認してください。

アクティブ モードまたはパッシブ Microsoft Defender ウイルス対策実行されているかどうかを確認するには、デバイスでコマンド プロンプトまたは PowerShell を使用Windows。

|Method|プロシージャ|
|---|---|
|PowerShell|1. 選択したスタート メニュー入力`PowerShell`を開始し、結果でWindows PowerShellを開きます。<br/><br/>2. と入力します `Get-MpComputerStatus`。<br/><br/>3. 結果の一覧の **[AMRunningMode** ] 行で、次のいずれかの値を探します。<br/>- `Normal`<br/>- `Passive Mode`<br/><br/>詳細については、「 [Get-MpComputerStatus」を参照してください](/powershell/module/defender/get-mpcomputerstatus)。|
|コマンド プロンプト|1. コマンド を選択スタート メニュー`Command Prompt`入力を開始し、結果でコマンド Windowsを開きます。<br/><br/>2. と入力します `sc query windefend`。<br/><br/>3. 結果の一覧の **STATE** 行で、サービスが実行されているのを確認します。 |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>操作方法モードでEDRがオンになっていることを確認し、パッシブ モードでMicrosoft Defender ウイルス対策を確認しますか?

PowerShell を使用して、パッシブ モードEDR実行されている状態でブロック モードのMicrosoft Defender ウイルス対策確認できます。

1. 選択したスタート メニュー入力を開始`PowerShell`し、結果でWindows PowerShellを開きます。

2. 種類`Get-MPComputerStatus|select AMRunningMode`

3. 結果が表示 `EDR Block Mode`されます。

   > [!TIP]
   > アクティブ Microsoft Defender ウイルス対策モードの場合は、 の代わりに`Normal`表示されます`EDR Block Mode`。 詳細については、「 [Get-MpComputerStatus」を参照してください](/powershell/module/defender/get-mpcomputerstatus)。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2"></a>ブロック EDR R2 でブロック モードWindows Server 2016サポートWindows Server 2012か。

アクティブ Microsoft Defender ウイルス対策またはパッシブ モードで実行されている場合は、ブロック モードEDR次のバージョンのデバイスがサポートWindows。

- Windows 11
- Windows 10 (すべてのリリース)
- Windows Server バージョン 1803 以降 
- Windows Server 2022
- Windows Server 2019 
- Windows Server 2016とWindows Server 2012 R2 (新しい[統合クライアント ソリューションを使用](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview))

R2 [と](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) Windows Server 2016 R2 の新しい統合クライアント ソリューションをWindows Server 2012、パッシブ モードまたはアクティブ モードでブロック モードで EDRを実行できます。

> [!NOTE]
> Windows Server 2016およびWindows Server 2012 R2 は、この機能を動作するには、「[オンボード](configure-server-endpoints.md) サーバー Windowsを使用してオンボードする必要があります。 

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>ブロック モードで無効にEDRにどのくらいの時間が必要ですか?

ブロック モードで EDRを無効にした場合、システムがこの機能を無効にするには最大 30 分かかる場合があります。

## <a name="see-also"></a>関連項目

- [Tech Community ブログ: ブロック モードでのEDRの導入: トラックでの攻撃の停止](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)

- [動作ブロックと封じ込め](behavioral-blocking-containment.md)
