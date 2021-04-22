---
title: Microsoft 365 Defender
description: Microsoft 365 Defender は、デバイス、ID、データ、アプリケーションを保護するように設計された協調脅威保護ソリューションです。
keywords: MMicrosoft 365 Defender の概要、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な検出
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 32defdf459ec65ba0fd268a5a7c84851e9014efa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934047"
---
# <a name="microsoft-365-defender"></a><span data-ttu-id="59ee2-104">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59ee2-104">Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59ee2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="59ee2-105">**Applies to:**</span></span>
- <span data-ttu-id="59ee2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59ee2-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="59ee2-107">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="59ee2-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="59ee2-108">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="59ee2-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="59ee2-109">Microsoft 365 Defender は、エンドポイント、ID、メール、およびアプリケーション全体での検出、防止、調査、応答をネイティブに調整し、高度な攻撃に対する統合された保護を提供する、侵害の前後に対応した統合エンタープライズ防御スイートです。</span><span class="sxs-lookup"><span data-stu-id="59ee2-109">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span>

<span data-ttu-id="59ee2-110">統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ専門家は、これらの各製品が受け取る脅威信号を一緒にまとめ、脅威の全範囲と影響を特定できます。環境に入った方法、影響を受けるもの、組織に現在どのように影響を与えています。</span><span class="sxs-lookup"><span data-stu-id="59ee2-110">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that each of these products receive and determine the full scope and impact of the threat; how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="59ee2-111">Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復するために自動アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-111">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span>  


<center><h2><span data-ttu-id="59ee2-112">Microsoft 365 Defender サービス</center></span><span class="sxs-lookup"><span data-stu-id="59ee2-112">Microsoft 365 Defender services</center></span></span></h2>
<table><tr><td><span data-ttu-id="59ee2-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>エンドポイント用 Microsoft Defender</b></center></span><span class="sxs-lookup"><span data-stu-id="59ee2-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></span></span></a></td>
<td><span data-ttu-id="59ee2-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></span><span class="sxs-lookup"><span data-stu-id="59ee2-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></span></span></a></td>
<td><span data-ttu-id="59ee2-115"><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></span><span class="sxs-lookup"><span data-stu-id="59ee2-115"><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></span></span></td>
<td><span data-ttu-id="59ee2-116"><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span><span class="sxs-lookup"><span data-stu-id="59ee2-116"><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span></span></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a><span data-ttu-id="59ee2-117">Microsoft 365 Defender 対話型ガイド</span><span class="sxs-lookup"><span data-stu-id="59ee2-117">Microsoft 365 Defender interactive guide</span></span>

<span data-ttu-id="59ee2-118">この対話型ガイドでは、Microsoft 365 Defender を使用して組織を保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-118">In this interactive guide, you'll learn how to protect your organization with Microsoft 365 Defender.</span></span> <span data-ttu-id="59ee2-119">Microsoft 365 Defender がセキュリティ リスクの検出、組織への攻撃の調査、有害なアクティビティの自動防止に役立つ方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-119">You'll see how Microsoft 365 Defender can help you detect security risks, investigate attacks to your organization, and prevent harmful activities automatically.</span></span>

[<span data-ttu-id="59ee2-120">対話型のガイドをチェックしてください</span><span class="sxs-lookup"><span data-stu-id="59ee2-120">Check out the interactive guide</span></span>](https://aka.ms/M365Defender-InteractiveGuide)



<span data-ttu-id="59ee2-121">Microsoft 365 Defender スイートは次のものを保護します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-121">Microsoft 365 Defender suite protects:</span></span> 
- <span data-ttu-id="59ee2-122">**Microsoft Defender for Endpoint** を使用するエンドポイント - Microsoft Defender for Endpoint は、予防保護、侵害後の検出、自動調査、および対応のための統合エンドポイント プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="59ee2-122">**Endpoints with Microsoft Defender for Endpoint** - Microsoft Defender for Endpoint is a unified endpoint platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> 
- <span data-ttu-id="59ee2-123">**Office 365 用 Microsoft Defender** との電子メールとコラボレーション - Office 365 の Defender は、電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによる悪意のある脅威から組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-123">**Email and collaboration with Microsoft Defender for Office 365** - Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs) and collaboration tools.</span></span> 
- <span data-ttu-id="59ee2-124">**Id** と Microsoft Defender for Identity と Azure AD Identity Protection - Microsoft Defender for Identity は、Active Directory シグナルを使用して、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダー アクションを特定、検出、および調査します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-124">**Identities with Microsoft Defender for Identity and Azure AD Identity Protection** - Microsoft Defender for Identity uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> 
- <span data-ttu-id="59ee2-125">**Microsoft Cloud App** セキュリティを備えたアプリケーション - Microsoft Cloud App セキュリティは、クラウド アプリに深い可視性、強力なデータ制御、強化された脅威保護をもたらす包括的なクロス SaaS ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="59ee2-125">**Applications with Microsoft Cloud App security** - Microsoft Cloud App security is a comprehensive cross-SaaS solution bringing deep visibility, strong data controls, and enhanced threat protection to your cloud apps.</span></span> 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

<span data-ttu-id="59ee2-126">Microsoft 365 Defender の固有のクロスプロダクト レイヤーは、個々のスイート コンポーネントを次の機能に拡張します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-126">Microsoft 365 Defender's unique cross-product layer augments the individual suite components to:</span></span>
- <span data-ttu-id="59ee2-127">信号の共有と自動化されたアクションを通じて、攻撃から保護し、スイート全体の防御応答を調整するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="59ee2-127">Help protect against attacks and coordinate defensive responses across the suite through signal sharing and automated actions</span></span>
- <span data-ttu-id="59ee2-128">アラート、疑わしいイベント、影響を受けた資産に関するデータを 「インシデント」 に参加することで、セキュリティ チームの製品アラート、動作、コンテキスト全体にわたる攻撃の全ストーリーを説明します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-128">Narrate the full story of the attack across product alerts, behaviors, and context for security teams by joining data on alerts, suspicious events and impacted assets to 'incidents'</span></span>
- <span data-ttu-id="59ee2-129">影響を受け取ったアセットの自己修復を自動修復でトリガーすることで、侵害への対応を自動化する</span><span class="sxs-lookup"><span data-stu-id="59ee2-129">Automate response to compromise by triggering self-healing for impacted assets through automated remediation</span></span>
- <span data-ttu-id="59ee2-130">セキュリティ チームがエンドポイントとデータ全体で詳細かつ効果的な脅威Office可能</span><span class="sxs-lookup"><span data-stu-id="59ee2-130">Enable security teams to perform detailed and effective threat hunting across endpoint and Office data</span></span>

<span data-ttu-id="59ee2-131">![インシデントの概要ページの画像](../../media/overview-incident.png)</span><span class="sxs-lookup"><span data-stu-id="59ee2-131">![Image of incident overview page](../../media/overview-incident.png)</span></span> <br>
<span data-ttu-id="59ee2-132">製品間インシデント (概要)</span><span class="sxs-lookup"><span data-stu-id="59ee2-132">Cross-product incident (Overview)</span></span>

<span data-ttu-id="59ee2-133">![アラート キューのイメージ](../../media/incident-list.png)</span><span class="sxs-lookup"><span data-stu-id="59ee2-133">![Image of alerts queue](../../media/incident-list.png)</span></span><br>
<span data-ttu-id="59ee2-134">スイート製品全体のすべての関連アラートが 1 つのインシデントに関連付け (アラート ビュー)</span><span class="sxs-lookup"><span data-stu-id="59ee2-134">All related alerts across the suite products correlated together into a single incident (alerts view)</span></span>

<span data-ttu-id="59ee2-135">![インシデント キューのイメージ](../../media/advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="59ee2-135">![Image of incident queue](../../media/advanced-hunting.png)</span></span><br>
<span data-ttu-id="59ee2-136">電子メールとエンドポイントの生データの上でのクエリ ベースの検索</span><span class="sxs-lookup"><span data-stu-id="59ee2-136">Query-based hunting on top of email and endpoint raw data</span></span>


<span data-ttu-id="59ee2-137">Microsoft 365 Defender のクロスプロダクト機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="59ee2-137">Microsoft 365 Defender cross-product features include:</span></span> 
- <span data-ttu-id="59ee2-138">**ガラスの** 製品間単一ウィンドウ - 中央には、security.microsoft.com の 1 つのキューと 1 つのウィンドウで、検出、影響を受けるアセット、自動アクション、および関連する証拠に関 [するすべての情報が表示されます](https://security.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="59ee2-138">**Cross-product single pane of glass** - Central view all information for detections, impacted assets, automated actions taken, and related evidence in a single queue and a single pane in [security.microsoft.com](https://security.microsoft.com).</span></span> 
- <span data-ttu-id="59ee2-139">**複合インシデント** キュー - セキュリティ専門家が攻撃範囲全体を確保することで重要な作業に集中するために、影響を受けたアセットと自動修復アクションがグループ化され、適切な時期に表示されます。</span><span class="sxs-lookup"><span data-stu-id="59ee2-139">**Combined incidents queue** - To help security professionals focus on what is critical by ensuring the full attack scope, impacted assets and automated remediation actions are grouped together and surfaced in a timely manner.</span></span> 
- <span data-ttu-id="59ee2-140">**脅威への自動対応** - 重大な脅威情報は、攻撃の進行を止めるのに役立つ Microsoft 365 Defender 製品間でリアルタイムで共有されます。</span><span class="sxs-lookup"><span data-stu-id="59ee2-140">**Automatic response to threats** - Critical threat information is shared in real time between the Microsoft 365 Defender products to help stop the progression of an attack.</span></span> <span data-ttu-id="59ee2-141">たとえば、Microsoft Defender for Endpoint で保護されたエンドポイントで悪意のあるファイルが検出された場合、すべての電子メール メッセージからファイルをスキャンして削除するように Defender に Office 365 を指示します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-141">For example, if a malicious file is detected on an endpoint protected by Microsoft Defender for Endpoint, it will instruct Defender for Office 365 to scan and remove the file from all e-mail messages.</span></span> <span data-ttu-id="59ee2-142">ファイルは、Microsoft 365 セキュリティ スイート全体でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="59ee2-142">The file will be blocked on sight by the entire Microsoft 365 security suite.</span></span>
- <span data-ttu-id="59ee2-143">**侵害された** デバイス、ユーザー ID、メールボックスの自己修復 - Microsoft 365 Defender は、AI による自動アクションとプレイブックを使用して、影響を受け取ったアセットを安全な状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-143">**Self-healing for compromised devices, user identities, and mailboxes** - Microsoft 365 Defender uses AI-powered automatic actions and playbooks to remediate impacted assets back to a secure state.</span></span> <span data-ttu-id="59ee2-144">Microsoft 365 Defender はスイート製品の自動修復機能を活用して、インシデントに関連する影響を受けたすべての資産を可能な限り自動的に修復します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-144">Microsoft 365 Defender leverages automatic remediation capabilities of the suite products to ensure all impacted assets related to an incident are automatically remediated where possible.</span></span>
- <span data-ttu-id="59ee2-145">**製品間の脅威** の検出 - セキュリティ チームは、独自の組織の知識を活用して、さまざまな保護製品によって収集された生データに対して独自のカスタム クエリを作成することで、侵害の兆候を探し出します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-145">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries over the raw data collected by the various protection products.</span></span> <span data-ttu-id="59ee2-146">Microsoft 365 Defender は、エンドポイント全体で 30 日間の過去の生信号とアラート データへのクエリ ベースのアクセスを提供し、365 データのOffice提供します。</span><span class="sxs-lookup"><span data-stu-id="59ee2-146">Microsoft 365 Defender provides query-based access to 30 days of historic raw signals and alert data across endpoint and Microsoft Defender for Office 365 data.</span></span> 


## <a name="get-started"></a><span data-ttu-id="59ee2-147">開始する</span><span class="sxs-lookup"><span data-stu-id="59ee2-147">Get started</span></span>
<span data-ttu-id="59ee2-148">Microsoft 365 Defender のライセンス要件を満たしてから、Microsoft 365 セキュリティ センター (microsoft 365 セキュリティ センター) でサービスを有効[security.microsoft.com。](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="59ee2-148">Microsoft 365 Defender licensing requirements must be met before you can enable the service in the Microsoft 365 security center at [security.microsoft.com](https://security.microsoft.com).</span></span> <span data-ttu-id="59ee2-149">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59ee2-149">For more information, read:</span></span>
- [<span data-ttu-id="59ee2-150">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="59ee2-150">Licensing requirements</span></span>](prerequisites.md#licensing-requirements)
- [<span data-ttu-id="59ee2-151">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="59ee2-151">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)


## <a name="see-also"></a><span data-ttu-id="59ee2-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="59ee2-152">See also</span></span>
- [<span data-ttu-id="59ee2-153">Microsoft 365 E5 全体に脅威保護機能を展開する</span><span class="sxs-lookup"><span data-stu-id="59ee2-153">Deploy threat protection capabilities across Microsoft 365 E5</span></span>](https://docs.microsoft.com/microsoft-365/solutions/deploy-threat-protection)
