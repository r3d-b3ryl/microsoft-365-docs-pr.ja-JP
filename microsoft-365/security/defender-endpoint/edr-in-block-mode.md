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
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b0fe1da56c34cd0a79e1a41dba2fcb7a79c5a9f6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259573"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>ブロック モードでのエンドポイントEDR応答 (EDR)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>ブロック モードEDR機能とは

[ブロック モードでのエンドポイント](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)EDR応答 (Microsoft Defender ウイルス対策) は、パッシブ モードで実行されている場合でも、悪意のあるアーティファクトからの保護を提供します。 オンにすると、EDRモードでデバイスで検出された悪意のあるアーティファクトや動作がブロックされます。 EDRモードでは、侵害後に検出された悪意のあるアーティファクトを修復するために、舞台裏で動作します。 

EDRモードの場合は、脅威の検出[と統合& 脆弱性の管理。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 組織のセキュリティ チームは、まだ有効[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)になっていない場合EDRモードで有効にするセキュリティの推奨事項を受け取ります。 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="ブロック モードでEDRする推奨事項":::

> [!NOTE]
> 最適な保護を得る場合は、 **[必ず Microsoft Defender for Endpoint ベースラインを展開してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**。

## <a name="what-happens-when-something-is-detected"></a>何かが検出されると何が起こりますか?

ブロック EDRがオンになっていて、悪意のあるアーティファクトが検出されると、Microsoft Defender for Endpoint は、そのアーティファクトをブロックして修復します。 アクション センターには、検出の状態が **[ブロック**] または [防止済み] として完了したアクションとして [表示されます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)。

次の図は、ブロック モードで検出され、ブロックされたソフトウェアのインスタンスEDR示しています。

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDRモードで何かが検出された場合":::


## <a name="enable-edr-in-block-mode"></a>ブロック モードEDR有効にする

> [!IMPORTANT]
> ブロック モードで[オンにする前](#requirements-for-edr-in-block-mode)に、要件EDR確認してください。

1. [パスワード] ( ) にMicrosoft Defender セキュリティ センター [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。 

2. [高度  >  **設定] を選択します**。

3. ブロック モードで **EDRをオンにします**。

> [!NOTE]
> EDRモードの場合は、ブロック モードでのみ有効Microsoft Defender セキュリティ センター。 レジストリ キー、Intune、またはグループ ポリシーを使用して、ブロック モードでEDR無効にすることはできません。

## <a name="requirements-for-edr-in-block-mode"></a>ブロック モードでのEDRの要件

|要件  |詳細  |
|---------|---------|
|アクセス許可 |グローバル管理者またはセキュリティ管理者の役割は、Azure Active Directory で[割り当てられます](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。 「基本 [アクセス許可」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)。 |
|オペレーティング システム     |次のいずれかのバージョン。 <br/>- Windows 10 (すべてのリリース) <br/>- Windows Server バージョン 1803 以降 <br/>- Windows Server 2019  <p>**注**: EDRモードの設定は、ブロック モードではWindows Server 2016。       |
|WindowsE5 登録     |WindowsE5 は、次のサブスクリプションに含まれています。 <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3脅威保護サービスと&を組み合わせて使用する <br/><br/>「[各プランの](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components)[コンポーネントと機能」を参照してください](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。       |
|Microsoft Defender ウイルス対策  |Microsoft Defender ウイルス対策アクティブ モードまたはパッシブ モードでインストールして実行する必要があります。 (Microsoft 以外のウイルスMicrosoft Defender ウイルス対策と一緒に使用できます。[アクティブMicrosoft Defender ウイルス対策パッシブ モードの状態を確認します](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。 |
|クラウドによる保護 |クラウド配信Microsoft Defender ウイルス対策有効にするように構成[されていることを確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。 |
|Microsoft Defender ウイルス対策マルウェア対策クライアント |クライアントが最新の情報に更新されていないことを確認します。 PowerShell を使用して [、Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) コマンドレットを管理者として実行します。 **AMProductVersion 行** に **4.18.2001.10 以上** が表示されます。 |
|Microsoft Defender ウイルス対策 エンジン |エンジンが最新の情報に更新されていないことを確認します。 PowerShell を使用して [、Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) コマンドレットを管理者として実行します。 **AMEngineVersion 行に** **1.1.16700.2** 以上が表示されます。 |

> [!IMPORTANT]
> 最高の保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成され、除外 [が構成されていることを確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。 EDRモードでは、ブロック モードに対して定義されている除外をMicrosoft Defender ウイルス対策。

## <a name="frequently-asked-questions"></a>よく寄せられる質問 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>デバイスで実行しているEDR場合でも、ブロック モードでMicrosoft Defender ウイルス対策する必要がありますか?

パッシブ モードでもEDRモードでも、ブロック モードMicrosoft Defender ウイルス対策状態を維持することをお勧めします。 EDRモードでは、Microsoft Defender for Endpoint を使用して別の防御層を提供します。 Defender for Endpoint では、侵害後の動作と検出に基づいてアクションEDRできます。 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>ブロック モードEDRユーザーのウイルス対策保護に影響を与える可能性がありますか? 

EDRモードの場合、ユーザーのデバイスで実行されているサードパーティのウイルス対策保護には影響しません。 EDRウイルス対策ソリューションで何かが見つからない場合、または侵害後の検出がある場合は、ブロック モードで動作します。 EDRモードでの動作は、パッシブ モードの[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)Microsoft Defender ウイルス対策 と同様に動作しますが、検出された悪意のあるアーティファクトや動作もブロックおよび修復します。 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>最新の状態を維持Microsoft Defender ウイルス対策する必要がある理由 

悪意のあるMicrosoft Defender ウイルス対策を検出して修復するために、最新の状態に保つ必要があります。 ブロック EDRを有効にするために、最新のデバイス学習モデル、動作検出、ヒューリスティックを使用します。 Defender [for Endpoint の機能](https://docs.microsoft.com/windows/security/threat-protection) スタックは、統合された方法で動作します。 最適な保護値を取得するには、最新のMicrosoft Defender ウイルス対策する必要があります。  

### <a name="why-do-we-need-cloud-protection-on"></a>クラウド保護が必要な理由 

デバイスの機能を有効にするには、クラウド保護が必要です。 クラウド保護により [、Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) は、セキュリティ インテリジェンスの幅と深さに基づいて、行動モデルとデバイス学習モデルに基づいて、最新の最大の保護を提供できます。

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>パッシブ モードにMicrosoft Defender ウイルス対策設定する方法

「[有効にするMicrosoft Defender ウイルス対策し、パッシブ モードにあるか確認する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>アクティブまたはパッシブ モードMicrosoft Defender ウイルス対策確認する方法

アクティブ モードまたはパッシブ Microsoft Defender ウイルス対策実行されているかどうかを確認するには、コマンド プロンプトまたは PowerShell を、アクティブ モードで実行しているデバイスでWindows。

#### <a name="use-powershell"></a>PowerShell を使う

1. [スタート] メニューを選択し、入力を開始し、結果 `PowerShell` Windows PowerShellを開きます。

2. 種類`Get-MpComputerStatus`

3. 結果の一覧の **[AMRunningMode]** 行で、次のいずれかの値を探します。
   - `Normal` - 通常は実行されている Defender サービス。 特別なモードは有効になりません。
   - `Passive Mode`- 組織で Microsoft Defender for Endpoint を Microsoft 以外のウイルス対策/マルウェア対策ソリューションと組み合わせて使用している場合は、Microsoft Defender ウイルス対策パッシブ モードに切り替わります。 (リアルタイムの保護と脅威は、ユーザーによって修復Microsoft Defender ウイルス対策)。
   - `SxS Passive Mode`- パッシブ モードに似ていますが、制限付き定期的なスキャンを有効にするオプションがあります。
   
詳細については [、「Get-MpComputerStatus」を参照してください](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)。

#### <a name="use-command-prompt"></a>コマンド プロンプトの使用

1. [スタート] メニューを選択し、入力を開始し、結果 `Command Prompt` Windowsコマンド プロンプトを開きます。

2. 種類`sc query windefend`

3. 結果の一覧の STATE **行で、** サービスが実行されているのを確認します。

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>ブロック モードで無効にEDRにどのくらいの時間が必要ですか?

ブロック モードで EDRを無効にした場合、システムがこの機能を無効にするには最大 30 分かかる場合があります。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>ブロック EDRは、ブロック モードでサポートWindows Server 2016。

いいえ。 EDRモードの場合、次のバージョンのブロック モードがサポートWindows。

- Windows 10 (すべてのリリース)
- Windowsサーバー、バージョン 1803 以降 
- Windows Server 2019 

## <a name="see-also"></a>関連項目

- [Tech Communityブログ: ブロック モードでのEDRの導入: トラックでの攻撃の停止](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [動作ブロックと封じ込め](behavioral-blocking-containment.md)
- [ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

