---
title: 展開フェーズ
description: そのサービスにエンドポイントを準備、設定、オンボードしてMicrosoft Defender for Endpointをデプロイする方法について説明します
keywords: デプロイ、準備、セットアップ、オンボード、フェーズ、デプロイ、デプロイ、導入、構成
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c39ef92448317e625f3f2e6948f69a38093b1504
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467711"
---
# <a name="deployment-phases"></a>展開フェーズ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

企業が予防的な保護、違反後の検出、自動調査、および対応を利用できるように、Microsoft Defender for Endpointをデプロイする方法について説明します。

このガイドは、利害関係者間で作業して環境を準備し、評価から意味のあるパイロット、完全なデプロイに移行する方法でデバイスをオンボードするのに役立ちます。

各セクションは、このソリューションの個別の記事に対応しています。

:::image type="content" source="images/deployment-guide-phases.png" alt-text="テーブルの詳細を含むデプロイ フェーズ" lightbox="images/deployment-guide-phases.png":::


:::image type="content" source="images/phase-diagrams/deployment-phases.png" alt-text="デプロイ フェーズの概要:準備、セットアップ、オンボード" lightbox="images/phase-diagrams/deployment-phases.png":::

<br>

****

|段階|説明|
|---|---|
|[フェーズ 1: 準備](prepare-deployment.md)|関係者の承認、環境に関する考慮事項、アクセス許可、機能の導入順序など、Defender for Endpoint を展開する際に考慮する必要がある事項について説明します。|
|[フェーズ 2: セットアップ](production-deployment.md)|ライセンスの検証、セットアップ ウィザードの完了、ネットワーク構成など、ポータルにアクセスするために必要な最初の手順に関するガイダンスを取得します。|
|[フェーズ 3: オンボード](onboarding.md)|展開リングを使用する方法、エンドポイントの種類に基づいてサポートされているオンボード ツール、使用可能な機能の構成方法について説明します。|
|

このガイドを完了すると、適切なアクセス許可が設定され、エンドポイントがオンボードされ、センサー データがサービスに報告され、次世代の保護や攻撃面の削減などの機能が適用されます。

このガイドでは、プラン展開ガイダンスで説明されている環境アーキテクチャと [デプロイ](deployment-strategy.md) 方法に関係なく、エンドポイントのオンボードをサポートします。

## <a name="key-capabilities"></a>主な機能

Microsoft Defender for Endpointには多くの機能が用意されていますが、この展開ガイドの主な目的は、デバイスのオンボードを開始することです。 このガイダンスでは、オンボードに加えて、次の機能の使用を開始します。

<br>

****

|機能|説明|
|---|---|
|エンドポイントの検出および応答|エンドポイントの検出機能と応答機能は、侵入の試行とアクティブな侵害を検出、調査、および対応するために用意されています。|
|次世代の保護|ネットワークのセキュリティ境界をさらに強化するために、エンドポイント用の Microsoft Defender は、あらゆる種類の新しい脅威をキャッチするために設計された次世代の保護が使用されます。|
|攻撃面の縮小|スタック内の防御の最初の行を指定します。 構成設定が正しく設定され、悪用軽減手法が適用されるようにすることで、これらの機能は攻撃や悪用に抵抗します。|
|

これらの機能はすべて、Microsoft Defender for Endpointライセンス所有者が利用できます。 詳細については、「 [ライセンス要件」を](minimum-requirements.md#licensing-requirements)参照してください。

## <a name="scope"></a>範囲

### <a name="in-scope"></a>スコープ内

- Microsoft エンドポイント マネージャーとMicrosoft Endpoint Configuration Managerを使用してエンドポイントをサービスにオンボードし、機能を構成する
- Defender for Endpoint エンドポイントでの検出と対応 (EDR) 機能を有効にする
- Defender for Endpoint Endpoint Protection Platform (EPP) 機能を有効にする
  - 次世代の保護
  - 攻撃面の縮小

### <a name="out-of-scope"></a>対象外

このデプロイ ガイドの範囲外は次のとおりです。

- Defender for Endpoint と統合される可能性があるサード パーティ製ソリューションの構成
- 運用環境での侵入テスト

## <a name="see-also"></a>関連項目

- [フェーズ 1: 準備](prepare-deployment.md)
- [フェーズ 2: 設定](production-deployment.md)
- [フェーズ 3: オンボード](onboarding.md)
- [展開を計画する](deployment-strategy.md)
