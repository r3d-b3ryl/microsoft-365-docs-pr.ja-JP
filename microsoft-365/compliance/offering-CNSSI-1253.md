---
title: 米国のセキュリティシステムの委員会に関する指示はありません。 1253 (CNSSI 1253)
description: Azure 自治体は、高機密性、高整合性、高可用性を必要とする米国政府機関向けの CNSSI 1253 セキュリティ制御に準拠しています。
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
ms.openlocfilehash: 232d8ddcdcd108d069247bc76850d7d17f18b629
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690694"
---
# <a name="compliance-offering-committee-on-national-security-systems-instruction-no-1253-cnssi-1253"></a>コンプライアンスオファリング: 米国のセキュリティシステムの委員会に関する指示はありません。 1253 (CNSSI 1253)

## <a name="about-cnss-instruction-1253"></a>CNSS 命令1253について

米国のセキュリティシステム (CNSS) の委員会は、米国の政府機関および機関向けの national cybersecurity ポリシーを設定する行政機関です。 [Cnss 命令 1253](https://www.dss.mil/Portals/69/documents/io/rmf/CNSSI_No1253.pdf)、「米国のセキュリティシステムのセキュリティの分類と制御の選択」では、各国のセキュリティ情報およびシステムを適切なセキュリティレベルで分類するために連邦政府機関が適用する必要があるセキュリティ標準についてのガイダンスを提供します。  
  
CNSSI 1253 は、NIST SP 800-53 上に構築されます。これにより、FedRAMP の高レベルの承認のためのコントロールのベースラインが提供されます。 ただし、CNSSI 1253 と NIST の2つの文書にはいくつかの重要な相違点があります。  
  
たとえば、CNSSI 1253 の方法では、セキュリティ制御を使用した機密性、整合性、および可用性の関連付けが明示的に定義され、national セキュリティコミュニティでセキュリティ制御オーバーレイの使用が詳細になります。 CNSS は、これら3つのセキュリティ目標のそれぞれに対して、個別の低、中、高のカテゴリを使用します。 この結果、中程度の機密性、中程度の整合性、低可用性といった分類が行われます。 CNSSI 1253 は、NIST SP 800-53 からの制御を使用して、考えられる各システムの分類に適切なセキュリティ基準を提供します。

## <a name="microsoft-and-cnssi-1253"></a>Microsoft および CNSSI 1253

FedRAMP で承認されたサードパーティの評価組織 (3PAO)、Kratos SecureInfo では、Microsoft Azure Government system の高高高度ベースライン1253とのコンプライアンスを個別に検証しました。 Kratos SecureInfo attests では、Azure Government の CNSSI 1253 Security アセスメントレポート (SAR) によって、セキュリティアセスメントプラン (SAP) に明記されている適用可能なセキュリティ制御の完全な評価が提供されます。 テストの対象となった SAR ドキュメントでは、高機密性、高整合性、高可用性を必要とするシステムのために、選択されている CNSSI 1253 セキュリティコントロールに対して Azure Government を検証します。  
  
現時点では、Azure Government は、共同認証ボード (JAB) によって発行される (ATO)、またはクラウドコンピューティングセキュリティの影響レベル5にある国防総省の暫定認証 (PA) を所有しています。要件ガイド (SRG)。 これらの承認を使用して、Kratos SecureInfo は、以前の評価でテストされたセキュリティ制御を分析し、CNSSI 1253 の高高度なベースラインへの準拠を保証するために、どの追加 CNSSI 1253 セキュリティ制御をテストするかを決定します。 Kratos SecureInfo では、43の適用可能なセキュリティコントロールの実装が成功したことを検証し、CNSSI 1253 SAR での完全なテストの結果を公開しています。  
  
要求の厳しい CNSSI 1253 要件を持つ Azure Government のコンプライアンスにより、Azure は米国内の公的機関のお客様に対して、CNSSI 1253 に準拠した豊富なサービスを提供できるようになります。Microsoft クラウドのセキュリティ。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft スコープ内クラウドサービス

- [Azure Government](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>監査、レポート、および証明書

Azure Government CNSSI 1253 CNSSI 1253 高高度ベースラインに準拠していることの証明

## <a name="how-to-implement"></a>実装方法

- [Azure government ドキュメント](https://docs.microsoft.com/azure/azure-government/): 開発者が azure government を使用してサービスを展開および管理するのに役立つチュートリアルと方法ガイドです。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**CNSSI 1253 が適用されるユーザー**

全国セキュリティシステム (NSS) を使用しているお客様は、CNSSI 1253 の要件と制御に準拠している必要があります。

**CNSSI 1253 のセキュリティコントロールに対してテストされた Azure 環境はどれですか。**

Azure Government (FedRAMP パッケージ ID F1603087869) は、これらのコントロールを再度テストしました。

## <a name="resources"></a>リソース

- [Azure Government とは](https://docs.microsoft.com/azure/azure-government/documentation-government-welcome)
- [Azure Government](https://aka.ms/Azure-Government)
- [Microsoft および FedRAMP](offering-fedramp.md)
- [マイクロソフトおよび DoD 暫定認証](offering-DoD-DISA-L2-L4-L5.md)
- [Microsoft Government クラウド](https://www.microsoft.com/enterprise/government)
- [Microsoft セキュリティセンターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>オファーリング backgrounder をダウンロードする

このオファーリングの backgrounder ドキュメントは必要ですか? [PDF](https://download.microsoft.com/download/6/E/C/6EC27E89-826E-44CB-A107-2A37AC879206/CNSSI_1253-Compliance.pdf)をダウンロードします。
