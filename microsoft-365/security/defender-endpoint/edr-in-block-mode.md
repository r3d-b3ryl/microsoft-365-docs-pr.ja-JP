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
ms.date: 06/11/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 835195f0c35ada409ef632b2dbfa1b6de0291351
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409154"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>ブロック モードでのエンドポイントEDR応答 (EDR)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>ブロック モードEDR機能とは

[ブロック モードでのエンドポイント](overview-endpoint-detection-response.md)EDR応答 (Microsoft Defender ウイルス対策) は、パッシブ モードで実行されている場合でも、悪意のあるアーティファクトからの保護を提供します。 オンにすると、EDRモードでデバイスで検出された悪意のあるアーティファクトや動作がブロックされます。 EDRモードでは、侵害後に検出された悪意のあるアーティファクトを修復するために、舞台裏で動作します。 

EDRモードの場合は、脅威の検出[と統合& 脆弱性の管理。](next-gen-threat-and-vuln-mgt.md) 組織のセキュリティ チームは、まだ有効[](tvm-security-recommendation.md)になっていない場合EDRモードで有効にするセキュリティの推奨事項を受け取ります。 

:::image type="content" source="images/enable-edr-in-block-mode.png" alt-text="ブロック モードでEDRする推奨事項":::

> [!NOTE]
> 最適な保護を得る場合は、 **[必ず Microsoft Defender for Endpoint ベースラインを展開してください](configure-machines-security-baseline.md)**。

## <a name="what-happens-when-something-is-detected"></a>何かが検出されると何が起こりますか?

ブロック EDRがオンになっていて、悪意のあるアーティファクトが検出されると、Microsoft Defender for Endpoint は、そのアーティファクトをブロックして修復します。 セキュリティ運用チームは、アクション センターに [ブロック] または[](respond-machine-alerts.md#check-activity-details-in-action-center)[防止済み] と表示され、完了したアクションとして一覧表示されます。 

次の図は、ブロック モードで検出され、ブロックされたソフトウェアのインスタンスEDR示しています。

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDRモードで何かが検出された場合":::


## <a name="enable-edr-in-block-mode"></a>ブロック モードEDR有効にする

> [!IMPORTANT]
> ブロック モードで[オンにする前](#requirements-for-edr-in-block-mode)に、要件EDR確認してください。

1. ポータルに移動[Microsoft 365 Defenderサインイン](microsoft-defender-security-center.md)します。 

2. [高度  >  **設定] を選択します**。

3. ブロック モードで **EDRをオンにします**。

   > [!NOTE]
   > EDRモードの場合、このポータルでのみ有効Microsoft 365 Defenderできます。 レジストリ キー、Intune、またはグループ ポリシーを使用して、ブロック モードでEDR無効にすることはできません。

## <a name="requirements-for-edr-in-block-mode"></a>ブロック モードでのEDRの要件

|要件  |詳細  |
|---------|---------|
|権限 |グローバル管理者またはセキュリティ管理者の役割は、Azure Active Directory で[割り当てられます](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。 「基本 [アクセス許可」を参照してください](basic-permissions.md)。 |
|オペレーティング システム     |次のいずれかのバージョン。 <br/>- Windows 10 (すべてのリリース) <br/>- Windows Server バージョン 1803 以降 <br/>- Windows Server 2019 <br/>- Windows Server 2016 (Microsoft Defender ウイルス対策モードの場合のみ)     |
|WindowsE5 登録     |WindowsE5 は、次のサブスクリプションに含まれています。 <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3アドオンとMicrosoft 365 E5 Security一緒に使用する <br/><br/>「[各プランの](/microsoft-365/enterprise/microsoft-365-overview#components)[コンポーネントと機能」を参照してください](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。       |
|Microsoft Defender ウイルス対策  |Microsoft Defender ウイルス対策アクティブ モードまたはパッシブ モードでインストールして実行する必要があります。 (Microsoft 以外のウイルスMicrosoft Defender ウイルス対策と一緒に使用できます。[アクティブMicrosoft Defender ウイルス対策パッシブ モードの状態を確認します](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。 |
|クラウドによる保護 |クラウド配信Microsoft Defender ウイルス対策有効にするように構成[されていることを確認します](enable-cloud-protection-microsoft-defender-antivirus.md)。 |
|Microsoft Defender ウイルス対策マルウェア対策クライアント |クライアントが最新の情報に更新されていないことを確認します。 PowerShell を使用して [、Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを管理者として実行します。 **AMProductVersion 行** に **4.18.2001.10 以上** が表示されます。 |
|Microsoft Defender ウイルス対策 エンジン |エンジンが最新の情報に更新されていないことを確認します。 PowerShell を使用して [、Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドレットを管理者として実行します。 **AMEngineVersion 行に** **1.1.16700.2** 以上が表示されます。 |

> [!IMPORTANT]
> 最高の保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成され、除外 [が構成されていることを確認します](configure-exclusions-microsoft-defender-antivirus.md)。 EDRモードでは、ブロック モードに対して定義されている除外をMicrosoft Defender ウイルス対策。

## <a name="frequently-asked-questions"></a>よく寄せられる質問 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>デバイスで実行しているEDR場合でも、ブロック モードでMicrosoft Defender ウイルス対策する必要がありますか?

パッシブ モードでもEDRモードでも、ブロック モードMicrosoft Defender ウイルス対策状態を維持することをお勧めします。 EDRモードでは、Microsoft Defender for Endpoint を使用して別の防御層を提供します。 Defender for Endpoint では、侵害後の動作と検出に基づいてアクションEDRできます。 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>ブロック モードEDRユーザーのウイルス対策保護に影響を与える可能性がありますか? 

EDRモードの場合、ユーザーのデバイスで実行されているサードパーティのウイルス対策保護には影響しません。 EDRウイルス対策ソリューションで何かが見つからない場合、または侵害後の検出がある場合は、ブロック モードで動作します。 EDRモードでの動作はパッシブ モードの Microsoft Defender ウイルス対策と同様に動作しますが、検出された悪意のあるアーティファクトや動作もブロックおよび修復します。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>最新の状態を維持Microsoft Defender ウイルス対策する必要がある理由 

悪意のあるMicrosoft Defender ウイルス対策を検出して修復するために、最新の状態に保つ必要があります。 ブロック EDRを有効にするために、最新のデバイス学習モデル、動作検出、ヒューリスティックを使用します。 Defender [for Endpoint の機能](microsoft-defender-endpoint.md) スタックは、統合された方法で動作します。 最適な保護値を取得するには、最新のMicrosoft Defender ウイルス対策する必要があります。 「[更新プログラムの管理Microsoft Defender ウイルス対策ベースラインの適用」を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。 

### <a name="why-do-we-need-cloud-protection-on"></a>クラウド保護が必要な理由 

デバイスの機能を有効にするには、クラウド保護が必要です。 クラウド保護により [、Defender for Endpoint](microsoft-defender-endpoint.md) は、セキュリティ インテリジェンスの幅と深さに基づいて、行動モデルとデバイス学習モデルに基づいて、最新の最大の保護を提供できます。

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>パッシブ モードにMicrosoft Defender ウイルス対策設定する方法

オペレーティング システムによっては、Microsoft 以外のウイルス対策/マルウェア対策ソリューションを実行しているデバイスが Defender for Endpoint にオンボードされている場合、Microsoft Defender ウイルス対策 は自動的にパッシブ モードに入ります。 詳細については、「Defender [for Endpoint の機能にMicrosoft Defender ウイルス対策方法」を参照してください](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality)。 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>アクティブまたはパッシブ モードMicrosoft Defender ウイルス対策確認する方法

アクティブ モードまたはパッシブ Microsoft Defender ウイルス対策実行されているかどうかを確認するには、コマンド プロンプトまたは PowerShell を、アクティブ モードで実行しているデバイスでWindows。


|メソッド  |Procedure  |
|---------|---------|
| PowerShell     | 1. 選択したスタート メニュー入力を開始し、結果 `PowerShell` でWindows PowerShellを開きます。 <p>2. と入力します `Get-MpComputerStatus` 。 <p>3. 結果の一覧の **[AMRunningMode]** 行で、次のいずれかの値を探します。 <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>詳細については [、「Get-MpComputerStatus」を参照してください](/powershell/module/defender/get-mpcomputerstatus)。        |
|コマンド プロンプト     | 1. コマンド を選択スタート メニュー入力を開始し、結果 `Command Prompt` Windowsコマンド プロンプトを開きます。 <p>2. と入力します `sc query windefend` 。 <p>3. 結果の一覧の **STATE** 行で、サービスが実行されているのを確認します。         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>ブロック モードで無効にEDRにどのくらいの時間が必要ですか?

ブロック モードで EDRを無効にした場合、システムがこの機能を無効にするには最大 30 分かかる場合があります。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>ブロック EDRは、ブロック モードでサポートWindows Server 2016。

アクティブ Microsoft Defender ウイルス対策またはパッシブ モードで実行されている場合、ブロック モードEDR次のバージョンのデバイスがサポートWindows。

- Windows 10 (すべてのリリース)
- Windows Server バージョン 1803 以降 
- Windows Server 2019 

アクティブ Windows Server 2016でMicrosoft Defender ウイルス対策し、エンドポイントが Defender for Endpoint にオンボードされている場合は、ブロック モードの EDRが技術的にサポートされます。 ただし、EDRモードのユーザーは、エンドポイントのプライマリ ウイルス対策ソリューションMicrosoft Defender ウイルス対策保護を強化することを目的とします。 このような場合、Microsoft Defender ウイルス対策モードで実行されます。 現在、パッシブ モードMicrosoft Defender ウイルス対策の実行は、パッシブ モードではサポートWindows Server 2016。 詳細については、「microsoft Microsoft Defender ウイルス対策/マルウェア対策ソリューション」[を参照してください](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)。

## <a name="see-also"></a>関連項目

- [Tech Communityブログ: ブロック モードでのEDRの導入: トラックでの攻撃の停止](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [動作ブロックと封じ込め](behavioral-blocking-containment.md)

