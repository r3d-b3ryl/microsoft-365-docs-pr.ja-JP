---
title: 商品計画取引委員会 (CFTC) ルール 1.31 (c-d) 米国
description: 独立した評価会社では、Azure と Office 365 が、金融企業が CFTC ルール1.31 レコードの保持と不変のストレージ要件を満たすことができることを検証しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: e2c911592dea19afeca8d0f347e20ac3bd6c6ba2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805440"
---
# <a name="commodity-futures-trading-commission-cftc-rule-131c-d-united-states"></a>商品計画取引委員会 (CFTC) ルール 1.31 (c-d) 米国

## <a name="about-cftc-rule-13c-d"></a>CFTC ルール 1.3 (c-d) について

独立した米国連邦政府機関である[商品計画取引委員会](https://www.cftc.gov/)(cftc) は、商品計画とオプションマーケット、および最近のスワップ市場を規制します。  
  
長期的な CFTC ルール1.31 は、SEC Rule 17a-4 (f) によって確立されたレコード保持要件を定義します。 さらに、電子記録を5年間保持する必要があり、最初の2年間に元の情報を「すぐにアクセス可能」にしておき、コミッションまたは米国防省の中での調査で利用できるようにすることを指定しています。保持期間。  
  
2017では、 [Cftc がルールを改訂](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrfederalregister/documents/file/2017-11014a.pdf)し、修正とモダン化を管理しています。これにより、規範のない原則に基づく標準が採用され、レコードをより柔軟に管理することができます。 これにより、ルールがより適切に機能するようになり、規制対象エンティティは、"記録管理プロセスの信頼性を確保する" 保護を維持しながら、ビジネスに最も適したテクノロジを選択することができます。 変更されたルールは、組織が2年間、元のレコードを保持するという要件を削除しますが、5年間の保守期間を保持します。これは、CFTC と SEC の両方によって規制される企業の harmonizes プラクティスです。

## <a name="microsoft-and-cftc-rule-131c-d"></a>Microsoft および CFTC Rule 1.31 (c-d)

金融サービスのお客様は、世界で最も厳しい規制がある業界の1つを表しており、財務トランザクションの保持や、未消去および変更不能な状態での関連する通信のような、複雑な繰入の対象となります。 最も規範的なのは、米方の商品計画取引委員会 (CFTC) のルール1.31 で、電子記憶メディアに関する書籍や記録を保持することを選択する規制対象エンティティに対して厳しい要件を stipulates ます。 保存されたレコードは改ざんが可能であり、指定した保持期間が経過するまで変更または削除することはできません。 Microsoft Azure 不変 Blob ストレージ (ポリシーロック付き) と Microsoft Office 365 (保持ロック付き) は、金融機関が CFTC Rule 1.31 (c-d) のストレージ要件を満たすのに役立ちます。

### <a name="microsoft-azure"></a>Microsoft Azure

CFTC Rule 1.31 (c-d) に準拠した Azure コンプライアンスを評価するために、Microsoft はレコード管理と情報ガバナンスに特化した独立した評価会社を保有しています。 Cohasset が関連付けられています。 生成されたレポートの[cftc 1.31 (c) – (d) コンプライアンス評価: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), cohasset ポリシーロックオプションを使用して、時間ベースの blob を保持するように設定された[Azure 不変 blob ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage)を、消去不可および書き換え不可 (WORM) 形式で保持するために使用する場合は、cftc ルールの原則に基づいた 各 Blob (レコード) は、必要な保存期間が期限切れになり、関連付けられた法的保持が解放されるまで、変更、上書き、または削除されないように保護されます。 機密性の高いワークロードを持つソフトウェアプロバイダーとパートナーは、レコード保持のワンストップショップクラウドソリューションとして、Azure 不変 Blob ストレージを利用できるようになりました。 金融機関は、これらの機能を利用して、準拠したまま、自分のアプリケーションを構築できるようになりました。

### <a name="microsoft-office-365"></a>Microsoft Office 365

CFTC Rule 1.31 (c-d) に対する Office 365 のコンプライアンスを評価するために、Microsoft は、規制上の問題に特化した、Covington & の気流を含む独立した法律事務所を参加しています。 結果のレポート、 [Microsoft Office 365、データ保持、およびルール17a-4 のコンプライアンス](https://go.microsoft.com/fwlink/?linkid=830440)において、Covington では、 [Office 365 に保持ロック](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy)が設定されていることを検証しています。これにより、規制を適用している顧客は、レコード保持のための cftc 要件に準拠するための方法でデータを保存できます。

Office 365 のアーカイブは、電子メール、ボイスメール、共有ドキュメント、インスタントメッセージ、サードパーティのデータなど、さまざまなデータを保持するのに役に立ちます。 特に、Office 365 のアーカイブを使用すると、グローバルまたは詳細なメッセージ保持ポリシーを設定して、定義済みの期間にデータを保存することができます。また、上書き不可で消去不能な形式にすることもできます。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure](https://aka.ms/AzureCompliance)
- [Office 365](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

[Azure & CFTC Rule 1.31-SEC 17a-4-4 (f) & Azure ストレージの CFTC 1.31 (c-d) コンプライアンス評価

[Office 365 & CFTC Rule 1.31-Office 365、データ保持、および SEC 規則17a-4 に準拠するためのアーカイブ

## <a name="how-to-implement"></a>実装方法

- [金融サービスの規制](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides): クラウドコンピューティングおよび Microsoft online services の主要な US 規制原則のコンプライアンスマップ。
- [リスク評価およびコンプライアンス ガイド](https://aka.ms/RiskGovernanceGuide): Microsoft クラウド サービスのリスク評価および規制機関の通知のガバナンス モデルを作成します。
- [金融ユース ケース](https://docs.microsoft.com/azure/industry/financial/): 金融サービス向けの Azure ソリューションを構築するためのユース ケースの概要、チュートリアル、およびその他のリソース。

## <a name="resources"></a>リソース

- [Microsoft 金融サービス コンプライアンス プログラム](https://aka.ms/FSCP-Print)
- [Microsoft 法人向けクラウド サービスおよび金融サービス](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Azure における金融サービス コンプライアンス](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融サービス クラウド リスク評価ツール](https://aka.ms/FFIEC-CSDT)
- [Microsoft Office 365 のアイテム保持ポリシー](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融サービスのブログ](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景資料をダウンロードする

このサービスに関する背景資料が必要ですか? [PDF](https://download.microsoft.com/download/9/A/9/9A9847FE-164A-4321-8112-50719D9EA877/CFTC1.31-Compliance.pdf) をダウンロードします。
