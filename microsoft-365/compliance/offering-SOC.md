---
title: Service Organization Controls (SOC)
description: Microsoft クラウド サービスは、運用セキュリティについて Service Organization Controls 基準に準拠しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 2428109743b408061ead8ad87d5e59ac30417c06
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898085"
---
# <a name="service-organization-controls-soc"></a>Service Organization Controls (SOC)

## <a name="soc-1-2-and-3-reports-overview"></a>SOC 1、2、3 報告書の概要

データ ストレージ、アプリケーションへのアクセスなど、基本的な機能をクラウド サービス プロバイダー (CSP) やその他のサービス組織にアウトソースするビジネスが増えています。 これを受けて、米国公認会計士協会 (American Institute of Certified Public Accountants: AICPA) は、クラウドで保存および処理される情報の機密性とプライバシーを保護する制御基準である Service Organization Controls (SOC) フレームワークを策定しました。 これは、国際サービス組織の報告書作成基準である 国際保証業務基準 (International Standard on Assurance Engagements: ISAE) に合致するものです。

SOC フレームワークに基づくサービス監査は、SOC 1 と SOC 2 の 2 つに分類され、対象となる Microsoft クラウド サービスに適用されます。

SOC 1 監査は、財務諸表を監査する公認会計士事務所を対象としており、プロバイダーのクラウド サービスを使用している顧客の財務報告に影響する、CSP の内部コントロールの有効性を評価します。 監査は保証業務基準書 (SSAE 18) および国際保証業務基準書第  3402 号 (ISAE 3402) を基準として実施され、これを基に SOC 1 報告書が作成されます。

SOC 2 監査では、AICPA Trust Service Principles and Criteria に基づいて CSP のシステムの有効性を評価します。 Attestation Standards (AT) Section 101 の Attest Engagement を基に SOC 2 および SOC 3 報告書が作成されます。

SOC 1 または SOC 2 監査の終了時、サービス監査人は SOC 1 Type 2 または SOC 2 Type 2 報告書で意見を述べます。報告書では、CSP のシステムについて説明し、CSP による自身の制御の説明の正当性を評価します。 また、CSP の制御が適切に設計されているかどうか、指定した日付に実行されていたか、また、指定した期間に正常に運用されていたかも評価します。

監査人は SOC 3 報告書 (SOC 2 Type 2 監査報告書が簡略化されたもの) を作成することもできます。これは、CSP の制御についての保証は必要なものの、完全な SOC 2 報告書を必要としないユーザーを対象としています。 SOC 3 報告書を提供できるのは、CSP が SOC 2 で無限定適正意見を得ている場合に限られます。

## <a name="microsoft-and-soc-1-2-and-3-reports"></a>Microsoft と SOC 1、2、3 報告書

Microsoft の対象クラウド サービスは、少なくとも年に 1 回、独立第三者監査機関による監査が SOC 報告フレームワークに照らして実施されています。 Microsoft クラウド サービスの監査は、サービスごとに適用される信頼の原則に従って、データ セキュリティ、可用性、処理の整合性、および機密性の制御が対象となります。

Microsoft では、SOC 1 Type 2、SOC 2 Type 2、および SOC 3 報告書を取得しています。 原則として、SOC 1 報告書と SOC 2 報告書は、Microsoft と秘密保持契約を結んでいるお客様しか入手できませんが、SOC 3 報告書は公開されています。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

### <a name="covered-services-for-soc-1-and-soc-2"></a>SOC 1 および SOC 2 の対象サービス

- [Azure、Azure Government、Azure Germany](https://aka.ms/AzureCompliance)
- Microsoft Cloud App Security
- [Dynamics 365、Dynamics 365 U.S. Government](https://aka.ms/d365-compliance-list)
- Microsoft Graph
- Intune
- Microsoft マネージド デスクトップ
- Power Automate (旧称 Microsoft Flow) スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービスとしてのクラウド サービス
- [Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)
- Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに組み込まれているサービス)
- Microsoft Stream
- Azure DevOps Services

### <a name="covered-services-for-soc-3"></a>SOC 3 の対象サービス

- [Azure、Azure Government、Azure Germany](https://aka.ms/AzureCompliance)
- Microsoft Cloud App Security
- Microsoft Graph
- Intune
- Microsoft マネージド デスクトップ
- Power Automate (旧称 Microsoft Flow) スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービスとしてのクラウド サービス
- Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)
- [Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Power BI
- Microsoft Stream

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

### <a name="audit-cycle"></a>監査サイクル

Microsoft クラウド サービスでは、少なくとも年に 1 回、SOC 1 (SSAE18、ISAE 3402)、SOC 2 (AT Section 101)、SOC 3 基準に照らした監査が実施されます。

#### <a name="azure-dynamics-365-microsoft-cloud-app-security-flow-microsoft-graph-intune-power-bi-powerapps-microsoft-stream-and-microsoft-datacenters"></a>Azure、Dynamics 365、Microsoft Cloud App Security、Flow、Microsoft Graph、Intune、Power BI、Power Apps、Microsoft Stream、Microsoft データセンター

- [Azure + Dynamics 365 と Azure + Dynamics 365 Government SOC 1 タイプ 2 レポート](https://aka.ms/azuresoc1auditreport)
- [Azure + Dynamics 365 と Azure + Dynamics 365 Government SOC 2 タイプ 2 レポート](https://aka.ms/azuresoc2auditreport)
- [Azure + Dynamics 365 と Azure + Dynamics 365 Government SOC 3 レポート](https://aka.ms/azuresoc3auditreport)

#### <a name="office-365"></a>Office 365

- [Office 365 Core - SSAE 18 SOC 1 報告書](https://aka.ms/o365SOC-1)
- [Office 365 Core - SSAE 18 SOC 2 報告書](https://aka.ms/o365SOC-2)
- [Office 365 Core - SSAE 18 SOC 3 報告書](https://aka.ms/o365SOC-3)
- [Office 365 Microservices T1 – SSAE 18 SOC2 Type I 報告書](https://aka.ms/o365-MS-SOC-2-type1)
- [顧客ロックボックス SOC 1 SSAE 16 監査報告書](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [Yammer SOC 2 AT 101 Type I 監査報告書](https://aka.ms/YammerSOC2Type1AuditReport)
- [Yammer SOC 2 Type II 報告書](https://aka.ms/yammerSOC-2)
- [ブリッジ レターおよびその他の監査報告書を参照する](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**SOC 報告書のコピーはどのようにして入手できますか?**

監査人は、報告書を使って、Microsoft ビジネス クラウド サービスの結果と顧客の法的規制要件を比較できます。

- [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx)を使用して、すべての SOC 報告書を閲覧できます。
- Azure DevOps のサービスをご利用のお客様で、[Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) にアクセスできないお客様は、お客様の SOC 1 および SOC 2 報告書については [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) にメールでご連絡ください。 このメールは、Azure DevOps SOC 報告書の要求のみにご使用ください。

**Azure SOC 報告書が発行される頻度はどれくらいですか?**

Azure、Microsoft Cloud App Security、Flow、Microsoft Graph、Intune、Power BI、PowerApps、Microsoft Stream、Microsoft データセンターの SOC 報告書は、12 か月連続の実行期間 (監査期間) に基づいており、半年ごとに新たな報告書が発行されます (期間は 3 月 31 日と 9 月 30 日に終了)。 ブリッジ レターは四半期ごとに発行され、過去 3 か月間をカバーします。 たとえば、1 月のレターは 10 月 1 日から 12 月 31 日を、4 月のレターは 1 月 1 日から 3 月 31 日を、7 月のレターは 4 月 1 日から 6 月 30 日を、10 月のレターは 7 月 1 日から 9 月 30 日をカバーします。 最新の報告書は Service Trust Portal から[ダウンロード](https://aka.ms/stp)できます。

**Microsoft データセンターの監査は、自分自身で実施する必要がありますか?**

いいえ。 Microsoft では、Microsoft のセキュリティ コミットメントに Microsoft が準拠していることを確認していただけるように、第三者監査報告書と認定をお客様にも公開しています。

**Microsoft のコンプライアンスを自分の組織の認定プロセスに利用できますか?**

はい、できます。 対象となる Microsoft クラウド サービスにアプリケーションやデータを移行する場合、Microsoft が保持する監査と認定を利用できます。 お客様のデータのセキュリティとプライバシーを維持するために Microsoft が実装してきた制御の有効性が第三者報告書により証明されます。

**組織でのコンプライアンス活動は、何から始めればよいですか?**

[SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) は、SOC 報告書のプロセスを理解し、組織で報告書の利用を促進する上で役立つリソースです。

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>Microsoft コンプライアンス スコアを使用してリスクを評価する

[Microsoft コンプライアンス スコア](compliance-score.md)は、[Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)のプレビュー機能で、組織のコンプライアンスの状況を把握し、リスクを軽減するための処置を実行できるようにします。 [コンプライアンス スコアの設定](compliance-score-setup.md)後、[**テンプレート**] ドロップダウン メニューから事前に構成された [SOC 1 テンプレート](https://go.microsoft.com/fwlink/?linkid=2117918)と [SOC 2 テンプレート](https://go.microsoft.com/fwlink/?linkid=2117919)を選択してこの規制の要件を満たすようにします。

## <a name="resources"></a>リソース

- [Microsoft クラウド サービスによるデータの保護の強化](https://www.microsoft.com/trustcenter/guidance/protect-data)
- [Service Organization Control (SOC) 報告書](https://aka.ms/mssocreports)
- [SSAE 16 の概要](http://ssae16.com/SSAE16_overview.html)
- [ISAE 3402 の概要](http://isae3402.com/ISAE3402_overview.html)
- [Microsoft オンライン サービス条件](https://aka.ms/Online-Services-Terms)
- [Microsoft Government クラウド](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
