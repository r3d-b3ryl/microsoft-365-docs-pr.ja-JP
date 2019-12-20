---
title: 米国証券取引委員会 (SEC) ルール 17a-4-4 (f) 米国
description: 独立した評価会社が、金融企業が SEC Rule 17a-4 (f) レコードの保持と不変のストレージ要件を満たすことができること365を検証しています。
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
ms.openlocfilehash: 915e70065e6efb05424c710bb3e8a98902857c6c
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40804250"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>米国証券取引委員会 (SEC) ルール 17a-4-4 (f) 米国

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft および SEC Rule 17a-4 (f)

米国[証券取引委員会 (SEC)](https://www.sec.gov/)は米国連邦政府機関の独立系であり、米国証券業界の主要な overseer とレギュレータです。 It wields は、連邦証券法による執行機関を提示し、新しい証券ルールを提案し、証券業界の市場規制を監視します。

SEC は、電子記憶メディアに書籍や記録を保持することを選択する規制対象エンティティの厳密かつ明示的な要件を定義します。 この It は、証券会社ディーラーの保存期間を含め、記録管理を規制する[17 cfr 240.17 a-3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3)および[17 cfr 240.17 a-4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64)を確立しました。 その後、SEC が[修正](https://www.sec.gov/rules/interp/34-47806.htm)した 17 CFR 240.17 a-4 段落 (f) は、2つの interpretive リリースを明示的に発行して、特定の条件が満たされている限り、書籍や記録を電子記憶媒体に保持できるようにします。

必要な保存期間におけるレコードの変更または消去を阻止した場合、電子ストレージシステムはこれらの条件を満たします。 保存期間は、レコードの種類に基づいて3から6年に変化し、最初の2年間に対して直接アクセスが義務付けられています。 さらに、interpretive リリースの1つでは、subpoenas、法務ホールド、その他の要件に準拠するために、SEC が確立した保存期間を超えたレコードをストレージシステムが保持できることが要求されます。

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft および SEC Rule 17a-4 (f)

金融サービスのお客様は、世界で最も厳しい規制がある業界の1つを表しており、財務トランザクションの保持や、未消去および変更不能な状態での関連する通信のような、複雑な繰入の対象となります。 米国のセキュリティおよび Exchange 委員会 (SEC) の最も規範となるのは、電子記憶メディア上の書籍や記録を保持することを選択する規制対象エンティティの厳しい要件を stipulates するルール17a-4 です。 保存されたレコードは改ざんが可能であり、指定した保持期間が経過するまで変更または削除することはできません。

ポリシーロックを使用した microsoft Azure 不変 Blob ストレージ、および保持ロック付きの Microsoft Office 365 は、金融機関が SEC Rule 17a-4 (f) の不変のストレージ要件を満たすのに役立ちます。

SEC Rule 17a-4 (f) に準拠するように Azure と Office 365 のコンプライアンスを評価するために、Microsoft は、レコード管理と情報ガバナンスに特化した独立した評価会社を保有しています。 Cohasset が関連しています。 生成されるレポートの対象:

- **Azure**: [SEC 17a-4-4 (f) コンプライアンス評価: Microsoft azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), Cohasset は、ポリシーロックオプションを使用して、時間ベースの blob[ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage)を消去できないようにすることを検証しています。このオプションを使用すると、消去不能かつ書き換え不可 (WORM) 形式で時間ベースの blob を保持することができます。 各 Blob (レコード) は、必要な保存期間が期限切れになり、関連付けられた法的保持が解放されるまで、変更、上書き、または削除されないように保護されます。 機密性の高いワークロードを持つソフトウェアプロバイダーとパートナーは、レコード保持と不変のストレージのための onestop ショップクラウドソリューションとして、Azure 不変 Blob ストレージを利用できるようになりました。 金融機関は、これらの機能を利用して、準拠したまま、自分のアプリケーションを構築できるようになりました。
- **Office 365**: [Exchange Online を使用して SEC 17a-4 に準拠](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4)します。 Cohasset では、 [office 365 に保持ロック](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy)が設定されていると、ブローカーディーラーを含む規制対象の顧客が、レコード保持の SEC 要件に準拠するために役立つ方法でデータを保存できるようにするアーカイブ機能があります。 Office 365 のアイテム保持ポリシーでは、電子メール、ボイスメール、共有ドキュメント、インスタントメッセージ、サードパーティのデータなど、さまざまなデータを保持するのに役立ちます。 特に、Office 365 のアーカイブを使用すると、グローバルまたは詳細なメッセージ保持ポリシーを設定して、定義済みの期間にデータを保存することができます。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

### <a name="azure--sec-rule-17"></a>Azure & SEC ルール17

[SEC 17a-4 (f) & CFTC 1.31 (c-d) Azure Storage のコンプライアンス評価](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Office 365 & SEC ルール17

[SEC 17a-4 (f) コンプライアンス評価: Microsoft Security & Exchange Online を使用したコンプライアンスセンター](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>実装方法

### <a name="financial-services-regulation"></a>金融サービスの規制

クラウドコンピューティングと Microsoft online services の主要な US 規制原則のコンプライアンスマップ。 [詳細情報](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>リスク評価 & コンプライアンスガイド

Microsoft クラウドサービスおよびレギュレータの通知のリスク評価のためのガバナンスモデルを作成します。 [詳細情報](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>財務の使用例

ケースの概要、チュートリアル、およびその他のリソースを使用して、金融サービスの Azure ソリューションを構築します。 [詳細情報](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>リソース

- [Microsoft Office 365、データ保持、およびルール17a-4 でのアーカイブ](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)
- [コンプライアンス Microsoft 金融サービス](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [コンプライアンスプログラム Microsoft business cloud services および金融サービス](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure における金融サービス コンプライアンス](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融サービス クラウド リスク評価ツール](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 のアイテム保持ポリシー](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融サービスのブログ](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景資料をダウンロードする

このサービスに関する背景資料が必要ですか? [PDF](https://download.microsoft.com/download/E/5/2/E52103E7-C1BB-4118-9725-4452FEA931D8/SEC17a-4(f)-Compliance.pdf) をダウンロードします。
