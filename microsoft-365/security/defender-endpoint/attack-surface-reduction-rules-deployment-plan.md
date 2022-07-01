---
title: 攻撃面の縮小 (ASR) ルールの展開を計画する
description: 攻撃面削減 (ASR) ルールのデプロイを計画するためのガイダンスを提供します。
keywords: 攻撃表面の縮小ルールの展開、ASR 展開、ASR の有効化、ASR の構成、ホスト侵入防止システム、保護規則、悪用防止ルール、悪用防止ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、ASR 規則の構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 4e538a4e986ad0636c380ec2ba167249221ac3ec
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66602494"
---
# <a name="plan-attack-surface-reduction-asr-rules-deployment"></a>攻撃面の縮小 (ASR) ルールの展開を計画する

攻撃表面縮小 (ASR) ルールをテストする場合は、適切なビジネス ユニットから始める必要があります。 まず、特定の部署の少数のユーザー グループから始めます。 特定のビジネス ユニット内で、ASR ルールに対する実際の影響を提供し、実装の調整に役立つ ASR チャンピオンを特定できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-planning-steps.png" alt-text="ASR ルールの計画手順" lightbox="images/asr-rules-planning-steps.png":::

## <a name="start-with-the-right-business-unit"></a>適切な部署から始める

ASR ルールの展開をロールアウトする部署を選択する方法は、次のような要因によって異なります。

- 部署のサイズ
- ASR ルールのチャンピオンの可用性  
- 次の分布と使用方法:
  - ソフトウェア
  - 共有フォルダー
  - スクリプトの使用
  - Office マクロ
  - ASR 規則の影響を受けるその他のエンティティ

ビジネス ニーズに応じて、ソフトウェア、共有フォルダー、スクリプト、マクロなどの広範なサンプリングを取得するために、複数の部署を含めることにした場合があります。逆に、最初の ASR ルールロールアウトの範囲を 1 つの部署に制限し、ASR ルールのロールアウト プロセス全体を他の部署 (一度に 1 回) に繰り返します。

## <a name="identify-asr--rules-champions"></a>ASR ルールのチャンピオンを特定する

ASR ルールのチャンピオンは組織内のメンバーであり、事前のテストと実装の段階で最初の ASR ルールのロールアウトに役立ちます。 通常、チャンピオンは技術的に熟達しており、断続的なワークフロー停止によって脱線していない従業員です。 チャンピオンの関与は、組織への ASR ルールの展開の広範な拡大を通じて継続されます。 ASR ルールのチャンピオンは、最初に ASR ルールのロールアウトの各レベルを体験します。

ASR ルールのチャンピオンに対してフィードバックと応答チャネルを提供して、ASR ルール関連の作業中断を通知し、ASR ルールのロールアウトに関連する通信を受け取るようにすることが重要です。

## <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>基幹業務アプリのインベントリを取得し、部署のプロセスを理解する

ASR ルールの展開を成功させるには、組織全体で使用されるアプリケーションとビジネス単位ごとのプロセスを完全に理解することが重要です。 さらに、組織内のさまざまな部署内でこれらのアプリがどのように使用されるかを理解することが不可欠です。
まず、組織全体で使用が承認されているアプリのインベントリを取得する必要があります。 Microsoft 365 Apps管理センターなどのツールを使用して、ソフトウェア アプリケーションのインベントリを作成できます。 参照: [Microsoft 365 Apps管理センターのインベントリの概要](/deployoffice/admincenter/inventory)。

## <a name="define-reporting-and-response-team-roles-and-responsibilities"></a>レポートと応答チームの役割と責任を定義する

ASR ルールの状態とアクティビティの監視と伝達を担当する担当者の役割と責任を明確に明示することは、ASR メンテナンスの中核となるアクティビティです。 そのため、次の点を判断することが重要です。

- レポートの収集を担当するユーザーまたはチーム
- レポートを共有する方法と相手
- ASR ルールによって引き起こされる新たに特定された脅威または望ましくないブロックに対するエスカレーションの対処方法

一般的なロールと責任は次のとおりです。

- IT 管理者: ASR ルールを実装し、除外を管理します。 アプリとプロセスでさまざまな部署を操作します。 利害関係者へのレポートのアセンブルと共有
- 認定セキュリティ オペレーション センター (CSOC) アナリスト: 優先度の高いブロックされたプロセスを投資し、脅威が有効かどうかを判断する責任があります
- 最高情報セキュリティ責任者 (CISO): 組織の全体的なセキュリティ体制と正常性を担当する

## <a name="ring-deployment"></a>リング展開

大企業の場合は、ASR ルールを "リング" に展開することをお勧めします。 リングは、重複しないツリー リングのように外側に放射する同心円として視覚的に表されるデバイスのグループです。 最も内側のリングが正常にデプロイされたら、次のリングをテスト フェーズに移行できます。 ビジネス ユニット、ASR ルールのチャンピオン、アプリ、プロセスを徹底的に評価することは、リングを定義するために不可欠です。
ほとんどの場合、組織は、Windows 更新プログラムの段階的なロールアウト用に展開リングを設計します。 既存のリングデザインを使用して、ASR ルールを実装できます。
参照: [Windows の展開計画を作成する](/windows/deployment/update/create-deployment-plan)

## <a name="additional-topics-in-this-deployment-collection"></a>このデプロイ コレクションのその他のトピック

[攻撃面の縮小 (ASR) ルールの展開の概要](attack-surface-reduction-rules-deployment.md)

[攻撃面の減少 (ASR) ルールをテストする](attack-surface-reduction-rules-deployment-test.md)

[攻撃面の減少 (ASR) ルールを有効にする](attack-surface-reduction-rules-deployment-implement.md)

[攻撃面の減少 (ASR) ルールの運用化](attack-surface-reduction-rules-deployment-operationalize.md)

[攻撃面の減少 (ASR) ルールの参照](attack-surface-reduction-rules-reference.md)
