---
title: データプライバシー規制の対象となる情報を管理する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: ユーザー Microsoft 365保持ラベルとポリシーを使用して、ユーザー環境で個人Microsoft 365管理します。
ms.openlocfilehash: b131c90e83a2ce211d51af444dd570f71f3b8263
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176309"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>データプライバシー規制の対象となる情報を管理する

情報ガバナンス管理は、一般データ保護規則 (GDPR)、HIPAA-HITECH (米国の医療プライバシー法)、カリフォルニア州消費者保護法 (CCPA)、およびブラジルデータ保護法 (LGPD) に固有の番号を含む、データ プライバシーコンプライアンスのニーズに対応するために使用できます。 

これらのコントロールは、主に次のソリューション領域に含まれます。

- 保持ポリシー
- 保持ラベル
- レコード管理

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>情報ガバナンス管理に影響を与えるデータプライバシー規制

情報ガバナンス制御に関連する可能性があるデータプライバシー規制の一覧の例を次に示します。

- GDPR 記事 (13)(2)(a)
- GDPR 記事 (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- LGPD 第 46 条

これらの規制の詳細については、「データプライバシーリスクを評価し、機密情報を [特定する」の記事を参照してください](information-protection-deploy-assess.md)。

情報ガバナンスの場合、通常、データプライバシー規制では次の情報が必要です。

- ユーザーは、ユーザーに保存されている個人データの保持と削除に関する技術的なMicrosoft 365。
- 個人データを保存する場合は、データの保存期間を件名に通知します。これは、フロントエンド Web システムでの標準的な方法です。
- 個人データは、検証可能な方法を使用して、偶発的な処理、損失、または変更から保護する必要があります。
- 個人データに対して実行されるアクションは文書化する必要があります。そのドキュメントは指定された期間保持する必要があります。

データの保持と削除に関しては、データのプライバシーに関する規制が非常に具体的ではないので、Microsoft 365 サブスクリプションに保存されている個人情報に関する情報ガバナンス ガイドラインを決定する可能性があるその他の要因を考慮する必要があります。 いくつかの例を示します。

- 5 年間の非アクティブ化後にコンシューマー アカウントをエージングし、その時点以降にアカウント データを削除または匿名化する必要があります。通知や他の自動化に関連するデータとワークフローを格納するシステム間のオーケストレーションが必要です。
- GDPR に関連するポリシーと手順を、ポリシーと手順の保持スケジュールに合わせて組織の保持スケジュールに合わせて 3 年間保持するためのルールを構成します。
- サポート組織を通じて消費者と通信するための個別のサブスクリプションを維持する。 すべての電子メール通信は、システム内のプライバシー負債の増加を減らすために、2 週間後に保持および削除されました。

答える重要な質問は次の場合です。 

- ビジネス上の有効な理由から、個人データを含む情報を保持し、"永遠に保つ" 方法を避ける必要がある期間。 これは、ビジネス継続性の保持ニーズとバランスを取る必要があります。

個人情報を保持または削除する法的およびビジネス上の理由に関係なく、Microsoft は、Microsoft 365 でデータ ガバナンス スキームを実装するためのさまざまな機能を提供します。

## <a name="managing-information-governance-in-microsoft-365"></a>管理サイトでの情報ガバナンスのMicrosoft 365

まず、「Manage [information Governance and Data](../compliance/manage-information-governance.md) [Retention, Deletion and Destruction in Microsoft 365」 を参照してください](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)。

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>コンテナー、電子メール、およびコンテンツのデータ保持スケジュールを開発する

以下の点にご注意ください:

- 定義された情報の種類のデータ保持スケジュールを確立するには、保持または削除のスキームを実装するための前提条件と見なす必要があります。

- ほとんどの組織が重要と考える情報の種類の数と、それに沿った対応する大規模なレコード保持スケジュールを考えると、データ保持とレコード管理戦略を実装するには計画が必要です。 

- この種類の効果的なデータ ガバナンス戦略を確立する鍵は、より正式な管理を必要とする最も優先度の高いビジネス機能と情報の種類に焦点を当てすることです。 例としては、法的契約、財務諸表、および規制コンプライアンスに関するドキュメントがあります。 単一の情報の種類ごとに個別の保持スケジュールを設定しないようにしてください。 一般的なビジネス コンテンツの保持スケジュールが 7 年など、可能な限り一般的なカテゴリを使用してください。

- 環境内の個人情報の種類がよりよく知られたら、この種類のコンテンツの保持と削除のスケジュールを確立し、このような情報のガバナンスを容易にするために情報アーキテクチャを調整します。 たとえば、アクセスを制御する個別のサイト、ライブラリ、またはフォルダーで個人情報を分離します。

### <a name="retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベル

アイテム[保持ポリシーと保持ラベルを使用](../compliance/retention.md)して、個人データを含む、またはMicrosoft 365コンテンツを保持または削除します。

### <a name="records-management"></a>レコード管理

コンテンツを宣言する保持ラベルを使用して、レコード[](../compliance/records-management.md)内のデータのレコード管理ソリューションMicrosoft 365。

データのプライバシーを保護するために、法務部門が受け取ったデータ主体要求 (DSR) はレコードとして宣言され、規制活動保持仕様に準拠するために無期限に保存または証拠付き廃棄することができます。