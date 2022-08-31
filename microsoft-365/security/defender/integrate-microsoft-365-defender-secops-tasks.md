---
title: 手順 6. SOC メンテナンス タスクを特定する
description: Microsoft 365 Defenderをセキュリティ操作に統合する場合は、SOC メンテナンス タスクを特定します。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365, インシデント対応, サイバー攻撃, secops, セキュリティ操作, soc
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: b066b248444dbd897e7c560ec58622787c5fed9a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482430"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>手順 6. SOC メンテナンス タスクを特定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

MICROSOFT 365 DEFENDERの SOC を維持するための定期的または必要に応じてのタスクを次に示します。

|最新情報|説明|頻度|割り当てられたチーム|
|---|---|---|---|
|SOC Teams とのサービス管理コラボレーション|資産追跡 (CMDB)、アプリケーション ライセンス (新しい SaaS ライセンス)、デバイス購入 (デバイスの展開のアップグレードまたは更新)、その他の Microsoft 365 テナント全体の変更 (Intune、Microsoft 365 など) などの周辺機器サービスの管理は、Microsoft 365 Defender製品の展開に影響を与える可能性があります。|毎週、必要に応じて|エンジニアリング & SecOps|
|フィッシング対策とデータ損失防止キャンペーンを更新する|SOC ユース ケースと、拡張組織 (人事、法的、トレーニングなど) で学習した教訓を組み込みます。|月次と必要に応じて|SOC 監視|
|必要に応じてオートメーション スクリプトとサービスをデプロイする|承認された Microsoft サイトから自動化スクリプトと構成ファイルをダウンロードしてテストし、Microsoft 365 Defender操作を改善します。|毎週、必要に応じて|エンジニアリングと SecOps|
|ポータルまたはライセンス管理|Microsoft の更新プログラムと新機能に基づいて、Microsoft 365 Defender ポータルまたはライセンスのニーズに関するお知らせとMicrosoft メッセージング センターを確認してください。|Weekly (週単位)|SOC 監視|
|SOC エスカレーション チケットを更新する|すべての SOC チームは、それらに割り当てられたエスカレーション チケット (Sentinel、ServiceNow チケットなど) を更新します。|毎日|すべての SOC チーム|
|Microsoft Defender 脆弱性の管理 (MDVM) 修復アクティビティを追跡する|MDVM セキュア スコア修復アクティビティを生成し、イントラネット ポータルを使用して資産所有者に報告します。|毎日|監視|
|セキュア スコア レポートを生成する|監視チームは、セキュリティスコアの改善を追跡し、報告します。|Weekly SOC|監視|
|IR テーブルトップ演習を実行する|卓上演習で SOC チームプレイブックをテストします。|必要に応じて|すべての SOC チーム|

これらのタスクを現在の SOC プロセスに統合します。

## <a name="next-steps"></a>次の手順

このコンテンツと[Microsoft 365 Defender ライブラリ](/microsoft-365/security/defender)で参照されているガイドを確認して、Microsoft 365 Defenderの独自の実装を構造化および統合する方法を決定する必要があります。
