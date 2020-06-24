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
- M365solutions
ms.custom: ''
description: 情報を保護し、データのプライバシー規制に準拠するように、セキュリティとサービスインフラストラクチャを構成します。
ms.openlocfilehash: ea0f5ead93dc631a28577a61f33bca3b601406f4
ms.sourcegitcommit: 4512f54ba80d869d4c04e8f9bd897d1878280852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854337"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Microsoft 365 を使用して、データプライバシー規制の情報保護を展開する

組織は、オンプレミスとクラウドの両方を含む、IT インフラストラクチャに格納されている個人情報に関する権限と制御を保護、管理、提供する必要がある地域データのプライバシー規制の対象となる場合があります。 データプライバシー規制の最も良い例は、欧州連合の一般的なデータ保護規則 (GDPR) です。 データプライバシー規制への準拠に失敗すると、膨大な罰金を得られることがあります。

Microsoft 365 のデータの種類の例には、Microsoft Teams のチャットセッション、Exchange の電子メール、および SharePoint および OneDrive のファイルが含まれています。 このソリューションでは、データプライバシーの規制の対象となる Microsoft 365 services に格納されている個人データについて、データのプライバシーインシデントを特定、特定、保護、制御、および対応する方法についてのガイダンスを提供します。

![データプライバシー規制のための情報の展開保護](../media/information-protection-deploy/information-protection-deploy-big-picture.png)

また、データのプライバシーのニーズに合わせて Microsoft 365 の id、デバイス、および脅威保護の制御を使用する場合にも、追加情報が提供されます。 

データのプライバシー規制に準拠するために情報を保護するための基準を満たすには、次の Microsoft 365 の機能と機能を使用します。

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| コンプライアンス マネージャー | Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを、Microsoft Service Trust Portal のこのワークフローベースのリスク評価ツールを使用して管理します。 | Microsoft 365 E3、E5 |
| コンプライアンス スコア (プレビュー) | Microsoft 365 コンプライアンスセンターでの改善に関する、現在のコンプライアンス構成と推奨事項の全体的なスコアを参照してください。 | Microsoft 365 E3、E5 |
| Office Advanced Threat Protection (ATP) | Microsoft 365 のアプリとデータ (電子メールメッセージ、Office ドキュメント、コラボレーションツールなど) を攻撃から保護します。 | Microsoft 365 E3、E5 | 
| 秘密度ラベル | ユーザーの生産性を低下させることなく、組織のデータを分類して保護することができます。また、電子メール、ファイル、またはサイトにさまざまなレベルの保護を使用してラベルを作成することによって、共同作業が妨げられます。 | Microsoft 365 E3、E5 |
| データ損失防止 (DLP) | 内部と外部の両方で個人情報を含むデータの共有など、危険、偶発的、または不適切な共有の検出、警告、ブロックを行います。 | Microsoft 365 E3、E5 | 
| データ保持ラベルとポリシー | お客様の組織のポリシーやデータの規制に準拠するために、お客様の個人データの保存に関するデータと要件を維持する時間など、情報ガバナンス統制を実装します。 | Microsoft 365 E3、E5 |
| メールの暗号化 | 顧客の個人データなどの規制データを含む、組織内外のユーザー間で暗号化された電子メールメッセージの送受信を行います。 | Microsoft 365 E3、E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>このソリューションのガイダンスの編成

1つまたは複数のプライバシー関連の規制の対象となる個人データの識別、管理、制御、監視に使用できる Microsoft 365 ツールの理解を助けるために、このガイダンスはセクションで構成されています。
 
![データプライバシー規制のための情報の展開保護](../media/information-protection-deploy/information-protection-deploy-grid.png)

これらの各セクションは、このソリューションの個別の記事に対応しています。

>[!Note]
>データプライバシーの義務に精通していて、既存のプランに対して実行されている場合は、禁止、保護、保持、および調査のガイダンスに集中することをお勧めします。

>[!Important]
>このガイダンスに従うことで、特に、機能のコンテキストの範囲外で必要とされる手順の数を考慮して、データプライバシー規制に準拠しているわけではありません。 お客様は、コンプライアンスを保証し、法務/コンプライアンスチームを参照したり、コンプライアンスを専門とするサードパーティのガイダンスやアドバイスを求めたりする責任を負います。
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>計画: データのプライバシーリスクを評価し、機密アイテムを識別する 

お客様の組織が対象となるデータのプライバシーに関する規制とリスクは、Microsoft 365 構成を通じて実現可能なものを含む、改善の実装を開始する前に行う重要な最初の手順です。 これには、全体的な準備状況の評価、または組織が準拠する必要がある規制統制の対象となる特定の機密情報の種類の確認、および Microsoft 365 環境でのそれらの発生の確認が含まれます。

詳細については、「[データプライバシーのリスクを評価し、機密性の高いアイテムを識別](information-protection-deploy-assess.md)する」を参照してください。

## <a name="track-use-compliance-score-and-compliance-manager"></a>追跡: コンプライアンススコアとコンプライアンスマネージャーを使用する 

コンプライアンススコア/コンプライアンスマネージャー Microsoft 365 コンプライアンス管理センターおよびサービス信頼ポータルで使用可能な一連のツールを統合して提供します。 これらのツールによって、強化された操作全体を追跡して管理することができます。また、対象とする複数のデータプライバシー規制に関連するものも提供します。

また、このツールを使用すると、各規制に固有の組み込みの評価テンプレートを活用することができます。ここでは、選択された各評価テンプレートのアクションアイテムを追跡し、特定の規制統制を表示し、特定のアクションに関連付けることができます。

詳細については、「[コンプライアンススコアとコンプライアンスマネージャーを使用して改善アクションを管理する](information-protection-deploy-compliance.md)」を参照してください。

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>回避方法: id、デバイス、および脅威保護にデータプライバシー規制を使用します。

Microsoft 365 は、id、デバイス、および脅威の保護に関するさまざまな機能を提供します。これを使用すると、データプライバシーに関する法令遵守に準拠することができます。 

詳細については、「[データプライバシー規制の id、デバイス、および脅威保護を使用する](information-protection-deploy-identity-device-threat.md)」を参照してください。

この記事では、一般的にこれらの分野でのデータプライバシー規制について説明し、関連する Microsoft 365 ソリューションの一覧を示します。また、実装要件に対処するための詳細情報へのリンクも掲載しています。 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>情報をデータプライバシーの規則に従って保護する

データプライバシーに関する規制では、GDPR のサンプルセットに含まれる4つのデータプライバシー規制、HIPAA (米国の医療保険法)、HIPAA データ保護法 (LGPD) での4つのデータプライバシー規制に関する情報を保護することができる40、さまざまな個人情報保護の制御があります。

詳細については、「[組織のデータプライバシー規制に関する情報を保護する](information-protection-deploy-protect-information.md)」を参照してください。

この記事では、組織内のデータプライバシーに関する情報保護のニーズに対処するために使用できる主要な制御スキームについて説明します。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保持: データプライバシーの規則に従って情報を管理する

データプライバシーに関する規制 GDPR のサンプルセットに含まれる4つのデータプライバシー規則 (CCPA、HIPAA、および LGPD) について、24個を超えるコントロールを含む、個人情報ガバナンスの統制についてご連絡ください。

詳細については、「[組織のデータプライバシー規制に関する情報を管理する](information-protection-deploy-govern.md)」を参照してください。

意図的の保存、削除、アーカイブなどの情報ガバナンスに関しては、データプライバシーに関する規制をあいまいにすることができますが、 &mdash; &mdash; この記事では、組織内のデータのプライバシーに関する情報ガバナンスのニーズを解決するために使用できる主要な制御スキームについて説明します。

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>調査: データプライバシー規制を監視し、件名に対応する

Operationalize 関連の機能を使用して、組織内のデータプライバシーインシデントの監視、調査、および対応に役立てることができる Microsoft 365 の機能があります。 

これらのプロセス、手順、およびその他のドキュメントに関するその他のドキュメントは、規制機関に準拠していることを示すために重要な場合があります。

詳細については、「[組織内のデータプライバシーインシデントを監視および応答する](information-protection-deploy-monitor-respond.md)」を参照してください。
