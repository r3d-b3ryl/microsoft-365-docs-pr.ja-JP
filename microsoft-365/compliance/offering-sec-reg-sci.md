---
title: 証券および Exchange の委員会規制システムのコンプライアンスと整合性 (SCI)
description: SCI ルールは、そのような自己規制組織 (SROs) をストックおよび options 交換、登録済みクリアエージェンシー、代替取引システム (ATSs) として含む、SCI エンティティに適用されます。
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
ms.openlocfilehash: de28f982fe7615d0ca81af756af81b3c25fc9de1
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807710"
---
# <a name="securities-and-exchange-commission-regulation-systems-compliance-and-integrity-sci"></a>証券および Exchange のコミッション: 規制システムのコンプライアンスと整合性 (SCI)

## <a name="about-regulation-sci"></a>規制 SCI について

米国証券取引委員会 (SEC) は米国連邦政府機関の独立系であり、米国証券業界の主要な overseer とレギュレータです。 It wields は、連邦証券法による執行機関を提示し、新しい証券ルールを提案し、証券業界の市場規制を監視します。

2014年11月に、SEC は、[システムのコンプライアンスと整合性 (sci)](https://www.sec.gov/rules/final/2014/34-73639.pdf) (およびレポートされた sci イベントのための bolster) を採用して、米国証券市場のテクノロジインフラストラクチャをしました。 規制は、システム停止の頻度を抑え、そのようなインシデントが発生した場合の復元性を向上させ、SEC による証券市場のテクノロジの監督および規制の適用を行うように設計されています。

SCI ルールは、そのような自己規制組織 (SROs) をストックおよび options 交換、登録済みクリアエージェンシー、代替取引システム (ATSs) として含む、SCI エンティティに適用されます。 ルールは主に、主な証券市況の機能 (取引、クリアランスと決済、注文ルーティング、市場データ、市場規制、市場監視) を直接サポートするシステムを制御します。

## <a name="microsoft-and-sec-regulation-sci"></a>Microsoft および SEC の規制 SCI

米国証券取引委員会 (SEC) は、米国証券を運用およびサポートする金融機関のテクノロジインフラストラクチャを強化するために、規制 SCI を採用しています。 SEC の監視では、これらのシステムが高可用性、強力な復元性、および低遅延 (メッセージの大容量で遅延が少ない) を確実にするための要件が設計されています。

この規制に準拠する必要があるお客様の金融サービスのお客様のためのガイダンスを提供するため、Microsoft は[Microsoft AZURE SEC 規制システムのコンプライアンスと整合性に関するクラウド実装ガイド](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)を公開しています。 このドキュメント内のガイダンス:

- 強力な復元性、高可用性、および低遅延をサポートする、全体的な Azure 機能の概要について説明します。
- Azure が管理する領域および規制面を明確にします。 このポイントごとの Azure 機能とサービスの SCI 要件へのマッピングは、規制フレームワークに対する Azure コンプライアンスを測定します。 また、お客様は、社内での運用時に完全に所有されていたセキュリティ責任を Azure に移行できることを理解しやすくなります。 これらの機能は、Microsoft が Azure の Sla で行う約束によって支えられています。
- お客様の責任範囲である各規制 SCI 要件を指定します。また、これらの責任に対処するための Azure ドキュメントとサービスを提供します。

このドキュメントでは、重要な規制の重点分野の詳細チェックリストを示します。 このチェックリストを使用すると、金融機関が Azure を採用する方法を理解し、それらの規制要件に準拠することができるように、お客様を支援します。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure](https://aka.ms/AzureCompliance)

## <a name="how-to-implement"></a>実装方法

- [規制 SCI 実装ガイド](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers): 規則に対して Azure 機能をマップし、コンプライアンスの共有責任を詳細にします。
- [信頼性の高い azure アプリケーションの設計](https://docs.microsoft.com/azure/architecture/resiliency/): azure アプリケーション設計の各ステップに信頼性を構築する方法について、簡単な概要を示します。
- [可用性の高いアプリケーションを設計](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs)する: 開発者が Azure ストレージアプリケーションの高可用性を確保する方法について説明します。
- [リスク評価およびコンプライアンス ガイド](https://aka.ms/RiskGovernanceGuide): Microsoft クラウド サービスのリスク評価および規制機関の通知のガバナンス モデルを作成します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**クラウドテクノロジを使用する場合の共有責任の意味**

コンピューティング環境を社内設置型からクラウド内のデータセンターに移行すると、クラウドサービスプロバイダー (CSP) にもセキュリティの責任が移行されるため、お客様はその責任を共有できるようになります。 すべてのアプリケーションとソリューションについて、その責任がどの程度お客様のものになっているか、およびお客様が展開する Azure モデル (IaaS、SaaS、または PaaS) によって、CSP にどの程度が依存しているか。 必要なセキュリティ制御を実装するために、ユーザーが責任を負う度合いを把握することはお客様の責任です。 ただし、Microsoft では、この複雑なダイナミックにお客様が移動するのに役立つガイダンスを提供しています。 詳細については、「[クラウドコンピューティングの共有責任](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91)」を参照してください。

**どの金融機関が Azure を利用して、規制の SCI 要件を満たすことができるか。**

この規制の対象となる金融機関または SCI エンティティは、Azure を展開することができます。 SEC は、株式とオプションの交換、登録されたクリアエージェンシー、FINRA、MSRB、代替取引システム (ATSs)、および指定されていない取り引きと非 NMS 株の指定を含む、「自己規制組織 (SROs)」に規制を適用することを主張しています。ボリュームのしきい値、統合された市場データの disseminators (プランプロセッサ)、および特定の免税クリアエージェンシー。

## <a name="resources"></a>リソース

- [規制 SCI に関してよく寄せられる質問に対する SEC の回答](https://www.sec.gov/divisions/marketreg/regulation-sci-faq.shtml)
- [ビジネス継続性と障害復旧 (BCDR): Azure ペアリングされた領域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)
- [クラウドコンピューティングの規制原則と Microsoft Online Services のコンプライアンスマップ](https://aka.ms/FinServ-Guide-US)
- [Microsoft Cloud Financial Services Compliance Program](https://aka.ms/FSCP-Print)
- [Azure における金融サービス コンプライアンス](https://aka.ms/FinServ-Compliance-Azure)
- [Microsoft 金融サービス](https://aka.ms/FinServ-Compliance)
- [Microsoft および SEC Rule 17a-4](offering-SEC-17a-4.md)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景資料をダウンロードする

このサービスに関する背景資料が必要ですか? [PDF](https://download.microsoft.com/download/8/1/a/81aa04eb-3c1f-4c1a-ba7d-9d30032acc52/SEC_Reg_SCI-Compliance.pdf) をダウンロードします。