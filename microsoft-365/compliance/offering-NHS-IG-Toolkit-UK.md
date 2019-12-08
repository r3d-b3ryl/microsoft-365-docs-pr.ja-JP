---
title: 国民保健サービス (NHS) 情報ガバナンス (IG) ツールキット
description: Azure は Health Information Trust Alliance Common Security Framework の認証を取得しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 69cc897f749a591da9bdc69057bccf2dc96351da
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859537"
---
# <a name="national-health-service-nhs-information-governance-ig-toolkit"></a>国民保健サービス (NHS) 情報ガバナンス (IG) ツールキット

## <a name="nhs-ig-toolkit-overview"></a>NHS IG ツールキットの概要

国民保健サービス (NHS) は英国の国営医療システムで、すべての医療分野に対応し、英国国民の医療の大半を提供しています。 1948 年に創設された NHS は、世界初の単独の医療システムでした。 また、従業員数 150 万人以上、2016 年度の予算は 1,164 億ポンドという、世界最大の医療システムでもあります。

NHS は 6,400 万人を超える NHS の患者の医療データを管理しています。 NHS の患者データの収集、格納、処理には、1998 年のデータ保護法や守秘義務 NHS 行動規範など、複数の法令が適用されます。

NHS は、患者データの収集、管理、処理を統制するための単一の規格の開発と維持管理を健康社会福祉情報センター (HSCIC) に委託しました。この規格が、[情報ガバナンス (IG) ツールキット](https://www.igt.hscic.gov.uk/resources/About%20the%20IG%20Toolkit.pdf)です。 IG ツールキットは、ガイドラインに準拠するプロセスを経て、個人の医療データをホストすることに関心がある組織を支援し、ガイドすることを目的としています。

NHS 患者データにアクセスできる組織は例外なく、NHS IG ツールキットを使用して、患者データを保護する適切な対策を講じていることを証明する必要があります。

また、Microsoft など、医療プロバイダーのプラットフォームを提供する組織は、NHS IG ツールキットを使用して、NHS の情報ガバナンス、セキュリティ、およびプライバシー要件を基準に、セキュリティとプライバシー コントロールの自己評価を実施します。

NHS IG ツールキットに準拠することで、患者データの整合性と機密性を確保し、不正アクセスやデータ損失、破損、破壊から保護します。 評価プロセス中に非準拠の問題が見つかった場合は、適切な対処を行い、問題を修正する必要があります。

NHS IG ツールキットの目的は次のとおりです。

- NHS 患者データのセキュリティと機密性、およびビジネスに及ぶ影響についてのお客様の一般的な懸念事項に対処する規格を提供する
- 測定できる形で準拠状態を示し、患者データに対する潜在的なリスクを可視化する
- NHS とパートナー組織に対する信用と国民からの信頼を向上する

## <a name="microsoft-and-nhs-ig-toolkit"></a>Microsoft と NHS IG ツールキット

民間のサード パーティである Microsoft Azure は、[NHS IG ツールキットの評価](https://www.igt.hscic.gov.uk/AssessmentReportCriteria.aspx?tk=427399452776248&lnv=3&cb=48ea00e0-c594-4758-8634-f22b6efa0c39&sViewOrgId=50721&sDesc=8JH14)のレベル 2 を完了しています。 また、NHS IG ツールキットの新版がリリースされる場合は、その年のうちに中間評価が完了する予定です。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure および Azure Government](https://aka.ms/AzureCompliance)
- Intune
- Power BI: クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに組み込まれているサービス)

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

Azure 評価は毎年更新されます: [Microsoft Azure IG ツールキット評価レポート](https://www.igt.hscic.gov.uk/AssessmentReportCriteria.aspx?tk=427399452776248&lnv=3&cb=48ea00e0-c594-4758-8634-f22b6efa0c39&sViewOrgId=50721&sDesc=8JH14)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Azure NHS IG ツールキットの評価を利用できるのは誰ですか?**

NHS 患者データをホストするプラットフォームに Microsoft Azure の使用を考える組織は、Microsoft の評価レポートを基に、独自の NHS IG ツールキット評価を実施できます。その場合は、クラウド サービス プロバイダーの責任に含まれないコントロールを中心に、追加のコントロールにも対応する必要があることに留意してください。

**組織でのコンプライアンス活動は、何から始めればよいですか?**

NHS 患者データのホストに関心がある組織は、[NHS IG ツールキット ガイドラインを確認](https://www.igt.hscic.gov.uk/requirementsorganisation.aspx)して適用される要件を把握し、実装が必要な範囲と統制を決定することをお勧めします。

**IG ツールキットの達成レベルはどのような内容ですか?**

IG ツールキットの達成レベルは 0 - 3 あります。

- レベル 1 を達成できるという十分な証拠がない
- 組織は、準拠に必要なポリシー、手順、プロセスの計画に着手している
- IG のポリシーと手順が承認および実装されていて、関係するスタッフ全員に伝達されている
- スタッフのコンプライアンスとポリシーおよび手順の有効性が、監視され保証されている

## <a name="resources"></a>リソース

- [情報ガバナンスのツールキット](https://www.igt.hscic.gov.uk/)
- [Microsoft Azure IG ツールキット評価レポート](https://www.igt.hscic.gov.uk/AssessmentReportCriteria.aspx?tk=427399452776248&lnv=3&cb=48ea00e0-c594-4758-8634-f22b6efa0c39&sViewOrgId=50721&sDesc=8JH14)
- [IG ツールキットの要件](https://www.igt.hscic.gov.uk/requirementsorganisation.aspx?tk=427399392327814&cb=5815499d-070a-49e2-ac2e-c70d74d81ddc&lnv=2&clnav=YES)
- [IG ツールキット FAQ](https://www.igt.hscic.gov.uk/resources/About%20the%20IG%20Toolkit.pdf)
- [Microsoft トラスト センターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景資料をダウンロードする

このサービスに関する背景資料が必要ですか? [PDF](https://download.microsoft.com/download/7/F/6/7F6EBDDE-F3EF-4225-ACDA-ADCD851430C4/NHS_IG-Compliance.pdf) をダウンロードします。
