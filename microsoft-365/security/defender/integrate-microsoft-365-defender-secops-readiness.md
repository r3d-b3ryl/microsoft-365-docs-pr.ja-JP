---
title: 手順 2.  ゼロトラスト フレームワークを使用して SOC 統合準備評価を実行する
description: セキュリティ操作に組み込む際にゼロトラスト フレームワークを使用して SOC 統合準備Microsoft 365 Defender実行する基本。
keywords: インシデント、アラート、調査、相関関係、攻撃、デバイス、ユーザー、ID、ID、メールボックス、メール、365、microsoft、m365、インシデント対応、サイバー攻撃、secops、セキュリティ操作、soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fab50cd24bd8b3bf8e07717d14503ca1cf2106e227d5e28efea25f87e80b4455
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53838844"
---
# <a name="step-2-perform-a-soc-integration-readiness-assessment-using-the-zero-trust-framework"></a>手順 2. ゼロトラスト フレームワークを使用して SOC 統合準備評価を実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

セキュリティ 運用センター (SOC) チームの主要な機能が定義された後、組織の次のステップは、ゼロトラストアプローチを通じて Microsoft Defender の導入に備 [える方法です](/security/zero-trust/)。 導入は、お客様の環境に対する Defender の機能を評価しながらMicrosoft 365 Defender業界をリードする最新のプラクティスを使用してアプリケーションを展開するために必要な要件を判断するのに役立ちます。 

このアプローチは、強力な保護基盤に基づいており、ID、エンドポイント (デバイス)、データ、アプリ、インフラストラクチャ、ネットワークなどの主要な分野が含まれます。 準備状況評価チームは、サービスを有効にするための基礎要件がまだ満たされていないMicrosoft 365 Defender修復が必要な領域を決定します。 

SOC が SOC のプロセスを完全に最適化するために修復する必要がある項目の一部を次に示します。

- **ID:**     従来のオンプレミス Active Directory ドメイン サービス (AD DS) ドメイン、MFA プランなし、特権アカウントのインベントリなし、その他。
- **エンドポイント (デバイス):**  従来のオペレーティング システム、限られたデバイス インベントリなど多数。
- **データとアプリ:**    データ ガバナンスの標準が不足し、統合しないカスタム アプリのインベントリはありません。
- **インフラストラクチャ:**   未許可の SaaS ライセンスの数が多く、コンテナー のセキュリティはありません。その他。
- **ネットワーク:**   低帯域幅、フラット ネットワーク、ワイヤレス セキュリティの問題などによるパフォーマンスの問題。

組織は、構成要件の[ベースライン セットをMicrosoft 365 Defender](m365d-enable.md)に関する記事のオンに従う必要があります。 次の手順では、SOC チームが効果的に使用例を開発するために実行する必要がある修復アクティビティを決定します。 

導入手順と使用例の作成については、手順 3 と 4 を参照してください。

## <a name="next-step"></a>次の手順

[手順 3.サービスの SOC Microsoft 365 Defenderとの統合を計画する](integrate-microsoft-365-defender-secops-services.md)
