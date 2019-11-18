---
title: NIST SP 800 –171
description: Microsoft クラウドサービスは NIST SP 800 に準拠しています。連邦情報システムで制御されていない未分類情報 (CUI) を保護するための171ガイドラインです。
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
ms.openlocfilehash: 8924905e83d1911dc30a420319d61940b75bfe05
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690736"
---
# <a name="compliance-offering-nist-sp-800171"></a>コンプライアンスオファリング: NIST SP 800 –171

## <a name="about-nist-sp-800171"></a>NIST SP 800 –171について

米国国立標準技術局 (NIST) は、連邦政府機関の情報と情報システムを保護するための測定基準とガイドラインを推進および維持します。 統制されていない未分類情報の管理 (CUI) についてエグゼクティブオーダー13556に応答すると、 [NIST SP 800 – 171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)を公開していますが、*連邦情報システムおよび組織で*は、管理されていない未分類情報を保護しています。 CUI は、政府によって作成されたデジタルおよび物理の情報 (つまり、分類されていないものの代理となるエンティティ) として定義されており、機密保護を必要とします。

NIST SP 800 –171は2015年6月に最初に公開されており、脅威の進化に対応するために複数回更新されています。 このガイドでは、政府機関以外の情報システムおよび組織に対して、CUI への安全なアクセス、転送、保存を行う方法についてのガイドラインを提供します。この要件は、次の4つの主なカテゴリに分類されます。

- 管理と保護のためのコントロールとプロセス
- IT システムの監視と管理
- エンドユーザーのためのプラクティスと手順を明確にする
- 技術的および物理的なセキュリティ対策の実装

## <a name="microsoft-and-nist-sp-800171"></a>Microsoft および NIST SP 800 –171

Kratos Secureinfo および Coalfire を認定したサードパーティの評価組織では、Microsoft と提携して、*米国連邦情報システムおよび組織内の管理されていない未分類情報 (cui)* を、ユーザーがプロセスを処理するときに使用することを証明します。 [FedRAMP 要件の microsoft 実装](offering-fedramp.md)により、microsoft のスコープ内のクラウドサービスが、既に配置されているシステムとプラクティスを使用して、NIST SP 800 –171の要件を満たしていることを確認できます。

NIST SP 800 –171要件は、NIST SP 800-53 のサブセットで、FedRAMP が使用する標準です。 付録 D: NIST SP 800 –171は、自分の CUI セキュリティ要件を、NIST SP 800-53 の関連するセキュリティコントロールに直接マッピングします。これは、スコープ内のクラウドサービスが既に評価され、FedRAMP プログラムで承認されています。

米国政府機関を処理または保存するエンティティ (研究機関、コンサルティング会社、製造請負業者) は、NIST SP 800 –171の厳格な要件に準拠している必要があります。 この構成証明とは、microsoft が完全に準拠していることを保証するために CUI ワークロードの展開を検討しているお客様に対して、Microsoft のスコープを持つクラウドサービスが可能になります。 たとえば、情報システムの Microsoft クラウドサービスをスコープ内で使用することによって、「対象となる防衛情報」を処理、保存、または送信するすべての DoD 請負業者は、セキュリティに準拠する必要がある米国国防総省の各主要な条項を満たしています。NIST SP 800 –171の要件。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft スコープ内クラウドサービス

- [Azure Government](https://aka.ms/AzureCompliance)
- [Dynamics 365 米国政府](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 米国政府機関向けコミュニティクラウド (GCC)、Office 365 GCC 高、DoD](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>監査、レポート、および証明書

- [NIST SP 800 –171に準拠した Azure Government の構成証明](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a>実装方法

- [NIST sp 800 –171ブループリント](https://aka.ms/NIST-800-171-Blueprint): nist sp 800 –171に準拠する、Azure でのワークロードの実装のサポートを受けます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**NIST SP 800 –171を使用して、組織の Microsoft コンプライアンスを使用できますか?**

正解です。 Microsoft のお客様は、独自の FedRAMP の一部としての、独立したサードパーティの評価組織 (3PAO) からのレポートで説明されている監査された統制を使用できます。 これらのレポートは、Microsoft がスコープ内のクラウドサービスで実装した統制の有効性を証明します。 お客様は、CUI ワークロードが NIST SP 800 –171ガイドラインに準拠していることを確認する責任があります。

## <a name="resources"></a>リソース

- [Microsoft DoD 認定資格は NIST 800 –171の要件を満たしている](offering-DoD-DISA-L2-L4-L5.md)
- [NIST 800 –171準拠は Cybersecurity のドキュメントで始まります。](https://www.nist800171.com/)
- [Microsoft Cloud Services FedRAMP 承認](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [NIST 800-171 3.3 監査およびアカウンタビリティ (Office 365 GCC 高)](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [Microsoft および NIST Cybersecurity Framework](offering-nist-csf.md)
- [Microsoft Government クラウド](https://www.microsoft.com/enterprise/government)
- [Microsoft セキュリティセンターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>オファーリング backgrounder をダウンロードする

このオファーリングの backgrounder ドキュメントは必要ですか? [PDF](https://download.microsoft.com/download/9/8/F/98F1D966-FB62-4B58-B6F0-8F3DCCAC484A/NIST_SP-800-171-Compliance.pdf )をダウンロードします。
