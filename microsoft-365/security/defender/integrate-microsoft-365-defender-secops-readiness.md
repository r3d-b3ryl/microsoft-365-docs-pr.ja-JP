---
title: 手順 2.  ゼロ トラスト Framework を使用して SOC 統合準備性評価を実行する
description: Microsoft 365 Defenderをセキュリティ操作に統合するときに、ゼロ トラスト Framework を使用して SOC 統合準備評価を実行する基本。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365, インシデント対応, サイバー攻撃, secops, セキュリティ操作, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1197edf14977c0232936531399d726f62ab70889
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314309"
---
# <a name="step-2-perform-a-soc-integration-readiness-assessment-using-the-zero-trust-framework"></a>手順 2。 ゼロ トラスト Framework を使用して SOC 統合準備性評価を実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Security Operations Center (SOC) チームの中核となる機能が定義されたら、組織の次のステップは、[ゼロ トラストアプローチ](/security/zero-trust/)を通じてMicrosoft 365 Defenderを導入する準備をすることです。 導入は、最新の業界をリードするプラクティスを使用してMicrosoft 365 Defenderを展開するために必要な要件を決定するのに役立ち、環境に対するMicrosoft 365 Defenderの機能を評価するのに役立ちます。

このアプローチは、保護の強力な基盤に基づいており、ID、エンドポイント (デバイス)、データ、アプリ、インフラストラクチャ、ネットワークなどの主要な領域が含まれます。 準備状況評価チームは、Microsoft 365 Defenderを有効にするための基本的な要件がまだ満たされておらず、修復が必要な領域を決定します。

SOC でプロセスを完全に最適化するために修復する必要がある項目の一部を次に示します。

- **Id：** レガシ オンプレミスの Active Directory Domain Services (AD DS) ドメイン、MFA プランなし、特権アカウントのインベントリなし、その他。
- **エンドポイント (デバイス):** レガシ オペレーティング システムの数が多く、デバイス インベントリが限られているなど。
- **データとアプリ:**  データ ガバナンス標準の欠如。統合されないカスタム アプリのインベントリはありません。
- **インフラストラクチャ：** 承認されていない SaaS ライセンスの数が多く、コンテナー のセキュリティなどはありません。
- **ネットワーク：** 低帯域幅、フラット ネットワーク、ワイヤレス セキュリティの問題などによるパフォーマンスの問題。

組織は、構成要件のベースライン セットをキャプチャするために[、Microsoft 365 Defenderの有効化](m365d-enable.md)に関する記事に従う必要もあります。 これらの手順により、SOC チームが効果的にユース ケースを開発するために実行する必要がある修復アクティビティが決定されます。 

導入手順とユース ケースの作成については、手順 3 と 4 で説明します。

## <a name="next-step"></a>次の手順

[手順 3.MICROSOFT 365 DEFENDERサービスの SOC カタログとの統合を計画する](integrate-microsoft-365-defender-secops-services.md)
