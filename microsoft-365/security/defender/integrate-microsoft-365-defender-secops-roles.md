---
title: 手順 4. 役割Microsoft 365 Defender監督の定義
description: セキュリティ操作に組み込む際の役割、責任、監督Microsoft 365 Defender基本。
keywords: インシデント、アラート、調査、相関関係、攻撃、デバイス、ユーザー、ID、ID、メールボックス、メール、365、microsoft、Microsoft 365、インシデント対応、サイバー攻撃、secops、セキュリティ操作、soc
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
ms.openlocfilehash: a780c30b2919aac1f5a50c475c79df87d5b1f1f3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192450"
---
# <a name="step-4-define-microsoft-365-defender-roles-responsibilities-and-oversight"></a>手順 4. 役割Microsoft 365 Defender監督の定義

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

運用上の役割を定義するには、Microsoft 365 Defender ライセンス、構成、および管理の所有権と説明責任を初期タスクとして確立する必要があります。 通常、Microsoft 365 および Enterprise セキュリティ + モビリティ (EMS) サービス (Microsoft 365 Defender を含む場合があります) のライセンス、サブスクリプション コスト、および管理の所有権は、セキュリティ 運用センター (SOC) チームの外にあります。 SOC チームは、これらの個人と一緒に作業して、ユーザーの適切な監視をMicrosoft 365 Defender。 

多くの最新の SOC は、自分のスキルセットと機能に基づいてチーム メンバーをカテゴリに割り当てる。 以下に例を示します。

- 脅威と分析機能のライフサイクル管理に関連するタスクに割り当てられた脅威インテリジェンス チーム。
- ログ、アラート、イベント、および監視機能の管理を担当する SOC アナリストで構成される監視チーム。
- セキュリティ デバイスの&に割り当てられたエンジニアリング チーム。

SOC チームの役割と責任Microsoft 365 Defenderこれらのチームに自然に統合されます。

次の表では、各 SOC チームの役割と責任、および各チームの役割とチームの役割の統合Microsoft 365 Defender。

| SOC チーム | 役割と責任 | Microsoft 365 Defenderタスク  |
|:-------|:-----|:-------|
| SOC の監視 | <ul><li>SOC ガバナンスを実行する</li><li>毎日、毎週、毎月のプロセスを確立する</li><li>トレーニングと認識を提供する</li><li>スタッフの採用、ピア グループと会議への参加</li><li>青、赤、紫のチーム演習を実施する</ul>  | <ul><li>Microsoft 365 Defenderアクセス制御</li><li>機能/URL とライセンス更新プログラムの登録を維持する</li><li>IT 関係者、法務関係者、コンプライアンス関係者、プライバシー関係者とのコミュニケーションを維持する</li><li>新しいグループまたはグループの取り組みMicrosoft 365変更Microsoft Azure参加する</ul> |
| 脅威インテリジェンス & Analytics  | <ul><li>脅威の Intel フィード管理</li><li>ウイルスとマルウェアの属性</li><li>脅威のモデリング&イベントの分類</li><li>Insider Threat Attribute の開発 </li><li>Threat Intel Integration with Risk Management program</li><li>人事、法務、IT、およびセキュリティ チーム全体のデータ サイエンス、BI、分析とデータインサイトを統合する<ul> | <ul><li>Microsoft Defender for Identity の脅威モデリングを維持する</li><li>脅威のモデリングのための Microsoft Defender Office 365維持</li><li>Microsoft Defender for Endpoint の脅威モデリングを維持する</ul> |
| 監視 | <ul><li>Tier 1、2、3 アナリスト</li><li>ログ ソースのメンテナンスとエンジニアリング</li><li>データ ソースの取り込み </li><li>SIEM の解析、アラート、相関関係、最適化</li><li>イベントとアラートの生成</li><li>イベントとアラートの分析</li><li>イベントとアラートのレポート</li><li>チケット システムのメンテナンス</ul> | 用途: <ul><li>セキュリティ/コンプライアンス センター</li><li>Microsoft 365 Defender ポータル</ul> |
| エンジニアリング & SecOps | <ul><li>アプリ、システム、およびエンドポイントの脆弱性管理</li><li>XDR/SOAR オートメーション</li><li>コンプライアンス テスト</li><li>フィッシングおよび DLP エンジニアリング</li><li>エンジニアリング</li><li>座標変更コントロール</li><li>Runbook の更新を調整する</li><li>侵入テスト<ul> | <ul><li>Microsoft Cloud App Security</li><li>Defender for Endpoint</li><li>Defender for Identity</ul> |
| コンピューター セキュリティ インシデント対応チーム (CSIRT) | <ul><li>サイバー インシデントの調査と対応</li><li>forensics を実行する</li><li>**SOC から分離される場合が多い**</ul> | インシデント対応プレイブックMicrosoft 365 Defenderし、管理する |
||||


## <a name="next-step"></a>次の手順

[手順 5.使用例の開発とテスト](integrate-microsoft-365-defender-secops-use-cases.md)
