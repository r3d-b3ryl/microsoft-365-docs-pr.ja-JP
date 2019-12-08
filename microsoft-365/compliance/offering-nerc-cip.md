---
title: '北米電力信頼度協議会 (North American Electric Reliability Corporation: NERC)'
description: Azure および Azure Government は、NERC の CIP 基準の対象となる特定のワークロードをクラウドで展開する登録エンティティに適しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: ceb87ace9d4ed832ea23ea7cddaf7e73ce0a17cb
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859363"
---
# <a name="north-american-electric-reliability-corporation-nerc"></a>北米電力信頼度協議会 (North American Electric Reliability Corporation: NERC)

## <a name="about-the-nerc"></a>NERC について

[北米電力信頼度協議会](https://www.nerc.com/) (North American Electric Reliability Corporation: NERC) は、北米の基幹系統の信頼性を確保することを目的とした非営利の規制当局です。 NERC は、米国連邦エネルギー規制委員会 (US Federal Energy Regulatory Commission: FERC) およびカナダの政府当局による監督を受けます。 2006 年に、FERC は 2005 年エネルギー政策法 (Energy Policy Act of 2005) (US Public Law 109-58) に基づき NERC に対して電力信頼度機関 (Electric Reliability Organization: ERO) の指定を付与しました。 NERC は、NERC [重要インフラ保護 (Critical Infrastructure Protection: CIP) 基準](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)として知られる信頼性基準の整備と執行を行います。

## <a name="microsoft-and-the-nerc-cip-standard"></a>Microsoft と NERC CIP 基準

北米電力信頼度協議会 (North American Electric Reliability Corporation: NERC) は、北米の基幹系統の信頼性を確保することを目的とした非営利の規制当局です。 NERC は、米国連邦エネルギー規制委員会 (US Federal Energy Regulatory Commission: FERC) およびカナダの政府当局による監督を受けます。 2006 年に、FERC は 2005 年エネルギー政策法 (Energy Policy Act of 2005) (US Public Law 109-58) に基づき NERC に対して電力信頼度機関 (Electric Reliability Organization: ERO) の指定を付与しました。 NERC は、NERC [重要インフラ保護 (Critical Infrastructure Protection: CIP) 基準](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)として知られる信頼性基準の整備と執行を行います。

基幹系統のすべての所有者、運用者、および利用者は [NERC CIP 基準に準拠](https://www.nerc.com/pa/comp/Pages/default.aspx)する必要があります。 これらのエンティティは、NERC への登録が義務付けられています。 クラウド サービスプ ロバイダーおよびサードパーティ ベンダーは CIP 基準の対象ではありませんが、この基準には、[登録エンティティ](https://www.nerc.com/pa/comp/Pages/Registration.aspx)が基幹系統 (Bulk Electric System: BES) の運用業者を使用する場合に検討すべき目標が含まれています。 基幹系統を運用する Microsoft のお客様は、組織で NERC CIP 基準への準拠を確保することに対して、全責任を負います。 Microsoft Azure と Microsoft Azure Government のいずれも、BES または BES サイバー資産ではありません。

現在の [CIP 基準](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf)および NERC [用語集](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)において NERC が述べているように、BES サイバー資産は BES の監視および制御においてリアルタイム機能を実行し、障害の発生から 15 分以内に BES の運用の信頼性に影響を与えます。 クラウド コンピューティングの BES サイバー資産および保護されたサイバー資産に適切に対応するには、NERC CIP 基準の現在の定義を[改訂する必要があります](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx)。 しかし、BES サイバー システム情報 (BCSI) とう大分類を含め、CIP の対象となるデータを取り扱い、15 分ルールの適用外のワークロードが多くあります。

Azure および Azure Government は、BCSI ワークロードなど、NERC CIP 基準の対象となる特定のワークロードを展開する登録エンティティに適しています。 Microsoft では、NERC CIP への準拠義務を持つデータおよびワークロードを Azure または Azure Government で展開することを希望する登録エンティティに向けて、以下のドキュメントを提供しています。

- 『[NERC CIP 基準とクラウドコンピューティング (NERC CIP Standards and Cloud Computing)](https://aka.ms/AzureNERC)』は、FedRAMP などのクラウド サービス プロバイダーに適用される、確立されたサードパーティ監査に基づいて NERC CIP 要件へ準拠するための考慮事項を説明するホワイト ペーパーです。 クラウド運用担当者の背景スクリーニングの他、登録エンティティが知る必要がある論理的分離やマルチテナントに関するよくある質問への回答が網羅されています。 オンプレミスとクラウド展開におけるセキュリティに関する考慮事項も説明されています。
- 『[NERC 監査用クラウド実装ガイド (Cloud Implementation Guide for NERC Audits)](https://aka.ms/AzureNERCGuide)』は、NERC CIP 基準の現行の要件と FedRAMP の元となっている [NIST SP 800-53 Rev 4](https://nvd.nist.gov/800-53/Rev4) との間でのコントロール マッピングを提供するガイダンス ドキュメントです。 クラウドに展開されている資産における CIP のコンプライアンス要件への登録エンティティの対応を支援するための技術的なハウツー ガイダンスとして作られています。 Azure 制御によるNERC CIP 要件への対応方法を説明する事前入力された[信頼性基準監査ワークシート (Reliability Standard Audit Worksheets: RSAWs)](https://www.nerc.com/pa/comp/Pages/Reliability-Standard-Audit-Worksheets-\(RSAWs\).aspx) に関する説明および、所有する制御を Azure サービスで実装する方法に関する登録エンティティ向けガイダンスが含まれています。

NERC ERO エンタープライズは、[実践ガイド](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf)『コンプライアンス監視執行プログラム (Compliance Monitoring and Enforcement Program: CMEP) 』を[公開しました](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx)。これは、指定された BCSI の保存場所へのアクセスおよび登録エンティティが実装したすべてのアクセス制御に関するエンティティにおける承認プロセスを評価する際のガイダンスを ERO エンタープライズ CMEP 担当者に提供するものです。 NERC はまた、NERC CIP-004-6 基準および CIP-011-2 基準に関連する Azure 制御の実装の詳細および FedRAMP 監査の証拠のうち、BCSI に該当するものについてレビューを行いました。 ERO が発行する実践ガイドおよび登録エンティティにおけるデータの暗号化を確認するためのレビューが行われた FedRAMP 制御に基づき、登録エンティティが BCSI および関連ワークロードをクラウドで展開するのに追加のガイダンスまたは説明は必要ありません。 ただし、登録エンティティは、各エンティティにおける実情や状況に応じて、NERC CIP 基準への準拠に対して最終的な責任を負います。 登録エンティティは、Azure および Azure Government における BCSI の暗号化暗号キーの管理を含む、BCSI 保存場所への電子アクセスを承認するのに使用した各自のプロセスおよび証拠を記録化するために、『[NERC 監査用クラウド実装ガイド](https://aka.ms/AzureNERCGuide)』を確認する必要があります。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure および Azure Government](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

Microsoft は、P-ATO および ATO を維持するために、Microsoft のクラウド サービスを再認定する必要があります。 そのため、Microsoft は Microsoft のセキュリティ制御を継続的に監視および評価して、準拠性の維持を示す必要があります。

- [Microsoft クラウド サービス承認](https://marketplace.fedramp.gov/?sort=productName&productNameSearch=azure#/product/azure-government)
- [Microsoft FedRAMP 監査レポート](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="how-to-implement"></a>実装方法

### <a name="nerc-cip-standards-and-cloud-computing"></a>NERC CIP 基準とクラウド コンピューティング

NERC CIP 基準の対象となるワークロードでのクラウドの導入を検討している登録エンティティ向けに、コンプライアンスの説明をしています。

[詳細情報](https://aka.ms/AzureNERC)

### <a name="cloud-implementation-guide-for-nerc-audits"></a>NERC 監査用クラウド実装ガイド

登録エンティティ向けの、Azure または Azure Government に展開されている資産に対する NERC の監査に関する技術ガイダンスです。 

[詳細情報](https://aka.ms/AzureNERCGuide)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**NERC CIP 基準への準拠は、誰の責任ですか?**

基幹系統のすべての所有者、運用者、および利用者は [NERC CIP 基準に準拠](https://www.nerc.com/pa/comp/Pages/default.aspx)する必要があります。 これらのエンティティは、NERC への登録が義務付けられています。 クラウド サービスプ ロバイダーおよびサードパーティ ベンダーは CIP 基準の対象ではありませんが、この基準には、[登録エンティティ](https://www.nerc.com/pa/comp/Pages/Registration.aspx)が基幹系統 (Bulk Electric System: BES) の運用業者を使用する場合に検討すべき目標が含まれています。 基幹系統を運用する Microsoft のお客様は、組織で NERC CIP 基準への準拠を確保することに対して、全責任を負います。 Azure と Azure Government のいずれも、BES または BES サイバー資産ではありません。

NERC CIP 基準の対象のワークロードへの Azure および Azure Government の適合性を評価するには、登録エンティティは各エンティティのコンプライアンス責任者や NERC 監査員と協議する必要があります。 登録エンティティは、クラウドで展開されているアセットのプロセスおよび証拠の記録化について、『[NERC 監査用クラウド実装ガイド](https://aka.ms/AzureNERCGuide)』を確認する必要があります。

**登録エンティティはどのようなワークロードを Azure および Azure Government で展開できますか?**

[NERC CIP 基準](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf)および[用語集](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)では、BES サイバー資産は BES の監視および制御においてリアルタイム機能を実行し、障害が発生した場合は 15 分以内に BES の運用の信頼性に影響を与えるとしています。 クラウド コンピューティングの BES サイバー資産および保護されたサイバー資産に適切に対応するには、NERC CIP 基準の現在の定義を[改訂する必要があります](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx)。 しかし、BES サイバー システム情報 (BCSI) とう大分類を含め、CIP の対象となるデータを取り扱い、15 分ルールの適用外のワークロードが多くあります。

NERC ERO エンタープライズは、[実践ガイド](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf)『コンプライアンス監視執行プログラム (Compliance Monitoring and Enforcement Program: CMEP) 』を[公開しました](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx)。これは、指定された BCSI の保存場所へのアクセスおよび登録エンティティが実装したすべてのアクセス制御に関するエンティティにおける承認プロセスを評価する際のガイダンスを ERO エンタープライズ CMEP 担当者に提供するものです。 NERC はまた、NERC CIP-004-6 基準および CIP-011-2 基準に関連する Azure 制御の実装の詳細および FedRAMP 監査の証拠のうち、BCSI に該当するものについてレビューを行いました。 ERO が発行する実践ガイドおよび登録エンティティにおけるデータの暗号化を確認するためのレビューが行われた FedRAMP 制御に基づき、登録エンティティが BCSI および関連ワークロードをクラウドで展開するのに追加のガイダンスまたは説明は必要ありません。 ただし、登録エンティティは、各エンティティにおける実情や状況に応じて、NERC CIP 基準への準拠に対して最終的な責任を負います。

## <a name="resources"></a>リソース

- [NERC コンプライアンス ガイダンス](https://www.nerc.com/pa/comp/guidance/)
- [NERC コンプライアンスと執行](https://www.nerc.com/pa/comp/Pages/default.aspx)
- [NERC 組織と認定](https://www.nerc.com/pa/comp/Pages/Registration.aspx)
- [Microsoft と FedRAMP](offering-fedramp.md)
- Microsoft と CSA STAR [準拠証明](offering-csa-star-attestation.md)および[認定](offering-csa-star-certification.md)
- [Microsoft と SOC 2 レポート](offering-soc.md)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
