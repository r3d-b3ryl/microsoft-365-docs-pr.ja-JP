---
title: クライアントの動作ブロック
description: クライアントの動作ブロックは、Microsoft Defender for Endpoint の動作ブロックと格納機能の一部です。
keywords: 動作のブロック、迅速な保護、クライアントの動作、Microsoft Defender for Endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: c58c81cd4623ec03850c167cad285e052413174c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933423"
---
# <a name="client-behavioral-blocking"></a>クライアントの動作ブロック

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>概要

クライアントの動作ブロックは、Defender [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) for Endpoint の動作ブロックと格納機能のコンポーネントです。 デバイス (クライアントまたはエンドポイントとも呼ばれます) で疑わしい動作が検出されると、アーティファクト (ファイルやアプリケーションなど) が自動的にブロック、チェック、修復されます。 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="クラウドとクライアントの保護":::

ウイルス対策保護は、クラウド保護と組み合わせた場合に最適です。

## <a name="how-client-behavioral-blocking-works"></a>クライアントの動作のブロックのしくみ

[Microsoft Defender ウイルス対策では](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 、デバイス上で疑わしい動作、悪意のあるコード、ファイルレス攻撃やメモリ内攻撃を検出できます。 疑わしい動作が検出されると、Microsoft Defender ウイルス対策は、疑わしい動作とそのプロセス ツリーを監視し、クラウド保護サービスに送信します。 機械学習は、悪意のあるアプリケーションと適切な動作をミリ秒単位で区別し、各成果物を分類します。 ほぼリアルタイムで、アーティファクトが悪意のあると判明すると、デバイス上でブロックされます。 

疑わしい動作が検出されると、 [アラートが生成](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) され、Microsoft Defender セキュリティ センター () に表示されます [https://securitycenter.windows.com](https://securitycenter.windows.com) 。

クライアントの動作ブロックは、攻撃の開始を防ぐだけでなく、実行を開始した攻撃を停止するのに役立つため、効果的です。 また、フィードバック [ループブロック](feedback-loop-blocking.md) (別の動作ブロックと格納機能) を使用すると、組織内の他のデバイスに対する攻撃が防止されます。

## <a name="behavior-based-detections"></a>動作ベースの検出

動作ベースの検出の名前は [、MITRE ATT](https://attack.mitre.org/matrices/enterprise)&CK Matrix for Enterprise に従います。 名前付け規則は、悪意のある動作が観察された攻撃段階を特定するのに役立ちます。


|戦術 |   検出の脅威名 |
|----|----|
|初期アクセス | 動作:Win32/InitialAccess.*!ml |
|実行  | 動作:Win32/Execution.*!ml |
|永続性    | 動作:Win32/Persistence.*!ml |
|特権エスカレーション   | 動作:Win32/PrivilegeEscalation.*!ml |
|Defense Evasion    | 動作:Win32/DefenseEvasion.*!ml |
|資格情報アクセス  | 動作:Win32/CredentialAccess.*!ml |
|Discovery  | 動作:Win32/Discovery.*!ml |
|横方向の動き | 動作:Win32/LateralMovement.*!ml |
|Collection |   動作:Win32/Collection.*!ml |
|コマンドとコントロール | 動作:Win32/CommandAndControl.*!ml |
|Exfiltration   | 動作:Win32/Exfiltration.*!ml |
|影響 | 動作:Win32/Impact.*!ml |
|未分類  | 動作:Win32/Generic.*!ml |

> [!TIP]
> 特定の脅威の詳細については、「最近のグローバル脅威 **[アクティビティ」を参照してください](https://www.microsoft.com/wdsi/threats)**。


## <a name="configuring-client-behavioral-blocking"></a>クライアントの動作ブロックの構成

組織で Defender for Endpoint を使用している場合、クライアントの動作ブロックは既定で有効になっています。 ただし、動作ブロックや格納を含むすべての Defender [](behavioral-blocking-containment.md)for Endpoint 機能を利用するには、Defender for Endpoint の次の機能が有効で構成されていることを確認してください。

- [Defender for Endpoint baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Defender for Endpoint にオンボードされているデバイス](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [ブロック モードの EDR](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [攻撃面の減少](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [次世代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (ウイルス対策)

## <a name="related-articles"></a>関連記事

- [動作ブロックと封じ込め](behavioral-blocking-containment.md)

- [フィードバック ループのブロック](feedback-loop-blocking.md)

- [(ブログ)動作のブロックと格納: 光学を保護に変換する](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [エンドポイントのリソースに役立つ Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
