---
title: 米国国防総省 (DoD) 暫定認証
description: Microsoft は、影響レベル5、4、および2で、米国国防総省 (DoD) の仮承認を受けました。
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
ms.openlocfilehash: fee91c384850b5a1593cc17e6215985217ada033
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415475"
---
# <a name="us-department-of-defense-dod-provisional-authorization-at-impact-levels-2-4-and-5"></a>米国国防総省 (DoD) の影響レベル2、4、および5の仮承認

## <a name="dod-and-disa-overview"></a>DoD および DISA の概要

防衛情報システムエージェンシー (DISA) は、米国国防総省 (DoD) の戦闘サポートエージェンシーです。 これにより、エンタープライズ情報インフラストラクチャ、通信のサポート、DoD、ホワイトハウス、および米国の防御の役割を果たすその他の組織のための、セキュリティで保護された安全なエンタープライズクラウド環境が提供されます。

委任状を実装するには、「DoD クラウドコンピューティングのセキュリティ要件ガイド (SRG)」を展開します。 SRG は、DoD 情報、システム、およびアプリケーションをホストするクラウドサービスプロバイダー (Csp) のベースラインセキュリティ要件と、DoD によるクラウドサービスの使用について定義します。 DoD クラウドセキュリティモデルを置き換え、DoD リスク管理フレームワークと NIST 800-37/53 にマッピングします。

DoD Cloud Service のサポートによって、SRG のポリシー、セキュリティ制御、およびその他の要件が定義されます。これにより、が公開および保守されます。 このガイドでは、クラウドサービスプロバイダーの計画と承認に関して、DoD エージェンシーと部署について説明します。 また、クラウドサービスのサポートは、attestations が DoD 標準に準拠していることを示すために、csp が提供する認証プロセスである SRG に準拠するために CSP を評価します。 必要に応じて DoD 暫定承認 (PAs) を発行します。そのため、DoD エージェンシーおよびサポート組織は、自分の完全な承認プロセスを実行することなく、クラウドサービスを使用して、時間と労力を節約できます。

## <a name="microsoft-and-us-dod-provisional-authorization"></a>Microsoft および米国の米国の暫定認証

Microsoft の官公庁クラウドサービスは、影響レベル2から5までの米国国防総省の要件を満たしています。米国国防総省は、Microsoft Cloud のコスト削減と厳重なセキュリティによる恩恵を受けることができます。 Azure Government、Office 365 米国政府、および Dynamics 365 Government を含む保護されたサービスを展開することで、防衛機関は、準拠しているサービスの豊富なアレイを使用できます。

- Microsoft [Azure Dod ブループリント](https://docs.microsoft.com/azure/governance/blueprints/samples/dod-impact-level-4/)を使用して、DoD を迅速に展開し、L4 を展開する方法について説明します。

## <a name="dod-impact-level-5-provisional-authorization"></a>DoD 影響レベル5の暫定認証

DISA Cloud Service のサポートには、DoD に関して Microsoft Azure Government の DoD 影響レベル 5 PA が与えられています。 DISA には、Office 365 の米国政府機関による DoD への影響レベル5の PA が与えられています。 影響レベル5法律、その他の政府規制、または情報を所有し、レベル4より高いレベルの保護を必要とする機関によって示される、統制されていない未分類情報 (CUI) を対象としています。 また、未分類の National セキュリティシステムについても説明します。

## <a name="dod-impact-level-4-provisional-authorization"></a>DoD 影響レベル4暫定認証

DISA Cloud Service のサポートには、Microsoft Azure Government に DoD 影響レベル4の PA が与えられています。 これは、FedRAMP 認証のレビューと、クラウドコンピューティング SRG に必要な追加のセキュリティ制御に基づいていました。 (FedRAMP は、政府機関向けのセキュアなクラウドコンピューティングを可能にする US プログラムです)。

影響レベル4制御されていない未分類の情報 (エグゼクティブオーダー 13556 (2010 年11月) およびその他のミッションクリティカルなデータを保護する必要があるデータを対象としています。 公式の使用のみ、法的執行機関の機密情報、または機密性の高いセキュリティ情報として指定されたデータが含まれている場合があります。 この承認により、連邦政府のお客様は、範囲内の Microsoft government クラウドサービスにこれらの種類の機密性の高いデータを展開できます。

## <a name="covered-services-for-dod-impact-level-2-authorization"></a>DoD 影響レベル2承認の対象となるサービス

FedRAMP の承認に基づいて、クラウドサービスのサポートに DoD 影響レベル 2 PA が与えられています。

- Azure および Azure Government Infrastructure as Service (IaaS) とプラットフォームとしてのプラットフォーム (PaaS) は、FedRAMP ジョイント認証ボードからの運用 (ATO) に基づいてこの認証を許可されていました。
- Dynamics 365 米国政府機関のサービスとしてのソフトウェア (SaaS) には、機関 (ATO) と都市開発 (HUD) の運用 () に基づいてこの承認が付与されていました。
- Office 365 の米国政府機関には、ATO のエージェンシー FedRAMP に基づいて、この承認が付与されています (DHHS)。

影響レベル2は、制御されていない未分類情報 (公開リリースに対して承認されるデータ) を対象としています。 また、「ミッションクリティカル」とは見なされませんが、最小限のレベルのアクセス制御が必要なその他の未分類情報についても説明します。 この承認により、連邦政府のお客様は、範囲内の Microsoft クラウドサービスに機密情報や基本的な防衛アプリケーションと web サイトを展開できます。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

### <a name="covered-services-for-dod-impact-level-5"></a>DoD 影響レベル5の対象となるサービス

- [DoD のための Azure Government](https://aka.ms/AzureCompliance)
- [Office 365 米国防総省](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

### <a name="covered-services-for-dod-impact-level-4"></a>DoD 影響レベル4の対象となるサービス

- [Azure Government](https://aka.ms/AzureCompliance)
- [Office 365 米国防総省](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

### <a name="covered-services-for-dod-impact-level-2"></a>DoD 影響レベル2の対象となるサービス

- [Azure](https://aka.ms/AzureCompliance)
- [Dynamics 365 米国政府](https://aka.ms/d365-compliance-list)
- [Office 365 米国政府機関](https://aka.ms/o365-compliance-framework)
- Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

DoD PA が付与されると、Microsoft cloud services が毎年監視および評価されます。 [Microsoft FedRAMP 承認](https://marketplace.fedramp.gov/#/products?sort=productName&productNameSearch=microsoft)

## <a name="fast-track-your-deployment-of-dod-solutions-on-azure"></a>Azure での DoD ソリューションの展開を迅速に追跡する

Azure のセキュリティとコンプライアンス部門の防御の青写真を使用して、government のクラウドの利点を活用することについて、すぐに開始します。 この青写真は、今日の DoD 準拠ソリューションの構築を開始するためのツールとガイダンスを提供します。 [Azure DoD 青写真の使用を開始](https://docs.microsoft.com/azure/governance/blueprints/samples/dod-impact-level-4/)します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Microsoft のコンプライアンスを自分の組織の認定プロセスに利用できますか?**

はい、できます。 すべての DoD 機関は、DoD 認証を必要とするプログラムまたはイニシアチブの基礎として、Microsoft クラウドサービスの証明書に頼ることができます。 (これは、DoD をサポートし、クラウドサービスを必要とする他の組織にも適用されます)。ただし、これらのサービスの外部にあるコンポーネントについては、独自の承認を得る必要があります。

**Microsoft の DoD 認定資格は、NIST 800 –171の要件を満たしていますか?**

2016年10月に、国防総省 (DoD) は、情報システムを使用して、"対象となる防衛情報" を処理、保存、または送信するすべての DoD 請負業者に適用される、連邦防御 (promulgated) 句を実装する最終規則を示しています。 このようなシステムは、NIST SP 800 –171で規定されているセキュリティ要件を満たしている必要があります。 [連邦情報システムや組織内の規制](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-171.pdf)されていない未分類情報を保護すること、または DoD 契約責任者によって承認された「代替の効果的なセキュリティ対策」というものです。 また、DoD 請負業者は、対象となる防御情報を処理、保存、または送信するために外部クラウドサービスプロバイダーを使用する必要があります。このプロバイダーは、FedRAMP の適度なベースラインと同等のセキュリティ要件を満たしている必要があります。

次の Microsoft クラウドサービスは、FedRAMP の中程度の承認を受信しています。 Azure、Azure Government、Dynamics 365 米国政府、Office 365 MT、Office 365 米国政府機関、および Office 365 米国政府機関による防御。

また、「対象となる防衛情報」を処理、保存、または送信するために DoD 請負業者によって使用される可能性がある、FedRAMP で認証された境界の外側にあるマイクロソフトのサービスは、2017年12月31日のコンプライアンスの期限に達したことをレビューしています。 Microsoft は、このような内部サービスおよび顧客向けサービスが、DFARS 800 –171または適切なセキュリティ同等のものに準拠しているかどうかを文書化して、dfars 関連する句を満たすようにしています。

## <a name="resources"></a>リソース

- [DoD クラウドコンピューティングのセキュリティ要件ガイド (SRG) とその他のドキュメント](https://public.cyber.mil/dccs/dccs-documents/)
- [DISA Cloud Service サポート](https://storefront.disa.mil/kinetic/disa/service-catalog#/forms/cloud-service-support)
- [連邦情報システムおよび組織での制御されていない未分類情報の保護](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-171.pdf)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- [Microsoft Common Controls Hub コンプライアンス フレームワーク](https://www.microsoft.com/trustcenter/common-controls-hub)
- [Microsoft Government クラウド](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
