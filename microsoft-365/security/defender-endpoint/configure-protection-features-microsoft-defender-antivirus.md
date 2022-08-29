---
title: Microsoft Defender ウイルス対策保護機能を有効にして構成する
description: Microsoft Defender ウイルス対策で、動作ベース、ヒューリスティック、およびリアルタイム保護を有効にします。
keywords: ヒューリスティック, 機械学習, 動作モニター, リアルタイム保護, 常時オン, Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, Defender
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 0c67af35776d5fdc55dcc06472b9121ead19a571
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387773"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>行動、ヒューリスティック、リアルタイム保護を構成する


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策 

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策では、いくつかの方法を使用して脅威の保護を提供します。

- 新しい脅威と新しい脅威のほぼ瞬時の検出とブロックのためのクラウド保護
- ファイルとプロセスの動作の監視とその他のヒューリスティックを使用した常時オン スキャン ("リアルタイム保護" とも呼ばれます)
- 機械学習、人間と自動化されたビッグ データ分析、詳細な脅威対策の研究に基づく専用の保護更新

Microsoft Defender ウイルス対策では、グループ ポリシー、System Center Configuration Manage、PowerShell コマンドレット、および Windows Management Instrumentation (WMI) を使用して、これらのメソッドを使用する方法を構成できます。

このセクションでは、安全でないと見なされるがマルウェアとして検出されない可能性があるアプリを検出してブロックする方法など、常時オン スキャンの構成について説明します。

[Microsoft Defender ウイルス対策クラウド保護を有効にして構成する方法については、「クラウド保護を通じて次世代の Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) ウイルス対策テクノロジを使用する」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

| トピック|説明 |
|---|---|
| [望ましくない可能性のあるアプリケーションを検出してブロックする](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| ネットワーク内で望ましくない可能性があるアプリ (awanted、ブラウザー修飾子とツール バー、悪意のあるウイルス対策アプリや偽のウイルス対策アプリなど) を検出してブロックする |
| [Microsoft Defender ウイルス対策保護機能を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|リアルタイム保護、ヒューリスティック、およびその他の常時オンの Microsoft Defender ウイルス対策監視機能を有効にして構成する |

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
