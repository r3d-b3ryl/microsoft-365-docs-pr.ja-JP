---
title: GDRP の下での Azure および Dynamics 365 の侵害通知
description: Azure および Dynamics 365 における個人データの侵害に対する保護および侵害発生時の Microsoft による対応とユーザーへの通知。
keywords: Azure、Microsoft 365、Dynamics 365、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0cdd3a2d8e158800cef534a1488df0f25e3d232f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920263"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>GDRP の下での Azure および Dynamics 365 の侵害通知

Microsoft Azure では、一般データ保護規則 (GDPR) の下での責務を真剣に受け止めており、データ侵害から保護するための広範なセキュリティ対策を講じています。これには物理的/論理的セキュリティ コントロール、自動化されたセキュリティ プロセス、包括的な情報セキュリティ/プライバシー ポリシー、すべての人員を対象とするセキュリティ/プライバシー トレーニングが含まれます。

Microsoft Azure では、「プライバシー バイ デザイン」および「プライバシー バイ デフォルト」の方法論を取り入れた必須の開発プロセスである 「[セキュリティ開発ライフサイクル](https://www.microsoft.com/sdl/)」 を始めとして、セキュリティ機能を一から構築しています。Microsoft のセキュリティ戦略の中心原則は、高度な防御戦略の概念を拡張した「侵害の想定」です。Microsoft は Azure のセキュリティ機能を絶えず自己吟味することで、新たな脅威の一歩先を進むことができます。Azure のセキュリティについて詳しくは、「[リソース](https://www.microsoft.com/trustcenter/security/azure-security)」 をご覧ください。

Microsoft では Microsoft Azure に対する攻撃の影響を軽減するためのインシデント対応サービスを全世界で 24 時間 365 日体制で実施しています。([ISO/IEC 27018](offering-iso-27018.md) などの) 複数のセキュリティ/コンプライアンス監査で実証されているように、Microsoft は無許可アクセスを防ぐための厳格な運用とプロセスを自社のデータ センターで実施しています。これには毎日 24 時間の常時モニタリング、トレーニングを受けたセキュリティ担当者、スマート カード、バイオメトリック コントロールなどが含まれます。

## <a name="detection-of-potential-breaches"></a>潜在的な侵害の検出

Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.

Microsoft does not monitor for or respond to security incidents within the customer's realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. また、Microsoft Azure は、 (例えば[Azure Defender](https://azure.microsoft.com/services/security-center/)など) お客様がセキュリティ インシデント 対応の開発と管理に活用できる、さまざまなサービスも提供します。

Microsoft Azure インシデント管理計画に含まれるセキュリティ インシデント対応プロセスに従い、Azure は潜在的なデータ侵害に対処します。Azure のセキュリティ インシデント対応は 5 段階のプロセス (検出、評価、診断、安定化、クローズ) で実装されています。セキュリティ インシデント対応チームは、調査の進捗に合わせて診断ステージと安定化ステージの間で切り替えをすることがあります。セキュリティ インシデント対応プロセスの概要は次のとおりです:

|**Stage**|**説明**|
| ------- | ------------- |
| **_1 — 検出_* _ | 潜在的なインシデントの最初の兆候です。 |
| _*_2 — 評価_*_ | 待機中のインシデント対応チーム メンバーがイベントの影響度と重大度を評価します。証拠に基づき、この評価をセキュリティ対応チームにエスカレートするかどうか判断されます。 |
| _*_3 — 診断_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 — 安定化と回復_*_ | インシデント対応チームは問題を軽減するための回復計画を作成します。リスク封じ込めステップ (影響を受けたシステムの隔離など) を診断と並行してただちに開始する場合があります。当面のリスクが過ぎ去った後の長期的な軽減計画を立てる場合もあります。 |
| _*_5 — クローズと事後分析_*_ | インシデント対応チームはインシデントの詳細を示す事後分析を作成します。その目的は、ポリシー、手順、プロセスを改訂してイベントの再発を防ぐことです。 |

ホワイトペーパー「[クラウドにおける Microsoft Azure のセキュリティ対応](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678)」では、Azure 内で発生するセキュリティ インシデントをどのように Microsoft が調査、管理、対応するかを詳しく述べています。

Microsoft Azure で使われる検出プロセスの目的は、Azure サービスの機密保持性、整合性、可用性にとってリスクとなるイベントを検出することです。次のようなイベントにより、調査が開始する可能性があります:

- Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
- Microsoft Azure および Azure Government で実行されている Microsoft サービスからの第一者レポート。
- Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com](mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
- [カスタマー サポート ポータル](https://www.windowsazure.com/support/contact/)または Microsoft Azure および Azure Government 管理ポータルを介して提出される、(お客様の責任範囲内で生じるアクティビティではなく) Azure インフラストラクチャに帰属する疑わしいアクティビティを記述するお客様レポート。
- Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team's activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
- Azure サービス オペレーターによるエスカレーション。Microsoft スタッフは潜在的なセキュリティ問題を見分けてエスカレートできるように訓練を受けています。

## <a name="azures-data-breach-response"></a>Azure のデータ侵害対応措置

Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. 

Microsoft Azure では、情報に対するインシデントの影響度を以下の侵害カテゴリに分類します:

| _ *カテゴリ**             | **定義**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_なし_* _               | 情報の抜き出し、変更、削除、その他の侵害は発生しなかった。                                                      |
| _*_プライバシー侵害_*_     | 納税者、従業員、受給者などの機密個人データにアクセスされたか、データが抜き出された。                                |
| _*_専有情報違反_*_ | 保護された重要インフラ情報 (PCII) などの非機密の専有情報にアクセスされたか、情報が抜き出された。 |
| _*_完全性損失_*_     | 機密情報または専有情報が改変または削除された。                                                                     |

セキュリティ対応チームは Microsoft Azure セキュリティ エンジニアおよび SME と協力し、証拠から得られたデータに基づいてイベントを分類します。セキュリティ イベントは次のように分類されます:

- _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team identifies the root cause for false positives and will address them in a systematic way using detection sources and fine-tuning them as needed.
- **セキュリティ インシデント** : Microsoft の機器や設備に保管された何らかの顧客データまたはサポート データへの不正アクセス、またはそのような機器や設備への無許可アクセスが発生した結果、顧客データまたはサポート データが喪失、開示、または改変されたインシデント。
- **お客様報告対象セキュリティ/プライバシー インシデント (CRSPI)** : Microsoft のシステム、機器、または設備に対する不正/無許可アクセスまたはその使用によってもたらされる顧客データの開示、改変、または喪失。
- **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.

For a CRSPI to be declared, Microsoft must determine that unauthorized access to customer data has or has likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSPI after the conclusion of the Diagnose stage of a security incident. However, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.

調査期間中、セキュリティ対応チームは全世界の法律顧問と協力し、法的義務およびお客様への責任に基づいて捜査を確実に行います。また、さまざまな運用環境でシステム データや顧客データの閲覧と処理がかなり制限されます。該当するインシデント チケットに記録されたインシデント管理者による明確な書面の同意なしで、機密データおよび顧客データが運用環境から外部に移送されることはありません。

Microsoft はお客様にとってのリスクと業務上のリスクが適切に抑止され、是正措置が実施されていることを検証します。必要に応じて、イベントに関連する当座のセキュリティ リスクを解決するための緊急軽減ステップを実施します。

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure's routine audit cycle.

## <a name="customer-notification"></a>お客様への通知

Microsoft Azure では必要に応じてデータ侵害についてお客様や規制機関に通知いたします。Microsoft では Azure の運用において社内の本格的な区画化を採用しています。またデータ フロー ログも堅牢です。このような設計により、ほとんどのインシデントの範囲を特定のお客様層に限定できます。データが侵害されたときに、影響を受けたお客様に対して正確かつアクション可能な通知をタイムリーに提供することを目標としています。

After the declaration of a CRSPI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* in the following circumstances:

- Microsoft believes that the act of performing a notification increases the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.
- Microsoft の法務部である Corporate External and Legal Affairs (CELA) およびエグゼクティブ インシデント マネージャーによって精査される、他の通常と異なる状況または極端な状況。
- The 72-hour timeline may leave some incident details available. These are provided to customers and regulatory authorities as the investigation proceeds.

Microsoft Azure は、お客様が内部調査を行ってエンド ユーザーへの責務を果たせるよう、詳細な情報をお客様に提供すると同時に、通知プロセスを不必要に遅らせないようにします。

個人データ侵害の通知は、Microsoft が選択する任意の方法 (電子メールなど) でお客様に送られます。データ侵害の通知は Azure Defender 内にあるセキュリティ連絡先一覧に向けて配信され、[実装ガイドライン](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)に従ってこれを構成できます。連絡先情報が Azure Defender に提供されていない場合、Azure サブスクリプションの 1 人以上の管理者に通知が送られます。通知を確実に受け取るには、お客様に該当する各サブスクリプションおよびオンライン サービス ポータルで管理者の連絡先情報を正しく指定していただく必要があります。

さらに Microsoft Azure または Azure Government チームは、カスタマー サービス (CSS) などの追加の Microsoft スタッフ、およびお客様のアカウント マネージャー (AM) やテクニカル アカウント マネージャー (TAM) にも通知することを選択する場合があります。 多くの場合、これらのスタッフはお客様と緊密な関係にあり、迅速な修復をサポートさせていただきます。

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 に組み込まれているセキュリティ機能

Microsoft Dynamics 365 では、クラウド サービス インフラストラクチャと組み込みセキュリティ機能を利用したセキュリティ対策およびセキュリティ メカニズムにより、データの安全を確保します。さらに、Dynamics 365 はデータの完全性とプライバシーを確保した効果的なデータ アクセスおよびコラボレーションを、次の分野において提供します: [セキュア ID、データ保護、ロール ベースのセキュリティと脅威の管理](https://www.microsoft.com/trustcenter/security/dynamics365-security)。

Microsoft Dynamics 365 のサービスは、データ侵害プロセスに対するセキュリティに関して、1 つまたは複数の Microsoft Azure サービス チームが実行する技術的および組織的対策に準じます。 したがって、ここに記載する "Microsoft Azure データ侵害" 通知ドキュメント上の情報は、Microsoft Dynamics 365 のものと類似しています。

## <a name="learn-more"></a>詳細情報

[Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
