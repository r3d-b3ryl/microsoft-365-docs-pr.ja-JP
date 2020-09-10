---
title: US DoE 10 CFR Part 810
description: 米国 DoE 10 CFR Part 810 の輸出規制要件の対象となるお客様は、Azure Government を使用できます。
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
ms.openlocfilehash: a809ae91bbe1302ae4087b3a430dea87e2c913a1
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415697"
---
# <a name="us-doe-10-cfr-part-810"></a>US DoE 10 CFR Part 810

## <a name="microsoft-and-doe-10-cfr-part-810"></a>Microsoft および DoE 10 CFR Part 810

Microsoft Azure Government は、米国エネルギー (DoE) 10 CFR Part 810 の輸出規制要件に従ってお客様をサポートするのに役立ちます。次の2つの承認があります。

- FedRAMP (ATO) が共同認証ボード (JAB) によって発行された、高暫定の承認。
- 国防総省 (DoD) 防衛情報システムエージェンシーからのレベル4および5の仮承認

FedRAMP は適切な基準を提供しており、Azure 自治体がコアインフラストラクチャと仮想化テクノロジと、厳格な NIST 統制を使用して設計されたコンピューティング、ストレージ、ネットワークなどのサービスを提供することを保証します。 これらは、顧客データの分離要件を満たし、ユーザーのオンプレミス環境への安全な接続を可能にするのに役立ちます。

さらに、Azure Government は、Azure クラウドから物理的に分離された米国政府機関のコミュニティクラウドです。 米国政府機関による特定のバックグラウンド審査要件に関する追加の保証を提供します。これには、Azure の運用担当者間で、情報やシステムへのアクセスを制限する特定のコントロールが含まれます。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure Government](https://aka.ms/AzureCompliance)
- Intune

## <a name="how-to-implement"></a>実装方法

- [CIP 標準 & クラウドコンピューティング](https://aka.ms/AzureNERC): azure または azure Government にワークロードを展開するための、電気ユーティリティーおよび登録エンティティに関するガイダンス。

## <a name="about-doe-10-cfr-part-810"></a>DoE 10 CFR Part 810 について

米国防省エネルギー (DoE) 輸出規制 [10 CFR part 810](https://www.govinfo.gov/content/pkg/FR-2015-02-23/pdf/2015-03479.pdf) は、未分類の核技術およびアシスタントのエクスポートを管理します。 米国からエクスポートされた核テクノロジが peaceful の目的にのみ使用されることを保証するのに役立つ情報を記載しています。 改訂されたパーツ 810 (最終規則) は、2015年3月に有効になり、 [国内の核セキュリティ管理](https://www.energy.gov/nnsa/national-nuclear-security-administration)によって管理されます。 セクション810.6 は、「一般に承認された」と、特定の認証を必要とするもの (たとえば、エンリッチメントやヘビー水の生産などの機密性の高い核テクノロジを必要とする技術) の両方について、特別な DoE 承認が必要であることを示しています。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Azure Government に適用される米国の核となる規制委員会の 10 CFR Part 110 の規制を行いますか?**

いいえ。 [アメリカ弾頭ミサイル規制委員会](https://www.nrc.gov/)(nrc) は、 [10 CFR part 110](https://www.nrc.gov/reading-rm/doc-collections/cfr/part110/)の下の核施設と関連する機器および材料の[エクスポートとインポート](https://www.nrc.gov/about-nrc/ip/export-import.html)を規制します。 NRC では、DoE 管轄区の下にあるこれらのアイテムに関連する核技術および支援を規制していません。 そのため、NRC 10 CFR Part 110 の規則は Azure Government には適用されません。

**DoE 10 CFR Part 810 に準拠している証拠を提供するにはどうすればよいですか?**

組織がデータを Azure Government に展開している場合は、適切に制限された方法でデータを処理しているという証拠として、Azure Government FedRAMP High P-ATO を利用できます。 ただし、クラウドサービスの使用を含む、独自のシステムの DoE 認証を取得する責任があります。

**Azure Government に展開されたデータの分類について、どのような責任がありますか?**

Azure Government にデータを展開するお客様は、独自のセキュリティ分類プロセスを担当します。 DoE export コントロールの対象となる顧客データの場合、分類システムは、 [US Atomic Energy Act](https://www.epa.gov/laws-regulations/summary-atomic-energy-act)のセクション148によって確立された未分類の管理対象核兵器情報 (ucni) コントロールによって補強されます。

## <a name="resources"></a>リソース

- [Azure クラウドサービスおよび US 輸出統制](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- [Microsoft と FedRAMP](offering-fedramp.md)
- [Microsoft および DoD](offering-dod-disa-l2-l4-l5.md)
- [Microsoft Government クラウド](https://www.microsoft.com/enterprise/government)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
