---
title: 展開フェーズ
description: エンドポイントを準備、セットアップ、オンボーディングして、そのサービスに Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: 展開、準備、セットアップ、オンボード、フェーズ、展開、展開、導入、構成
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
ms.openlocfilehash: 5715a796e0c7b78ae369f074b5edcb6ccfc8ae90
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330567"
---
# <a name="deployment-phases"></a>展開フェーズ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Microsoft Defender for Endpoint を展開して、企業が予防保護、侵害後の検出、自動調査、および対応を活用する方法について説明します。

このガイドは、関係者間で作業して環境を準備し、評価から有意義なパイロット、完全な展開に移行する方法でデバイスをオンボードするのに役立ちます。

各セクションは、このソリューションの個別の記事に対応します。

![表の詳細を含む展開フェーズのイメージ。](images/deployment-guide-phases.png)


![展開フェーズの概要: 準備、セットアップ、オンボード。](images/phase-diagrams/deployment-phases.png)

<br>

****

|段階|説明|
|---|---|
|[フェーズ 1: 準備](prepare-deployment.md)|利害関係者の承認、環境に関する考慮事項、アクセス許可、機能の導入順序など、Defender for Endpoint を展開する際に考慮する必要がある事項について説明します。|
|[フェーズ 2: セットアップ](production-deployment.md)|ライセンスの検証、セットアップ ウィザードの完了、ネットワーク構成などのポータルにアクセスするために必要な最初の手順に関するガイダンスを取得します。|
|[フェーズ 3: オンボード](onboarding.md)|展開リングを使用する方法、エンドポイントの種類に基づいてサポートされるオンボーディング ツール、および使用可能な機能の構成について説明します。|
|

このガイドを完了すると、適切なアクセス許可が設定され、エンドポイントがオンボードされ、センサー データがサービスに報告され、次世代の保護や攻撃表面の縮小などの機能が実装されます。

「展開の計画」のガイダンスで説明されている環境アーキテクチャと展開方法に[](deployment-strategy.md)関係なく、このガイドでは、オンボーディング エンドポイントのサポートを行います。

## <a name="key-capabilities"></a>主な機能

Microsoft Defender for Endpoint には多くの機能が備え付けられますが、この展開ガイドの主な目的は、デバイスのオンボーディングを開始する方法です。 オンボーディングに加えて、このガイダンスでは、次の機能を使用して開始できます。

<br>

****

|機能|説明|
|---|---|
|エンドポイントの検出および応答|エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応するために配置されます。|
|次世代の保護|ネットワークのセキュリティ境界をさらに強化するために、エンドポイント用の Microsoft Defender は、あらゆる種類の新しい脅威をキャッチするために設計された次世代の保護が使用されます。|
|攻撃面の縮小|スタック内の防御の最初の行を指定します。 構成設定が適切に設定され、悪用の軽減手法が適用されていることを確認することで、これらの機能は攻撃や悪用に抵抗します。|
|

これらすべての機能は、Microsoft Defender for Endpoint ライセンスホルダーで使用できます。 詳細については、「ライセンス要件 [」を参照してください](minimum-requirements.md#licensing-requirements)。

## <a name="scope"></a>範囲

### <a name="in-scope"></a>スコープ内

- サービスへのMicrosoft エンドポイント マネージャーとMicrosoft Endpoint Configuration Managerの使用と機能の構成
- Defender for Endpoint エンドポイントの検出と応答 (EDR) 機能の有効化
- Defender for Endpoint Endpoint Protection platform (EPP) 機能の有効化
  - 次世代の保護
  - 攻撃面の縮小

### <a name="out-of-scope"></a>対象外

以下は、この展開ガイドの範囲を外しています。

- Defender for Endpoint と統合される可能性のあるサード パーティ製ソリューションの構成
- 実稼働環境での侵入テスト

## <a name="see-also"></a>関連項目

- [フェーズ 1: 準備](prepare-deployment.md)
- [フェーズ 2: 設定](production-deployment.md)
- [フェーズ 3: オンボード](onboarding.md)
- [展開を計画する](deployment-strategy.md)
