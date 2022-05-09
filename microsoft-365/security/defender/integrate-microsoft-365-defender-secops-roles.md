---
title: 手順 4. Microsoft 365 Defenderロール、責任、監視を定義する
description: Microsoft 365 Defenderをセキュリティ操作に統合する際のロール、責任、監視を定義する基本。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, Microsoft 365, インシデント対応, サイバー攻撃, secops, セキュリティ操作, soc
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
ms.openlocfilehash: 5410db413ece81a39453070985e6c744e8b684a6
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664064"
---
# <a name="step-4-define-microsoft-365-defender-roles-responsibilities-and-oversight"></a>手順 4. Microsoft 365 Defenderロール、責任、監視を定義する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

組織は、運用ロールを定義する前に、初期タスクとして、Microsoft 365 Defender ライセンス、構成、および管理の所有権と説明責任を確立する必要があります。 通常、ライセンスの所有権、サブスクリプション コスト、Microsoft 365および Enterprise Security + Mobility (EMS) サービス (Microsoft 365 Defenderを含む) の管理は、Security Operations Center (SOC) チームの外部にあります。 SOC チームは、これらの個人と協力して、Microsoft 365 Defenderを適切に監視する必要があります。 

多くの最新 SOC では、スキルセットと機能に基づいてチーム メンバーをカテゴリに割り当てます。 例:

- 脅威と分析機能のライフサイクル管理に関連するタスクに割り当てられた脅威インテリジェンス チーム。
- ログ、アラート、イベント、監視機能の管理を担当する SOC アナリストで構成される監視チーム。
- セキュリティ デバイスのエンジニアリングと最適化に割り当てられたエンジニアリング &運用チーム。

MICROSOFT 365 DEFENDERに対する SOC チームの役割と責任は、これらのチームに自然に統合されます。

次の表は、各 SOC チームの役割と責任、およびそれらのロールがMicrosoft 365 Defenderとどのように統合されるかを示しています。

| SOC チーム | 役割と責任 | Microsoft 365 Defenderタスク  |
|:-------|:-----|:-------|
| SOC 監視 | <ul><li>SOC ガバナンスを実行する</li><li>毎日、毎週、毎月のプロセスを確立します</li><li>トレーニングと認識を提供する</li><li>スタッフを採用し、ピア グループや会議に参加する</li><li>青、赤、紫のチーム演習を実施する</ul>  | <ul><li>Microsoft 365 Defender ポータルのアクセス制御</li><li>機能/URL とライセンス更新レジスタを維持します</li><li>IT、法的、コンプライアンス、プライバシーの利害関係者とのコミュニケーションを維持します</li><li>新しいMicrosoft 365またはMicrosoft Azureイニシアチブの変更管理会議に参加する</ul> |
| 脅威インテリジェンス & Analytics  | <ul><li>脅威 Intel フィード管理</li><li>ウイルスとマルウェアの属性</li><li>脅威モデリング&脅威イベントの分類</li><li>Insider threat Attribute development </li><li>Threat Intel と Risk Management プログラムの統合</li><li>人事、法務、IT、セキュリティ チーム全体のデータ サイエンス、BI、分析とデータ分析情報を統合する<ul> | <ul><li>Microsoft Defender for Identity脅威モデリングを維持します</li><li>Microsoft Defender for Office 365脅威モデリングを維持します</li><li>Microsoft Defender for Endpoint脅威モデリングを維持します</ul> |
| 監視 | <ul><li>階層 1、2、3 のアナリスト</li><li>ログ ソースのメンテナンスとエンジニアリング</li><li>データ ソース インジェスト </li><li>SIEM 解析、アラート、相関関係、最適化</li><li>イベントとアラートの生成</li><li>イベントとアラートの分析</li><li>イベントとアラートのレポート</li><li>チケット発行システムのメンテナンス</ul> | 使用： <ul><li>セキュリティ/コンプライアンス センター</li><li>Microsoft 365 Defender ポータル</ul> |
| エンジニアリング & SecOps | <ul><li>アプリ、システム、エンドポイントの脆弱性管理</li><li>XDR/SOAR オートメーション</li><li>コンプライアンス テスト</li><li>フィッシングと DLP エンジニアリング</li><li>エンジニアリング</li><li>座標変更コントロール</li><li>Runbook の更新を調整する</li><li>侵入テスト<ul> | <ul><li>Microsoft Defender for Cloud Apps</li><li>Defender for Endpoint</li><li>Defender for Identity</ul> |
| コンピューター セキュリティ インシデント対応チーム (CSIRT) | <ul><li>サイバー インシデントの調査と対応</li><li>フォレンジックを実行する</li><li>**SOC から分離されることがよくあります**</ul> | インシデント対応プレイブックMicrosoft 365 Defender共同作業と保守 |
||||


## <a name="next-step"></a>次の手順

[手順 5.ユース ケースの開発とテスト](integrate-microsoft-365-defender-secops-use-cases.md)
