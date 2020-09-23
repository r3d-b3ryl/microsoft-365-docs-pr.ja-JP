---
title: NIST SP 800-171
description: Microsoft クラウドサービスは、非連邦情報システムの管理されていない未分類情報 (CUI) を保護するために、NIST SP 800-171 ガイドラインに準拠しています。
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
ms.openlocfilehash: 9874a68978e5755e8e86ff476ec96170878a10da
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208089"
---
# <a name="nist-sp-800-171"></a>NIST SP 800-171

## <a name="about-nist-sp-800-171"></a>NIST SP 800-171 について

米国国立標準技術局 (NIST) は、連邦政府機関の情報と情報システムを保護するための測定基準とガイドラインを推進および維持します。 統制されていない未分類情報 (CUI) を管理するエグゼクティブオーダー13556への対応として、 [NIST SP 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)が公開されました。 *連邦情報システムおよび組織の非分類情報を保護*しています。 CUI は、政府によって作成されたデジタルおよび物理の情報 (つまり、分類されていないものの代理となるエンティティ) として定義されており、機密保護を必要とします。

NIST SP 800-171 は当初は2015年6月に公開されており、脅威の進化に対応するために複数回更新されています。 このガイドでは、政府機関以外の情報システムおよび組織に対して、CUI への安全なアクセス、転送、保存を行う方法についてのガイドラインを提供します。この要件は、次の4つの主なカテゴリに分類されます。

- 管理と保護のためのコントロールとプロセス
- IT システムの監視と管理
- エンドユーザーのためのプラクティスと手順を明確にする
- 技術的および物理的なセキュリティ対策の実装

## <a name="microsoft-and-nist-sp-800-171"></a>Microsoft および NIST SP 800-171

サードパーティの認定組織、Kratos Secureinfo、および Coalfire は、Microsoft と提携して、 *米国連邦情報システムおよび組織で、管理されていない未分類の情報 (cui) を保護*する800-171 ことを証明しています。 [Microsoft の FedRAMP 要件の実装](offering-fedramp.md)により、microsoft のスコープ内のクラウドサービスが、既に導入されているシステムとプラクティスを使用して、NIST SP 800-171 の要件を満たしていることを確認できます。

NIST SP 800-171 の要件は、NIST SP 800-53 のサブセットで、FedRAMP が使用する標準です。 付録 D (NIST SP 800-171) は、自分のセキュリティ要件を NIST SP 800-53 の関連するセキュリティコントロールに直接マッピングしています。この場合、スコープ内のクラウドサービスは、FedRAMP プログラムで既に評価および承認されています。

米国政府機関を処理または保存するエンティティ (研究機関、コンサルティング会社、製造請負業者) は、NIST SP 800-171 の厳しい要件に準拠している必要があります。 この構成証明とは、microsoft が完全に準拠していることを保証するために CUI ワークロードの展開を検討しているお客様に対して、Microsoft のスコープを持つクラウドサービスが可能になります。 たとえば、「対象となる防衛情報」を処理、保存、または送信するすべての DoD 請負業者は、情報システムの Microsoft クラウドサービスをスコープ内で使用することにより、米国国防総省の、米国国防総省の、NIST SP 800-171 のセキュリティ要件に準拠する必要があることを満たします。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure Government](https://aka.ms/AzureCompliance)
- [Dynamics 365 米国政府](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 米国政府機関向けコミュニティクラウド (GCC)、Office 365 GCC 高、DoD](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

- [NIST SP 800-171 に準拠するための Azure 自治体の構成証明](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a>実装方法

- [Azure 青写真サンプル](https://docs.microsoft.com/azure/governance/blueprints/samples/): NIST ベースのコントロールに準拠したワークロードの実装のサポートを受けることができます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**組織の NIST SP 800-171 で Microsoft コンプライアンスを使用できますか?**

はい。 Microsoft のお客様は、独自の FedRAMP の一部としての、独立したサードパーティの評価組織 (3PAO) からのレポートで説明されている監査された統制を使用できます。 これらのレポートは、Microsoft がスコープ内のクラウドサービスで実装した統制の有効性を証明します。 お客様は、CUI ワークロードが NIST SP 800-171 ガイドラインに準拠していることを確認する責任があります。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Microsoft コンプライアンスマネージャーを使用してリスクを評価する

[Microsoft コンプライアンスマネージャー](compliance-manager.md) は、 [microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md) の機能であり、組織のコンプライアンスの状況を理解し、リスクを軽減するためのアクションを実行するのに役立ちます。 コンプライアンスマネージャーには、この規制の評価を構築するためのプレミアムテンプレートが用意されています。 [コンプライアンスマネージャー] の [ **評価テンプレート** ] ページでテンプレートを検索します。 [コンプライアンスマネージャーで評価を作成](compliance-manager-assessments.md)する方法について説明します。

## <a name="resources"></a>リソース

- [Microsoft DoD 認定資格は、NIST 800-171 の要件を満たしている](offering-DoD-DISA-L2-L4-L5.md)
- [NIST 800-171 コンプライアンスは Cybersecurity のドキュメントで始まります。](https://www.nist800171.com/)
- [Microsoft Cloud Services FedRAMP 承認](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [NIST 800-171 3.3 監査およびアカウンタビリティ (Office 365 GCC 高)](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [Microsoft および NIST Cybersecurity Framework](offering-nist-csf.md)
- [Microsoft Government クラウド](https://www.microsoft.com/enterprise/government)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
