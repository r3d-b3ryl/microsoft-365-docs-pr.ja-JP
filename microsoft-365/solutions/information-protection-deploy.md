---
title: Microsoft 365 を使用して、データプライバシー規制の情報保護を展開する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 情報を保護し、データのプライバシー規制に準拠するように、セキュリティとサービスインフラストラクチャを構成します。
ms.openlocfilehash: 4296e2f08d9dada62cc45226885d9519a33e6532
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655815"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Microsoft 365 を使用して、データプライバシー規制の情報保護を展開する

組織は、オンプレミスとクラウドの両方を含む、IT インフラストラクチャに格納されている個人情報に関する権限と制御を保護、管理、提供する必要がある地域データのプライバシー規制の対象となる場合があります。 データプライバシー規制の最も良い例は、欧州連合の一般的なデータ保護規則 (GDPR) です。 データプライバシー規制への準拠に失敗すると、膨大な罰金を得られることがあります。

Microsoft 365 のデータの種類の例には、Microsoft Teams のチャットセッション、Exchange の電子メール、および SharePoint および OneDrive のファイルが含まれています。 このソリューションでは、データのプライバシーに関する規制の対象となる Microsoft 365 services に格納されている個人データについて、リスクを評価し、情報の識別、データの保護、管理、および応答を行う方法についてのガイダンスを提供します。

![データプライバシー規制に関する情報保護とは](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

また、データのプライバシーのニーズに合わせて Microsoft 365 の id、デバイス、および脅威保護の制御を使用する場合にも、追加情報が提供されます。 

データのプライバシー規制に準拠するために情報を保護するための基準を満たすには、次の Microsoft 365 の機能と機能を使用します。

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| コンプライアンス マネージャー | 法令遵守のアクティビティを管理し、現在のコンプライアンス構成の全体的なスコアを取得し、このワークフローベースのリスク評価ツールでの改善に関する推奨事項を Microsoft 365 コンプライアンスセンターで見つけることができます。 | Microsoft 365 E3、E5 |
| Office Advanced Threat Protection (ATP) | メール メッセージ、Office ドキュメント、共同作業のツールなど、Microsoft 365 のアプリやデータを攻撃から保護します。 | Microsoft 365 E3、E5 | 
| 秘密度ラベル | メール、ファイル、サイトに様々な保護レベルを持ったラベルを適用することで、ユーザーの生産性や共同作業機能を妨げることなく、組織のデータを分類して保護します。 | Microsoft 365 E3、E5 |
| データ損失防止 (DLP) | 内部や外部での個人情報を含むデータの共有などの危険な共有、偶発的な共有、不適切な共有を検出し、警告し、ブロックします。 | Microsoft 365 E3、E5 | 
| データの保持ラベルとポリシー | データの保持期間や、顧客の個人データの保管についての要件などの情報ガバナンスの制御を展開し、組織のポリシーやデータ規制に準拠します。 | Microsoft 365 E3、E5 |
| メールの暗号化 | 組織内外のユーザーとの間で、顧客の個人情報などの規制されたデータを含む暗号化されたメール メッセージを送受信します。 | Microsoft 365 E3、E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>このソリューションのガイダンスの編成

1つまたは複数のプライバシー関連の規制の対象となる個人データの識別、管理、制御、監視に使用できる Microsoft 365 ツールの理解を助けるために、このガイダンスはセクションで構成されています。
 
![データプライバシー規制に関する情報保護を実装するための手順](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

これらの各セクションは、このソリューションの個別の記事に対応しています。

>[!Note]
>データプライバシーの義務に精通していて、既存のプランに対して実行されている場合は、禁止、保護、保持、および調査のガイダンスに集中することをお勧めします。

>[!Important]
>このガイダンスに従うことで、特に、機能のコンテキストの範囲外で必要とされる手順の数を考慮して、データプライバシー規制に準拠しているわけではありません。 お客様は、コンプライアンスを保証し、法務/コンプライアンスチームを参照したり、コンプライアンスを専門とするサードパーティのガイダンスやアドバイスを求めたりする責任を負います。
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>計画: データのプライバシーリスクを評価し、機密アイテムを識別する

お客様の組織が対象となるデータのプライバシーに関する規制とリスクは、Microsoft 365 構成を通じて実現可能なものを含む、改善の実装を開始する前に行う重要な最初の手順です。 これには、全体的な準備状況の評価、または組織が準拠する必要がある規制統制の対象となる特定の機密情報の種類の確認、および Microsoft 365 環境でのそれらの発生の確認が含まれます。

詳細については、「 [データプライバシーのリスクを評価し、機密性の高いアイテムを識別](information-protection-deploy-assess.md)する」を参照してください。

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>追跡: リスク評価を実行し、コンプライアンススコアを確認する

Microsoft 365 コンプライアンスセンターで提供されるコンプライアンスマネージャーには、強化アクション全体を追跡および管理するための組み込みの機能と、ユーザーに適用される複数のデータプライバシー規制に関連する機能が用意されています。

各規制に固有の組み込みの評価テンプレートを活用して、選択した各評価テンプレートのアクションアイテムを追跡したり、特定の規制統制を表示したり、特定のアクションに関連付けたりすることができます。

詳細については、「 [コンプライアンスマネージャーを使用して改善アクションを管理する](information-protection-deploy-compliance.md)」を参照してください。

## <a name="prevent-protect-personal-data"></a>禁止: 個人データを保護する

Microsoft 365 は、id、デバイス、および脅威の保護に関するさまざまな機能を提供します。これを使用すると、データプライバシーに関する法令遵守に準拠することができます。 

詳細については、「 [データプライバシー規制の id、デバイス、および脅威保護を使用する](information-protection-deploy-identity-device-threat.md)」を参照してください。

この記事では、一般的にこれらの分野でのデータプライバシー規制について説明し、関連する Microsoft 365 ソリューションの一覧を示します。また、実装要件に対処するための詳細情報へのリンクも掲載しています。 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>情報をデータプライバシーの規則に従って保護する

データプライバシーに関する規制では、GDPR のサンプルセットに含まれる4つのデータプライバシー規制、HIPAA (米国の医療保険法)、HIPAA データ保護法 (LGPD) での4つのデータプライバシー規制に関する情報を保護することができる40、さまざまな個人情報保護の制御があります。

詳細については、「 [組織のデータプライバシー規制に関する情報を保護する](information-protection-deploy-protect-information.md)」を参照してください。

この記事では、組織内のデータプライバシーに関する情報保護のニーズに対処するために使用できる主要な制御スキームについて説明します。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保持: データプライバシーの規則に従って情報を管理する

データプライバシーに関する規制 GDPR のサンプルセットに含まれる4つのデータプライバシー規則 (CCPA、HIPAA、および LGPD) について、24個を超えるコントロールを含む、個人情報ガバナンスの統制についてご連絡ください。

詳細については、「 [組織のデータプライバシー規制に関する情報を管理する](information-protection-deploy-govern.md)」を参照してください。

意図的の保存、削除、アーカイブなどの情報ガバナンスに関しては、データプライバシーに関する規制をあいまいにすることができますが、 &mdash; &mdash; この記事では、組織内のデータのプライバシーに関する情報ガバナンスのニーズを解決するために使用できる主要な制御スキームについて説明します。

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>調査: データプライバシーインシデントの監視、調査、および対応

Operationalize 関連の機能を使用して、組織内のデータプライバシーインシデントの監視、調査、および対応に役立てることができる Microsoft 365 の機能があります。 

これらのプロセス、手順、およびその他のドキュメントに関するその他のドキュメントは、規制機関に準拠していることを示すために重要な場合があります。

詳細については、「 [組織内のデータプライバシーインシデントを監視および応答する](information-protection-deploy-monitor-respond.md)」を参照してください。
