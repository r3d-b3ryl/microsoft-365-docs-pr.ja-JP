---
title: ブロック モードでのエンドポイントの検出と応答
description: ブロック モードでのエンドポイントの検出と応答の詳細
keywords: Microsoft Defender ATP、ブロック モードの EDR、パッシブ モードのブロック
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
ms.date: 01/26/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b31e7aeb9178cb6021434319e55ddef927d7c263
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165875"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>ブロック モードでのエンドポイントの検出と応答 (EDR)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>ブロック モードの EDR とは

[ブロック モードのエンドポイント検出](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) と応答 (EDR) は、Microsoft Defender Antivirus がパッシブ モードで実行されている場合でも、悪意のあるアーティファクトからの保護を提供します。 オンにすると、ブロック モードの EDR は、デバイスで検出された悪意のあるアーティファクトや動作をブロックします。 ブロック モードの EDR は、侵害後に検出された悪意のあるアーティファクトを修復するために、舞台裏で動作します。 

ブロック モードの EDR は、脆弱性管理の [脅威&統合されます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)。 組織のセキュリティ チームは、まだ有効[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)になっていない場合は、ブロック モードで EDR を有効にするセキュリティに関する推奨事項を受け取ります。 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="ブロック モードで EDR を有効にする推奨事項":::

> [!NOTE]
> 最適な保護を得る場合は、 **[必ず Microsoft Defender for Endpoint ベースラインを展開してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**。

## <a name="what-happens-when-something-is-detected"></a>何かが検出されると何が起こりますか?

ブロック モードの EDR がオンになっていて、悪意のあるアーティファクトが検出されると、Microsoft Defender for Endpoint は、そのアーティファクトをブロックして修復します。 アクション センターには、検出の状態が **[ブロック**] または [防止済み] として完了したアクションとして [表示されます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)。

次の図は、ブロック モードで EDR を介して検出およびブロックされた望ましくないソフトウェアのインスタンスを示しています。

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="ブロック モードの EDR が何かを検出しました":::


## <a name="enable-edr-in-block-mode"></a>ブロック モードで EDR を有効にする

> [!IMPORTANT]
> ブロック モード [で](#requirements-for-edr-in-block-mode) EDR をオンにする前に、要件が満たされている必要があります。

1. Microsoft Defender セキュリティ センター ( ) に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。 

2. [設定 **] [**  >  **高度な機能] を選択します**。

3. ブロック モード **で EDR をオンにします**。

> [!NOTE]
> ブロック モードの EDR は、Microsoft Defender セキュリティ センターでのみ有効にできます。 レジストリ キー、Intune、またはグループ ポリシーを使用して、ブロック モードで EDR を有効または無効にすることはできません。

## <a name="requirements-for-edr-in-block-mode"></a>ブロック モードでの EDR の要件

|要件  |詳細  |
|---------|---------|
|アクセス許可 |Azure Active Directory で割り当てられたグローバル管理者または [セキュリティ管理者の役割](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。 「基本 [アクセス許可」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)。 |
|オペレーティング システム     |次のいずれかのバージョン。 <br/>- Windows 10 (すべてのリリース) <br/>- Windows Server バージョン 1803 以降 <br/>- Windows Server 2019         |
|Windows E5 登録     |Windows E5 は、次のサブスクリプションに含まれています。 <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 と Identity &脅威保護サービス <br/><br/>「[各プランの](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components)[コンポーネントと機能」を参照してください](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。       |
|Microsoft Defender ウイルス対策  |Microsoft Defender ウイルス対策は、アクティブ モードまたはパッシブ モードでインストールして実行する必要があります。 (Microsoft Defender ウイルス対策を Microsoft 以外のウイルス対策ソリューションと共に使用できます。 [Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードの状態を確認します](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。 |
|クラウドによる保護 |Microsoft Defender ウイルス対策がクラウド配信の保護が有効にするように [構成されていることを確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。 |
|Microsoft Defender ウイルス対策クライアント |クライアントが最新の情報に更新されていないことを確認します。 PowerShell を使用して [、Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) コマンドレットを管理者として実行します。 **AMProductVersion 行** に **4.18.2001.10 以上** が表示されます。 |
|Microsoft Defender ウイルス対策エンジン |エンジンが最新の情報に更新されていないことを確認します。 PowerShell を使用して [、Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) コマンドレットを管理者として実行します。 **AMEngineVersion 行に** **1.1.16700.2** 以上が表示されます。 |

> [!IMPORTANT]
> 最高の保護値を取得するには、ウイルス対策ソリューションが定期的な更新プログラムと重要な機能を受信するように構成され、除外 [が構成されていることを確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。 ブロック モードの EDR は、Microsoft Defender ウイルス対策に定義されている除外を尊重します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>デバイスで Microsoft Defender ウイルス対策を実行している場合でも、ブロック モードで EDR をオンにする必要がありますか?

Microsoft Defender Antivirus がパッシブ モードまたはアクティブ モードで実行されているかどうかに関して、ブロック モードで EDR をオンに維持することをお勧めします。 ブロック モードの EDR は、Microsoft Defender for Endpoint で別の防御層を提供します。 これにより、Defender for Endpoint は侵害後の動作 EDR 検出に基づいてアクションを実行できます。 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>ブロック モードの EDR は、ユーザーのウイルス対策保護に影響を与えますか? 

ブロック モードの EDR は、ユーザーのデバイスで実行されているサード パーティ製のウイルス対策保護には影響しません。 ブロック モードの EDR は、プライマリ ウイルス対策ソリューションで何かが見つからない場合、または侵害後の検出がある場合に機能します。 ブロック モードの EDR は、パッシブ モードの [Microsoft Defender ウイルス](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)対策と同様に動作しますが、検出された悪意のあるアーティファクトや動作もブロックおよび修復します。 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Microsoft Defender ウイルス対策を最新の状態に保つ必要がある理由 

Microsoft Defender Antivirus は悪意のあるアイテムを検出して修復しますので、最新の状態に保つ必要があります。 ブロック モードの EDR を有効にするには、最新のデバイス学習モデル、動作検出、ヒューリスティックを使用します。 Defender [for Endpoint の機能](https://docs.microsoft.com/windows/security/threat-protection) スタックは、統合された方法で動作します。 最高の保護値を取得するには、Microsoft Defender ウイルス対策を最新の状態に保つ必要があります。  

### <a name="why-do-we-need-cloud-protection-on"></a>クラウド保護が必要な理由 

デバイスの機能を有効にするには、クラウド保護が必要です。 クラウド保護により [、Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) は、セキュリティ インテリジェンスの幅と深さに基づいて、行動モデルとデバイス学習モデルに基づいて、最新の最大の保護を提供できます。

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Microsoft Defender ウイルス対策をパッシブ モードに設定する方法

「Microsoft [Defender ウイルス対策を有効にする」を参照し、パッシブ モードの状態を確認します](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードにあることを確認する方法

Microsoft Defender Antivirus がアクティブ モードまたはパッシブ モードで実行されているかどうかを確認するには、Windows を実行しているデバイスでコマンド プロンプトまたは PowerShell を使用します。

#### <a name="use-powershell"></a>PowerShell を使う

1. [スタート] メニューを選択し、入力を開始し、結果 `PowerShell` Windows PowerShellを開きます。

2. 種類`Get-MpComputerStatus`

3. 結果の一覧の **[AMRunningMode]** 行で、次のいずれかの値を探します。   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

詳細については [、「Get-MpComputerStatus」を参照してください](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)。

#### <a name="use-command-prompt"></a>コマンド プロンプトの使用

1. [スタート] メニューを選択し、入力を `Command Prompt` 開始し、結果で Windows コマンド プロンプトを開きます。

2. 種類`sc query windefend`

3. 結果の一覧の STATE **行で、** サービスが実行されているのを確認します。

## <a name="see-also"></a>関連項目

- [Tech Community ブログ: ブロック モードでの EDR の導入: トラックでの攻撃の停止](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [動作のブロックと格納](behavioral-blocking-containment.md)
- [より良い一緒に:Microsoft Defender Antivirus と Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

