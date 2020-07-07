---
title: GDPR に基づく Windows　通知向け データ プロセッサー サービス
description: Windows 用データプロセッササービスの個人データ漏洩の保護と、漏洩が発生した場合の Microsoft の対応、ユーザーへの通知方法について説明します。
keywords: Windows 版 Microsoft 365、Microsoft 365 ドキュメント、GDPR 用データプロセッササービス
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: bfadeae0f4f0b01197f58f0610d1040da3080922
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023633"
---
# <a name="data-processor-service-for-windows-breach-notification-under-the-gdpr"></a>GDPR 下の Windows　通知向け データ プロセッサー サービス

>[!NOTE]
>このトピックは、Windows プレビュー プログラムの参加者を対象としており、特定の使用条件に同意することが要求されています。 プログラムの詳細を確認し、使用条件に同意するには、[https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview) を参照してください。

Microsoft プロフェッショナル サービスでは、一般データ保護規則 (GDPR) の下での義務を重く受け止めています。 Windows 版 Microsoft データ プロセッサー サービスでは、データ漏洩を防ぐために、高度なセキュリティ対策を行っています。 これには、悪意のあるアクセスを事前に予想、回避、軽減する専門の脅威管理チームが含まれます。 内部のセキュリティ対策として、悪意のあるアクセスを検出し、保護するセキュリティプロセス、総合的な情報セキュリティおよびプライバシーポリシー、従業員のセキュリティとプライバシートレーニングなど、あらゆるセキュリティ対策を行います。 

Windows 版 Microsoft データ プロセッサー サービスは、「プライバシー バイ デザイン」および「プライバシー バイ デフォルト」の方法論を取り入れた必須の開発プロセスである[セキュリティ開発ライフサイクル](https://www.microsoft.com/sdl/)を始めとして、セキュリティに組み込んでいます。 Microsoft のセキュリティ戦略の指針は、"違反を想定" (防御の多層防御戦略の延長) です。 Windows 向けデータプロセッササービスのセキュリティ機能に常に挑戦することで、Microsoft は新たな脅威に対応していきます。 Windows セキュリティ用のデータプロセッササービス の詳細については、Windows 版データプロセッササービスが、セキュリティインシデント対応プロセスに従って、データ漏洩の可能性に対応していることをこちらの[リソース](https://www.microsoft.com/TrustCenter/Security/windows10-security)でご確認ください。 Windows セキュリティインシデント対応用のデータプロセッササービスは、検出、評価、診断、安定化、および終了という5段階のプロセスが実装されています。 セキュリティインシデント対応チームは、調査の進捗に合わせて、診断段階と安定段階と交互に対応します。 インシデント対応プロセスの概要は以下のとおりです： 

|**Stage**|**説明**|
| ------- | ------------- |
| ***1 — 検出*** | 潜在的なインシデントの最初の兆候です。 |
| ***2 — 評価*** | An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team. |
| ***3 — 診断*** | セキュリティ対応チームの専門家がテクニカルまたはフォレンシックな調査を行い、抑制、軽減、回避のストラテジーを特定します。 不正な目的を持つ個人や無許可の個人に顧客データが漏洩した可能性があるとセキュリティ チームが判断した場合には、カスタマー インシデント通知プロセスが並行して開始します。 |
| ***4 — 安定化と回復*** | The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed. |
| ***5 — クローズと事後分析*** | インシデント対応チームはインシデントの詳細を示す事後分析を作成します。その目的は、ポリシー、手順、プロセスを改訂してイベントの再発を防ぐことです。 |

Windows 版 Microsoft データ プロセッサー サービスで使われる検出プロセスの目的は、Windows 版 Microsoft データ プロセッサー サービスの機密保持性、整合性、可用性にとってリスクとなるイベントを検出することです。次のようなイベントにより、調査が開始する可能性があります。 いくつかのイベントによって、調査が開始されます。 

 - 内部監視および警告フレームワークによる自動システム警告。 これらの警告はマルウェア対策、侵入検知などのシグネチャ ベースのアラームとして出されることも、または予期されるアクティビティをプロファイル化して異常があれば警告を発するアルゴリズムを介して出されることもあります。
 - Microsoft Azure および Azure Government で実行されている Microsoft サービスからの第一者レポート。
 - セキュリティ脆弱性が secure@microsoft.com(mailto:secure@microsoft.com) 経由で [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) に報告されます。 MSRC は世界各地のパートナーやセキュリティ調査員と連携してセキュリティ インシデントの防止と Microsoft 製品のセキュリティ向上に努めています。
 - カスタマー サポート ポータルまたは Microsoft Azure および Azure Government 管理ポータルを介して提出される、(お客様の責任範囲内で生じるアクティビティではなく) Azure インフラストラクチャに帰属する疑わしいアクティビティを記述するお客様レポート。
 - セキュリティの[レッド チームとブルー チーム](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)のアクティビティ。 この戦略では、高度な技術を持つ攻撃担当の Microsoft のセキュリティ専門家からなるレッド チームが Azure の潜在的弱点を見つけ出して攻撃します。 セキュリティ対応担当のブルー チームはレッド チームのアクティビティを検知して防御する必要があります。 レッド チームとブルー チームの両方のアクティビティを使用して、セキュリティ インシデントが Azure のセキュリティ対応措置により効果的に管理されているかどうかが検証されます。 セキュリティ レッド チームとブルー チームのアクティビティは交戦規定の下に実施されるため、お客様のデータは確実に保護されます。
 - Azure サービス オペレーターによるエスカレーション。 Microsoft スタッフは潜在的なセキュリティ問題を特定してエスカレーションする訓練を受けています。

 ## <a name="data-processor-service-for-windows-data-breach-response"></a>Windows のデータ侵害対応の データ プロセッサー サービス 

 Microsoft はインシデントによる機能上の影響、回復可能性、情報に対する影響を判断することで、適切な優先度と重大度レベルを調査に対して割り当てます。 調査が進むにつれて、新たな発見や結論に応じて優先度と重大度が変更されることがあります。 お客様データに対する緊急または確定されたリスクを伴うセキュリティ イベントは重大度「高」として扱われ、24 時間体制でその解決に努めます。 Windows 版 Microsoft　データ プロセッサー サービスでは、インシデントによる情報への影響度を以下の侵害カテゴリに分類しています。 

| **カテゴリ**             | **定義**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***なし***               | 情報の抜き出し、変更、削除、その他の侵害は発生しなかった。 |
| ***プライバシー侵害***     | 納税者、従業員、受給者などの機密個人データにアクセスされたか、データが抜き出された。 |
| ***専有情報違反*** | 重要インフラ情報保護 (PCII) などの非機密の専有情報にアクセスされたか、情報が抜き出された。 |
| ***完全性損失***     | 機密情報または専有情報が改変または削除された。 |

セキュリティ対応チームは Windows 版 Microsoft データ プロセッサー サービスの セキュリティ エンジニアおよび SME と協力し、証拠から得られたデータに基づいてイベントを分類します。 セキュリティイベントは次のように分類されます。 

 - **誤検知**: 検出基準を満たしているが、正常な業務プロセスの一部であることが判明し、場合によってはフィルタリングする必要があるイベント。 サービス チームは誤検知の根本原因を特定し、体系的な方法でそれを扱います (必要に応じて検出ソースを利用したり微調整したりします)。 
 - **セキュリティ インシデント**: Microsoft の機器や設備に保管された何らかの顧客データまたはサポート データへの不正アクセス、またはそのような機器や設備への無許可アクセスが発生した結果、顧客データまたはサポート データが喪失、開示、または改変されたインシデント。 
 - **お客様報告対象セキュリティ インシデント (CRSI)**： Microsoft のシステム、機器、または設備に対する不正/無許可アクセスまたは使用の結果として、顧客データの開示、改変、または喪失が発生した。 
 - **プライバシーの侵害**: 個人データに関わるセキュリティ インシデントのサブタイプ。 処理方法は、セキュリティインシデントと同様です。 

 For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process. 

Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket. 

Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken. 

Microsoft では、データ侵害に関する社内向けの事後分析も行います。 この検証の一環として、対応および運用手順が充分であったかどうかを評価し、セキュリティインシデント対応の SOP または関連するプロセスに必要な更新プログラムを特定し、実装します。 データ漏洩の内部事後分析は、非常に機密性の高い社外秘の記録であり、顧客には公開されません。 ただし、事後分析は要約され、他の顧客のイベント通知に含まれる場合があります。 これらのレポートは、Windows 版 Microsoft データ プロセッサー サービス の監査サイクルの一部として外部監査者に提供されます。 

## <a name="customer-notice"></a>お客様へのお知らせ

Microsoft データ プロセッサー サービス は、必要に応じてデータ漏洩をお客様と規制当局に通知します。 Microsoft は、Windows 版 Microsoft データ プロセッサー サービスの運用において、内部の区画化に依存しています。 データフローログも強化されています。 この設計の利点として、ほとんどのインシデントを特定の顧客に限定できます。 ユーザーのデータが漏洩された場合に、正確かつ実用的な通知をユーザーに提供することが目標です。 

CRSPI の宣言後、通知プロセスは、出来るだけ迅速に行われますが、その一方で、リスクに対しても迅速に対応します。 通常、インシデントの調査が行われているときに、通知を作成するプロセスが実行されます。 次の場合を除き、お客様への通知は、漏洩の発生を認識してから 72 時間以内に行われます。 

 - Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate. 
 - Microsoft の法務部である Corporate External and Legal Affairs (CELA) およびエグゼクティブ インシデント マネージャーによって精査される、他の異常な状況または極端な状況。 

 Windows 版 Microsoft データ プロセッサー サービス は、内部調査を行ってエンド ユーザーへの責務を果たせるよう、詳細な情報をお客様に提供すると同時に、通知プロセスを不必要に遅らせないようにします。 

個人データの侵害についての通知は、メールなど Microsoft が選択した方法で、お客様に送信されます。 データが侵害通知は、Azure Security Center で提供されているセキュリティ連絡先リスト上の連絡先に配信されます。このリストは、[実装ガイドライン](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)に従って構成できます。 連絡先情報が Azure Security Center に提供されていない場合、Azure サブスクリプションの 1 人または複数の管理者に通知が送信されます。 通知が正常に配信されるようにするには、該当する各サブスクリプションおよびオンライン サービス ポータルに関する管理連絡先情報が正しいことを確認する必要があります。

さらに Windows 版 Microsoft データ プロセッサー サービスは、カスタマー サービス (CSS) などの追加的な Microsoft スタッフ、およびお客様のアカウント マネージャー (AM) やテクニカル アカウント マネージャー (TAM) に通知するかを選択する場合があります。 多くの場合、これらのスタッフはお客様と緊密な関係にあり、迅速な修復をサポートさせていただきます。 

マイクロソフトが個人データの侵害を検出して対応する方法の詳細については、Service Trust Portal の [GDPR の下でのデータ侵害の通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)を参照してください。