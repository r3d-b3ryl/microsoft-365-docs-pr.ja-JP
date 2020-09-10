---
title: Federal Risk and Authorization Management Program (FedRAMP)
description: Microsoft には、米国連邦リスクおよび承認管理プログラム P-ATOs と ATOs が付与されました。
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
ms.openlocfilehash: c91c71f199ef36c1c9a0da023c7b26d6cb64282e
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415781"
---
# <a name="federal-risk-and-authorization-management-program-fedramp"></a>Federal Risk and Authorization Management Program (FedRAMP)

## <a name="fedramp-overview"></a>FedRAMP の概要

米国連邦リスクおよび承認管理プログラム (FedRAMP) は、連邦情報セキュリティ管理法 (FISMA) でのクラウドコンピューティング製品とサービスの評価、監視、承認のための標準化されたアプローチを提供し、連邦機関による安全なクラウドソリューションの導入を促進するために確立されました。

管理および予算の事務所では、すべてのエグゼクティブ連邦機関が FedRAMP を使用して、クラウドサービスのセキュリティを検証する必要があります。 (他の機関もその機能を採用しているため、公共の部門の他の分野でも役立ちます)。米国標準技術局 (NIST) SP 800-53 は、必須の標準を設定し、情報システムのセキュリティカテゴリ (機密、整合性、可用性) を確立して、情報システムと情報システムが侵害されている必要がある組織への潜在的な影響を評価します。 FedRAMP は、クラウドサービスプロバイダー (CSP) がこれらの基準を満たしていることを認定するプログラムです。

連邦機関にサービスを販売するための Csp desiring は、次の3つのパスを使用して、FedRAMP コンプライアンスを示します。

- 共同認証ボード (JAB) から運用するための (ATO) 仮の機関を獲得します。 JAB は、FedRAMP の主要なガバナンスおよび意思決定の本文です。 国防総省の代表者、国土安全保障の部署、および一般的なサービス管理は、取締役会で提供されます。 ボードは、FedRAMP コンプライアンスを実証した ATO を Csp に付与します。
- 連邦機関から操作する権限 (ATO) を受け取ります。
- または、プログラムの要件を満たす CSP 提供のパッケージを開発するために、単独で作業します。

これらのパスには、FedRAMP プログラムマネジメントオフィス (PMO) による厳格な技術レビューと、プログラムによって認可された独立した第三者の組織による評価が必要です。

FedRAMP 承認は、NIST ガイドライン (低、中、高) に基づく3つの影響レベルで付与されます。 これらのレベルは、機密、整合性、または可用性が組織に与える可能性のある影響 (低 (影響)、中程度 (重大な悪影響)、高 (重大または致命的な影響) をランク付けします。

## <a name="microsoft-and-fedramp"></a>Microsoft と FedRAMP

Microsoft の官公庁クラウドサービス (Azure Government、Dynamics 365 Government、Office 365 など) は米国連邦リスクおよび承認管理プログラム (FedRAMP) の要件を満たしており、米国連邦政府機関は、Microsoft クラウドのコスト削減と厳密なセキュリティによる恩恵を受けることができます。

Microsoft government cloud service では、公的機関のお客様に、fedramp に準拠した豊富なサービスを提供しています。これにより、お客様は fedramp の高レベルの [設計](https://aka.ms/fedrampblueprint)を実装する必要がある、あらゆる Azure で展開されたアーキテクチャに対して一連のポリシーを展開することができます。

## <a name="microsoft-azure-p-atos"></a>Microsoft Azure P-ATOs

Azure および Azure Government は、ATO を共同認証ボード (FedRAMP 認定の最高レベルのバー) から取得しています。これは、非常に機密性の高いデータを処理するために Azure および Azure Government の使用を承認します。

Azure および Azure Government の FedRAMP 監査には、スコープ内サービスのインフラストラクチャ、開発、運用、管理、サポートを含む情報セキュリティ管理システムが含まれていました。 ATO が付与されている場合でも、CSP は、動作するすべての政府機関からの承認 (ATO) を必要とします。 Azure では、政府機関は、独自のセキュリティ承認プロセスで Azure ATO を使用して、FedRAMP 要件にも合致するエージェンシー ATO を発行するための基礎として利用できます。

Azure は、他のクラウドプロバイダーよりも多くのサービスを FedRAMP の高影響レベルでサポートし続けます。 また、Azure パブリッククラウドの FedRAMP は、多くの政府機関のお客様のニーズに対応していますが、より厳しい要件を持つ機関は Azure Government を引き続き利用します。これにより、スタッフの高度な審査などの追加の手段が提供されます。 Microsoft は、現在の年に対して計画されているサービスに加えて、現在 Azure Government で [利用可能なすべての azure パブリックサービス](https://docs.microsoft.com/azure/azure-government/compliance/azure-services-in-fedramp-auditscope#azure-public-services-by-audit-scope) をリストしています。

## <a name="microsoft-dynamics-365-us-government-ato"></a>Microsoft Dynamics 365 米国政府機関 ATO

Dynamics 365 米国政府機関は、米国の米国国防省、都市開発 (HUD) によって、ATO の高い影響レベルで、FedRAMP エージェンシーを付与されました。 認定の範囲は政府機関のコミュニティクラウドに限定されていますが、Dynamics 365 米国政府のビジネスプランとエンタープライズプランは、同じ一連の厳しい FedRAMP コントロールに従って動作します。

## <a name="microsoft-office-365-and-office-365-us-government-atos"></a>Microsoft Office 365 および Office 365 米国政府 ATOs

- Office 365 および Office 365 の米国政府機関は、米国の医療機関および人事サービス (DHHS) の ATO を所有しています。
- Office 365 米国政府機関による ATO は、米国国防総省の情報システムエージェンシー (DISA) からの P-を備えています。 Office 365 を展開するお客様は、米国政府による防御を使用して、ATO を使用してエージェンシー ATO を生成し、その承認を文書化することができます。
- Office 365 (エンタープライズおよびビジネスプラン) および Office 365 の米国政府機関は、Inspector ATO の DHHS オフィスの中程度の影響レベルで、FedRAMP エージェンシーを所有しています。 Office 365 米国政府機関は、この承認を得るための最初のクラウドベースの電子メールおよびコラボレーションサービスです。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure および Azure Government](https://go.microsoft.com/fwlink/p/?linkid=2095323)
- [Dynamics 365 米国政府](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 および Office 365 U.S. Governmen](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- Office 365 米国防総省
- Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに組み込まれているサービス)
- Microsoft Defender ATP

> [!NOTE]
> Azure Government で Azure Active Directory を使用するには、azure パブリッククラウドに Azure Government の外部に展開されているコンポーネントを使用する必要があります。

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

Microsoft は、P-ATO および ATO を維持するために、Microsoft のクラウド サービスを再認定する必要があります。 そのためには、Microsoft はセキュリティ制御を継続的に監視して評価する必要があり、サービスのセキュリティが準拠していることを示します。

- [Microsoft cloud services FedRAMP 承認</span>](https://marketplace.fedramp.gov/#/product/azure-government?sort=productName&productNameSearch=azure)
- [Microsoft FedRAMP 監査レポート</span>](https://aka.ms/MicrosoftFedRAMPAuditDocuments)  

他の FedRAMP レポートを受信するには、 [Azure 連邦ドキュメント](mailto:AzFedDoc@microsoft.com)に電子メールを送信します。

## <a name="quickly-deploy-your-fedramp-solutions-on-azure-government"></a>Azure Government に FedRAMP ソリューションを迅速に展開する

Microsoft が ATO プロセスについて説明し、fedramp の大規模な青写真を使用して FedRAMP ソリューションをすばやく展開することができます。これにより、FedRAMP High controls を実装する必要がある Azure で展開されたアーキテクチャに対して、一連のポリシーを実装することができます。

[Azure FedRAMP の概要 (青写真) の使用を開始する](https://aka.ms/fedrampblueprint)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Microsoft クラウドサービスは連邦情報セキュリティ管理法 (FISMA) に準拠していますか?**

FISMA は、FISMA 要件に準拠している組織からのみ情報システムおよびサービスを調達する必要がある連邦法です。 FISMA に準拠していることを示すほとんどの政府機関およびベンダーは、特別文書 800-53 rev 4 で NIST によって識別されたコントロールをどのように満たすかを示しています。 FISMA プロセス (基礎となる標準は含まれていません) は、2011の FedRAMP に置き換えられました。

**FedRAMP が適用されるユーザー**

低および中程度のリスク影響レベルで、連邦機関のクラウド展開およびサービスモデルでは、' FedRAMP は必須です。 ' CSP を要請する連邦機関は、FedRAMP 仕様を満たす必要がある場合があります。 また、連邦政府が使用する製品やサービスでクラウドテクノロジを採用している企業は、ATO を入手する必要がある場合があります。

**エージェンシーが独自のコンプライアンス作業を開始する場所**

連邦機関が、FedRAMP を正常に移動し、その要件を満たすために必要な手順の概要については、「 [承認済み: 代理を取得](https://www.fedramp.gov/agency-authorization/)する」に移動してください。

**代理店の承認プロセスで Microsoft のコンプライアンスを使用できますか?**

はい、できます。 連邦政府機関からの ATO を必要とするプログラムまたはイニシアチブの基礎として、Microsoft クラウドサービスの証明書を使用することができます。 ただし、これらのサービスの外部にあるコンポーネントについては、独自の承認を得る必要があります。

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>Microsoft コンプライアンス スコアを使用してリスクを評価する

[Microsoft コンプライアンス スコア](compliance-score.md)は、[ Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)のプレビュー機能で、組織のコンプライアンスの状況を把握し、リスクを軽減するための処置を実行できるようにします。 [コンプライアンススコアを設定](compliance-score-setup.md)した後、[**テンプレート**] ドロップダウンメニューから事前に構成された[fedramp テンプレート](https://go.microsoft.com/fwlink/?linkid=2118102)を選択して、組織がこの規制の要件を満たすのを支援します。

## <a name="resources"></a>リソース

- [連邦リスクおよび承認管理プログラム](https://www.fedramp.gov/)
- [FedRAMP セキュリティ評価フレームワーク](https://www.fedramp.gov/assets/resources/documents/FedRAMP_Security_Assessment_Framework.pdf)
- [マイクロソフトのクラウドでコンプライアンスを管理する](https://www.microsoft.com/trustcenter/common-controls-hub)
- [Microsoft Government クラウド](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Azure コンプライアンスの提供](https://aka.ms/azurecompliance)
