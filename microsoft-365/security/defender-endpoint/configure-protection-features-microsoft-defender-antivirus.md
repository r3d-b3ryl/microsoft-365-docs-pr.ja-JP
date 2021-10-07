---
title: 保護機能を有効Microsoft Defender ウイルス対策構成する
description: Microsoft Defender AV で動作ベース、ヒューリスティック、およびリアルタイム保護を有効にする。
keywords: ヒューリスティック、機械学習、動作モニター、リアルタイム保護、常時オン、Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: beb7b022bd8e0dbd9296e18cbc4befa19690e492
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212559"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>行動、ヒューリスティック、リアルタイム保護を構成する


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策を使用して脅威保護を提供します。

- 新しい脅威や新しい脅威のほぼ瞬時の検出とブロックのためのクラウド保護
- ファイルとプロセスの動作の監視、その他のヒューリスティックを使用した常時スキャン ("リアルタイム保護" とも呼ばれる)
- 機械学習、手動および自動のビッグデータ分析、徹底した脅威耐性調査に基づいた専用の保護の更新

グループ ポリシー、Microsoft Defender ウイルス対策 System Center構成管理、PowerShell コマンドレット、および WINDOWS 管理インストルメンテーション (WMI) を使用して、これらのメソッドWindows構成できます。

このセクションでは、安全ではないと見なされるがマルウェアとして検出されない可能性があるアプリを検出およびブロックする方法など、常時スキャンの構成について説明します。

クラウド[保護を有効にして構成するMicrosoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)については、「クラウド保護を通じて次世代テクノロジを使用するMicrosoft Defender ウイルス対策参照してください。

## <a name="in-this-section"></a>このセクションの内容

| トピック|説明 |
|---|---|
| [望ましくない可能性のあるアプリケーションを検出してブロックする](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| アドウェア、ブラウザー修飾子、ツール バー、不正なウイルス対策アプリや偽のウイルス対策アプリなど、ネットワークで望ましくない可能性があるアプリを検出してブロックする |
| [保護機能を有効Microsoft Defender ウイルス対策構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|リアルタイム保護、ヒューリスティック、その他の常時監視機能を有効Microsoft Defender ウイルス対策構成する |
