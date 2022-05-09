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
description: Microsoft 365保持ラベルとポリシーを使用して、Microsoft 365環境で個人データを管理します。
ms.openlocfilehash: 05aad5b26f65dc66543afb29834e7cc4514e3366
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64947387"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>データプライバシー規制の対象となる情報を管理する

情報ガバナンス制御は、一般データ保護規則 (GDPR)、HIPAA-HITECH (米国医療プライバシー法)、カリフォルニア消費者保護法 (CCPA)、ブラジルデータ保護法 (LGPD) に固有の数を含む、データ プライバシー コンプライアンスのニーズに対応するために、環境で使用できます。 

これらのコントロールは、主に次のソリューション領域に分類されます。

- 保持ポリシー
- 保持ラベル
- レコード管理

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>情報ガバナンス制御に影響を与えるデータ プライバシー規制

情報ガバナンス管理に関連する可能性のあるデータ プライバシー規制のサンプル一覧を次に示します。

- GDPR 記事 (13)(2)(a)
- GDPR 記事 (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- LGPD 記事 46

これらの規制の詳細については、 [データ プライバシー リスクの評価と機密情報の特定に関する記事を](information-protection-deploy-assess.md)参照してください。

情報ガバナンスの場合、データ プライバシー規制では通常、次のものが必要です。

- Microsoft 365に格納されている個人データの保持と削除に関する技術的スキームを採用する必要があります。
- 個人データを保存する場合は、データが保存される期間を件名に通知します。これは、フロントエンド Web システムでの標準的なプラクティスです。
- 個人データは、検証可能な方法を使用して、偶発的な処理、損失、または変更から保護する必要があります。
- 個人データに対して実行されるすべてのアクションを文書化し、そのドキュメントを指定された期間保持する必要があります。

データの保持と削除に関しては、データプライバシー規制はそれほど具体的ではないため、Microsoft 365 サブスクリプションに格納されている個人情報の情報ガバナンスガイドラインを規定する可能性があるその他の要因を考慮する必要があります。 いくつかの例を示します。

- 非アクティブな状態が 5 年間続いた後にコンシューマー アカウントをエージングアウトするには、その時点以降にアカウント データを削除または匿名化する必要があり、通知とその他の自動化に関連するデータとワークフローを格納するシステム間のオーケストレーションが必要になります。
- GDPR に関連するポリシーと手順を置き換えてから約 3 年間保持するためのルールを構成します。これは、ポリシーと手順に関する組織の保持スケジュールに合わせて調整されます。
- サポート組織を通じてコンシューマーと通信するための別のサブスクリプションを維持する。 すべての電子メール通信は、システム内のプライバシー負債の蓄積を減らすために、2 週間後に保持および削除されました。

回答する重要な質問は次のとおりです。 

- 個人データを含む情報を、ビジネス上の正当な理由で保持し、"無期限に保持" する必要がある期間はどれくらいですか? これは、ビジネス継続性の保持ニーズとバランスを取る必要があります。

個人情報を保持または削除するための法的およびビジネス上の理由に関係なく、Microsoft はデータ ガバナンススキームをMicrosoft 365に実装するためのさまざまな機能を提供します。

## <a name="managing-information-governance-in-microsoft-365"></a>Microsoft 365での情報ガバナンスの管理

最初に、「[Microsoft 365の Microsoft Purview](../compliance/manage-data-governance.md) と[データの保持、削除、破棄を使用してデータを](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)管理する」を参照してください。

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>コンテナー、電子メール、およびコンテンツのデータ保持スケジュールを作成する

以下の点にご注意ください。

- 定義された情報の種類のデータ保持スケジュールを確立することは、保持または削除スキームを実装するための前提条件と見なす必要があります。

- ほとんどの組織が重要と考える情報の種類の数とそれに伴う対応する大規模なレコード保持スケジュールを考えると、データ保持とレコード管理戦略を実装するには、計画が必要です。 

- この種の効果的なデータ ガバナンス戦略を確立するための鍵は、より正式な管理を必要とする最も優先度の高いビジネス機能と情報の種類に焦点を当てることです。 たとえば、法的契約、財務明細書、および規制コンプライアンスのドキュメントがあります。 1 つの情報の種類ごとに個別の保持スケジュールを設定しないようにしてください。 たとえば、一般的なビジネス コンテンツのリテンション期間が 7 年間など、できるだけ一般的なカテゴリを利用してみてください。

- 環境内の個人情報の種類をよりよく知ったら、この種類のコンテンツの保持と削除のスケジュールを確立し、この種の情報のガバナンスを容易にするために情報アーキテクチャを調整します。 たとえば、アクセスが制御された個別のサイト、ライブラリ、またはフォルダーに個人情報を分離します。

### <a name="retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベル

[保持ポリシーと保持ラベル](../compliance/retention.md)を使用して、個人データを含む、または含まれると予想されるMicrosoft 365内のコンテンツを保持または削除します。

### <a name="records-management"></a>レコード管理

コンテンツを宣言する保持ラベルを使用して、Microsoft 365内のデータの[レコード管理ソリューション](../compliance/records-management.md)を実装します。

データプライバシーの場合、法務部門が受け取ったデータ主体要求 (DSR) はレコードとして宣言され、規制活動の保持仕様に準拠するために、無期限に保存したり、証拠を使用して破棄したりできます。