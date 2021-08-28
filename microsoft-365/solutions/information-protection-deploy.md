---
title: データプライバシーに関する規制に関する情報保護を、Microsoft 365
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
description: GDPR、Microsoft 365消費者プライバシー法 (CCPA) などのデータプライバシー規制 (Microsoft Teams、SharePoint、電子メールなど) に関する情報保護を構成します。
ms.openlocfilehash: 1cf58564938efafb0b711680cf7260222c514864
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58571207"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>データプライバシーに関する規制に関する情報保護を、Microsoft 365

組織は、オンプレミスとクラウドの両方を含む、IT インフラストラクチャに保存されている個人情報を保護、管理、および提供する必要がある地域のデータプライバシー規制の対象となる場合があります。 データプライバシー規制の最良の例は、欧州連合の一般データ保護規則 (GDPR) です。 データプライバシー規制に準拠しない場合、多額の罰金が科される可能性があります。

Microsoft 365 のデータの種類には、Microsoft Teams でのチャット セッション、Exchange のメール、SharePoint と OneDrive のファイルがあります。 このソリューションは、リスクを評価し、リスクに関する個人データを保護するための適切なアクションを実行する方法に関するMicrosoft 365。 これには、データ プライバシー インシデントを保護、管理、および対応するための個人情報の識別が含まれます。

![データプライバシー規制に関する情報保護とは。](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

また、データプライバシーのニーズに合Microsoft 365 ID、デバイス、および脅威保護制御の使用に関する追加情報も提供されます。

このビデオでは、展開プロセスの概要について説明します。
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

これらのMicrosoft 365機能は、情報を保護するための条件を満たすのに役立ちます。

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| コンプライアンス マネージャー | 規制コンプライアンス活動を管理し、現在のコンプライアンス構成の全体的なスコアを取得し、改善のための推奨事項を見つける。 これは、ワークフローベースのリスク評価ツールです。Microsoft 365 コンプライアンス センター。 | Microsoft 365 E3、E5 |
| Microsoft Defender for Office 365 | メール メッセージ、Office ドキュメント、共同作業のツールなど、Microsoft 365 のアプリやデータを攻撃から保護します。 | Microsoft 365 E3、E5 |
| 機密ラベル | ユーザーの生産性と共同作業能力を妨げることなく、組織のデータを分類して保護します。 メール、ファイル、またはサイトにさまざまなレベルの保護を持つラベルを配置します。 | Microsoft 365 E3、E5 |
| データ損失防止 (DLP) | 内部および外部の両方で、個人情報を含むデータのリスク、不注意、または不適切な共有を検出、警告、ブロックします。 | Microsoft 365 E3、E5 |
| データの保持ラベルとポリシー | 情報ガバナンス制御を実装する。 これには、組織のポリシーやデータ規制に準拠するためにデータ (顧客に関連する個人データなど) を保持する期間を決定する場合があります。 | Microsoft 365 E3、E5 |
| メールの暗号化 | 組織内外のユーザー間で暗号化された電子メール メッセージを送受信することで、個人データを保護します。 | Microsoft 365 E3、E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>このソリューションのガイダンスの構成

1 つ以上のプライバシー関連Microsoft 365を満たすのに役立つツールを理解するために、このガイダンスはセクションに整理されています。

![データプライバシー規制に関する情報保護を実装する手順。](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

これらの各セクションは、このソリューションの個別の記事に対応しています。

> [!NOTE]
> データプライバシーの義務について既に理解し、既存のプランに対して実行している場合は、予防、保護、保持、調査のガイダンスに焦点を当てる必要があります。

> [!IMPORTANT]
> このガイダンスに従って、特に機能のコンテキスト外に必要な手順の数を考慮すると、必ずしもデータプライバシー規制に準拠するとは限りません。 お客様は、コンプライアンスを確保し、法務およびコンプライアンス チームに相談するか、コンプライアンスに特化した第三者からのガイダンスとアドバイスを求める責任があります。

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>計画: データプライバシーリスクを評価し、機密性の高いアイテムを特定する

組織が対象となるデータプライバシー規制とリスクを評価する方法は、Microsoft 365 での機能の構成など、改善の実装を開始する前に取る重要な第一歩です。 この作業には、組織が遵守する必要がある規制管理の対象となる特定の機密情報の種類の全体的な準備状況評価または識別が含まれる場合があります。

詳細については、「データプライバシーリスク [を評価し、機密性の高いアイテムを特定する」を参照してください](information-protection-deploy-assess.md)。

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>追跡: リスク評価を実行し、コンプライアンス スコアを確認する

Microsoft 365 コンプライアンス センター で利用できるコンプライアンス マネージャーは、改善アクション全体と、適用される複数のデータ プライバシー規制に関連するアクションを追跡および管理する組み込みの機能を提供します。

各規制に固有の組み込みの評価テンプレートを使用して、選択した評価テンプレートごとにアクション アイテムを追跡し、特定の規制コントロールを表示し、それらを特定のアクションに関連付けできます。

詳細については、「コンプライアンス マネージャーを [使用して改善アクションを管理する」を参照してください](information-protection-deploy-compliance.md)。

## <a name="prevent-protect-personal-data"></a>防止: 個人データを保護する

Microsoft 365、ID、デバイス、および脅威保護機能を提供し、データ プライバシーの規制コンプライアンスの遵守に役立ちます。

詳細については、「データプライバシー規制に ID、デバイス、および脅威保護を使用 [する」を参照してください](information-protection-deploy-identity-device-threat.md)。

この記事では、これらの分野で一般的に必要なデータプライバシー規制について簡単に説明し、実装要件に対処するために役立つ詳細な情報へのリンクを含む、関連する Microsoft 365 ソリューションの一覧を提供します。

## <a name="protect-information-subject-to-data-privacy-regulation"></a>データプライバシー規制の対象となる情報を保護する

データプライバシー規制では、GDPR、カリフォルニア州消費者保護法 (CCPA)、HIPAA-HITECH (米国の医療プライバシー法)、およびブラジルデータ保護法 (LGPD) のサンプル セットの 4 つのデータ プライバシー規制に対する 40 以上の制御を含む、環境で使用できる多数の個人情報保護管理が規定されています。

詳細については、「組織内の [データプライバシー規制の対象となる情報を保護する」を参照してください](information-protection-deploy-protect-information.md)。

この記事では、組織内のデータプライバシーに関する情報保護のニーズに対処するために使用できる主な制御スキームについて説明します。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保持: データプライバシー規制の対象となる情報を管理する

データ プライバシー規制では、GDPR、CCPA、HIPAA-HITECH、および LGPD のサンプル セットの 4 つのデータ プライバシー規制全体で 24 以上のコントロールを含む、お客様の環境で使用できる個人情報ガバナンス管理が必要です。

詳細については、「組織内の [データプライバシー規制の対象となる情報を管理する」を参照してください](information-protection-deploy-govern.md)。

この記事では、目的に合った保持、削除、アーカイブなどの情報ガバナンスに関するデータプライバシー規制はあいまいですが、組織のデータプライバシーに関するアドレス情報ガバナンスのニーズを使用できる主な制御スキームが示されています。 &mdash; &mdash;

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>調査: データ プライバシー インシデントの監視、調査、対応

関連する機能Microsoft 365、組織内のデータ プライバシー インシデントの監視、調査、および対応に役立つ機能が用意されています。

これらの機能を使用するプロセス、手順、その他のドキュメントを持つことは、規制機関へのコンプライアンスを実証するために重要な場合があります。

詳細については、「組織内の [データ プライバシー インシデントの](information-protection-deploy-monitor-respond.md)監視と対応」を参照してください。

## <a name="training-for-administrators"></a>管理者向けトレーニング

Microsoft Learn のトレーニング モジュールは、情報保護に重要な機能について学ぶのに役立ちます。


#### <a name="information-protection"></a>情報保護

|トレーニング:|Microsoft 365 で企業情報を保護する|
|:---|:---|
|![Teamsのトレーニング アイコンをクリックします。](../media/protect-enterprise-information-microsoft-365.svg)|組織の情報を保護することは、かつてないほど困難になっています。 「Microsoft 365 で社内の情報を保護する」のラーニング パスでは、機密情報を不用意な共有や誤用から保護する方法、データを検出して分類する方法、秘密度ラベルを使用して保護する方法、損失から保護するために機密情報を監視および分析する方法について説明します。 この学習パスは、セキュリティ管理者の認定:セキュリティ管理者アソシエMicrosoft 365 Microsoft 365認定: Enterpriseエキスパート認定の準備に役立ちます。<br><br>1 時間 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>ID とアクセス

|トレーニング:|Azure Active Directory で ID とアクセスを保護する|
|:---|:---|
|![ID とアクセスのトレーニング アイコン。](../media/protect-identity-and-access-with-microsoft-365.svg)|ID とアクセスのラーニングパスは、最新の ID およびアクセステクノロジ、認証を強化するためのツール、組織内での ID 保護のガイダンスについて説明しています。 Microsoft ID およびアクセステクノロジを使用すると、組織のIDをオンプレミスでもクラウドでも保護し、ユーザーがどこからでも安全に作業できるようになります。 このラーニングパスはMicrosoft 365 認定: セキュリティ管理者 と Microsoft 365 認定: エンタープライズ管理エキスパート の認定のための準備を行うことが出来ます。<br><br>2 時間 52 分 - ラーニング パス - 6 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/m365-identity-overview/introduction/)