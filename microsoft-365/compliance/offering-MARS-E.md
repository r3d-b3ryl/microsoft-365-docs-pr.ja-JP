---
title: Minimum Acceptable Risk Standards for Exchanges (MARS-E) 2.0 フレームワーク
description: Microsoft は米国の Minimum Acceptable Risk Standards for Exchanges (MARS-E) に準拠しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 2d2c9862fe5af3eedd9ff90ff5bb6d33e1e06f10
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417521"
---
# <a name="minimum-acceptable-risk-standards-for-exchanges-mars-e-20-framework"></a>Minimum Acceptable Risk Standards for Exchanges (MARS-E) 2.0 フレームワーク

## <a name="mars-e-20-framework-overview"></a>MARS-E 2.0 フレームワークの概要

2012 年、Center for Medicare and Medicaid Services (CMS) は、CMS 情報セキュリティおよびプライバシー プログラムに従い、Minimum Acceptable Risk Standards for Exchanges (MARS-E) を発行しました。 これは、ガイダンス、要件、テンプレートを含むドキュメント セットで、Patient Protection and Affordable Care Act (ACA) の命令と、ACA に適用される Department of Health and Human Services の規則に対応できるよう策定されています。 米国標準技術研究所 (NIST) Special Publication 800-53 が、ACA が強制適用される医療保健取引所と市場間のすべてのシステム、インターフェイス、接続を対象とするセキュリティおよびコンプライアンス要件を規定する大元のフレームワークになっています。

MARS-E のリリースに続き、NIST は新しいパブリケーションの Special Publication 800-53r4 をリリースしました。これは、アプリケーション セキュリティ、内部からの脅威や高度で執拗な脅威、サプライ チェーンにおけるリスクのほか、モバイルおよびクラウド コンピューティングのシステムの信頼性、保証、回復性など、増え続けるオンライン セキュリティの課題に対応しています。 その後、CMS は、NIST 800.53r4 の更新されたコントロールとパラメーターに合わせて MARS-E フレームワークを改訂し、2015 年に MARS-E 2.0 を発行しました。

上記の各更新は、健康保険取引所における保護対象データの機密性、整合性、可用性に対応しています。保護対象データには、個人を特定できる情報、保護対象の医療情報、連邦税金情報 (FTI) が含まれます。 MARS-E 2.0 フレームワークは、この保護対象データを保護することを目的としており、ACA が適用されるすべての法人に適用されます。適用対象には、取引所やマーケットプレース (連邦政府関係機関、州政府関係機関、州のメディケイド機関、児童医療保険プログラム (CHIP) 機関) と委託先会社が含まれます。

## <a name="microsoft-and-mars-e-20-framework"></a>Microsoft と MARS-E 2.0 フレームワーク

現時点では、MARS-E には正式な承認や認定のプロセスはありません。 ただし、Microsoft Azure Platform サービスは独立機関による FedRAMP 監査を Moderate Impact Level で、Azure Government は High Impact Level で受けており、FedRAMP 規格に準拠していることが認定されています。 これらは MARS-E のための規格ではありませんが、MARS-E の統制要件と目標は似通っていて、Azure でのデータの機密性、整合性、可用性の確保に利用できます。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure および Azure Government](https://aka.ms/AzureCompliance)
- Intune

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

Microsoft ビジネス クラウド サービスは、FedRAMP 認定プロセスに従い、毎年監視および評価されます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**この標準はだれに適用されますか?**

MARS-E は、Affordable Care Act が適用されるすべての法人に適用されます。適用対象には、取引所やマーケットプレース (Basic Health Program を運営する連邦政府関係機関、州政府関係機関、メディケイド機関、CHIP 機関) と、それらのすべての委託先会社および下請けの委託先会社が含まれます。

**Azure および Azure Government がこの規格に準拠していることは、どのように実証されますか?**

第三者による正式な FedRAMP 認定のための監査レポートを使用することで、Microsoft はこれらのレポートに記載されている関連するコントロールにより、Azure が MARS-E のセキュリティおよびプライバシー コントロール要件に準拠できることを実証できます。 Microsoft が実装している監査対象のコントロールによって、Azure Platform に格納されるデータの機密性、整合性、および可用性を確保できます。これらは、Microsoft の責任として特定されている MARS-E の規制要件に対応します。

**この標準への準拠を維持するうえで Microsoft にはどのような責任がありますか?**

Microsoft は Azure Platform が[オンライン サービス条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)と該当するサービス レベル アグリーメント (SLA) で規定されている条件に適合していることを保証します。 そこでは、Azure Platform の安全を確保してシステムを監視するために適切なコントロールを実装および維持する責任が Microsoft にあることが規定されています。

**Microsoft のコンプライアンスを自分の組織の MARS-E の適合認定プロセスに利用できますか?**

はい。 FedRAMP 規格に対する第三者監査レポートは、Azure Platform のセキュリティとプライバシーを維持するために Microsoft が実装しているコントロールの有効性を証明しています。 Azure および Azure Government のお客様は、FedRAMP や MARS-E のリスク分析や適合認定の一環で、これらの関連レポートに記載されている監査済みの統制を利用できます。

## <a name="resources"></a>リソース

- MARS-E regulatory guidance, MARS-E Document Suite, Version 2.0
    - [第 II 版: Minimum Acceptable Risk Standards for Exchanges](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/2-MARS-E-v2-0-Minimum-Acceptable-Risk-Standards-for-Exchanges-11102015.pdf)
    - [第 III 版: Minimum Acceptable Risk Standards for Exchanges のカタログ](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/3-MARS-E-v2-0-Catalog-of-Security-and-Privacy-Controls-11102015.pdf)
- [オンライン サービス用の Microsoft コンプライアンス フレームワーク ホワイト ペーパー](https://aka.ms/compliance-framework)
- [Microsoft オンライン サービス条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [Microsoft セキュリティ センターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
