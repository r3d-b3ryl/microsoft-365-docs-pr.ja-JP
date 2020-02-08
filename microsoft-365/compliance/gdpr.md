---
title: 一般データ保護規則
description: 一般データ保護規則 (GDPR) のための Microsoft 技術ガイダンス
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0ead7cbabc87b7d852cf61fc414df65315c25e39
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596334"
---
# <a name="general-data-protection-regulation-summary"></a>一般データ保護規則の概要

一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrOQI] 

このドキュメントでは、Microsoft の製品とサービスを使用する際の GDPR に基づく権利の尊重と義務の履行に役立つ情報を提供します。 「[GDPR の推奨アクション プラン](gdpr-action-plan.md)」および「[アカウンタビリティ対応準備チェックリスト](gdpr-arc.md)」では、GDPR コンプライアンスの評価と実装のための追加リソースを参照できます。

## <a name="terminology"></a>用語

このドキュメントで使用されている GDPR 用語の役に立つ定義:

- *データ コントローラー (コントローラー)*: 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。  
- *個人データ*と*データ主体*: 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。  
- *処理者*: コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。  
- *顧客データ*: ビジネス運営における日々の業務で作成および保存されるデータ。

## <a name="what-is-the-gdpr"></a>GDPR とは?

GDPR では、組織によって収集された個人データを管理する権利が人々に付与されます。 これらの権利は、データ主体の要求 (DSR) 経由で行使できます。 組織は、DSR およびデータ違反に関する情報をタイムリーに提供し、データ保護影響評価 (DPIA) を実行する必要があります。

GDPR 要件を実装または評価する場合は、いくつかの点を考慮する必要があります。

- GDPR コンプライアンスのデータ プライバシー ポリシーの開発または評価。
- 組織のデータ セキュリティの評価。
- データ コントローラーとなる人は?
- どのようなデータ セキュリティ プロセスを実行する必要があるか?

「[GDPR の推奨アクション プラン](gdpr-action-plan.md)」と「[アカウンタビリティ対応準備チェックリスト](gdpr-arc.md)」では、考慮するポイントがさらに示される場合があります。

GDPR 基準を満たすには、次のタスクが必要です。 実装に関する詳細については、リスト内のリンクを参照してください。  

- **[データ主体の要求 (DSR)](gdpr-data-subject-requests.md)**。 個人データに関するアクション (変更、制限、アクセス) を実行するように、データ主体がコントローラーに対して行う正式な要求。
- **[違反の通知](gdpr-breach-notification.md)**。 GDPR では、個人データ違反とは、「送信、保存、またはその他の方法で処理される個人データの偶発的または違法の破損、損失、改変、不正漏洩、またはアクセスを引き起こすセキュリティ違反」です。
- **[データ保護影響評価 (DPIA)](gdpr-data-protection-impact-assessments.md)**。 データ コントローラーは、GDPR に基づき、「自然人の権利と自由を危険にさらす可能性が高い」データ操作に関して DPIA を準備する必要があります。

上記で説明したように、GDPR の推奨アクション プランとアカウンタビリティ対応準備チェックリストでは、Microsoft の製品とサービスの使用において GDPR 準拠を実装または評価するためのガイドが提供されています。

## <a name="the-gdpr-in-action"></a>実行中の GDPR

このセクションでは、前述の GDPR タスクの完了に関する概要と考慮するポイントについて説明します。 これらのタスクの完了は、Microsoft の構成によって異なる場合があります。

### <a name="data-subject-request-dsr"></a>データ主体の要求 (DSR)

データ主体の要求は、GDPR に基づきデータ主体が権限を行使する手段を提供します。 コントローラーには、タイムリーで一貫性のある GDPR 応答を提供する責任があります。 検討する必要がある質問については、以下を参照してください。 技術的な詳細については、「[データ主体の要求](gdpr-data-subject-requests.md)」を参照してください。  

- **DSR を完了するにはどのようなアクションが必要か?**: DSR には、検出、アクセス、修正、制限、エクスポート、削除の 6 つのアクティビティが含まれています。
- **データ ソースとは?**: 組織のデータの大部分は、Excel や Outlook などの [Office アプリケーション](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)で生成されます。 また、DSR に関連するデータは、Microsoft の製品とサービスによって生成された[分析情報](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)、および[システム生成ログ](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)でも検索することもできます。
- **どのような種類のデータを検索する必要があるか?**: 個人データは、顧客データ、Microsoft の製品とサービスによって生成された分析情報、システム生成ログに含まれていることがあります。
- **個人データの検索方法は?**: 個人データの検索は、Microsoft の製品とサービスによって異なる場合があります。 検索ツールには、[コンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)、または[アプリ内検索](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs)能力が用意されています。 管理者は、ユーザーのアクティビティに関連する[システム生成ログ](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)にアクセスできます。  
- **どのような形式で個人データを利用できるようにする必要があるか?**: GDPR の「データの移植の権利」により、データ主体は、「構造化された一般的に使用されているコンピューターが読み取り可能な形式」で個人データのコピーを要求できます。また、そうしたファイルを別のデータ コントローラーに送信するように組織に要求することもできます。

### <a name="data-protection-impact-assessment"></a>データ保護影響評価

GDPR では、データ コントローラーは「自然人の権利と自由を危険にさらす可能性が高い」操作処理に関して[データ保護影響評価](gdpr-data-protection-impact-assessments.md) (DPIA) を準備する必要があります。 DPIA の作成を必要とする Microsoft の製品とサービスに固有のものはありません。 むしろ、Microsoft 構成の詳細に依存しています。

以下に、DPIA に関するいくつかの考慮事項について説明します。 Office での考慮事項に関する詳細のリストは、「[DPIA の内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)」を参照してください。

- 組織内のどのようなデータ アクティビティが個人データのセキュリティを侵害する可能性があるか?
- Microsoft の製品とサービスの構成がデータ侵害に対して脆弱である可能性があるか?
- DPIA はいつ実行する必要があるか?

    - コントローラーは、個人データのセキュリティに対するリスク、またはデータ侵害から生じるリスクに対処する DPIA を実行する必要があります。 Office のリスク要因の具体例は、「[DPIA が必要であるかどうかの判断](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed)」で説明されています。  

- DPIA を完了するために何が必要か?

    GDPR では、DPIA に次の事項を含めるよう規定されています。  
    - DPIA の目的に関するデータ処理作業の必要性および比例性の評価。
    - データ主体の権利および自由に関するリスクの評価。
    - リスク、セーフガード、セキュリティ対策、メカニズムに対処して、個人データを確実に保護し、GDPR 準拠を実証するための想定された対策。

### <a name="breach-notification"></a>違反の通知

データ処理者として、Microsoft は、必ずお客様が GDPR の違反通知要件を満たせるようにしています。 データ コントローラーは、データ プライバシーに対するリスクを評価し、お客様の DPA に通知する必要がある違反かどうかを判断する責任があります。 Microsoft は、その評価に必要な情報を提供しています。 Microsoft が個人データの侵害を検出して対応する方法の詳細については、「[GDPR の下での違反の通知](gdpr-breach-notification.md)」を参照してください。 違反の通知に関する質問には、次のようなものがあります。

- データ主体に、違反についてどのような情報を伝える必要があるか?
- データ主体にどのような方法 (メール、書面による通知など) で伝えるか?

### <a name="accountability-readiness-checklists-for-the-gdpr"></a>GDPR に関するアカウンタビリティ対応準備チェックリスト

これらの[チェックリスト](gdpr-arc.md)は、Microsoft 製品の使用において、GDPR をサポートしなければならない可能性のある情報にアクセスする便利な方法を提供します。 [Microsoft コンプライアンス スコア](compliance-score.md)で、GDPR タイル内の顧客管理コントロールの下にあるコントロール ID とコントロール タイトルを参照することによって、チェックリスト項目を管理できます。

## <a name="learn-more"></a>詳細情報

- [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
