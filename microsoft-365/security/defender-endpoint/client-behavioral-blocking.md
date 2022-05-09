---
title: クライアントの動作ブロック
description: クライアントの動作ブロックは、Microsoft Defender for Endpointでの動作ブロックと包含機能の一部です。
keywords: 動作ブロック, 迅速な保護, クライアントの動作, Microsoft Defender for Endpoint
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
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: f19e354a23af03abd905591993197ff8f484ceff
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788394"
---
# <a name="client-behavioral-blocking"></a>クライアントの動作ブロック

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>概要

クライアントの動作ブロックは、Defender for Endpoint の [動作ブロック機能とコンテインメント機能](behavioral-blocking-containment.md) のコンポーネントです。 デバイス (クライアントやエンドポイントとも呼ばれます) で疑わしい動作が検出されると、アーティファクト (ファイルやアプリケーションなど) が自動的にブロック、チェック、修復されます。

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="クラウドとクライアントの保護" lightbox="images/pre-execution-and-post-execution-detection-engines.png":::

ウイルス対策保護は、クラウド保護と組み合わせて使用する場合に最適です。

## <a name="how-client-behavioral-blocking-works"></a>クライアントの動作ブロックのしくみ

[Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)は、デバイス上で疑わしい動作、悪意のあるコード、ファイルレス攻撃やメモリ内攻撃などを検出できます。 疑わしい動作が検出されると、Microsoft Defender ウイルス対策はそれらの不審な動作とそのプロセス ツリーを監視し、クラウド保護サービスに送信します。 機械学習は、悪意のあるアプリケーションと良好な動作をミリ秒単位で区別し、各アーティファクトを分類します。 ほぼリアルタイムで、アーティファクトが悪意のあることが検出されるとすぐに、デバイスでブロックされます。

疑わしい動作が検出されるたびに、[アラート](alerts-queue.md)が生成され、攻撃が検出および停止された間に表示されます。"初期アクセス アラート" などのアラートがトリガーされ、[Microsoft 365 Defender ポータル](/microsoft-365/security/defender/microsoft-365-defender) (以前はMicrosoft 365 Defender) に表示されます。

クライアントの動作ブロックは、攻撃の開始を防ぐだけでなく、実行を開始した攻撃を停止するのに役立つため、効果的です。 また、 [フィードバック ループ ブロック](feedback-loop-blocking.md) (行動のブロックと包含の別の機能) を使用すると、組織内の他のデバイスに対する攻撃が防止されます。

## <a name="behavior-based-detections"></a>動作ベースの検出

動作ベースの検出は、[ENTERPRISEの MITRE ATT&CK マトリックス](https://attack.mitre.org/matrices/enterprise)に従って名前が付けられます。 名前付け規則は、悪意のある動作が観察された攻撃段階を特定するのに役立ちます。

|戦術|検出の脅威名|
|---|---|
|初期アクセス|`Behavior:Win32/InitialAccess.*!ml`|
|実行|`Behavior:Win32/Execution.*!ml`|
|永続性|`Behavior:Win32/Persistence.*!ml`|
|特権エスカレーション|`Behavior:Win32/PrivilegeEscalation.*!ml`|
|防御回避|`Behavior:Win32/DefenseEvasion.*!ml`|
|資格情報へのアクセス|`Behavior:Win32/CredentialAccess.*!ml`|
|検出|`Behavior:Win32/Discovery.*!ml`|
|横方向の移動|`Behavior:Win32/LateralMovement.*!ml`|
|コレクション|`Behavior:Win32/Collection.*!ml`|
|コマンドとコントロール|`Behavior:Win32/CommandAndControl.*!ml`|
|流出|`Behavior:Win32/Exfiltration.*!ml`|
|影響|`Behavior:Win32/Impact.*!ml`|
|未分類|`Behavior:Win32/Generic.*!ml`|

> [!TIP]
> 特定の脅威の詳細については、 **[最近のグローバル脅威アクティビティ](https://www.microsoft.com/wdsi/threats)** に関するページを参照してください。

## <a name="configuring-client-behavioral-blocking"></a>クライアント動作ブロックの構成

組織で Defender for Endpoint を使用している場合、クライアントの動作ブロックは既定で有効になっています。 ただし、 [動作のブロックや包含](behavioral-blocking-containment.md)を含むすべての Defender for Endpoint 機能の恩恵を受けるために、Defender for Endpoint の次の機能が有効で構成されていることを確認します。

- [Defender for Endpoint ベースライン](configure-machines-security-baseline.md)
- [Defender for Endpoint にオンボードされたデバイス](onboard-configure.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [攻撃面の減少](attack-surface-reduction.md)
- [次世代の保護](configure-microsoft-defender-antivirus-features.md) (ウイルス対策、マルウェア対策、その他の脅威保護機能)

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
