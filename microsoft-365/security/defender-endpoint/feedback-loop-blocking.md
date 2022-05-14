---
title: フィードバック ループのブロック
description: フィードバック ループブロックは、迅速な保護とも呼ばれ、Microsoft Defender for Endpointの動作ブロック機能と包含機能の一部です。
keywords: 行動ブロック, 迅速な保護, フィードバックのブロック, Microsoft Defender for Endpoint
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
ms.openlocfilehash: da3f16837b8715fe791fbd8abf48acb657fd4963
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65416774"
---
# <a name="feedback-loop-blocking"></a>フィードバック ループのブロック

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

## <a name="overview"></a>概要

フィードバック ループブロックは、迅速な保護とも呼ばれ、[Microsoft Defender for Endpoint](/windows/security/threat-protection/)の[動作ブロック機能と包含機能](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)のコンポーネントです。 フィードバック ループブロックを使用すると、組織全体のデバイスが攻撃から保護されます。 

## <a name="how-feedback-loop-blocking-works"></a>フィードバック ループブロックのしくみ

[Microsoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)など、疑わしい動作またはファイルが検出されると、そのアーティファクトに関する情報が複数の分類子に送信されます。 迅速な保護ループ エンジンは、ファイルをブロックするかどうかの決定に到達するために、情報を検査し、他のシグナルと関連付けます。 アーティファクトのチェックと分類は、すばやく行われます。 その結果、確認されたマルウェアが迅速にブロックされ、エコシステム全体の保護が推進されます。 

迅速な保護を実施すると、攻撃がその足場を広げようとするため、デバイス、組織内の他のデバイス、および他の組織のデバイスで攻撃を停止できます。


## <a name="configuring-feedback-loop-blocking"></a>フィードバック ループ ブロックの構成

組織で Defender for Endpoint を使用している場合、フィードバック ループブロックは既定で有効になっています。 ただし、迅速な保護は、Defender for Endpoint 機能、機械学習保護機能、および Microsoft セキュリティ サービス間でのシグナル共有の組み合わせによって発生します。 Defender for Endpoint の次の機能が有効で構成されていることを確認します。

- [ベースラインのMicrosoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Microsoft Defender for Endpointにオンボードされたデバイス](/microsoft-365/security/defender-endpoint/onboard-configure)

- [ブロック モードの EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [攻撃面の減少](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [次世代保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (ウイルス対策)

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-articles"></a>関連記事

- [動作ブロックと封じ込め](behavioral-blocking-containment.md)

- [(ブログ)動作のブロックと包含: 光学を保護に変換する](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [役に立つMicrosoft Defender for Endpointリソース](/microsoft-365/security/defender-endpoint/helpful-resources)
