---
title: ASR ルールの展開フェーズ 1 - 計画
description: 攻撃表面の縮小ルールの展開を計画するガイダンスを提供します。
keywords: 攻撃表面の縮小ルールの展開、ASR の展開、asr ルールの有効化、ASR の構成、ホスト侵入防止システム、保護ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、CONFIGURE ASR ルール
search.product: eADQiWindows 10XVcnh
ms.reviewer: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: ca6c7ed6265a1c68a513d6025227780fa429f6e8
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217400"
---
# <a name="attack-surface-reduction-rules-deployment-phase-1-plan"></a>攻撃表面の縮小ルールの展開フェーズ 1: 計画

ASR ルールのテストを開始するには、適切なビジネス ユニットから始める必要があります。 まず、特定のビジネス ユニットの少人数のグループから始める必要があります。 ASR ルールに実際の影響を与え、実装の調整に役立つ ASR チャンピオンを特定できます。

> [!div class="mx-imgBorder"]
> ![ASR ルールの計画手順](images/asr-rules-planning-steps.png)

## <a name="start-with-the-right-business-unit"></a>適切なビジネス ユニットから始める

ASR ルールの展開を展開するビジネス ユニットを選択する方法は、次のような要因によって異なっています。

- ビジネス ユニットのサイズ
- ASR ルール チャンピオンの可用性  
- の配布と使用法:
  - ソフトウェア
  - 共有フォルダー
  - スクリプトの使用
  - Officeマクロ
  - ASR ルールの影響を受けるその他のエンティティ

ビジネス ニーズに応じて、複数のビジネス ユニットを含めて、ソフトウェア、共有フォルダー、スクリプト、マクロなどの広範なサンプリングを取得する場合があります。逆に、最初の ASR ルールロールアウトの範囲を 1 つのビジネス ユニットに制限し、ASR ルールのロールアウト プロセス全体を他のビジネス ユニットに対して一度に 1 回繰り返す場合があります。

## <a name="identify-asr--rules-champions"></a>ASR ルール のチャンピオンを特定する

ASR ルール のチャンピオンは、事前テストと実装の段階で最初の ASR ルールのロールアウトに役立つ組織のメンバーです。 チャンピオンは通常、技術的に詳しく、断続的な作業フローの停止によって脱線しない従業員です。 チャンピオンの関与は、組織への ASR ルール展開の広範な拡大を通じて継続されます。 ASR ルール のチャンピオンは、最初に ASR ルールロールアウトの各レベルを体験します。

ASR ルールのチャンピオンにフィードバックと応答チャネルを提供して、ASR ルールに関連する作業の中断を警告し、ASR ルールロールアウト関連の通信を受信することが重要です。

## <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>業務用アプリのインベントリを取得し、ビジネス ユニット プロセスを理解する

組織全体で使用されるアプリケーションとビジネス単位ごとのプロセスを完全に理解するには、ASR ルールの展開を成功するために重要です。 さらに、組織内のさまざまなビジネス ユニット内でこれらのアプリがどのように使用されるかを理解する必要があります。
まず、組織全体で使用が承認されたアプリのインベントリを取得する必要があります。 管理センターなどのツールをMicrosoft 365 Apps、ソフトウェア アプリケーションのインベントリに役立ちます。 参照:[管理センターの在庫Microsoft 365 Appsを参照してください](/deployoffice/admincenter/inventory)。

## <a name="define-reporting-and-response-team--roles-and-responsibilities"></a>レポートと応答チームの役割と責任を定義する

ASR ルールの状態とアクティビティの監視と通信を担当する担当者の役割と責任を明確に明確に示すのは、ASR メンテナンスの中核的なアクティビティです。 したがって、次の点を判断することが重要です。

- レポートの収集を担当する担当者またはチーム
- レポートの共有方法と共有相手
- ASR ルールによって引き起こされた新たに特定された脅威または望ましくないブロックに対するエスカレーションの対処方法

一般的な役割と責任は次のとおりです。

- IT 管理者: ASR ルールを実装し、除外を管理します。 アプリとプロセスでさまざまなビジネス 単位を使用します。 関係者へのレポートの組み立てと共有
- 認定セキュリティ 運用センター (CSOC) アナリスト: 優先度の高いブロックされたプロセスを投資し、脅威が有効かどうかを判断する責任
- 最高情報セキュリティ責任者 (CISO): 組織の全体的なセキュリティ体制と正常性を担当する

## <a name="ring-deployment"></a>リング展開

大企業では、ASR ルールを "リング" に展開する方法をお勧めします。 リングは、重複しないツリー リングのように外側に放射する同心円として視覚的に表されるデバイスのグループです。 最も内側のリングが正常に展開されると、次のリングをテスト フェーズに移行できます。 リングを定義するには、ビジネス ユニット、ASR ルール のチャンピオン、アプリ、プロセスを徹底的に評価する必要があります。
ほとんどの場合、組織は、更新プログラムの段階的なロールアウト用に展開Windowsがあります。 既存のリングデザインを使用して ASR ルールを実装できます。
詳細については、「[展開計画を作成する」を参照Windows](/windows/deployment/update/create-deployment-plan)

## <a name="additional-topics-in-this-deployment-collection"></a>この展開コレクションのその他のトピック

[ASR ルールの展開ガイド - 概要](attack-surface-reduction-rules-deployment.md)

[ASR ルールの展開フェーズ 2 - test](attack-surface-reduction-rules-deployment-phase-2.md)

[ASR ルールの展開フェーズ 3 - 実装](attack-surface-reduction-rules-deployment-phase-3.md)

[ASR ルールの展開フェーズ 4 - 運用化](attack-surface-reduction-rules-deployment-phase-4.md)
