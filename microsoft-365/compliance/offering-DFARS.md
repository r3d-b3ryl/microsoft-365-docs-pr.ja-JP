---
title: 連邦政府機関買収規制補足 (DFARS dfars)
description: Microsoft Azure Government は、連邦取得の防御法 (DFARS dfars) の要件をサポートしています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
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
ms.openlocfilehash: edc520db1f16bb782ae10faa0e823c921de67ca2
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208579"
---
# <a name="defense-federal-acquisition-regulation-supplement-dfars"></a>連邦政府機関買収規制補足 (DFARS dfars)

## <a name="dfars-overview"></a>DFARS 概要

2016年10月21日に、米国国防総省 (DoD) によって最終的なルールが発行され、情報システムが対象の防御技術情報 (CDI) を処理、保存、または送信する防衛業者に対して、保護された修正とサイバーインシデントの報告に関する義務があります。  
  
「252.204-7012 (対象となる防衛情報およびサイバーインシデントレポートを保護する)」では、サイバーインシデントレポートの要件と、クラウドサービスプロバイダーの追加の考慮事項を含めるための保護を指定します。 DFARS 252.204-7012 では、すべての DoD 請負業者および国防工業基盤は、適切な2017セキュリティのための DFARS 要件に準拠する必要があります。

## <a name="microsoft-and-dfars"></a>Microsoft および DFARS お持ち

Microsoft Government Cloud services では、米国国防総省の基本および防衛請負業者のお客様が、252.204-7012 の DFARS に列挙されている、クラウドサービスプロバイダーに適用される DFARS 要件を満たすことができます。 契約請負業者が7012の DFARS 252.204-に準拠する必要がある場合、Microsoft は、Azure Government および Office 365 の米国政府機関向けの米国政府防衛技術サービスのためのクラウドサービスプロバイダーに適用される要件をサポートすることができます。 両方のサービスは、お客様が、「国防総省のセキュリティ要件ガイド」に対する L5 認定によって DFARS 7012 の条項に準拠するために必要な機能のサポートを示しています。  
  
Azure セキュリティおよびコンプライアンスブループリントを使用して、DFARS 迅速に展開する方法について説明します。「 [azure をダウンロードする」: 「青写真のお客様の責任マトリックス](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=7ed1b47c-b180-4323-9aec-21712d54b167&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_DoD_Blueprint)

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

DoD 影響レベル5の対象となるサービス

- [Azure および Azure Government](https://aka.ms/AzureCompliance)
- [Office 365 米国政府機関および Office 365 米国政府機関の防御](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

- [Microsoft クラウドサービスの承認](https://marketplace.fedramp.gov/index.html#/products?status=Compliant&sort=productName)
- [Azure P-ATO レター (2017 年3月3日)](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=94ff5b42-4077-4612-8cf7-3194ded323dc&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)
- [その他の監査レポートを見る](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Microsoft Azure Government および Office 365 の米国政府機関によってサポートされている DFARS 要件は何ですか。**

Azure 自治体および Office 365 の米国政府による防衛を利用することにより、技術部門の 252.204-7012 の DFARS 列挙された、クラウドサービスプロバイダーに適用されるの dfars 要件を満たすことができます。

**独立した査定官があります。これは、Azure 自治体および Office 365 の米国政府機関が DFARS 要件をサポートしているかどうかを検証しました**

はい。サードパーティの評価組織には、attested (未分類の管理技術情報を保護しています) という、Azure 自治体および Office 365 の米国政府防衛機関のクラウドサービスが、7012の要件を満たしていることが挙げられています。

**統制されていない未分類情報 (CUI) と対象となる防衛情報 (CDI) の関係は何ですか?**

CUI は、法律、規制、または政府全体のポリシーに従って、保護または disseminating の制御を必要とする情報です。 [Cui レジストリ](https://www.archives.gov/cui/registry/category-list.html)は、承認された cui カテゴリとサブカテゴリを識別します。

CDI は、制御された技術情報またはその他の情報 (CUI レジストリで説明) で、コントロールの保護または伝達を必要とするものであり、次のいずれかです。

- 契約または契約の業績に関連して、契約書、タスクオーダー、または納入注文でマークされているか、または DoD の代理として提供されています。
- 契約書のパフォーマンスをサポートするために、請負業者による収集、開発、受信、送信、使用、または契約者の代理としての保存

**すべての Microsoft サービスが、DFARS 規制下の「対象の防衛情報」に該当する「適切なセキュリティ」要件を満たしているか。**

2016年10月に、国防総省 (DoD) は、情報システムを使用して、"対象となる防衛情報" を処理、保存、または送信するすべての DoD 請負業者に適用される、連邦防御 (promulgated) 句を実装する最終規則を示しています。 このようなシステムは、NIST SP 800-171 で規定されているセキュリティ要件を満たしている必要があります。 [連邦情報システムや組織内の規制](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-171.pdf)されていない未分類情報を保護します。または、DoD 契約責任者が承認した「代替の効果的なセキュリティ対策」を適用する必要があります。 また、DoD 請負業者は、対象となる防御情報を処理、保存、または送信するために外部クラウドサービスプロバイダーを使用する必要があります。このプロバイダーは、FedRAMP の適度なベースラインと同等のセキュリティ要件を満たしている必要があります。

次の Microsoft クラウドサービスは、FedRAMP の中程度の承認を受け取り、DFARS 場合は、Azure Government、Dynamics 365 米国政府、Office 365 米国政府機関、および Office 365 米国政府機関との間で十分です。

また、「対象となる防衛情報」を処理、保存、または送信するために DoD 請負業者によって使用される可能性がある、FedRAMP で認証された境界の外側にあるマイクロソフトのサービスは、2017年12月31日のコンプライアンスの期限に達したことをレビューしています。 Microsoft では、このような内部サービスと顧客向けサービスが、DFARS に準拠しているか、または適切なセキュリティに準拠しているかを文書化して、dfars 関連する句を満たすように取り組んでいます。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Microsoft コンプライアンスマネージャーを使用してリスクを評価する

[Microsoft コンプライアンスマネージャー](compliance-manager.md) は、 [microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md) の機能であり、組織のコンプライアンスの状況を理解し、リスクを軽減するためのアクションを実行するのに役立ちます。 コンプライアンスマネージャーには、この規制の評価を構築するためのプレミアムテンプレートが用意されています。 [コンプライアンスマネージャー] の [ **評価テンプレート** ] ページでテンプレートを検索します。 [コンプライアンスマネージャーで評価を作成](compliance-manager-assessments.md)する方法について説明します。

## <a name="resources"></a>リソース

- [連邦政府機関買収規制補足 (DFARS dfars)](https://www.acq.osd.mil/dpap/dars/dfarspgi/current/index.html)
- [Microsoft Cloud for Government](https://enterprise.microsoft.com/industries/government/start-your-microsoft-cloud-for-government-trial-today)
- [オンライン サービスの使用条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [制御されていない未分類の情報 (CUI)](https://www.archives.gov/cui/registry/category-list)
- [Microsoft セキュリティ センターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
