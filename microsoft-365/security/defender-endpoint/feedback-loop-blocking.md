---
title: フィードバック ループのブロック
description: フィードバック ループのブロック (高速保護とも呼ばれる) は、Microsoft Defender for Endpoint の動作ブロックおよび格納機能の一部です。
keywords: 動作ブロック、迅速な保護、フィードバックブロック、Microsoft Defender for Endpoint
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
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 30e1fdb8baede9506af52ae844f456baed1097a9
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882683"
---
# <a name="feedback-loop-blocking"></a>フィードバック ループのブロック

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>概要

フィードバック ループブロックは、高速保護とも呼ばれますが、Microsoft Defender [](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) for Endpoint の動作ブロックおよび格納機能の[コンポーネントです](/windows/security/threat-protection/)。 フィードバック ループブロックを使用すると、組織全体のデバイスが攻撃から保護されます。 

## <a name="how-feedback-loop-blocking-works"></a>フィードバック ループのブロックのしくみ

不審な動作やファイルが検出された場合 (Microsoft Defender ウイルス対策など[](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10))、その成果物に関する情報が複数の分類子に送信されます。 高速保護ループ エンジンは、情報を検査し、他の信号と関連付け、ファイルをブロックするかどうかを決定します。 アーティファクトのチェックと分類は、迅速に行います。 その結果、確認されたマルウェアが急速にブロックされ、エコシステム全体の保護が強化されます。 

迅速な保護を実施すると、攻撃が足場を広げろとして、デバイス、組織内の他のデバイス、および他の組織のデバイスで攻撃を停止できます。


## <a name="configuring-feedback-loop-blocking"></a>フィードバック ループブロックの構成

組織で Defender for Endpoint を使用している場合、フィードバック ループブロックは既定で有効になっています。 ただし、Defender for Endpoint 機能、機械学習保護機能、および Microsoft セキュリティ サービス全体でのシグナル共有を組み合わせて、迅速な保護が行われます。 Defender for Endpoint の次の機能が有効で構成されていることを確認します。

- [エンドポイントベースライン用 Microsoft Defender](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Microsoft Defender for Endpoint にオンボードされているデバイス](/microsoft-365/security/defender-endpoint/onboard-configure)

- [ブロック モードの EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [攻撃面の減少](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [次世代保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (ウイルス対策)

## <a name="related-articles"></a>関連記事

- [動作ブロックと封じ込め](behavioral-blocking-containment.md)

- [(ブログ)動作のブロックと格納: 光学を保護に変換する](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [エンドポイントのリソースに役立つ Microsoft Defender](/microsoft-365/security/defender-endpoint/helpful-resources)
