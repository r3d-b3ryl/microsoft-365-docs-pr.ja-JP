---
title: Microsoft 365を使用してデータプライバシー規制の情報保護を展開する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: admindeeplinkCOMPLIANCE
description: GDPR やカリフォルニア州消費者プライバシー法 (CCPA) などのデータ プライバシー規制 (Microsoft Teams、SharePoint、電子メールなど) のMicrosoft 365で情報保護を構成します。
ms.openlocfilehash: ece8483773d3e2f5cdafe90bd93e11c52e2ba838
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939018"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Microsoft 365を使用してデータプライバシー規制の情報保護を展開する

組織は、オンプレミスとクラウドの両方を含め、IT インフラストラクチャに格納されている個人情報を保護、管理、提供することを求める地域のデータ プライバシー規制の対象となる場合があります。 データ プライバシー規制の最良の例は、欧州連合の一般データ保護規則 (GDPR) です。 データプライバシー規制に従わないと、大幅な罰金が科される可能性があります。

Microsoft 365のデータの種類の例には、Microsoft Teamsでのチャット セッション、Exchange内のメール、SharePointとOneDrive内のファイルなどがあります。 このソリューションでは、リスクを評価し、Microsoft 365の個人データを保護するための適切なアクションを実行する方法に関するガイダンスを提供します。 これには、データ プライバシー インシデントを保護、管理、および対応できるように個人情報を識別することが含まれます。

![データ プライバシー規制の情報保護とは何ですか。](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

また、データプライバシーのニーズに応じて、Microsoft 365 ID、デバイス、脅威保護の制御の使用に関する追加情報も提供されます。

このビデオでは、展開プロセスの概要について説明します。
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

これらのMicrosoft 365機能と機能は、情報を保護するための条件を満たすのに役立ちます。

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| コンプライアンス マネージャー | 規制コンプライアンス アクティビティを管理し、現在のコンプライアンス構成の全体的なスコアを取得し、改善のための推奨事項を見つけます。 これは、Microsoft Purview コンプライアンス ポータルのワークフロー ベースのリスク評価ツールです。 | Microsoft 365 E3、E5 |
| Microsoft Defender for Office 365 | メール メッセージ、Office ドキュメント、共同作業のツールなど、Microsoft 365 のアプリやデータを攻撃から保護します。 | Microsoft 365 E3、E5 |
| 秘密度ラベル | ユーザーの生産性と共同作業の能力を妨げることなく、組織のデータを分類して保護します。 電子メール、ファイル、またはサイトに、さまざまなレベルの保護を含むラベルを配置します。 | Microsoft 365 E3、E5 |
| データ損失防止 (DLP) | 個人情報を含むデータのリスク、不注意、または不適切な共有を、内部と外部の両方で検出、警告、ブロックします。 | Microsoft 365 E3、E5 |
| データの保持ラベルとポリシー | 情報ガバナンス制御を実装する。 これには、組織のポリシーやデータ規制に準拠するためにデータ (顧客に関連する個人データなど) を保持する期間を決定することが含まれます。 | Microsoft 365 E3、E5 |
| メールの暗号化 | 組織内外のユーザー間で暗号化された電子メール メッセージを送受信することで、個人データを保護します。 | Microsoft 365 E3、E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>このソリューションのガイダンスの編成

1 つ以上のプライバシー関連の規制を満たすために使用できるMicrosoft 365 ツールを理解しやすくするために、このガイダンスはセクションにまとめられます。

![データ プライバシー規制に対する情報保護を実装する手順。](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

これらの各セクションは、このソリューションの個別の記事に対応しています。

> [!NOTE]
> データプライバシーの義務に既に精通していて、既存のプランに対して実行している場合は、防止、保護、保持、および調査のガイダンスに重点を置く必要があります。

> [!IMPORTANT]
> このガイダンスに従うと、データ プライバシー規制に準拠できるとは限りません。特に、機能のコンテキスト外に必要な手順の数を考慮します。 お客様は、コンプライアンスを確保し、法的およびコンプライアンス チームに相談したり、コンプライアンスに特化したサード パーティからのガイダンスやアドバイスを求めたりする責任があります。

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>計画: データ プライバシー リスクを評価し、機密アイテムを特定する

組織の対象となるデータ プライバシー規制とリスクを評価することは、Microsoft 365での機能の構成など、改善の実装を開始する前に行う重要な最初のステップです。 この作業には、組織が遵守する必要がある規制の対象となる特定の機密情報の種類の全体的な準備状況の評価または識別が含まれる場合があります。

詳細については、「 [データ プライバシー リスクを評価し、機密アイテムを特定する](information-protection-deploy-assess.md)」を参照してください。

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>追跡: リスク評価を実行し、コンプライアンス スコアを確認する

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>で利用できるコンプライアンス マネージャーには、改善アクション全体を追跡および管理するための組み込みの機能と、お客様に適用される複数のデータ プライバシー規制に関連する機能が用意されています。

各規制に固有の組み込みの評価テンプレートを使用して、選択した各評価テンプレートのアクション 項目を追跡したり、特定の規制制御を表示したり、特定のアクションに関連付けたりすることができます。

詳細については、「 [コンプライアンス マネージャーを使用して改善アクションを管理する」を](information-protection-deploy-compliance.md)参照してください。

## <a name="prevent-protect-personal-data"></a>防止: 個人データを保護する

Microsoft 365は、データ プライバシー規制コンプライアンスへの準拠に役立つ ID、デバイス、脅威保護機能を提供します。

詳細については、「 [データ プライバシー規制に ID、デバイス、脅威保護を使用する」を](information-protection-deploy-identity-device-threat.md)参照してください。

この記事では、これらの分野でデータ プライバシー規制が一般的に求める内容について簡単に説明し、関連するMicrosoft 365 ソリューションの一覧を提供します。実装要件に対処するために役立つ詳細情報へのリンクが記載されています。

## <a name="protect-information-subject-to-data-privacy-regulation"></a>データプライバシー規制の対象となる情報を保護する

データプライバシー規制には、GDPR、カリフォルニア消費者保護法 (CCPA)、HIPAA-HITECH (米国医療プライバシー法)、ブラジルデータ保護法 (LGPD) の 4 つのデータ プライバシー規制だけで情報を保護するための 40 を超える制御など、お客様の環境で使用できるさまざまな個人情報保護管理が規定されています。

詳細については、「組織内の [データ プライバシー規制の対象となる情報を保護する」を参照してください](information-protection-deploy-protect-information.md)。

この記事では、組織内のデータプライバシーに関する情報保護のニーズに対処するために使用できる主な制御スキームについて説明します。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保持: データプライバシー規制の対象となる情報を管理する

データ プライバシー規制では、GDPR、CCPA、HIPAA-HITECH、LGPD のサンプル セットの 4 つのデータ プライバシー規制全体で 24 を超えるコントロールを含む、お客様の環境で使用できる個人情報ガバナンス制御が求められます。

詳細については、「組織の [データ プライバシー規制の対象となる情報を管理する」を参照してください](information-protection-deploy-govern.md)。

データプライバシー規制は、意図的な保持、削除、アーカイブ&mdash;など、情報ガバナンス&mdash;に関してあいまいな場合がありますが、この記事では、組織のデータプライバシーに必要な情報ガバナンスのアドレスを使用できる主な制御スキームを示しています。

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>調査: データ プライバシー インシデントの監視、調査、および対応

関連する機能を運用化するときに、組織内のデータ プライバシー インシデントの監視、調査、および対応に役立つMicrosoft 365機能があります。

これらの機能を使用するためのプロセス、手順、およびその他のドキュメントを持つことは、規制機関へのコンプライアンスを示すために重要な場合があります。

詳細については、「組織内の [データ プライバシー インシデントを監視して対応する](information-protection-deploy-monitor-respond.md)」を参照してください。

## <a name="training-for-administrators"></a>管理者向けのトレーニング

Microsoft Learn のこれらのトレーニング モジュールは、情報保護に重要な機能について学習するのに役立ちます。


#### <a name="information-protection"></a>情報保護

|トレーニング: |Microsoft 365 で企業情報を保護する|
|:---|:---|
|![Teams情報保護トレーニング アイコン。](../media/protect-enterprise-information-microsoft-365.svg)|組織の情報を保護することは、かつてないほど困難になっています。 「Microsoft 365 で社内の情報を保護する」のラーニング パスでは、機密情報を不用意な共有や誤用から保護する方法、データを検出して分類する方法、秘密度ラベルを使用して保護する方法、損失から保護するために機密情報を監視および分析する方法について説明します。 このラーニング パスは、Microsoft 365認定: セキュリティ管理者アソシエイトおよびMicrosoft 365認定: Enterprise Administration Expert 認定資格の準備に役立ちます。<br><br>1 時間 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>ID とアクセス

|トレーニング: |Azure Active Directory で ID とアクセスを保護する|
|:---|:---|
|![ID とアクセスのトレーニング アイコン。](../media/protect-identity-and-access-with-microsoft-365.svg)|ID とアクセスのラーニングパスは、最新の ID およびアクセステクノロジ、認証を強化するためのツール、組織内での ID 保護のガイダンスについて説明しています。 Microsoft ID およびアクセステクノロジを使用すると、組織のIDをオンプレミスでもクラウドでも保護し、ユーザーがどこからでも安全に作業できるようになります。 このラーニングパスはMicrosoft 365 認定: セキュリティ管理者 と Microsoft 365 認定: エンタープライズ管理エキスパート の認定のための準備を行うことが出来ます。<br><br>2 時間 52 分 - ラーニング パス - 6 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-identity-overview/introduction/)