---
title: 金融業界の法令当局 (FINRA) ルール 4511 (c) 米国
description: 独立した評価会社では、Azure と Office 365 を使用して、財務企業が、FINRA ルール4511レコードの保持と不変のストレージ要件を満たすことができることが検証されています。
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
ms.openlocfilehash: 1ef6f3c9e8f6a5b3aaef40b4d0aa8eaac1c3572c
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805010"
---
# <a name="financial-industry-regulatory-authority-finra-rule-4511c-united-states"></a>金融業界の法令当局 (FINRA) ルール 4511 (c) 米国

## <a name="about-finra-rule-4511"></a>FINRA ルール4511について

[金融業界の規制機関 (FINRA)](https://www.finra.org/#/)は、米国で4500を超える金融機関を監督する、独立した最大のセキュリティ関連企業です。 米国の Congress によって認定されたのは、仲介業者が公正で誠実に活動していることを確認することによって、アメリカの投資家を保護するためです。

2011では、米国のセキュリティおよび Exchange 委員会 (SEC) は、電子記憶メディアへのブックとレコードの保持を管理する SEC の規則を、FINRA が採用したものとして承認しました。 [Finra Rule 4511 (c)](https://www.finra.org/sites/default/files/NoticeDocument/p123548.pdf)は、"finra ルールに準拠しているすべての本とレコードを、SEA (証券交換法) ルール17a-4 に準拠した形式とメディアで保持する必要がある" ということを指定します。

また、FINRA Rule 4511 (c) は、少なくとも6年の期間、該当する FINRA または SEA ルールの下に指定された保持期間がない場合に、その記録を保持する必要があります。 実際には、書籍とレコードがアカウントに関連している場合、保持期間は、アカウントの閉鎖後に6年間必要です。 それ以外の場合、保存期間は、このような書籍とレコードが作成された後の6年間になります。

## <a name="microsoft-and-finra-rule-4511c"></a>Microsoft および FINRA ルールの 4511 (c)

金融サービスのお客様は、世界で最も厳しい規制がある業界の1つを表しており、財務トランザクションの保持や、未消去および変更不能な状態での関連する通信のような、複雑な繰入の対象となります。 これらの中には、金融業界の規制機関 (FINRA) のルール4511が含まれています。これは、stipulates が、電子記憶メディア上の書籍や記録を保持することを選択する規制エンティティに対して厳しい要件を適用します。 保存されたレコードは改ざんが可能であり、指定した保持期間が経過するまで変更または削除することはできません。

ポリシーロックを使用した microsoft Azure 不変 Blob ストレージ、および保持ロックのある Microsoft Office 365 は、財務機関が FINRA Rule 4511 (c) の不変のストレージ要件を満たすのに役立ちます。

## <a name="microsoft-azure"></a>Microsoft Azure

FINRA Rule 4511 (c) を使用して Azure のコンプライアンスを評価するために、Microsoft はレコード管理と情報ガバナンスに特化した独立した評価会社を保有しています。 Cohasset が関連付けられています。 生成されたレポート、 [sec 17a-4 (f) & CFTC 1.31 (c-d) コンプライアンス評価: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)は、SEC rule 17a-4 (f) の形式とメディア要件に従って、finra rule 4511 (c) との Azure コンプライアンスを含みます。

Cohasset では、ポリシーロックオプションを使用して[Azure 不変 Blob ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage)を検証することが検証されています。これを使用して、消去できないおよび書き換え不可 (WORM) 形式で時間ベースの blob を保持する場合は、関連する finra 記憶域の要件を満たしています。 各 Blob (レコード) は、必要な保存期間が期限切れになり、関連付けられた法的保持が解放されるまで、変更、上書き、または削除されないように保護されます。

機密性の高いワークロードを持つソフトウェアプロバイダーとパートナーは、レコードの保持と不変のストレージ用のワンストップショップクラウドソリューションとして、Azure 不変 Blob ストレージを利用できるようになりました。 金融機関は、これらの機能を利用して、準拠したまま、自分のアプリケーションを構築できるようになりました。

## <a name="microsoft-office-365"></a>Microsoft Office 365

4511 (c) を使用して Office 365 のコンプライアンスを評価するために、Microsoft は、規制上の問題に特化し、Covington & の気流を含む、主要な独立した法律事務所を保持しています。 生成されたレポート、Microsoft Office 365、データ保持、およびルール17a-4 のコンプライアンスにおいて、 [365](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) Covington は、ブローカーディーラーを含む規制対象の顧客がデータを保存できるようにするアーカイブ機能が含まれています。これらの機能を使用して、レコード保持に関する finra 要件に準拠するために役立つ方法があります。

Office 365 のアーカイブでは、電子メール、ボイスメール、共有ドキュメント、インスタントメッセージ、サードパーティのデータなど、さまざまなデータを保持することができます。 特に、Office 365 のアーカイブを使用すると、グローバルまたは詳細なメッセージ保持ポリシーを設定して、定義済みの期間にデータを保存することができます。また、上書き不可で消去不能な形式にすることもできます。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

### <a name="azure--finra-rule-4511c"></a>Azure & FINRA Rule 4511 (c)

[SEC 17a-4 (f) & CFTC 1.31 (c-d) Azure Storage のコンプライアンス評価](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--finra-rule-4511c"></a>Office 365 & FINRA Rule 4511 (c)

[Office 365、データ保持、および SEC Rule 17a-4 へのアーカイブ](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)

## <a name="how-to-implement"></a>実装方法

- **金融サービスの規制**: クラウドコンピューティングおよび Microsoft online services の主要な US 規制原則のコンプライアンスマップ。 [詳細情報](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- **リスク評価およびコンプライアンス ガイド**: Microsoft クラウド サービスのリスク評価および規制機関の通知のガバナンス モデルを作成します。 [詳細情報](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- **金融ユース ケース**: 金融サービス向けの Azure ソリューションを構築するためのユース ケースの概要、チュートリアル、およびその他のリソース。 [詳細情報](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>リソース

- [Microsoft 金融サービス コンプライアンス プログラム](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Microsoft 法人向けクラウド サービスおよび金融サービス](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure における金融サービス コンプライアンス](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融サービス クラウド リスク評価ツール](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 のアイテム保持ポリシー](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融サービスのブログ](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景資料をダウンロードする

このサービスに関する背景資料が必要ですか? [PDF](https://download.microsoft.com/download/6/B/2/6B20520B-E264-4B58-9EE2-DD6C87D9E254/FINRA-Compliance.pdf) をダウンロードします。
