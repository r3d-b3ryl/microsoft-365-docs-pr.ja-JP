---
title: アーキテクチャ要件とアーキテクチャの構造を確認し、Microsoft Cloud App Securityのフレームワークを知って構成と設計Cloud App Security計画Microsoft 365 Defender
description: Microsoft Cloud App Security図では、パイロット環境の構築に役立つMicrosoft 365 Defenderのアーキテクチャについて説明します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a3fa9670262b90d1566c375680946a131bb9c78a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458014"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-cloud-app-security"></a><span data-ttu-id="3dde7-103">アーキテクチャの要件と主要な概念を確認Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3dde7-103">Review architecture requirements and key concepts for Microsoft Cloud App Security</span></span>


<span data-ttu-id="3dde7-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3dde7-104">**Applies to:**</span></span>

- <span data-ttu-id="3dde7-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3dde7-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="3dde7-106">この記事は、ユーザーの評価環境を設定するプロセスの手順[1/3](eval-defender-mcas-overview.md)で、Microsoft Cloud App SecurityとMicrosoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="3dde7-106">This article is [Step 1 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security alongside Microsoft 365 Defender.</span></span> <span data-ttu-id="3dde7-107">このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3dde7-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="3dde7-108">この機能をMicrosoft Cloud App Security、アーキテクチャを理解し、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3dde7-108">Before enabling Microsoft Cloud App Security, be sure you understand the architecture and can meet the requirements.</span></span> 

## <a name="understand-the-architecture"></a><span data-ttu-id="3dde7-109">アーキテクチャを理解する</span><span class="sxs-lookup"><span data-stu-id="3dde7-109">Understand the architecture</span></span>

<span data-ttu-id="3dde7-110">Microsoft Cloud App Securityは、クラウド アクセス セキュリティ ブローカー (CASB) です。</span><span class="sxs-lookup"><span data-stu-id="3dde7-110">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB).</span></span> <span data-ttu-id="3dde7-111">CASB は、エンタープライズ ユーザーと使用するクラウド リソースの間で、ユーザーがどこにいても、使用しているデバイスに関係なく、リアルタイムでアクセスを仲介するゲートキーパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-111">CASBs act a gatekeeper to broker access in real time between your enterprise users and cloud resources they use, wherever your users are located and regardless of the device they are using.</span></span> <span data-ttu-id="3dde7-112">Microsoft Cloud App Securityは、Microsoft のセキュリティ機能とネイティブに統合されます (Microsoft 365 Defender)。</span><span class="sxs-lookup"><span data-stu-id="3dde7-112">Microsoft Cloud App Security natively integrates with Microsoft security capabilities, including Microsoft 365 Defender.</span></span> 

<span data-ttu-id="3dde7-113">このCloud App Security、組織で使用されているクラウド アプリは、図のように管理および保護されません。</span><span class="sxs-lookup"><span data-stu-id="3dde7-113">Without Cloud App Security, cloud apps that are used by your organization are unmanaged and unprotected, as illustrated.</span></span>

![アーキテクチャのMicrosoft Cloud App Security](../../media/defender/m365-defender-mcas-architecture-a.png)

<span data-ttu-id="3dde7-115">この図について:</span><span class="sxs-lookup"><span data-stu-id="3dde7-115">In the illustration:</span></span>
- <span data-ttu-id="3dde7-116">組織によるクラウド アプリの使用は、管理され保護されません。</span><span class="sxs-lookup"><span data-stu-id="3dde7-116">The use of cloud apps by an organization is unmonitored and unprotected.</span></span> 
- <span data-ttu-id="3dde7-117">この使用は、管理組織内で達成される保護の外に含まれる。</span><span class="sxs-lookup"><span data-stu-id="3dde7-117">This use falls outside the protections achieved within a managed organization.</span></span> 

#### <a name="discovering-cloud-apps"></a><span data-ttu-id="3dde7-118">クラウド アプリの検出</span><span class="sxs-lookup"><span data-stu-id="3dde7-118">Discovering cloud apps</span></span>

<span data-ttu-id="3dde7-119">クラウド アプリの使用を管理する最初の手順は、組織で使用されているクラウド アプリを検出する方法です。</span><span class="sxs-lookup"><span data-stu-id="3dde7-119">The first step to managing the use of cloud apps is to discover which cloud apps are used by your organization.</span></span> <span data-ttu-id="3dde7-120">次の図は、クラウド検出とクラウド検出の動作をCloud App Security。</span><span class="sxs-lookup"><span data-stu-id="3dde7-120">This next diagram illustrates how cloud discovery works with Cloud App Security.</span></span>

![アーキテクチャ Microsoft Cloud App Security - クラウド検出](../../media/defender/m365-defender-mcas-architecture-b.png)

<span data-ttu-id="3dde7-122">この図では、ネットワーク トラフィックを監視し、組織で使用されているクラウド アプリを検出するために使用できる 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3dde7-122">In this illustration, there are two methods that can be used to monitor network traffic and discover cloud apps that are being used by your organization.</span></span>
- <span data-ttu-id="3dde7-123">回答。</span><span class="sxs-lookup"><span data-stu-id="3dde7-123">A.</span></span> <span data-ttu-id="3dde7-124">クラウド アプリの検出は、Microsoft Defender for Endpoint とネイティブに統合されます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-124">Cloud App Discovery integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="3dde7-125">Defender for Endpoint は、IT 管理デバイスからアクセスされるクラウド アプリとサービスWindows 10します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-125">Defender for Endpoint reports cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 
- <span data-ttu-id="3dde7-126">B.</span><span class="sxs-lookup"><span data-stu-id="3dde7-126">B.</span></span> <span data-ttu-id="3dde7-127">ネットワークに接続されているすべてのデバイスでのカバレッジの場合、Cloud App Securityログ コレクターがファイアウォールや他のプロキシにインストールされ、エンドポイントからデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-127">For coverage on all devices connected to a network, the Cloud App Security log collector is installed on firewalls and other proxies to collect data from endpoints.</span></span> <span data-ttu-id="3dde7-128">このデータは、分析のためにCloud App Security送信されます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-128">This data is sent to Cloud App Security for analysis.</span></span>

#### <a name="managing-cloud-apps"></a><span data-ttu-id="3dde7-129">クラウド アプリの管理</span><span class="sxs-lookup"><span data-stu-id="3dde7-129">Managing cloud apps</span></span>

<span data-ttu-id="3dde7-130">クラウド アプリを検出し、組織でどのように使用されるのかについて分析した後、選択したクラウド アプリの管理を開始できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-130">After you discover cloud apps and analyze the behavior of how these are used by your organization, you can begin managing cloud apps that you choose.</span></span> 

![クラウド アプリMicrosoft Cloud App Securityアーキテクチャ - クラウド アプリの管理](../../media/defender/m365-defender-mcas-architecture-c.png)

<span data-ttu-id="3dde7-132">この図では、次の例を示します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-132">In this illustration:</span></span>
- <span data-ttu-id="3dde7-133">一部のアプリは使用が許可されています。</span><span class="sxs-lookup"><span data-stu-id="3dde7-133">Some apps are sanctioned for use.</span></span> <span data-ttu-id="3dde7-134">これは、アプリの管理を開始する簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="3dde7-134">This is a simple way of beginning to manage apps.</span></span>
- <span data-ttu-id="3dde7-135">アプリをアプリ コネクタに接続することで、より大きな可視性と制御を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-135">You can enable greater visibility and control by connecting apps with app connectors.</span></span> <span data-ttu-id="3dde7-136">アプリ コネクタは、アプリ プロバイダーの API を使用します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-136">App connectors use the APIs of app providers.</span></span>


#### <a name="applying-session-controls-to-cloud-apps"></a><span data-ttu-id="3dde7-137">クラウド アプリへのセッション コントロールの適用</span><span class="sxs-lookup"><span data-stu-id="3dde7-137">Applying session controls to cloud apps</span></span>

<span data-ttu-id="3dde7-138">Microsoft Cloud App Securityリバース プロキシとして機能し、認可されたクラウド アプリへのプロキシ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-138">Microsoft Cloud App Security serves as a reverse proxy, providing proxy access to sanctioned cloud apps.</span></span> <span data-ttu-id="3dde7-139">これにより、Cloud App Securityセッション コントロールを適用できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-139">This allows Cloud App Security to apply session controls that you configure.</span></span> 

![アプリケーションのアーキテクチャMicrosoft Cloud App Security - プロキシ アクセス セッション制御](../../media/defender/m365-defender-mcas-architecture-d.png)

<span data-ttu-id="3dde7-141">この図では、次の例を示します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-141">In this illustration:</span></span>
- <span data-ttu-id="3dde7-142">組織内のユーザーとデバイスから認可されたクラウド アプリへのアクセスは、ユーザーがCloud App Security。</span><span class="sxs-lookup"><span data-stu-id="3dde7-142">Access to sanctioned cloud apps from users and devices in your organization is routed through Cloud App Security.</span></span>
- <span data-ttu-id="3dde7-143">このプロキシ アクセスでは、セッション コントロールを適用できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-143">This proxy access allows session controls to be applied.</span></span>
- <span data-ttu-id="3dde7-144">許可されていない、または明示的に認可されていないクラウド アプリは影響を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dde7-144">Cloud apps that you have not sanctioned or explicitly unsanctioned are not affected.</span></span>

<span data-ttu-id="3dde7-145">セッション コントロールを使用すると、組織でのクラウド アプリの使用方法にパラメーターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-145">Session controls allow you to apply parameters to how cloud apps are used by your organization.</span></span> <span data-ttu-id="3dde7-146">たとえば、組織が Salesforce を使用している場合は、管理対象デバイスだけが Salesforce で組織のデータにアクセスできるセッション ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-146">For example, if your organization is using Salesforce, you can configure a session policy that allows only managed devices to access your organization's data in Salesforce.</span></span> <span data-ttu-id="3dde7-147">より簡単な例として、管理されていないデバイスからのトラフィックを監視するポリシーを構成して、より厳しいポリシーを適用する前に、このトラフィックのリスクを分析できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-147">A simpler example could be configuring a policy to monitor traffic from unmanaged devices so you can analyze the risk of this traffic before applying stricter policies.</span></span>

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a><span data-ttu-id="3dde7-148">Azure ADと条件付きアクセス アプリ制御の統合</span><span class="sxs-lookup"><span data-stu-id="3dde7-148">Integrating with Azure AD with Conditional Access App Control</span></span>

<span data-ttu-id="3dde7-149">多要素認証や他の条件付きアクセス ポリシーを適用するために、Azure AD テナントに SaaS アプリが既に追加されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3dde7-149">You might already have SaaS apps added to your Azure AD tenant to enforce multi-factor authentication and other conditional access policies.</span></span> <span data-ttu-id="3dde7-150">Microsoft Cloud App Security Azure とネイティブに統合AD。</span><span class="sxs-lookup"><span data-stu-id="3dde7-150">Microsoft Cloud App Security natively integrates with Azure AD.</span></span> <span data-ttu-id="3dde7-151">Azure AD で条件付きアクセス アプリ制御を使用するようにポリシーを構成Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="3dde7-151">All you have to do is configure a policy in Azure AD to use Conditional Access App Control in Cloud App Security.</span></span> <span data-ttu-id="3dde7-152">これにより、これらの管理 SaaS アプリのネットワーク トラフィックが Cloud App Security プロキシとしてルーティングされ、Cloud App Securityを監視し、セッションコントロールを適用できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-152">This routes network traffic for these managed SaaS apps through Cloud App Security as a proxy, which allows Cloud App Security to monitor this traffic and to apply session controls.</span></span> 

![アーキテクチャ Microsoft Cloud App Security - SaaS アプリ](../../media/defender/m365-defender-mcas-architecture-e.png)

<span data-ttu-id="3dde7-154">この図では、次の例を示します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-154">In this illustration:</span></span>
- <span data-ttu-id="3dde7-155">SaaS アプリは、Azure サービス テナントADされます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-155">SaaS apps are integrated with the Azure AD tenant.</span></span> <span data-ttu-id="3dde7-156">これにより、Azure AD多要素認証を含む条件付きアクセス ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-156">This allows Azure AD to enforce conditional access policies, including multi-factor authentication.</span></span>
- <span data-ttu-id="3dde7-157">SaaS アプリのトラフィックをAzure Active Directoryするポリシーが追加Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="3dde7-157">A policy is added to Azure Active Directory to direct traffic for SaaS apps to Cloud App Security.</span></span> <span data-ttu-id="3dde7-158">ポリシーは、このポリシーを適用する SaaS アプリを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-158">The policy specifies which SaaS apps to apply this policy to.</span></span> <span data-ttu-id="3dde7-159">したがって、Azure AD がこれらの SaaS アプリに適用される条件付きアクセス ポリシーを適用した後、Azure AD はセッション トラフィックを Cloud App Security 経由で送信 (プロキシ) します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-159">Consequently, after Azure AD enforces any conditional access policies that apply to these SaaS apps, Azure AD then directs (proxies) the session traffic through Cloud App Security.</span></span>
- <span data-ttu-id="3dde7-160">Cloud App Securityトラフィックを監視し、管理者が構成したセッション制御ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-160">Cloud App Security monitors this traffic and applies any session control policies that have been configured by administrators.</span></span> 

<span data-ttu-id="3dde7-161">Azure Cloud App Security に追加されていないアプリを使用して、クラウド アプリを検出してAD。</span><span class="sxs-lookup"><span data-stu-id="3dde7-161">You might have discovered and sanctioned cloud apps using Cloud App Security that have not been added to Azure AD.</span></span> <span data-ttu-id="3dde7-162">これらのクラウド アプリを Azure AD テナントと条件付きアクセス ルールの範囲に追加することで、条件付きアクセス アプリ制御を利用できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-162">You can take advantage of Conditional Access App Control by adding these cloud apps to your Azure AD tenant and the scope of your conditional access rules.</span></span>

#### <a name="protecting-your-organization-from-hackers"></a><span data-ttu-id="3dde7-163">ハッカーから組織を保護する</span><span class="sxs-lookup"><span data-stu-id="3dde7-163">Protecting your organization from hackers</span></span>

<span data-ttu-id="3dde7-164">Cloud App Security独自の強力な保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-164">Cloud App Security provides powerful protection on its own.</span></span> <span data-ttu-id="3dde7-165">ただし、Microsoft 365 Defender の他の機能と組み合Cloud App Security共有信号にデータを提供し、一緒に攻撃を停止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-165">However, when combined with the other capabilities of Microsoft 365 Defender, Cloud App Security provides data into the shared signals which, together, helps stop attacks.</span></span>

<span data-ttu-id="3dde7-166">この図は、概要からこの評価とパイロット ガイドMicrosoft 365 Defender繰り返す価値があります。</span><span class="sxs-lookup"><span data-stu-id="3dde7-166">It's worth repeating this illustration from the overview to this Microsoft 365 Defender evaluation and pilot guide.</span></span> 

![一Microsoft 365 Defenderを停止する方法](../../media/defender/m365-defender-eval-threat-chain.png)

<span data-ttu-id="3dde7-168">Microsoft Cloud App Security は、この図の右側に焦点を当て、移動不可能、資格情報アクセス、異常なダウンロード、ファイル共有、メール転送アクティビティのような異常な動作に気付き、セキュリティ チームに報告します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-168">Focusing on the right side of this illustration, Microsoft Cloud App Security notices anomalous behavior like impossible-travel, credential access, and unusual download, file share, or mail forwarding activity and reports these to the security team.</span></span> <span data-ttu-id="3dde7-169">その結果、Cloud App Securityによる横方向の移動や機密データの侵入を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-169">Consequently, Cloud App Security helps prevent lateral movement by hackers and exfiltration of sensitive data.</span></span> <span data-ttu-id="3dde7-170">Microsoft 356 Defender は、すべてのコンポーネントからの信号を関連付け、完全な攻撃ストーリーを提供します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-170">Microsoft 356 Defender correlates the signals from all the components to provide the full attack story.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="3dde7-171">主要な概念を理解する</span><span class="sxs-lookup"><span data-stu-id="3dde7-171">Understand key concepts</span></span>

<span data-ttu-id="3dde7-172">次の表では、評価、構成、および展開を行う際に重要な重要な概念を示Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="3dde7-172">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Cloud App Security.</span></span>


|<span data-ttu-id="3dde7-173">概念</span><span class="sxs-lookup"><span data-stu-id="3dde7-173">Concept</span></span>  |<span data-ttu-id="3dde7-174">説明</span><span class="sxs-lookup"><span data-stu-id="3dde7-174">Description</span></span> |<span data-ttu-id="3dde7-175">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3dde7-175">More information</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="3dde7-176">Cloud App Securityダッシュボード</span><span class="sxs-lookup"><span data-stu-id="3dde7-176">Cloud App Security Dashboard</span></span> | <span data-ttu-id="3dde7-177">組織に関する最も重要な情報の概要を示し、より深い調査へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-177">Presents an overview of the most important information about your organization and gives links to deeper investigation.</span></span>        | [<span data-ttu-id="3dde7-178">ダッシュボードの操作 </span><span class="sxs-lookup"><span data-stu-id="3dde7-178">Working with the dashboard </span></span>](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| <span data-ttu-id="3dde7-179">アプリの条件付きアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="3dde7-179">Conditional Access App Control</span></span>    | <span data-ttu-id="3dde7-180">Id プロバイダー (IdP) と統合するリバース プロキシ アーキテクチャを使用して、Azure ADポリシーを提供し、セッション制御を選択的に適用します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-180">Reverse proxy architecture that integrates with your Identity Provider (IdP) to give Azure AD conditional access policies and selectively enforce session controls.</span></span>        |  [<span data-ttu-id="3dde7-181">条件付きアクセス アプリMicrosoft Cloud App Securityアプリを保護する</span><span class="sxs-lookup"><span data-stu-id="3dde7-181">Protect apps with Microsoft Cloud App Security Conditional Access App Control</span></span>](/cloud-app-security/proxy-intro-aad)       |
|  <span data-ttu-id="3dde7-182">クラウド アプリ カタログ</span><span class="sxs-lookup"><span data-stu-id="3dde7-182">Cloud App Catalog</span></span>   | <span data-ttu-id="3dde7-183">クラウド アプリ カタログを使用すると、80 を超えるリスク要因に基づいてランク付けおよびスコア付けされた 16,000 を超えるクラウド アプリの Microsoft カタログに対する全体像を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-183">The Cloud App Catalog gives you a full picture against Microsoft catalog of over 16,000 cloud apps that are ranked and scored based on more than 80 risk factors.</span></span>    |  [<span data-ttu-id="3dde7-184">アプリのリスク スコアの操作</span><span class="sxs-lookup"><span data-stu-id="3dde7-184">Working with App risk scores</span></span>](/cloud-app-security/risk-score)       |
| <span data-ttu-id="3dde7-185">クラウド探索ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="3dde7-185">Cloud Discovery Dashboard</span></span>    | <span data-ttu-id="3dde7-186">クラウド検出は、トラフィック ログを分析し、組織内でのクラウド アプリの使用方法に関するより多くの洞察を提供し、アラートとリスク レベルを提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3dde7-186">Cloud Discovery analyzes your traffic logs and is designed to give more insight into how cloud apps are being used in your organization as well as give alerts and risk levels.</span></span>     |  [<span data-ttu-id="3dde7-187">検出されたアプリの操作   </span><span class="sxs-lookup"><span data-stu-id="3dde7-187">Working with discovered apps   </span></span>](/cloud-app-security/discovered-apps)    |
|<span data-ttu-id="3dde7-188">接続されたアプリ</span><span class="sxs-lookup"><span data-stu-id="3dde7-188">Connected Apps</span></span> |<span data-ttu-id="3dde7-189">Cloud App Securityは、Cloud-to-Cloud 統合、API コネクタ、条件付きアプリ アクセス制御を活用したリアルタイム アクセスおよびセッション制御を使用して、接続されたアプリに対するエンドツーエンドの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-189">Cloud App Security provides end-to-end protection for connected apps using Cloud-to-Cloud integration, API connectors, and real-time access and session controls leveraging our Conditional App Access Controls.</span></span> |[<span data-ttu-id="3dde7-190">接続されたアプリの保護</span><span class="sxs-lookup"><span data-stu-id="3dde7-190">Protecting connected apps</span></span>](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a><span data-ttu-id="3dde7-191">アーキテクチャ要件の確認</span><span class="sxs-lookup"><span data-stu-id="3dde7-191">Review architecture requirements</span></span>

### <a name="discovering-cloud-apps"></a><span data-ttu-id="3dde7-192">クラウド アプリの検出</span><span class="sxs-lookup"><span data-stu-id="3dde7-192">Discovering cloud apps</span></span>

<span data-ttu-id="3dde7-193">環境で使用されているクラウド アプリを検出するには、次の 1 つまたは両方を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-193">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="3dde7-194">Microsoft Defender for Endpoint と統合することで、クラウド探索を迅速に実行できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-194">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3dde7-195">このネイティブ統合により、ネットワークのオンとオフを切り替えて、Windows 10トラフィックのデータ収集をすぐに開始できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-195">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="3dde7-196">ネットワークに接続されているすべてのデバイスがアクセスしているすべてのクラウド アプリを検出するには、ファイアウォールや他のプロキシに Cloud App Security ログ コレクターを展開します。</span><span class="sxs-lookup"><span data-stu-id="3dde7-196">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="3dde7-197">これにより、エンドポイントからデータが収集され、分析Cloud App Security送信されます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-197">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="3dde7-198">Cloud App Security機能を強化するために、一部のサード パーティ製プロキシとネイティブに統合できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-198">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="3dde7-199">これらのオプションは、手順 [2 に含まれています。評価環境を有効にする](eval-defender-mcas-enable-eval.md)。</span><span class="sxs-lookup"><span data-stu-id="3dde7-199">These options are included in [Step 2. Enable the evaluation environment](eval-defender-mcas-enable-eval.md).</span></span> 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a><span data-ttu-id="3dde7-200">Azure AD条件付きアクセス ポリシーをクラウド アプリに適用する</span><span class="sxs-lookup"><span data-stu-id="3dde7-200">Applying Azure AD Conditional Access policies to cloud apps</span></span>

<span data-ttu-id="3dde7-201">条件付きアクセス アプリ制御 (条件付きアクセス ポリシーをクラウド アプリに適用する機能) には、Azure アプリとの統合がAD。</span><span class="sxs-lookup"><span data-stu-id="3dde7-201">Conditional Access App Control (the ability to apply Conditional Access policies to cloud apps) requires integration with Azure AD.</span></span> <span data-ttu-id="3dde7-202">これは、アプリケーションの使用を開始するCloud App Security。</span><span class="sxs-lookup"><span data-stu-id="3dde7-202">This isn't a requirement for getting started with Cloud App Security.</span></span> <span data-ttu-id="3dde7-203">これは、パイロット フェーズ (手順 3) の間に試用[することを推奨する手順です。パイロット Microsoft Cloud App Security](eval-defender-mcas-pilot.md).</span><span class="sxs-lookup"><span data-stu-id="3dde7-203">It is a step we encourage you to try out during the pilot phase — [Step 3. Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="3dde7-204">SIEM 統合</span><span class="sxs-lookup"><span data-stu-id="3dde7-204">SIEM integration</span></span>

<span data-ttu-id="3dde7-205">一般的な SIEM サーバー Microsoft Cloud App Security Azure Sentinel と統合して、接続されたアプリからのアラートとアクティビティを一元的に監視できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-205">You can integrate Microsoft Cloud App Security with your generic SIEM server or with Azure Sentinel to enable centralized monitoring of alerts and activities from connected apps.</span></span> 

<span data-ttu-id="3dde7-206">さらに、Azure Sentinel には、Azure Sentinel Microsoft Cloud App Security統合を提供するコネクタが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dde7-206">Additionally, Azure Sentinel includes a Microsoft Cloud App Security connector to provide deeper integration with Azure Sentinel.</span></span> <span data-ttu-id="3dde7-207">これにより、クラウド アプリを可視化できるだけでなく、高度な分析を利用してサイバー脅威を特定して対処し、データの移動方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3dde7-207">This enables you to not only gain visibility into your cloud apps but to also get sophisticated analytics to identify and combat cyberthreats and to control how your data travels.</span></span>

- [<span data-ttu-id="3dde7-208">一般的な SIEM 統合</span><span class="sxs-lookup"><span data-stu-id="3dde7-208">Generic SIEM integration</span></span>](/cloud-app-security/siem)
- [<span data-ttu-id="3dde7-209">MCAS から Azure Sentinel にアラートとクラウド探索ログをストリーミングする</span><span class="sxs-lookup"><span data-stu-id="3dde7-209">Stream alerts and Cloud Discovery logs from MCAS into Azure Sentinel</span></span>](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a><span data-ttu-id="3dde7-210">次の手順</span><span class="sxs-lookup"><span data-stu-id="3dde7-210">Next steps</span></span>

<span data-ttu-id="3dde7-211">手順 2/3:[評価環境を有効 Microsoft Cloud App Securityにする](eval-defender-mcas-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="3dde7-211">Step 2 of 3: [Enable the evaluation environment for Microsoft Cloud App Security](eval-defender-mcas-enable-eval.md)</span></span>

<span data-ttu-id="3dde7-212">[評価] の概要[に戻Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3dde7-212">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="3dde7-213">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3dde7-213">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>