---
title: Azure と GDPR の下での違反の通知
description: Azure による個人データ漏洩からの保護と、違反が発生した場合の Microsoft による対応とユーザーへの通知
keywords: Azure、Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 8b2a0bd52054a3228ba8c9536e6db552735b1f33
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869410"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a><span data-ttu-id="b8d1d-104">Azure と GDPR の下での違反の通知</span><span class="sxs-lookup"><span data-stu-id="b8d1d-104">Azure and Breach Notification Under the GDPR</span></span>

<span data-ttu-id="b8d1d-p101">Microsoft Azure では、一般データ保護規則 (GDPR) の下での責務を真剣に受け止めており、データ侵害から保護するための広範なセキュリティ対策を講じています。これには物理的/論理的セキュリティ コントロール、自動化されたセキュリティ プロセス、包括的な情報セキュリティ/プライバシー ポリシー、すべての人員を対象とするセキュリティ/プライバシー トレーニングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p101">Microsoft Azure takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft Azure takes extensive security measures to protect against data breaches. These include both physical and logical security controls, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel.</span></span>

<span data-ttu-id="b8d1d-p102">Microsoft Azure では、「プライバシー バイ デザイン」および「プライバシー バイ デフォルト」の方法論を取り入れた必須の開発プロセスである[セキュリティ開発ライフサイクル](https://www.microsoft.com/sdl/)を始めとして、組み込みセキュリティ機能を 1 つずつ積み重ねています。Microsoft のセキュリティ戦略の中心原則は、多層防御の概念を拡張した「侵害の想定」です。Microsoft は Azure のセキュリティ機能を絶えず自己吟味することで、新たな脅威の一歩先を進むことができます。Azure のセキュリティについて詳しくは、[リソース](https://www.microsoft.com/trustcenter/security/azure-security)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p102">Security is built into Microsoft Azure from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft’s security strategy is to “assume breach,” which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of Azure, Microsoft can stay ahead of emerging threats. For more information on Azure security, please review these [resources](https://www.microsoft.com/trustcenter/security/azure-security).</span></span>

<span data-ttu-id="b8d1d-p103">Microsoft では Microsoft Azure に対する攻撃の影響を軽減するためのインシデント対応サービスを全世界で 24 時間 365 日体制で実施しています。([ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018) などの) 複数のセキュリティ/コンプライアンス監査で実証されているように、Microsoft は無許可アクセスを防ぐための厳格な運用とプロセスを自社のデータ センターで実施しています。これには毎日 24 時間の常時モニタリング、トレーニングを受けたセキュリティ担当者、スマート カード、バイオメトリック コントロールなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p103">Microsoft has a global, 24x7 incident response service that works to mitigate the effects of attacks against Microsoft Azure. Attested by multiple security and compliance audits (e.g. [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)), Microsoft employs rigorous operations and processes at its data centers to prevent unauthorized access, including 24x7 video monitoring, trained security personnel, smart cards, and biometric controls.</span></span>

#### <a name="detection-of-potential-breaches"></a><span data-ttu-id="b8d1d-114">潜在的な侵害の検出</span><span class="sxs-lookup"><span data-stu-id="b8d1d-114">Detection of Potential Breaches</span></span>
-------------------------------

<span data-ttu-id="b8d1d-p104">最新型のクラウド コンピューティングの性質上、お客様のクラウド環境で発生するすべてのデータ侵害に Microsoft Azure サービスが関与しているわけではありません。Microsoft では Azure サービスに責任共有モデルを導入することで、セキュリティ上および運用上の責任範囲を定義しています。クラウド サービス プロバイダーとお客様の双方がクラウド セキュリティの特定部分の責務を負っているので、クラウド サービスのセキュリティについて考慮する際には責任共有が特に重要です。 </span><span class="sxs-lookup"><span data-stu-id="b8d1d-p104">Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is particularly important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.</span></span>

<span data-ttu-id="b8d1d-p105">Microsoft は、お客様の責任領域内で発生するセキュリティ インシデントの監視や対応措置を行うことはありません。特定のお客様のみで発生した侵害は Azure セキュリティ インシデントとして扱われず、お客様のテナントでその対応策を講じていただく必要があります。お客様のインシデント対応では、適切なサービス契約の下で Microsoft Azure [カスタマー サポート](https://azure.microsoft.com/support/options/)の支援をご利用いただける場合があります。また、お客様は Microsoft Azure のさまざまなサービス ([Azure Security Center](https://azure.microsoft.com/services/security-center/) など) をご利用いただくことで、セキュリティ インシデント対応を開発/管理できます。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p105">Microsoft does not monitor for or respond to security incidents within the customer’s realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure also offers various services (e.g., [Azure Security Center](https://azure.microsoft.com/services/security-center/)) that customers can utilize for developing and managing security incident response.</span></span>

<span data-ttu-id="b8d1d-p106">Microsoft Azure インシデント管理計画に含まれるセキュリティ インシデント対応プロセスに従い、Azure は潜在的なデータ侵害に対処します。Azure のセキュリティ インシデント対応は 5 段階のプロセス (検出、評価、診断、安定化、クローズ) で実装されています。セキュリティ インシデント対応チームは、調査の進捗に合わせて診断ステージと安定化ステージの間で交代することがあります。セキュリティ インシデント対応プロセスの概要は次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p106">Azure responds to a potential data breach according to the security incident response process, which is a subset of the Microsoft Azure incident management plan. Azure’s security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="b8d1d-126">ステージ</span><span class="sxs-lookup"><span data-stu-id="b8d1d-126">Stage</span></span></th>
<th align="left"><span data-ttu-id="b8d1d-127">説明</span><span class="sxs-lookup"><span data-stu-id="b8d1d-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="b8d1d-128">1</span><span class="sxs-lookup"><span data-stu-id="b8d1d-128">1</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-129">検出する</span><span class="sxs-lookup"><span data-stu-id="b8d1d-129">Detect</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-130">インシデントの可能性が最初に示唆されます。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-130">First indication of a potential incident.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b8d1d-131">2</span><span class="sxs-lookup"><span data-stu-id="b8d1d-131">2</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-132">評価する</span><span class="sxs-lookup"><span data-stu-id="b8d1d-132">Assess</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-p107">待機中のインシデント対応チーム メンバーがイベントの影響度と重大度を評価します。証拠に基づき、この評価をセキュリティ対応チームにエスカレートするかどうか判断されます。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p107">An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b8d1d-135">3</span><span class="sxs-lookup"><span data-stu-id="b8d1d-135">3</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-136">診断する</span><span class="sxs-lookup"><span data-stu-id="b8d1d-136">Diagnose</span></span></td>
<td align="left"><p><span data-ttu-id="b8d1d-137">セキュリティ対応チームの専門家がテクニカルまたはフォレンシックな調査を行い、抑制、軽減、回避のストラテジーを特定します。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-137">Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies.</span></span></p>
<p><span data-ttu-id="b8d1d-138">不正な目的を持つ個人や無許可の個人に顧客データが漏洩した可能性があるとセキュリティ チームが判断した場合には、カスタマー インシデント通知プロセスが並行して開始します。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-138">If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b8d1d-139">4</span><span class="sxs-lookup"><span data-stu-id="b8d1d-139">4</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-140">安定化して回復する</span><span class="sxs-lookup"><span data-stu-id="b8d1d-140">Stabilize and Recover</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-p108">インシデント対応チームは問題を軽減するための回復計画を作成します。リスク抑制ステップ (影響を受けたシステムの隔離など) が診断と並行してただちに開始する場合があります。当面のリスクが過ぎ去った後の長期的な軽減計画を立てる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p108">The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b8d1d-144">5</span><span class="sxs-lookup"><span data-stu-id="b8d1d-144">5</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-145">クローズして事後分析する</span><span class="sxs-lookup"><span data-stu-id="b8d1d-145">Close and Post-Mortem</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-146">インシデント対応チームはインシデントの詳細を示す事後分析を作成します。その目的は、ポリシー、手順、プロセスを改訂してイベントの再発を防ぐことです。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-146">The incident response team creates a post-mortem that outlines the details of the incident, with the intention to revise policies, procedures, and processes to prevent a reoccurrence of the event.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b8d1d-147">ホワイトペーパー「[クラウドにおける Microsoft Azure のセキュリティ対応](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678)」では、Azure 内で発生するセキュリティ インシデントをどのように Microsoft が調査、管理、対応するかを詳しく述べています。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-147">The [Microsoft Azure Security Response in the Cloud](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) white paper further details how Microsoft investigates, manages, and responds to security incidents within Azure.</span></span>

<span data-ttu-id="b8d1d-p109">Microsoft Azure で使われる検出プロセスの目的は、Azure サービスの機密保持性、整合性、可用性にとってリスクとなるイベントを検出することです。次のようなイベントにより、調査が開始する可能性があります:</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p109">The detection processes used by Microsoft Azure are designed to discover events that risk the confidentiality, integrity, and availability of Azure services. Several events can trigger an investigation:</span></span>

-   <span data-ttu-id="b8d1d-p110">内部モニタリング/アラート フレームワークを介してシステムが自動的に警告を発したとき。これらの警告は侵入検知、マルウェア対策などのシグネチャ ベースのアラームとして出されることも、または予期されるアクティビティをプロファイル化して異常があればアラートを発するアルゴリズムを介して出されることもあります。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p110">Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as antimalware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.</span></span>

-   <span data-ttu-id="b8d1d-152">Microsoft Azure および Azure Government で実行される Microsoft サービスからの第一者レポート。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-152">First party reports from Microsoft Services running on Microsoft Azure and Azure Government.</span></span>

-   <span data-ttu-id="b8d1d-p111">セキュリティ脆弱性が <secure@microsoft.com> を介して [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) に報告されたとき。MSRC は全世界のパートナーやセキュリティ研究者と協力してセキュリティ インシデントの防止と Microsoft 製品のセキュリティ向上に努めています。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p111">Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via <secure@microsoft.com>. MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.</span></span>

-   <span data-ttu-id="b8d1d-155">[カスタマー サポート ポータル](http://www.windowsazure.com/support/contact/)または Microsoft Azure および Azure Government 管理ポータルを介して提出される、(お客様の責任範囲内で生じるアクティビティではなく) Azure インフラストラクチャに帰属する疑わしいアクティビティを記述するお客様レポート。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-155">Customer reports via the [Customer Support Portal](http://www.windowsazure.com/support/contact/) or Microsoft Azure and Azure Government Management Portal, that describe suspicious activity attributed to the Azure infrastructure (as opposed to activity occurring within the customer’s scope of responsibility).</span></span>

-   <span data-ttu-id="b8d1d-p112">セキュリティ [レッド チームとブルー チーム](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)のアクティビティ。このストラテジーでは、高度な技術を持つ攻撃担当の Microsoft セキュリティ専門家からなるレッド チームが Azure の潜在的弱点を見つけ出して攻撃します。セキュリティ対応担当のブルー チームはレッド チームのアクティビティを検知して防御する必要があります。レッド チームとブルー チームの両方のアクションにより、Azure セキュリティ対応措置でセキュリティ インシデントを効果的に管理できることを検証します。セキュリティ レッド チームとブルー チームのアクティビティは特定のルールの下で実施され、お客様データの保護に役立っています。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p112">Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly-skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.</span></span>

-   <span data-ttu-id="b8d1d-p113">Azure サービス オペレーターによるエスカレーション。Microsoft スタッフは潜在的なセキュリティ問題を見分けてエスカレートできるように訓練を受けています。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p113">Escalations by operators of Azure Services. Microsoft employees are trained to identify and escalate potential security issues.</span></span>

#### <a name="azures-data-breach-response"></a><span data-ttu-id="b8d1d-163">Azure のデータ侵害対応</span><span class="sxs-lookup"><span data-stu-id="b8d1d-163">Azure’s Data Breach Response</span></span>
----------------------------

<span data-ttu-id="b8d1d-p114">Microsoft はインシデントによる機能上の影響、回復可能性、情報に対する影響を判断することで、適切な優先度/重大度レベルを調査に対して割り当てます。調査が進むにつれて、新たな発見や結論に応じて優先度と重大度が変更されることがあります。お客様データに対する緊急または確実なリスクをもたらすセキュリティ イベントは重大度「高」として扱われ、24 時間体制でその解決に努めます。Microsoft Azure では、情報に対するインシデント影響度を次のような違反カテゴリに分類しています:</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p114">Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft Azure categorizes the information impact of the incident into the following breach categories:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b8d1d-168">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="b8d1d-168">Category</span></span></th>
<th align="left"><span data-ttu-id="b8d1d-169">Definition</span><span class="sxs-lookup"><span data-stu-id="b8d1d-169">Definition</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="b8d1d-170">なし</span><span class="sxs-lookup"><span data-stu-id="b8d1d-170">None</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-171">情報の抜き出し、変更、削除、その他の侵害が発生しなかった。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-171">No information was exfiltrated, changed, deleted, or otherwise compromised.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b8d1d-172">プライバシー侵害</span><span class="sxs-lookup"><span data-stu-id="b8d1d-172">Privacy Breach</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-173">納税者、従業員、受給者などの機密個人データにアクセスされたか、データが抜き出された。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-173">Sensitive personal data of taxpayers, employees, beneficiaries, etc. was accessed or exfiltrated.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b8d1d-174">専有情報違反</span><span class="sxs-lookup"><span data-stu-id="b8d1d-174">Proprietary Breach</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-175">重要インフラ情報保護 (PCII) などの未分類の専有情報にアクセスされたか、情報が抜き出された。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-175">Unclassified proprietary information, such as protected critical infrastructure information (PCII), was accessed or exfiltrated.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b8d1d-176">整合性損失</span><span class="sxs-lookup"><span data-stu-id="b8d1d-176">Integrity Loss</span></span></td>
<td align="left"><span data-ttu-id="b8d1d-177">機密情報または専有情報が改変または削除された。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-177">Sensitive or proprietary information was changed or deleted.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b8d1d-p115">セキュリティ対応チームは Microsoft Azure セキュリティ エンジニアおよび SME と協力し、証拠から得られたデータに基づいてイベントを分類します。セキュリティ イベントは次のように分類されます:</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p115">The Security Response Team works with Microsoft Azure Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as:</span></span>

-   <span data-ttu-id="b8d1d-p116">**誤検知:** 検出基準を満たすが、正常な業務プロセスの一部であることがわかったイベント。場合によってはこれをフィルタリングする必要があります。サービス チームは誤検知の根本原因を特定し、体系的な方法でそれを扱います (必要に応じて検出ソースを利用したり<span id="_Toc350859432" class="anchor"></span>微調整したりします)。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p116">**False Positive:** An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-<span id="_Toc350859432" class="anchor"></span>tuning them as needed.</span></span>

-   <span data-ttu-id="b8d1d-182">**セキュリティ インシデント:** Microsoft の機器や設備に保管された何らかの顧客データまたはサポート データへの不正アクセス、またはそのような機器や設備への無許可アクセスが発生した結果、顧客データまたはサポート データが喪失、開示、または改変されたインシデント。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-182">**Security Incident:** An incident where unlawful access to any Customer Data or Support Data stored on Microsoft’s equipment or in Microsoft’s facilities, or unauthorized access to such equipment or facilities resulting in loss, disclosure, or alteration of Customer Data or Support Data has occurred.</span></span>

-   <span data-ttu-id="b8d1d-183">**お客様報告対象セキュリティ インシデント (CRSI):** Microsoft のシステム、機器、または設備に対する不正/無許可アクセスまたは使用の結果として、顧客データの開示、改変、または喪失が発生した。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-183">**Customer-Reportable Security Incident (CRSI):** An unlawful or unauthorized access to or use of Microsoft’s systems, equipment, or facilities resulting in disclosure, modification, or loss of customer data.</span></span>

-   <span data-ttu-id="b8d1d-p117">**プライバシー侵害:** 個人データに関連するセキュリティ インシデントのサブタイプの 1 つ。対処手順はセキュリティ インシデントの場合とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p117">**Privacy Breach:** A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.</span></span>

<span data-ttu-id="b8d1d-p118">CRSI として宣言するには、顧客データへの無許可アクセスが発生した (またはその可能性が極めて高い) と Microsoft が判断するか、通知を行う法律上または契約上の義務が存在する必要があります。特定のお客様への影響、リソースへのアクセス、修復ステップが具体的に判明することが望ましいものの、必須ではありません。インシデントが CRSI として宣言されるのは通常、セキュリティ インシデントの診断ステージの結論が下された後です。ただし、該当するすべての情報を入手できた任意の時点で宣言される可能性があります。セキュリティ インシデント管理者は、お客様インシデント通知プロセスを開始する前に、報告対象イベントが生じたことに対する合理的な疑念を払拭する証拠を得ておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p118">For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.</span></span>

<span data-ttu-id="b8d1d-p119">調査期間中、セキュリティ対応チームは全世界の法律顧問と協力し、法的義務およびお客様への責任に基づいて捜査を確実に行います。また、さまざまな運用環境でシステム データや顧客データの閲覧と処理がかなり制限されます。該当するインシデント チケットに記録されたインシデント管理者による明確な書面の同意なしで、機密データおよび顧客データが運用環境から外部に移送されることはありません。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p119">Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket.</span></span>

<span data-ttu-id="b8d1d-p120">Microsoft はお客様にとってのリスクと業務上のリスクが適切に抑止され、是正措置が実施されていることを検証します。必要に応じて、イベントに関連する当座のセキュリティ リスクを解決するための緊急軽減ステップを実施します。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p120">Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken.</span></span>

<span data-ttu-id="b8d1d-p121">さらに Microsoft は、データ侵害に関する社内の事後分析を完了します。その一環として、対応/運用手順が十分であったかどうか評価し、セキュリティ インシデント対応 SOP または関連するプロセスに改善すべき点があればそれを実施します。データ侵害に関する社内事後分析の記録は高度な機密情報であり、お客様には開示できません。ただし、その要約がお客様への他のイベント通知に含まれることがあります。これらの報告は Azure の通常の監査サイクルで外部監査者にレビュー用として提供されます。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p121">Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal post-mortems for data breaches are highly confidential records not available to customers. Post-mortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure’s routine audit cycle.</span></span>

#### <a name="customer-notification"></a><span data-ttu-id="b8d1d-200">お客様への通知</span><span class="sxs-lookup"><span data-stu-id="b8d1d-200">Customer Notification</span></span>
---------------------

<span data-ttu-id="b8d1d-p122">Microsoft Azure では必要に応じてデータ侵害についてお客様や規制機関に通知いたします。Microsoft では Azure の運用において社内の本格的な区画化を採用しています。またデータ フロー ログも堅牢です。このような設計により、ほとんどのインシデントの範囲を特定のお客様層に限定できます。データが侵害されたときに、影響を受けたお客様に対して正確かつアクション可能な通知をタイムリーに提供することを目標としています。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p122">Microsoft Azure notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of Azure. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached.</span></span>

<span data-ttu-id="b8d1d-p123">CRSI として宣言した後、できるだけ素早く通知プロセスを開始すると同時に、迅速に進めることのセキュリティ リスクについても考慮し続けます。一般的に、インシデント調査の進捗に合わせて通知のドラフトが作成されます。以下の場合を*除き*、侵害発生の宣言後 72 時間以内にお客様に通知をお送りします。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p123">After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* for the following circumstances:</span></span>

-   <span data-ttu-id="b8d1d-p124">通知を行うことで他のお客様にとってリスクが増大すると Microsoft が判断した場合。たとえば、通知行為によって敵対者にヒントを与えてしまい、結果として修正不能になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p124">Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.</span></span>

-   <span data-ttu-id="b8d1d-211">Microsoft の法務部である Corporate External and Legal Affairs (CELA) およびエグゼクティブ インシデント マネージャーによって精査される、他の異常な状況または極端な状況。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-211">Other unusual or extreme circumstances vetted by Microsoft’s legal department Corporate External and Legal Affairs (CELA) and the Executive Incident Manager.</span></span>

<span data-ttu-id="b8d1d-212">Microsoft Azure は、お客様が内部調査を行ってエンド ユーザーへの責務を果たせるよう、詳細な情報をお客様に提供すると同時に、通知プロセスを不必要に遅らせないようにします。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-212">Microsoft Azure provides customers with detailed information enabling them to perform internal investigations and assisting them in meeting end user commitments, while not unduly delaying the notification process.</span></span>

<span data-ttu-id="b8d1d-p125">個人データ侵害の通知は、Microsoft が選択する任意の方法 (電子メールなど) でお客様に送られます。データ侵害の通知は Azure Security Center にあるセキュリティ連絡先一覧に向けて配信されます ([実装ガイドライン](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)に従ってこれを構成できます)。連絡先情報が Azure Security Center に提供されていない場合、Azure サブスクリプションの 1 人以上の管理者に通知が送られます。通知を確実に受け取るには、お客様に該当する各サブスクリプションおよびオンライン サービス ポータルで管理者の連絡先情報を正しく指定していただく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p125">Notification of a personal data breach will be delivered to the customer by any means Microsoft selects, including via email. Notification of a data breach will be delivered to the list of security contacts provided in Azure Security center, which can be configured by following the [implementation guidelines](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). If contact information is not provided in Azure Security Center, the notification will be sent to one or more administrator in an Azure subscription. To ensure that notification can be successfully delivered, it is the customer’s responsibility to ensure that the administrative contact information on each applicable subscription and online services portal is correct.</span></span>

<span data-ttu-id="b8d1d-p126">さらに Microsoft Azure または Azure Government チームは、カスタマー サービス (CSS) などの追加的な Microsoft スタッフ、およびお客様のアカウント マネージャー (AM) やテクニカル アカウント マネージャー (TAM) にも通知することを選択する場合があります。多くの場合、このような個人はお客様との関係が深く、迅速な修復をお手伝いできます。<span id="_Appendix_A" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="b8d1d-p126">The Microsoft Azure or Azure Government team may also elect to notify additional Microsoft personnel such as Customer Service (CSS) and the customer’s Account Manager(s) (AM) or Technical Account Manager(s) (TAM). These individuals often have close relationships with the customer and can facilitate faster remediation<span id="_Appendix_A" class="anchor"></span></span></span>

#### <a name="microsoft-intune-data-breach"></a><span data-ttu-id="b8d1d-219">Microsoft InTune のデータ侵害</span><span class="sxs-lookup"><span data-stu-id="b8d1d-219">Microsoft InTune Data Breach</span></span>
----------------------------

<span data-ttu-id="b8d1d-p127">Microsoft Intune は Microsoft Enterprise Mobility + Security スイート クラウド サービスの主要なコンポーネントです。データ ガバナンス戦略をサポートするために、すべての Microsoft クラウド サービスは Microsoft の「プライバシー/セキュリティ バイ デザイン」および「プライバシー/セキュリティ バイ デフォルト」の方法論に従って開発されます。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p127">Microsoft Intune is key component of the Microsoft Enterprise Mobility and Security Suite cloud service offering. To support the data governance strategy, all Microsoft cloud services are developed with the Microsoft Privacy and Security by Design and Privacy and Security by Default methodologies.</span></span>

<span data-ttu-id="b8d1d-p128">このため Microsoft Intune のクラウド サービスは、データ侵害に対する保護プロセスに関して Microsoft Azure サービス チームと同じ技術上および組織上の手法に従います。したがって、この「Microsoft Azure のデータ侵害」通知ドキュメントに示されているすべての情報が Microsoft Intune サービスにも同様に当てはまります。たとえば Microsoft Intune には同じセキュリティ インシデント対応プロセスとライフサイクル (ステージ 1: 検出からステージ 5<strong>:</strong> クローズと事後分析) および同じお客様セキュリティ インシデント通知プロセスが存在します。さらに、Microsoft Intune は Microsoft O365 チームと直接協力することで、Intune をご使用の Microsoft O365 のすべてのお客様に対する侵害通知の責務を果たします。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-p128">As such Microsoft Intune ‘s cloud service offering follows the same Technical and Organizational measures the Microsoft Azure service team(s) take for securing against data breach processes. Therefore, any information documented in the “Microsoft Azure Data Breach” notification document here is analogous to the Microsoft Intune service as well. For example, Microsoft Intune has the same Security Incident Response Process and Lifecycle (Stage 1: Detect thru Stage 5<strong>:</strong> Close and Postmortem) and also the same Customer Security Incident Notification process. In addition, Microsoft Intune also fulfills its obligations for Breach Notification for any Microsoft O365 customers using Intune by working directly with the Microsoft O365 team.</span></span>

<span data-ttu-id="b8d1d-226">マイクロソフトが個人データの侵害を検出して対応する方法の詳細については、Service Trust Portal の [GDPR の下でのデータ侵害の通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8d1d-226">For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.</span></span>


#### <a name="learn-more"></a><span data-ttu-id="b8d1d-227">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b8d1d-227">Learn more</span></span>
[<span data-ttu-id="b8d1d-228">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="b8d1d-228">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
