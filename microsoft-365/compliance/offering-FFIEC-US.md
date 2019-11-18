---
title: 連邦金融機関調査委員会 (FFIEC)
description: Microsoft は、金融サービスクライアントが連邦金融機関調査委員会 (FFIEC) の監査要件に準拠しています。
keywords: Microsoft 365、コンプライアンス、オファーリング
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 61028937f469c21d50688912d9acccde7d1c117c
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690675"
---
# <a name="compliance-offering-federal-financial-institutions-examination-council-ffiec"></a>コンプライアンスオファリング: 連邦金融機関調査委員会 (FFIEC)

## <a name="ffiec-overview"></a>FFIEC の概要

連邦金融機関の調査協議会 (FFIEC) は、米国の金融機関の連邦政府機関による試験を担当する5つの銀行監督を構成する正式な interagency 本文です。 FFIEC の試験現場では、FFIEC メンバーエージェンシーからのフィールド examiners を対象とした調査ハンドブックを公開しています。

[FFIEC AUDIT it の調査ハンドブック](https://ithandbook.ffiec.gov/it-booklets/audit.aspx)には、これらの examiners のためのガイダンスが含まれており、金融機関と TSPS の IT 監査プログラムの品質と有効性を評価します。 具体的には、独立した監査レポートの例として、米国公認会計士 (AICPA) の SOC 1、SOC 2、および SOC 3 の証明書レポートを記載しています。 ただし、FFIEC では、これらのレポートに含まれる情報のみに依存するのではなく、 [FFIEC アウトソーシングテクノロジサービスの IT 調査ハンドブック](https://ithandbook.ffiec.gov/it-booklets/outsourcing-technology-services.aspx)で詳しく説明されている検証と監視の手順も使用することをお勧めします。

## <a name="microsoft-and-ffiec"></a>Microsoft および FFIEC

Microsoft Azure、Microsoft Power BI、Microsoft Office 365 は、金融サービス機関にクラウドサービスを提供するための厳しい要件を満たすように構築されています。 サポートの一環として、microsoft は、FFIEC の情報技術の監査要件を満たすためのガイダンスを提供します。また、FFIEC のコンプライアンス義務を採用する際に Azure SOC attestations を使用することもできます。

金融サービスの展開を促進する: [Azure Security And コンプライアンス FFIEC 金融サービスブループリントをダウンロードする](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint)

金融機関クライアントが Azure との FFIEC のコンプライアンス要件を満たすために、Microsoft では以下を開発しています。

- [クラウドセキュリティ診断ツール * *](https://aka.ms/FFIEC-CSDT)を使用して、Azure サービスのリスク評価を効率的に実施できるようにします。 このツール (Excel スプレッドシート) には、金融サービス規制やその他の関連基準の要件を追跡する19の情報セキュリティドメイン (ネットワークおよびシステムのセキュリティ、情報およびリスク管理など) があり、FFIEC IT試験ハンドブック このツールは、技術サービスプロバイダ (TSPs) に適用される各要件を Azure が準拠する方法について説明します。
- [FFIEC 規制サービスのワークロードのための Azure セキュリティおよびコンプライアンスブループリント](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint)。診断ツールの付属。 このガイドでは、Azure クラウドサービスの使用方法と、FFIEC の要件およびリスク評価ガイドラインに関するお客様のコンプライアンスに関する考慮事項について説明します。

FFIEC の要件に準拠するために、Microsoft クラウドサービスは、独立した CPA 企業によって作成された[SOC 構成証明書](offering-SOC.md)を提供します。 たとえば、認証された SOC の種類2は、AICPA SSAE 18 標準に基づいています (105 セクションを参照)。これは、SAS 70 を交換したものであり、財務報告に関する特定のコントロールのレポートに適しています。 SOC レポートには、指定された監視期間中に関連する制御目標を達成するために、監査者が Microsoft 統制の有効性についての意見が記載されています。 金融機関は、Azure、Power BI、および Office 365 に展開された資産に対して FFIEC 固有のコンプライアンス義務を遵守するときに、この公式監査を使用できます。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft スコープ内クラウドサービス

- [Azure](https://aka.ms/AzureCompliance)
- Intune
- [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Power BI cloud service をスタンドアロンサービスとして、または Office 365 ブランドプランまたはスイートに含める

## <a name="audits-reports-and-certificates"></a>監査、レポート、および証明書

Azure および Office 365 の SOC 構成証明レポート。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**マイクロソフトの SOC 標準を使用して、組織の機関の FFIEC 準拠の義務を満たすことはできますか?**

これらの義務を満たすために、Microsoft は、前述した SOC 標準への準拠についての詳細を提供しています。 しかし最終的には、お客様は自分のサービスが、お客様の機関に適用される特定の法律および規制に準拠しているかどうかを判断する必要があります。 また、FFIEC は、「監査レポートまたはレビューのユーザーは、レポートに含まれる情報のみに依存して TSP の内部統制環境を検証することはない」ということにもアドバイスしています。 「FFIEC IT の調査ハンドブック」の「[アウトソーシングテクノロジ](https://ithandbook.ffiec.gov/it-booklets/outsourcing-technology-services.aspx)」に記載されているように、追加の確認および監視手順を使用する必要があります。

## <a name="resources"></a>リソース

- [連邦金融機関調査委員会 (FFIEC)](https://www.ffiec.gov/)
- [当社のクラウドコンピューティングおよび規制原則のコンプライアンスマップ](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- [FFIEC 監査 IT 調査ハンドブック](https://ithandbook.ffiec.gov/it-booklets/audit.aspx)
- [FFIEC アウトソーシングテクノロジサービス IT 試験ハンドブック](https://ithandbook.ffiec.gov/it-booklets/outsourcing-technology-services.aspx)
- [Azure 金融サービス Cloud リスク評価ツール](https://aka.ms/FFIEC-CSDT)
- [Azure のセキュリティとコンプライアンス FFIEC 金融サービスブループリント](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint)

## <a name="other-microsoft-resources-for-financial-services"></a>金融サービスに関するその他の技術情報

- [Microsoft 金融サービスコンプライアンスプログラム](https://www.microsoft.com/download/details.aspx?id=55332)
- [Azure での金融サービスコンプライアンス](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Microsoft business cloud services および金融サービス](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [クラウドコンピューティングの共有責任](https://aka.ms/sharedresponsibility)
- [Microsoft セキュリティセンターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>オファーリング backgrounder をダウンロードする

このオファーリングの backgrounder ドキュメントは必要ですか? [PDF](https://download.microsoft.com/download/6/2/7/62760960-C4B5-456B-9CF8-DCB7D692AAC4/FFIEC-Compliance.pdf)をダウンロードします。
