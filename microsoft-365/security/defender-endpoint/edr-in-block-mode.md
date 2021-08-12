---
title: ブロック モードでのエンドポイントの検出と応答
description: ブロック モードでのエンドポイントの検出と応答の詳細
keywords: Microsoft Defender for Endpoint, mde, EDRモード, パッシブ モードのブロック
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 07/20/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 822d0cb12aa42d62fde3df1ec3632e400019d2e1
ms.sourcegitcommit: af575ade7b187af70f94db904b03f0471f56452a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "53591225"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>ブロック モードでのエンドポイントEDR応答 (EDR)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>ブロック モードEDR機能とは

[ブロック モードの](overview-endpoint-detection-response.md)エンドポイント検出と応答 (EDR) は、Microsoft Defender ウイルス対策 がプライマリウイルス対策製品ではなく、パッシブ モードで実行されている場合に、悪意のあるアーティファクトからの保護を強化します。 EDRモードでは、悪意のあるアーティファクトを修復するために、ブロック モードの機能によって検出された悪意のあるEDR動作します。 このようなアーティファクトは、Microsoft 以外のプライマリ ウイルス対策製品によって見逃されている可能性があります。 

> [!IMPORTANT]
> EDRモードの場合、リアルタイム保護が有効になっている場合に使用可能Microsoft Defender ウイルス対策保護が提供されるとは言えな アクティブなウイルス対策Microsoft Defender ウイルス対策に依存しているすべての機能は、次の主要な例を含めて機能しません。 
> 
> - パッシブ モードの場合、オンアクセス スキャンを含むリアルタイムMicrosoft Defender ウイルス対策使用できません。 リアルタイム保護ポリシー設定の詳細については、「常に保護を有効にして構成する」を参照Microsoft Defender ウイルス対策 **[を参照してください](configure-real-time-protection-microsoft-defender-antivirus.md)**。
> - ネットワーク保護 **[や攻撃表面](network-protection.md)****[の](attack-surface-reduction.md)** 縮小ルールのような機能は、アクティブ モードでMicrosoft Defender ウイルス対策場合にのみ使用できます。 
> 
> Microsoft 以外のウイルス対策ソリューションがこれらの機能を提供する必要があります。 

EDRモードのデータは、脅威の検出[と統合& 脆弱性の管理。](next-gen-threat-and-vuln-mgt.md) 組織のセキュリティ チームは、まだ有効[](tvm-security-recommendation.md)になっていない場合EDRモードで有効にするセキュリティの推奨事項を受け取ります。 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="ブロック モードでEDRする推奨事項":::

> [!TIP]
> 最適な保護を得る場合は、 **[必ず Microsoft Defender for Endpoint ベースラインを展開してください](configure-machines-security-baseline.md)**。

## <a name="what-happens-when-something-is-detected"></a>何かが検出されると何が起こりますか?

ブロック EDRがオンになっていて、悪意のあるアーティファクトが検出されると、Microsoft Defender for Endpoint は、そのアーティファクトをブロックして修復します。 セキュリティ運用チームは、アクション センターに [ブロック] または[](respond-machine-alerts.md#check-activity-details-in-action-center)[防止済み] と表示され、完了したアクションとして一覧表示されます。 

次の図は、ブロック モードで検出され、ブロックされたソフトウェアのインスタンスEDR示しています。

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDRモードで何かが検出された場合":::


## <a name="enable-edr-in-block-mode"></a>ブロック モードEDR有効にする

> [!TIP]
> ブロック モードで[オンにする前](#requirements-for-edr-in-block-mode)に、要件EDR確認してください。

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com/](https://security.microsoft.com/) します。 

2. [エンドポイント **設定**  >  **高度な**  >  **機能**  >  **] を選択します**。

3. 下にスクロールし、[ブロック モードでEDR **を有効にする] をオンにします**。


> [!NOTE]
> EDRモードの場合は、ポータル ( ) または以前の Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) でのみオンMicrosoft Defender セキュリティ センターできます [https://securitycenter.windows.com](https://securitycenter.windows.com) 。 ブロック モードでレジストリ キー、Microsoft Intune、またはグループ ポリシーを使用して、EDRを有効または無効にすることはできません。

## <a name="requirements-for-edr-in-block-mode"></a>ブロック モードでのEDRの要件

| 要件  | 詳細  |
|---------|---------|
| アクセス許可 | [グローバル管理者] または [セキュリティ管理者] ロールが [管理者] に割り当てられている[必要Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) 詳細については、「基本アクセス許可 [」を参照してください](basic-permissions.md)。 |
| オペレーティング システム     | デバイスは、次のいずれかのバージョンのデバイスを実行している必要Windows。 <br/>- Windows 10 (すべてのリリース) <br/>- Windows Server バージョン 1803 以降 <br/>- Windows Server 2019 <br/>- Windows Server 2016 (Microsoft Defender ウイルス対策モードの場合のみ)     |
| Microsoft Defender for Endpoint     | デバイスは Defender for Endpoint にオンボードされている必要があります。 「 [エンドポイント用 Microsoft Defender の最小要件」を参照してください](minimum-requirements.md)。       |
| Microsoft Defender ウイルス対策  | デバイスには、アクティブ Microsoft Defender ウイルス対策パッシブ モードでインストールおよび実行されている必要があります。 [アクティブMicrosoft Defender ウイルス対策パッシブ モードの状態を確認します](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。 |
| クラウドによる保護 | Microsoft Defender ウイルス対策保護を有効にするように[構成する必要があります](enable-cloud-protection-microsoft-defender-antivirus.md)。 |
| Microsoft Defender ウイルス対策プラットフォーム | デバイスは最新である必要があります。 PowerShell を使用して確認するには [、Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを管理者として実行します。 **AMProductVersion 行** に **4.18.2001.10 以上** が表示されます。 <p> 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。 |
| Microsoft Defender ウイルス対策 エンジン | デバイスは最新である必要があります。 PowerShell を使用して確認するには [、Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを管理者として実行します。 **AMEngineVersion 行に** **1.1.16700.2** 以上が表示されます。 <p> 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。 |

> [!IMPORTANT]
> 最高の保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成され、除外 [が構成されていることを確認します](configure-exclusions-microsoft-defender-antivirus.md)。 EDRモードでは、Microsoft Defender for Endpoint に対して定義されているインジケーターではなく、Microsoft Defender ウイルス対策に[](manage-indicators.md)対して定義されている除外が尊重されます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>デバイスで実行しているデバイスがEDR場合は、ブロック モードでMicrosoft Defender ウイルス対策する必要がありますか?

ブロック モードでEDRの主な目的は、Microsoft 以外のウイルス対策製品によって見逃された侵害後の検出を修復する方法です。 ただし、パッシブ モードEDRアクティブ モードの場合は、Microsoft Defender ウイルス対策モードをオンにすることをお勧めします。 

- パッシブ Microsoft Defender ウイルス対策モードの場合、EDRモードのユーザーは、Microsoft Defender for Endpoint と共に別の防御層を提供します。 
- Microsoft Defender ウイルス対策モードの場合、ブロック モードの EDR は追加のスキャンを提供しませんが、違反後の動作の検出に対して Defender for Endpoint が自動アクションを実行EDRします。

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>ブロック モードEDRユーザーのウイルス対策保護に影響しますか? 

EDRモードの場合、ユーザーのデバイスで実行されているサードパーティのウイルス対策保護には影響しません。 EDRウイルス対策ソリューションで何かが見つからない場合、または侵害後の検出がある場合は、ブロック モードで動作します。 EDRモードの場合はパッシブ モードの Microsoft Defender ウイルス対策 と同様に動作しますが、ブロック モードの EDR は悪意のあるアーティファクトや検出された動作もブロックおよび修復します。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>最新の状態を維持Microsoft Defender ウイルス対策する必要がある理由 

悪意のあるMicrosoft Defender ウイルス対策を検出して修復するために、最新の状態に保つ必要があります。 ブロック EDRを有効にするために、最新のデバイス学習モデル、動作検出、ヒューリスティックを使用します。 Defender [for Endpoint の機能](microsoft-defender-endpoint.md) スタックは、統合された方法で動作します。 最適な保護値を取得するには、最新のMicrosoft Defender ウイルス対策する必要があります。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。 

### <a name="why-do-we-need-cloud-protection-maps-on"></a>クラウド保護 (MAPS) が必要な理由 

デバイスの機能を有効にするには、クラウド保護が必要です。 クラウド保護により [、Defender for Endpoint](microsoft-defender-endpoint.md) は、セキュリティ インテリジェンスの幅と深さに基づいて、行動モデルとデバイス学習モデルに基づいて、最新の最大の保護を提供できます。

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>アクティブ モードとパッシブ モードの違いは何ですか?

Windows 10、Windows Server、バージョン 1803 以降、または Windows Server 2019 を実行しているエンドポイントでは、Microsoft Defender ウイルス対策 がアクティブ モードの場合、デバイス上のプライマリ ウイルス対策として使用されます。 パッシブ モードで実行する場合、Microsoft Defender ウイルス対策ウイルス対策製品ではありません。 この場合、脅威はリアルタイムでMicrosoft Defender ウイルス対策修復されるのではありません。

> [!NOTE]
> Microsoft Defender ウイルス対策は、デバイスが Microsoft Defender for Endpoint にオンボードされている場合にのみパッシブ モードで実行できます。

詳細については、「互換性」[をMicrosoft Defender ウイルス対策してください](microsoft-defender-antivirus-compatibility.md)。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>アクティブまたはパッシブ モードMicrosoft Defender ウイルス対策確認する方法

アクティブ モードまたはパッシブ Microsoft Defender ウイルス対策実行されているかどうかを確認するには、コマンド プロンプトまたは PowerShell を、アクティブ モードで実行しているデバイスでWindows。

|メソッド  |Procedure  |
|---------|---------|
| PowerShell     | 1. 選択したスタート メニュー入力を開始し、結果 `PowerShell` でWindows PowerShellを開きます。 <p>2. と入力します `Get-MpComputerStatus` 。 <p>3. 結果の一覧の **[AMRunningMode]** 行で、次のいずれかの値を探します。 <br/>- `Normal` <br/>- `Passive Mode` <p>詳細については [、「Get-MpComputerStatus」を参照してください](/powershell/module/defender/get-mpcomputerstatus)。        |
|コマンド プロンプト     | 1. コマンド を選択スタート メニュー入力を開始し、結果 `Command Prompt` Windowsコマンド プロンプトを開きます。 <p>2. と入力します `sc query windefend` 。 <p>3. 結果の一覧の **STATE** 行で、サービスが実行されているのを確認します。         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>パッシブ モードでブロック モードEDRがオンになっていることを確認するには、Microsoft Defender ウイルス対策確認する方法を示します。

PowerShell を使用して、パッシブ モードでEDRでブロック モードのMicrosoft Defender ウイルス対策を確認できます。

1. 選択したスタート メニュー入力を開始し、結果 `PowerShell` でWindows PowerShellを開きます。 

2. 種類 `Get-MPComputerStatus | select AMRunningMode`。

3. 結果が表示 `EDR Block Mode` されます。

   > [!TIP]
   > アクティブ Microsoft Defender ウイルス対策モードの場合は、 の代わりに `Normal` 表示されます `EDR Block Mode` 。 詳細については [、「Get-MpComputerStatus」を参照してください](/powershell/module/defender/get-mpcomputerstatus)。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>ブロック EDRは、ブロック モードでサポートWindows Server 2016。

アクティブ Microsoft Defender ウイルス対策またはパッシブ モードで実行されている場合、ブロック モードEDR次のバージョンのデバイスがサポートWindows。

- Windows 10 (すべてのリリース)
- Windows Server バージョン 1803 以降 
- Windows Server 2019 

#### <a name="what-about-windows-server-2016"></a>何をWindows Server 2016? 

アクティブ Windows Server 2016でMicrosoft Defender ウイルス対策し、エンドポイントが Defender for Endpoint にオンボードされている場合は、ブロック モードの EDRが技術的にサポートされます。 ただし、EDRモードのユーザーは、エンドポイントのプライマリ ウイルス対策ソリューションMicrosoft Defender ウイルス対策保護を強化することを目的とします。 このような場合、Microsoft Defender ウイルス対策モードで実行されます。 

現在、パッシブ モードMicrosoft Defender ウイルス対策の実行は、パッシブ モードではサポートWindows Server 2016。 詳細については、「microsoft Microsoft Defender ウイルス対策/マルウェア対策ソリューション」[を参照してください](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)。

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>ブロック モードで無効にEDRにどのくらいの時間が必要ですか?

ブロック モードで EDRを無効にした場合、システムがこの機能を無効にするには最大 30 分かかる場合があります。

## <a name="see-also"></a>関連項目

- [Tech Communityブログ: ブロック モードでのEDRの導入: トラックでの攻撃の停止](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [動作ブロックと封じ込め](behavioral-blocking-containment.md)

