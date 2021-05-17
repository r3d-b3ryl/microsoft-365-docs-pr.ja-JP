---
title: 手順 1. 最初のインシデントをトリアージして分析する
description: Microsoft 365 Defender で最初のインシデントをトリアージして分析を開始する方法。
keywords: インシデント、アラート、調査、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 83889123067897483478aec3d881a5a7b6ec14cc
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297226"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a><span data-ttu-id="842fd-105">手順 1.</span><span class="sxs-lookup"><span data-stu-id="842fd-105">Step 1.</span></span> <span data-ttu-id="842fd-106">最初のインシデントをトリアージして分析する</span><span class="sxs-lookup"><span data-stu-id="842fd-106">Triage and analyze your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="842fd-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="842fd-107">**Applies to:**</span></span>
- <span data-ttu-id="842fd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="842fd-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="842fd-109">組織の標準に従ってセキュリティ対策を確立、実装、および維持するために少し時間を費やすと、セキュリティ リスクと脅威をすばやく特定するのに役立つセキュリティ ソリューションをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="842fd-109">As you spend some time establishing, implementing, and maintaining security measures according to the organization’s standards, you can set up security solutions to help you quickly identify security risks and threats.</span></span> <span data-ttu-id="842fd-110">Microsoft 365 Defender を使用すると、1 ウィンドウのエクスペリエンスを通じてインシデントを検出、トリアージ、および調査できます。このエクスペリエンスでは、意思決定に必要な情報を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="842fd-110">Microsoft 365 Defender allows you to detect, triage, and investigate incidents through its single-pane-of-glass experience where you can find the information you need to make timely decisions.</span></span> 

<span data-ttu-id="842fd-111">セキュリティ インシデントが検出されると、Microsoft 365 Defender は、インシデントやインシデントを他のユーザーよりもトリアージまたは優先順位付けする必要がある詳細を提示します。</span><span class="sxs-lookup"><span data-stu-id="842fd-111">Once a security incident is detected, Microsoft 365 Defender presents details you will need to triage or prioritize an incident or incidents over others.</span></span> <span data-ttu-id="842fd-112">アナリストは、事前設定を決定した後、割り当てられたケースの調査に集中できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-112">After determining prioritization, analysts can then focus their energy on investigating cases assigned to them.</span></span>

## <a name="detection-by-microsoft-365-defender"></a><span data-ttu-id="842fd-113">Microsoft 365 Defender による検出</span><span class="sxs-lookup"><span data-stu-id="842fd-113">Detection by Microsoft 365 Defender</span></span>

<span data-ttu-id="842fd-114">Microsoft 365 Defender は、複数の Microsoft セキュリティ プラットフォームからアラートとイベントを検出ソースとして受け取り、悪意のあるアクティビティの全体像とコンテキストを作成します。</span><span class="sxs-lookup"><span data-stu-id="842fd-114">Microsoft 365 Defender receives alerts and events from multiple Microsoft security platforms as detection sources to create a holistic picture and context of malicious activity.</span></span> <span data-ttu-id="842fd-115">次に、検出の可能性があるソースを示します。</span><span class="sxs-lookup"><span data-stu-id="842fd-115">These are the possible detection sources:</span></span>

- <span data-ttu-id="842fd-116">[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) は、Microsoft Defender ウイルス対策と Microsoft セキュリティ グラフを使用したクラウド対応の高度な脅威保護を使用するエンドポイント検出および応答ソリューション (EDR) です。</span><span class="sxs-lookup"><span data-stu-id="842fd-116">[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) is an endpoint detection and response solution (EDR) that uses Microsoft Defender antivirus as well as cloud-enabled advanced threat protection using Microsoft Security Graph.</span></span> <span data-ttu-id="842fd-117">Defender for Endpoint は、予防保護、侵害後の検出、自動調査、および対応のための統合プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="842fd-117">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="842fd-118">エンドポイントをサイバー脅威から保護し、高度な攻撃とデータ侵害を検出し、セキュリティ インシデントを自動化し、セキュリティの態勢を改善します。</span><span class="sxs-lookup"><span data-stu-id="842fd-118">It protects endpoints from cyberthreats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span> 
- <span data-ttu-id="842fd-119">[Microsoft Defender for Identity](https://docs.microsoft.com/defender-for-identity/what-is) は、オンプレミスの Active Directory ドメイン サービス (AD DS) シグナルを使用して、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダーアクションを特定、検出、および調査するクラウドベースのセキュリティ ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="842fd-119">[Microsoft Defender for Identity](https://docs.microsoft.com/defender-for-identity/what-is) is a cloud-based security solution that uses your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> 
- <span data-ttu-id="842fd-120">[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) は、エンタープライズ ユーザーと使用するクラウド リソースの間で、ユーザーがどこにいても、使用しているデバイスに関係なく、リアルタイムでブローカー アクセスを仲介するゲートキーパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="842fd-120">[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) acts as a gatekeeper to broker access in real time between your enterprise users and the cloud resources they use, wherever your users are located and regardless of the device they are using.</span></span> 
- <span data-ttu-id="842fd-121">[Microsoft Defender for Office 365 は](../office-365-security/overview.md) 、電子メール メッセージ、リンク (URL)、およびコラボレーション ツールにおける悪意のある脅威から組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="842fd-121">[Microsoft Defender for Office 365](../office-365-security/overview.md) safeguards your organization against malicious threats in email messages, links (URLs), and collaboration tools.</span></span> 
- <span data-ttu-id="842fd-122">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-introduction) は、データ センターのセキュリティ体制を強化し、クラウドおよびオンプレミスのハイブリッド ワークロード全体で高度な脅威保護を提供する統合インフラストラクチャ セキュリティ管理システムです。</span><span class="sxs-lookup"><span data-stu-id="842fd-122">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-introduction) is a unified infrastructure security management system that strengthens the security posture of your data centers and provides advanced threat protection across your hybrid workloads in the cloud as well as on premises.</span></span> 

<span data-ttu-id="842fd-123">Microsoft 365 Defender[](incidents-overview.md)では、インシデントは、これらの異なる検出ソースからのアラートを関連付けによって識別されます。</span><span class="sxs-lookup"><span data-stu-id="842fd-123">In Microsoft 365 Defender, [incidents](incidents-overview.md) are identified by correlating alerts from these different detection sources.</span></span> <span data-ttu-id="842fd-124">リソースを一緒に文字列化したり、複数のアラートをそれぞれのインシデントに区別したりするのではなく、Microsoft 365 Defender のインシデント キューからすぐ開始できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-124">Instead of spending resources stringing together or distinguishing multiple alerts into their respective incidents, you can start with the incident queue in Microsoft 365 Defender right away.</span></span> <span data-ttu-id="842fd-125">これにより、エンドポイント、ID、電子メール、アプリケーション間で効率的にインシデントをトリアージし、攻撃による被害を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-125">This allows you to triage incidents in an efficient manner across endpoints, identities, email, and applications, and reduce the damage from an attack.</span></span>

## <a name="triage-your-incidents"></a><span data-ttu-id="842fd-126">インシデントのトリアージ</span><span class="sxs-lookup"><span data-stu-id="842fd-126">Triage your incidents</span></span>

<span data-ttu-id="842fd-127">Microsoft 365 Defender のインシデント対応は、組織の推奨される事前設定方法を使用してインシデントの一覧をトリアージすると開始されます。</span><span class="sxs-lookup"><span data-stu-id="842fd-127">Incident response in Microsoft 365 Defender starts once you triage the list of incidents using your organization’s recommended method of prioritization.</span></span> <span data-ttu-id="842fd-128">トリアージとは、インシデントに重要度または緊急度のレベルを割り当て、インシデントを調査する順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="842fd-128">To triage means to assign a level of importance or urgency to incidents, which then determines the order in which they will be investigated.</span></span> 

<span data-ttu-id="842fd-129">Microsoft 365 Defender で優先順位を付けるインシデントを決定するための便利なサンプル ガイドは、重大度 + 影響 = 優先度という数式 *で要約できます*。</span><span class="sxs-lookup"><span data-stu-id="842fd-129">A useful sample guide for determining which incident to prioritize in Microsoft 365 Defender can be summarized by the formula: *Severity + Impact = Priority*.</span></span> 

- <span data-ttu-id="842fd-130">**重大度は** 、Microsoft 365 Defender とその統合セキュリティ コンポーネントによって指定されるレベルです。</span><span class="sxs-lookup"><span data-stu-id="842fd-130">**Severity** is the level designated by Microsoft 365 Defender and its integrated security components.</span></span> 
- <span data-ttu-id="842fd-131">**影響** は組織によって決定され、一般に、影響を受けるユーザー、デバイス、影響を受けるサービス (またはその組み合わせ)、およびアラートの種類のしきい値数が含まれますが、これらに限定されません。</span><span class="sxs-lookup"><span data-stu-id="842fd-131">**Impact** is determined by the organization and generally includes, but not limited to, a threshold number of impacted users, devices, services affected (or a combination thereof), and even alert type.</span></span> 

<span data-ttu-id="842fd-132">アナリストは、組織が設定した優先度の基準 **に** 基づいて調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="842fd-132">Analysts then initiate investigations based on the **Priority** criteria set by the organization.</span></span>

<span data-ttu-id="842fd-133">インシデントの事前設定は、組織によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="842fd-133">Incident prioritization might vary depending on the organization.</span></span> <span data-ttu-id="842fd-134">NIST では、インシデントの機能的および情報的な影響、および回復可能性も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="842fd-134">NIST recommends also considering the functional and informational impact of the incident, and recoverability.</span></span>  

<span data-ttu-id="842fd-135">次に示すのは、トリアージに対する 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="842fd-135">The following is just one approach to triage:</span></span> 

1. <span data-ttu-id="842fd-136">インシデント ページに [移動してトリ](incidents-overview.md) アージを開始します。</span><span class="sxs-lookup"><span data-stu-id="842fd-136">Go to the [incidents](incidents-overview.md) page to initiate triage.</span></span> <span data-ttu-id="842fd-137">ここでは、組織に影響を与えるインシデントの一覧を確認できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-137">Here you can see a list of incidents affecting your organization.</span></span> <span data-ttu-id="842fd-138">既定では、最新のインシデントから最も古いインシデントに配置されます。</span><span class="sxs-lookup"><span data-stu-id="842fd-138">By default, they are arranged from the most recent to the oldest incident.</span></span> <span data-ttu-id="842fd-139">ここから、インシデントごとに異なる列が表示され、重大度、カテゴリ、アクティブなアラートの数、影響を受けたエンティティなどが表示されます。</span><span class="sxs-lookup"><span data-stu-id="842fd-139">From here, you can also see different columns for each incident showing their severity, category, number of active alerts, and impacted entities, among others.</span></span> <span data-ttu-id="842fd-140">列のセットをカスタマイズし、列名を選択して、これらの列によってインシデント キューを並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="842fd-140">You can customize the set of columns and sort the incident queue by some these columns by selecting the column name.</span></span> <span data-ttu-id="842fd-141">必要に応じてインシデント キューをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="842fd-141">You can also filter the incident queue according to your needs.</span></span> <span data-ttu-id="842fd-142">使用可能なフィルターの完全な一覧については、「インシデントの優先順位 [付け」を参照してください](incident-queue.md#available-filters)。</span><span class="sxs-lookup"><span data-stu-id="842fd-142">For a full list of available filters, see [Prioritize incidents](incident-queue.md#available-filters).</span></span>
  
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="インシデント キューの例"::: 

    <span data-ttu-id="842fd-144">この一連のインシデントに対してトリアージを実行する方法の 1 つの例は、より多くのユーザーとデバイスに影響を与えたインシデントに優先順位を付ける方法です。</span><span class="sxs-lookup"><span data-stu-id="842fd-144">One example of how you might perform triage for this set of incidents is to prioritize incidents that affected more users and devices.</span></span> <span data-ttu-id="842fd-145">この例では、7 台のデバイス、6 人のユーザー、および 2 つのメールボックスという最大のエンティティ数に影響を与えたため、インシデント ID 6769 の優先順位を付ける場合があります。</span><span class="sxs-lookup"><span data-stu-id="842fd-145">In this example, you might prioritize incident ID 6769 because it affected the largest number of entities: 7 devices, 6 users, and 2 mailboxes.</span></span> <span data-ttu-id="842fd-146">さらに、このインシデントには、ID ベースのアラートと資格情報の盗難の可能性を示す Microsoft Defender for Identity からのアラートが含まれていると思います。</span><span class="sxs-lookup"><span data-stu-id="842fd-146">Furthermore, the incident appears to contain alerts from Microsoft Defender for Identity which indicate an identity-based alert and possible credential theft.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="影響の大きなインシデントの例":::
 
2. <span data-ttu-id="842fd-148">インシデント名の横にある円を選択して詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="842fd-148">Select the circle next to the incident name to review the details.</span></span> <span data-ttu-id="842fd-149">右側にサイド ウィンドウが表示されます。このウィンドウには、トリアージをさらに支援する追加情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="842fd-149">A side pane will appear on the right side, which contains additional information that can assist your triage further.</span></span> 
 
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="インシデント側ウィンドウの例"::: 

   <span data-ttu-id="842fd-151">たとえば、攻撃者がインシデントのカテゴリに基づいて使用した [MITRE ATT&CK](https://attack.mitre.org/) の戦術を見て、攻撃者が盗まれた資格情報を使用し、コマンドと制御を確立し、横方向の動きを実行し、一部のデータを削除したため、このインシデントの優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="842fd-151">For example, by looking at which [MITRE ATT&CK](https://attack.mitre.org/) tactics the attacker used based on the incident’s categories, you might prioritize this incident because the attacker used stolen credentials, established command and control, performed lateral movement, and exfiltrated some data.</span></span> <span data-ttu-id="842fd-152">これは、攻撃者が既にネットワークに深く入り込み、機密情報を盗まれた可能性を示唆しています。</span><span class="sxs-lookup"><span data-stu-id="842fd-152">This suggests the attacker has already gone deep into the network and possibly stolen confidential information.</span></span>

   <span data-ttu-id="842fd-153">さらに、組織がゼロトラスト フレームワークを実装している場合は、資格情報アクセスを優先順位付けする価値のある重要なセキュリティ違反と見なします。</span><span class="sxs-lookup"><span data-stu-id="842fd-153">Additionally, if your organization has implemented the Zero Trust framework, you would consider credential access as an important security violation worth prioritizing.</span></span>
 
   <span data-ttu-id="842fd-154">サイド ウィンドウを下にスクロールすると、影響を受け取る特定のエンティティ (ユーザー、デバイス、メールボックスなど) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="842fd-154">Scrolling down the side pane, you will see the specific impacted entities such as users, devices, and mailboxes.</span></span> <span data-ttu-id="842fd-155">各デバイスの露出レベルと、影響を受けるメールボックスの所有者を確認できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-155">You can check the exposure level of each device and the owners of affected mailboxes.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="インシデント側ウィンドウの詳細の例"::: 
 
3. <span data-ttu-id="842fd-157">サイド ウィンドウをさらに下に移動すると、関連付けられたアラートを確認できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-157">Further down the side pane, you can find the associated alerts.</span></span> <span data-ttu-id="842fd-158">Microsoft 365 Defender は既に、このアラートを 1 つのインシデントに関連付け、攻撃の修復に費やした時間とリソースを節約しています。</span><span class="sxs-lookup"><span data-stu-id="842fd-158">Microsoft 365 Defender has already performed the correlation of said alerts into a single incident, saving you time and resources better spent remediating the attack.</span></span> <span data-ttu-id="842fd-159">アラートは疑わしいため、ネットワーク上に攻撃者が存在する可能性のある悪意のあるシステム イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="842fd-159">Alerts are suspicious and therefore possibly malicious system events that suggest the presence of an attacker on a network.</span></span> 

   <span data-ttu-id="842fd-160">この例では、87 個の個別のアラートが 1 つのセキュリティ インシデントの一部と判断されました。</span><span class="sxs-lookup"><span data-stu-id="842fd-160">In this example, 87 individual alerts were determined to be part of one security incident.</span></span> <span data-ttu-id="842fd-161">すべてのアラートを表示して、攻撃の実行方法を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-161">You can view all the alerts to get a quick view of how the attack played out.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="インシデント側ウィンドウのアラートの例"::: 
 
## <a name="analyze-your-first-incident"></a><span data-ttu-id="842fd-163">最初のインシデントを分析する</span><span class="sxs-lookup"><span data-stu-id="842fd-163">Analyze your first incident</span></span>

<span data-ttu-id="842fd-164">アラートを取り巻くコンテキストを理解するのも同様に重要です。</span><span class="sxs-lookup"><span data-stu-id="842fd-164">Understanding the context surrounding alerts is equally important.</span></span> <span data-ttu-id="842fd-165">多くの場合、アラートは 1 つの独立したイベントではありません。</span><span class="sxs-lookup"><span data-stu-id="842fd-165">Often an alert is not a single independent event.</span></span> <span data-ttu-id="842fd-166">同時に発生していない可能性があるプロセス、コマンド、およびアクションのチェーンがあります。</span><span class="sxs-lookup"><span data-stu-id="842fd-166">There is a chain of processes created, commands, and actions that might not have occurred at the same time.</span></span> <span data-ttu-id="842fd-167">そのため、アナリストは、アラートのコンテキストを理解するために、デバイスのタイムラインで不審なエンティティの最初と最後のアクティビティを探す必要があります。</span><span class="sxs-lookup"><span data-stu-id="842fd-167">Therefore, an analyst must look for the first and last activities of the suspicious entity in device timelines to understand the context of the alerts.</span></span>

<span data-ttu-id="842fd-168">Microsoft 365 Defender を使用してデータを読み取り、分析する方法は複数ありますが、アナリストの最後の目標は、インシデントに可能な限り迅速に対応することです。</span><span class="sxs-lookup"><span data-stu-id="842fd-168">There are multiple ways to read and analyze data using Microsoft 365 Defender but the end goal for analysts is to respond to incidents as quickly as possible.</span></span> <span data-ttu-id="842fd-169">Microsoft 365 Defender は、業界をリードする自動調査と対応機能を通じて修復の[](m365d-autoir.md)平均時間[(MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/)を大幅に短縮することができますが、手動分析が必要な場合は常に存在します。</span><span class="sxs-lookup"><span data-stu-id="842fd-169">While Microsoft 365 Defender can significantly reduce [Mean Time to Remediate (MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) through the industry-leading [automated investigation and response](m365d-autoir.md) feature, there are always cases that require manual analysis.</span></span> 

<span data-ttu-id="842fd-170">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="842fd-170">Here's an example:</span></span>

1. <span data-ttu-id="842fd-171">トリアージの優先度が決定された後、アナリストはインシデント名を選択して詳細な分析を開始します。</span><span class="sxs-lookup"><span data-stu-id="842fd-171">Once triage priority has been determined, an analyst begins an in-depth analysis by selecting the incident name.</span></span> <span data-ttu-id="842fd-172">このページには、 **分析を支援** するタブにデータが表示されるインシデントの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="842fd-172">This page brings up the **Incident Summary** where data is displayed in tabs to assist with the analysis.</span></span> <span data-ttu-id="842fd-173">[アラート] **タブ** の下に、アラートの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="842fd-173">Under the **Alerts** tab the type of alerts are displayed.</span></span> <span data-ttu-id="842fd-174">アナリストは、各アラートをクリックして、それぞれの検出ソースをドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="842fd-174">Analysts can click on each alert to drill down into the respective detection source.</span></span> 

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="インシデントの [概要] タブの例"::: 
 
    <span data-ttu-id="842fd-176">各検出ソースがカバーするドメインに関するクイック ガイドについては、この記事の [「Detect」](#detection-by-microsoft-365-defender) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="842fd-176">For a quick guide about which domain each detection source covers, review the [Detect](#detection-by-microsoft-365-defender) section of this article.</span></span>

2.  <span data-ttu-id="842fd-177">[アラート **] タブ** から、アナリストは検出ソースにピボットして、より詳細な調査と分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-177">From the **Alerts** tab, an analyst can pivot to the detection source to conduct a more in-depth investigation and analysis.</span></span> <span data-ttu-id="842fd-178">たとえば、検出元がアナリストを対応するアラート ページに移動する場合に、[Microsoft Cloud App Security を使用したマルウェア検出] を選択します。</span><span class="sxs-lookup"><span data-stu-id="842fd-178">For example, selecting Malware Detection with Microsoft Cloud App Security as the detection source takes the analyst to its corresponding alert page.</span></span>
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="インシデントのアラートを選択する例"::: 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Microsoft Cloud App Security の対応するページの例"::: 
  
3.  <span data-ttu-id="842fd-181">この例をさらに調査するには、ページの下部までスクロールして、影響を受ける **ユーザーを表示します**。</span><span class="sxs-lookup"><span data-stu-id="842fd-181">To investigate our example further, scrolling to the bottom of the page to view the **Users affected**.</span></span> <span data-ttu-id="842fd-182">マルウェア検出を取り巻くアクティビティとコンテキストを確認するには、Annette Hill のユーザー ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="842fd-182">To see the activity and context surrounding the malware detection, select Annette Hill’s user page .</span></span> 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="ユーザー ページの例":::
  
4.  <span data-ttu-id="842fd-184">ユーザー ページには *、TOR* ネットワーク IP アドレスアラートからの危険なサインインから始まるイベントの時系列リストがあります。</span><span class="sxs-lookup"><span data-stu-id="842fd-184">On the user page is a chronological list of events starting with a *Risky Sign-in from a TOR network IP Address* alert.</span></span> <span data-ttu-id="842fd-185">アクティビティの疑いは、組織がビジネスを行う方法の性質によって異なりますが、ほとんどの場合、ユーザーが匿名で Web を閲覧できるネットワークである Onion Router (TOR) を企業環境で使用すると、通常のオンライン操作では非常に可能性が低く、不要と見なされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="842fd-185">While the suspiciousness of an activity depends on the nature of how an organization conducts its business, in most cases the use of The Onion Router (TOR), a network that allows users to browse the web anonymously, in an enterprise environment might be considered highly unlikely and unnecessary for regular online operations.</span></span>
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="ユーザーのイベントの時系列リストの例":::
  
5.  <span data-ttu-id="842fd-187">各アラートを選択して、アクティビティの詳細を取得できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-187">Each alert can be selected to obtain more information on the activity.</span></span> <span data-ttu-id="842fd-188">たとえば、[Tor **IP アドレス** ] アラートから [アクティビティ] を選択すると、そのアラートの独自のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="842fd-188">For example, selecting **Activity from a Tor IP Address** alert leads you to that alert’s own page.</span></span> <span data-ttu-id="842fd-189">Annette は Office 365 の管理者であり、管理者特権を持ち、ソース インシデントが機密情報へのアクセスにつながっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="842fd-189">Annette is an Administrator of Office 365, which means she has elevated privileges and the source incident might have led to access to confidential information.</span></span> 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Microsoft Cloud App Security のアラートの詳細の例 "::: 
 
6.  <span data-ttu-id="842fd-191">他のアラートを選択すると、アナリストは攻撃の完全な画像を取得できます。</span><span class="sxs-lookup"><span data-stu-id="842fd-191">By selecting other alerts, an analyst can get a complete picture of the attack.</span></span>

## <a name="next-step"></a><span data-ttu-id="842fd-192">次の手順</span><span class="sxs-lookup"><span data-stu-id="842fd-192">Next step</span></span>

<span data-ttu-id="842fd-193">[![手順 2: インシデントを修復する方法について学習する](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)</span><span class="sxs-lookup"><span data-stu-id="842fd-193">[![Step 2: Learn how to remediate incidents](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)</span></span>

<span data-ttu-id="842fd-194">インシデントを [修復する方法について学習します](first-incident-remediate.md)。</span><span class="sxs-lookup"><span data-stu-id="842fd-194">Learn how to [remediate incidents](first-incident-remediate.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="842fd-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="842fd-195">See also</span></span>

- [<span data-ttu-id="842fd-196">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="842fd-196">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="842fd-197">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="842fd-197">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="842fd-198">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="842fd-198">Manage incidents</span></span>](manage-incidents.md)
