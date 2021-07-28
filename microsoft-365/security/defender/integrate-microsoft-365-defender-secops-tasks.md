---
title: 手順 6. SOC のメンテナンス タスクを特定する
description: セキュリティ操作に統合するときに SOC Microsoft 365 Defenderタスクを特定します。
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
ms.openlocfilehash: 229dbfd12ddca4e3a1444e2e9ca5771896ba07e0
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623889"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>手順 6. SOC のメンテナンス タスクを特定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

次に、ユーザーの SOC を維持するための定期的なタスクまたは必要なタスクMicrosoft 365 Defender。

| 最新情報  | 説明 | 頻度 | チームが割り当てられている |
|:-------|:-----|:-------|:-------|
| SOC サーバーとのサービス管理Teams   | アセット追跡 (CMDB)、アプリケーション ライセンス (新しい SaaS ライセンス)、デバイス購入 (アップグレードまたは更新デバイス展開)、および Microsoft 365 Defender 製品の展開に影響を与える可能性があるその他の Microsoft 365 テナント全体の変更 (Intune、Microsoft 365 など) の管理。 | 毎週、必要に応じて   | エンジニアリング & SecOps | 
| フィッシング対策とデータ損失防止キャンペーンを更新する | 拡張組織 (人事、法務、トレーニングなど) で学んだ SOC の使用例と教訓を組み込む。  | 月次および必要に応じて | SOC の監視 |
| 必要に応じて自動化スクリプトとサービスを展開する | 承認された Microsoft サイトから自動化スクリプトと構成ファイルをダウンロードしてテストし、Microsoft 365 Defenderします。 | 毎週、必要に応じて | エンジニアリングと SecOps | 
| ポータルまたはライセンス管理 | Microsoft の更新プログラムと新機能にMicrosoft メッセージングに基Microsoft 365 Defender、ポータルまたはライセンスのニーズに関するお知らせと Microsoft 365 Defenderセンターを確認してください。 | 週次 | SOC の監視| 
| SOC エスカレーション チケットの更新 | すべての SOC チームは、エスカレーション チケット (Sentinel、ServiceNow チケットなど) を更新します。 | 毎日 | すべての SOC チーム | 
| 脅威Microsoft 365 Defenderの&の修復アクティビティを追跡する | イントラネット ポータルを使用して、TvM Secure Score 修復アクティビティを生成し、資産所有者に報告します。 | 毎日 | 監視 | 
| [セキュリティで保護されたスコアの生成] レポート | チームの監視は、セキュリティで保護されたスコアの向上を追跡および報告します。 | 週次 SOC | 監視 | 
| IR テーブルトップの演習を実行する | 卓上演習で SOC チームのプレイブックをテストします。 | 必要に応じて | すべての SOC チーム | 
|||||

これらのタスクを現在の SOC プロセスに統合します。

## <a name="next-steps"></a>次のステップ

このコンテンツおよび[Microsoft 365 Defender](/microsoft-365/security/defender)ライブラリで参照されているガイドを確認して、Microsoft 365 Defender の独自の実装を構造化および統合する方法を決定する必要があります。
