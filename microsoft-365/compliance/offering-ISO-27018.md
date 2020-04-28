---
title: クラウドで個人データを保護するための ISO/IEC 27018 実施基準
description: Microsoft は、クラウド プライバシーに関するこの実施基準を順守した初のクラウド プロバイダーです。
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
ms.openlocfilehash: 4376d2ca5ac27ec8e12f266bb7d3bb54289c1dbd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637527"
---
# <a name="isoiec-27018-code-of-practice-for-protecting-personal-data-in-the-cloud"></a>クラウドで個人データを保護するための ISO/IEC 27018 実施基準

## <a name="isoiec-27018-overview"></a>ISO/IEC 27018 の概要

国際標準化機構 (ISO) は中立的な非政府組織で、国際基準を自主的に策定する世界最大の組織です。 ISO/IEC 27000 基準ファミリは、すべての形態および規模の組織が情報資産のセキュリティを確保できるよう支援します。

2014 年、ISO は、ISO/IEC 27001 の補遺として、クラウド プライバシーに関する初めての国際実施基準である ISO/IEC 27018:2014 を採用しました。 EU データ保護法に基づいて、個人を特定できる情報 (PII) の処理者の役割を担うクラウド サービス プロバイダー (CSP) に、PII 保護のためのリスク評価と最新制御の実装に関する特定のガイダンスを提供します。

Microsoft と ISO/IEC 27018

Microsoft Azure と Azure Germany は、年に 1 回以上、ISO/IEC 27001 および ISO/IEC 27018 への準拠に関して、第三者の公認認定機関の監査を受けています。この機関は、該当するセキュリティ コントロールが導入されていて、効果的に運用されていることを独自に検証します。 このコンプライアンスの検証プロセスの一環として、監査人は、適用宣言書で、対象となる Microsoft クラウド サービスおよび法人向けテクニカル サポート サービスに、Azure で PII を保護するための ISO/IEC 27018 制御が組み込まれていることを確認します。 コンプライアンスを確保し続けるために、Microsoft クラウド サービスは年 1 回第三者による審査を受ける必要があります。

ISO/IEC 27001 基準と ISO/IEC 27018 の実施基準への準拠が、この実施基準を採用した初めての主要クラウド プロバイダーである、Microsoft のプライバシー ポリシーと手順が堅牢で、高い水準が維持されていることの証明になります。

- **Microsoft クラウド サービスの顧客がデータの保存場所を把握している。** ISO/IEC 27018 では、認定 CSP が、データの保存先の国を顧客に知らせる必要があります。したがって、Microsoft クラウド サービスの顧客には、適用される情報セキュリティ ルールに従うために必要な可視性が提供されています。
- **お客様のデータは、明確な同意がない限りマーケティングや広告に使用されない。** CSP によっては、顧客データを自身の商業目的でターゲットを絞った広告などに使用することがあります。 Microsoft では対象となるエンタープライズ クラウド サービスに ISO/IEC 27018 を採用しているため、明確な同意がない限り、お客様のデータがこのような目的で使用されることありません。その点に関しては、お客様は安心して利用できます。また、このような同意が、クラウド サービスの使用条件になることもありません。
- **Microsoft の顧客は PII の状況を把握できる。** ISO/IEC 27018 には、適正な期間内に個人情報の返却、移行、および安全な破棄を可能にするポリシーが必要です。 顧客データにアクセスする必要がある他の企業と連携する場合、Microsoft ではこうした二次処理者の身元を積極的に開示します。
- **顧客データの開示に対する要求には法的拘束力がある場合にのみ応じる。** 犯罪捜査の場合のように、Microsoft がこうした要求に応じる必要がある場合は、法律で禁止されていない限り必ずお客様に通知します。

Microsoft Cloud における ISO-Iec-27018 のメリットを確認してください: [ISO/IEC 27017 背景解説をダウンロードする](https://aka.ms/iso27017-backgrounder)

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure、Azure Government、Azure Germany](https://aka.ms/AzureCompliance)
- Cloud App Security
- Microsoft Professional Services: Azure、Dynamics 365、Intune と、Microsoft 365 for business の Medium Business および Enterprise のお客様への Premier およびオンプレミス サポート
- [Dynamics 365、Dynamics 365 U.S. Government](https://aka.ms/d365-compliance-list)
- Genomics
- Graph
- Health Bot
- Intune
- Microsoft マネージド デスクトップ
- Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランまたはスイートに搭載されているサービス)
- [Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- Office 365 Germany
- OMS Service Map
- Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)
- Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)
- Stream
- Azure DevOps Services
- Windows Defender ATP - エンドポイントでの検出と対応、自動の調査と修復、セキュリティ スコア

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

### <a name="audit-cycle"></a>監査サイクル

Microsoft クラウド サービスおよび法人向けテクニカル サポート サービスは、年 1 回、ISO/IEC 27001 の認定プロセスの一環として、ISO/IEC 27018 実施基準に関する監査を受けています。

### <a name="audits-and-reports"></a>監査とレポート

- [Azure、Intune、Microsoft マネージド デスクトップ、Power BI、Cloud App Security、Microsoft PowerApps、Microsoft Flow、Microsoft Graph、Microsoft Genomics、Microsoft Datacenters - ISO 27001 および 27018 証明書](https://go.microsoft.com/fwlink/p/?linkid=2078016)
- [Azure、Intune、Microsoft マネージド デスクトップ、Power BI、Cloud App Security、Microsoft PowerApps、Microsoft Flow、Microsoft Graph、Microsoft Genomics、Microsoft Datacenters - ISO 27001 および 27018 監査評価レポート](https://go.microsoft.com/fwlink/p/?linkid=2078020)
- [Azure、Intune、Microsoft マネージド デスクトップ、Power BI、Cloud App Security、Microsoft PowerApps、Microsoft Flow、Microsoft Graph、Microsoft Genomics、Microsoft Datacenters - ISO 27001 および 27018 の適用宣言書 (SOA) 2017](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=47d89200-b24b-491d-b657-7c523ddfb6f9&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports)
- [Azure - Germany ISO 27018 - クラウドで個人データを保護するための実施基準 - 証明書](https://servicetrust.microsoft.com/Documents/ComplianceReports?downloadDocument=1&documentId=6a0dab80-8382-4af6-980c-ed2ed9a341c6)

### <a name="office-365"></a>Office 365

- [Office 365 - ISO 27001、ISO 27018、ISO 27017 監査評価レポート](https://aka.ms/o365isoreport)
- [Yammer ISO 27018 監査評価レポート](https://aka.ms/YammerISO27018Auditreport)

### <a name="dynamics-365"></a>Dynamics 365

- [Dynamics 365 の ISO 27018 監査評価レポート](https://aka.ms/dynamics365iso27018auditreport)
- [Dynamics 365 for Marketing の ISO 27018 監査評価レポート](https://aka.ms/dynamics365Marketingiso27018auditreport)
- [Dynamics 365 Parature の ISO 27018 監査評価レポート](https://aka.ms/dynamics365Paratureiso27018auditreport)

### <a name="azure-devops-services"></a>Azure DevOps Services

- [Azure DevOps Services ISO 27018 証明書 PII 665918](https://go.microsoft.com/fwlink/p/?linkid=2062252)

### <a name="windows-defender-atp"></a>Windows Defender ATP

- [Windows Defender ATP - エンドポイントでの検出と対応、自動の調査と修復、セキュリティ スコア - ISO 27018 証明書](https://aka.ms/windowsdefenderatpiso27018certificate)
- [Windows Defender ATP - エンドポイントでの検出と対応、自動の調査と修復、セキュリティ スコア - ISO 27001 および 27018 監査評価レポート](https://aka.ms/WindowsDefenderATPISO27001AuditReport)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**ISO/IEC 27018 はだれに適用されますか?**

この実施基準は、他の組織のために PII 処理契約を結んでいる CSP に適用されます。 また、Microsoft では、これは CSP のサポートにも適用されます。

**「個人情報管理者」と「個人情報処理者」はどう違うのですか?**

ISO/IEC 27018 のコンテキストでは、次のような違いがあります。

- 「管理者」は、個人情報の収集、保持、処理、または使用を管理します。他の企業に代わって個人情報を管理する管理担当者も含まれます。
- 「処理者」は、管理者に代わって情報を処理します。情報の使用方法または処理の目的に関する決定を下すことはありません。 ユーザーのベンダーである Microsoft は、エンタープライズ クラウド サービスを提供する際に、情報処理者の役割を果たします。

**Microsoft の ISO/IEC 27018 コンプライアンス情報はどこで確認できますか?**

- [Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016)、[Microsoft Professional Services](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270)、[Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016)の BSI から ISO/IEC 27018 証明書を確認できます。
- また、ISO/IEC 27018 証明書が [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert)、[Office 365](https://aka.ms/Office365-Cert)、[Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159) に基づいている BSI の ISO/IEC 27001 を確認することもできます。
- Microsoft が ISO/IEC 27018 に準拠していることを検証した独立した監査人である BSI のレポートを確認するには、[Service Trust Portal](https://aka.ms/stphelp) にアクセスしてください。

**Microsoft のコンプライアンスを自分の組織の認定プロセスに利用できますか?**

はい。 ISO/IEC 27018 への準拠が、お客様のビジネスおよび Microsoft の対象企業向けクラウド サービスへの展開において重要である場合、Microsoft の ISO/IEC 27018 への準拠証明書と Microsoft の ISO/IEC 27001 への準拠認証をコンプライアンス評価に使用できます。

ただし、コンプライアンスや、組織内の統制およびプロセスに関して、実装を評価する査定人の手配の責任は、審査を受ける組織が負うものとします。

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>Microsoft コンプライアンス スコアを使用してリスクを評価する

[Microsoft コンプライアンス スコア](compliance-score.md)は、[Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)のプレビュー機能で、組織のコンプライアンスの状況を把握し、リスクを軽減するための処置を実行できるようにします。 [コンプライアンス スコアの設定](compliance-score-setup.md)後、[**テンプレート**] ドロップダウン メニューから事前に構成された [ISO 27018 テンプレート](https://go.microsoft.com/fwlink/?linkid=2117523)を選択してこの規制の要件を満たすようにします。

## <a name="resources"></a>リソース

- [ISO/IEC 27018:2014 実施基準](https://aka.ms/ISO.IEC_27018.2014)
- [Microsoft Common Controls Hub コンプライアンス フレームワーク](https://www.microsoft.com/trustcenter/common-controls-hub)
- [Microsoft エンタープライズ クラウドおよびテクニカル サービスのデータ アクセス ポリシー](https://www.microsoft.com/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms)
- [Microsoft オンライン サービス条件](https://aka.ms/Online-Services-Terms)
- [Microsoft Government クラウド](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景解説をダウンロードする

このサービスに関する背景解説をご覧になりたい場合は、 [PDF](https://download.microsoft.com/download/F/D/A/FDA4697E-D72D-4513-8626-A5F294DC7A0F/ISOIEC_27018_Compliance_Backgrounder.pdf) ファイルをダウンロードできます。
