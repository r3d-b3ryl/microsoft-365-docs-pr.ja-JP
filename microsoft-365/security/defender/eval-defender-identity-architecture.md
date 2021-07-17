---
title: アーキテクチャ要件と Microsoft Defender for Identity の技術的フレームワーク、アーキテクチャ図、MDI を確認する
description: Microsoft Defender for Identity in Microsoft 365 Defenderテクニカル ダイアグラムは、試用版ラボまたはパイロット環境を構築する前Microsoft 365の ID を理解するのに役立ちます。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 8f0c736d07a2a66420416d30ae2dc45ae5fee37a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458304"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a><span data-ttu-id="0fb18-103">Microsoft Defender for Identity のアーキテクチャ要件と主な概念を確認する</span><span class="sxs-lookup"><span data-stu-id="0fb18-103">Review architecture requirements and key concepts for Microsoft Defender for Identity</span></span>


<span data-ttu-id="0fb18-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0fb18-104">**Applies to:**</span></span>
- <span data-ttu-id="0fb18-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0fb18-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="0fb18-106">この記事は、Microsoft Defender for Identity の評価環境をセットアップする手順 [1/3](eval-defender-identity-overview.md) です。</span><span class="sxs-lookup"><span data-stu-id="0fb18-106">This article is [Step 1 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="0fb18-107">このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0fb18-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="0fb18-108">Microsoft Defender for Identity を有効にする前に、アーキテクチャを理解し、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0fb18-108">Before enabling Microsoft Defender for Identity, be sure you understand the architecture and can meet the requirements.</span></span>

<span data-ttu-id="0fb18-109">Microsoft Defender for Identity は、機械学習と行動分析を使用して、クラウド ID に関連するユーザー サインイン リスクの検出と予防に加えて、オンプレミス ネットワーク全体の攻撃を特定します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-109">Microsoft Defender for Identity uses machine learning and behavioral analytics to identify attacks across your on-premises network along with detecting and proactively preventing user sign-in risks associated with cloud identities.</span></span> <span data-ttu-id="0fb18-110">詳細については [、「Microsoft Defender for Identity とは」を参照してください。](/defender-for-identity/what-is)</span><span class="sxs-lookup"><span data-stu-id="0fb18-110">For more information, see [What is Microsoft Defender for Identity?](/defender-for-identity/what-is)</span></span>

<span data-ttu-id="0fb18-111">Defender for Identity は、オンプレミスの Active Directory ユーザーおよび/またはユーザーを組織 (Azure Azure Active Directory) にAD。</span><span class="sxs-lookup"><span data-stu-id="0fb18-111">Defender for Identity protects your on-premises Active Directory users and/or users synced to your Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="0fb18-112">Azure ユーザーだけが構成する環境を保護するには、「Azure AD Id [Protection」を参照ADしてください](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="0fb18-112">To protect an environment made up of only Azure AD users, see [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="0fb18-113">アーキテクチャを理解する</span><span class="sxs-lookup"><span data-stu-id="0fb18-113">Understand the architecture</span></span>

<span data-ttu-id="0fb18-114">次の図は、Defender for Identity のベースライン アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="0fb18-114">The following diagram illustrates the baseline architecture for Defender for Identity.</span></span> 

![Microsoft Defender for Identity のアーキテクチャ](../../media/defender/m365-defender-identity-architecture.png)

<span data-ttu-id="0fb18-116">この図では、次の例を示します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-116">In this illustration:</span></span>
- <span data-ttu-id="0fb18-117">ドメイン コントローラーにインストールADは、ログとネットワーク トラフィックを解析し、分析とレポートのために Microsoft Defender for Identity に送信します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-117">Sensors installed on AD domain controllers parse logs and network traffic and send them to Microsoft Defender for Identity for analysis and reporting.</span></span>
-  <span data-ttu-id="0fb18-118">Azure AD がフェデレーション認証 (図の点線) を使用するように構成されている場合、センサーは Active Directory フェデレーション サービス (AD FS) を解析できます。</span><span class="sxs-lookup"><span data-stu-id="0fb18-118">Sensors can also parse Active Directory Federation Services (AD FS) when Azure AD is configured to use federated authentication (dotted line in illustration).</span></span> 
- <span data-ttu-id="0fb18-119">Microsoft Defender for Identity は、拡張検出Microsoft 365 Defender応答 (XDR) のシグナルを共有します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-119">Microsoft Defender for Identity shares signals to Microsoft 365 Defender for extended detection and response (XDR).</span></span>


<span data-ttu-id="0fb18-120">Defender for Identity センサーは、次のサーバーに直接インストールできます。</span><span class="sxs-lookup"><span data-stu-id="0fb18-120">Defender for Identity sensors can be directly installed on the following servers:</span></span>

- <span data-ttu-id="0fb18-121">ドメイン コントローラー: センサーは、専用サーバーやポート ミラーリングの構成を必要とせずに、ドメイン コントローラーのトラフィックを直接監視します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-121">Domain controllers: The sensor directly monitors domain controller traffic, without the need for a dedicated server, or configuration of port mirroring.</span></span>
- <span data-ttu-id="0fb18-122">AD FS: センサーはネットワーク トラフィックと認証イベントを直接監視します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-122">AD FS: The sensor directly monitors network traffic and authentication events.</span></span>

<span data-ttu-id="0fb18-123">Defender for Identity のアーキテクチャの詳細については、「Microsoft Defender for Identity architecture」を参照Cloud App Securityを[参照してください](/defender-for-identity/architecture)。</span><span class="sxs-lookup"><span data-stu-id="0fb18-123">For a deeper look into the architecture of Defender for Identity, including integration with Cloud App Security, see [Microsoft Defender for Identity architecture](/defender-for-identity/architecture).</span></span>


## <a name="understand-key-concepts"></a><span data-ttu-id="0fb18-124">主要な概念を理解する</span><span class="sxs-lookup"><span data-stu-id="0fb18-124">Understand key concepts</span></span>

<span data-ttu-id="0fb18-125">次の表では、Microsoft Defender for Identity の評価、構成、展開を行う際に重要な重要な概念を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fb18-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Identity.</span></span>


|<span data-ttu-id="0fb18-126">概念</span><span class="sxs-lookup"><span data-stu-id="0fb18-126">Concept</span></span>  |<span data-ttu-id="0fb18-127">説明</span><span class="sxs-lookup"><span data-stu-id="0fb18-127">Description</span></span> |<span data-ttu-id="0fb18-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0fb18-128">More information</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="0fb18-129">監視対象のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="0fb18-129">Monitored activities</span></span> | <span data-ttu-id="0fb18-130">Defender for Identity は、組織内から生成されたシグナルを監視して、疑わしいアクティビティや悪意のあるアクティビティを検出し、潜在的な脅威の有効性を判断し、効果的にトリアージして対応できます。</span><span class="sxs-lookup"><span data-stu-id="0fb18-130">Defender for Identity monitors signals generated from within your organization to detect suspicious or malicious activity and helps you determine the validity of each potential threat so that you can effectively triage and respond.</span></span>  |  [<span data-ttu-id="0fb18-131">Microsoft Defender for Identity 監視アクティビティ</span><span class="sxs-lookup"><span data-stu-id="0fb18-131">Microsoft Defender for Identity monitored activities</span></span>](/defender-for-identity/monitored-activities)       |
| <span data-ttu-id="0fb18-132">セキュリティの警告</span><span class="sxs-lookup"><span data-stu-id="0fb18-132">Security alerts</span></span>    | <span data-ttu-id="0fb18-133">Defender for Identity セキュリティ アラートは、ネットワーク上のセンサーによって検出された疑わしいアクティビティと、各脅威に関係するアクターとコンピューターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-133">Defender for Identity security alerts explain the suspicious activities detected by sensors on your network along with the actors and computers involved in each threat.</span></span>   | [<span data-ttu-id="0fb18-134">Microsoft Defender for Identity Security Alerts</span><span class="sxs-lookup"><span data-stu-id="0fb18-134">Microsoft Defender for Identity Security Alerts</span></span>](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| <span data-ttu-id="0fb18-135">エンティティ プロファイル</span><span class="sxs-lookup"><span data-stu-id="0fb18-135">Entity profiles</span></span>    | <span data-ttu-id="0fb18-136">エンティティ プロファイルは、アクセス履歴と共に、ユーザー、コンピューター、デバイス、およびリソースに関する包括的な詳細な調査を提供します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-136">Entity profiles provide a comprehensive deep-dive investigation of users, computers, devices, and resources along with their access history.</span></span>   | [<span data-ttu-id="0fb18-137">エンティティ プロファイルについて</span><span class="sxs-lookup"><span data-stu-id="0fb18-137">Understanding entity profiles</span></span>](/defender-for-identity/entity-profiles)  |
| <span data-ttu-id="0fb18-138">横方向の移動パス</span><span class="sxs-lookup"><span data-stu-id="0fb18-138">Lateral movement paths</span></span>    | <span data-ttu-id="0fb18-139">MDI セキュリティインサイトの重要なコンポーネントは、攻撃者が機密性の高いアカウントを使用してネットワーク全体の機密性の高いアカウントやコンピューターにアクセスする横方向の移動パスを特定する方法です。</span><span class="sxs-lookup"><span data-stu-id="0fb18-139">A key component of MDI security insights is identifying lateral movement paths in which an attacker uses non-sensitive accounts to gain access to sensitive accounts or machines throughout your network.</span></span>  | [<span data-ttu-id="0fb18-140">Microsoft Defender for Identity Lateral Movement Path (LMP)</span><span class="sxs-lookup"><span data-stu-id="0fb18-140">Microsoft Defender for Identity Lateral Movement Paths (LMPs)</span></span>](/defender-for-identity/use-case-lateral-movement-path)  |
| <span data-ttu-id="0fb18-141">ネットワーク名の解決</span><span class="sxs-lookup"><span data-stu-id="0fb18-141">Network Name Resolution</span></span>    |  <span data-ttu-id="0fb18-142">ネットワーク名解決 (NNR) は、ネットワーク トラフィック、Windows イベント、ETW などに基づいてアクティビティをキャプチャし、この生データを各アクティビティに関係する関連するコンピューターに関連付ける MDI 機能のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="0fb18-142">Network Name Resolution (NNR) is a component of MDI functionality which captures activities based on network traffic, Windows events, ETW, etc. and correlates this raw data to the relevant computers involved in each activity.</span></span>       | [<span data-ttu-id="0fb18-143">ネットワーク名の解決とは</span><span class="sxs-lookup"><span data-stu-id="0fb18-143">What is Network Name Resolution?</span></span>](/defender-for-identity/nnr-policy)      |
| <span data-ttu-id="0fb18-144">レポート</span><span class="sxs-lookup"><span data-stu-id="0fb18-144">Reports</span></span>    | <span data-ttu-id="0fb18-145">Defender for Identity レポートを使用すると、システムとエンティティの状態情報を提供するレポートをスケジュールまたは即座に生成およびダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0fb18-145">Defender for Identity reports allow you to schedule or immediately generate and download reports that provide system and entity status information.</span></span>  <span data-ttu-id="0fb18-146">システムの正常性、セキュリティアラート、および環境で検出された潜在的な横方向の移動パスに関するレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0fb18-146">You can create reports about system health, security alerts, and potential lateral movement paths detected in your environment.</span></span>   | [<span data-ttu-id="0fb18-147">Microsoft Defender for Identity Reports </span><span class="sxs-lookup"><span data-stu-id="0fb18-147">Microsoft Defender for Identity Reports </span></span>](/defender-for-identity/reports)       |
| <span data-ttu-id="0fb18-148">役割グループ</span><span class="sxs-lookup"><span data-stu-id="0fb18-148">Role groups</span></span>    | <span data-ttu-id="0fb18-149">Defender for Identity は、管理者、ユーザー、閲覧者を含む組織の特定のセキュリティとコンプライアンスのニーズに応じて、役割ベースのグループと委任されたアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0fb18-149">Defender for Identity offers role-based groups and delegated access to safeguard data according to your organization's specific security and compliance needs which includes Administrators, Users and Viewers.</span></span>        |  [<span data-ttu-id="0fb18-150">Microsoft Defender for Identity の役割グループ</span><span class="sxs-lookup"><span data-stu-id="0fb18-150">Microsoft Defender for Identity role groups</span></span>](/defender-for-identity/role-groups)       |
| <span data-ttu-id="0fb18-151">管理ポータル</span><span class="sxs-lookup"><span data-stu-id="0fb18-151">Administrative portal</span></span>    |  <span data-ttu-id="0fb18-152">セキュリティ センターにMicrosoft 365、Defender for Identity ポータル キャブを使用して、疑わしいアクティビティの監視と対応を行います。</span><span class="sxs-lookup"><span data-stu-id="0fb18-152">In addition to the Microsoft 365 Security Center, the Defender for Identity portal cab be used to monitor and respond to suspicious activity.</span></span>      | [<span data-ttu-id="0fb18-153">Microsoft Defender for Identity ポータルの操作</span><span class="sxs-lookup"><span data-stu-id="0fb18-153">Working with the Microsoft Defender for Identity portal</span></span>](/defender-for-identity/workspace-portal)        |
| <span data-ttu-id="0fb18-154">Microsoft Cloud App Security統合</span><span class="sxs-lookup"><span data-stu-id="0fb18-154">Microsoft Cloud App Security integration</span></span>   | <span data-ttu-id="0fb18-155">Microsoft Cloud App Security Microsoft Defender for Identity と統合して、クラウド アプリとオンプレミスの両方のハイブリッド環境全体でユーザー エンティティの動作分析 (UEBA) を提供する</span><span class="sxs-lookup"><span data-stu-id="0fb18-155">Microsoft Cloud App Security integrates with Microsoft Defender for Identity to provide user entity behavioral analytics (UEBA) across a hybrid environment - both cloud app and on-premises</span></span>   | <span data-ttu-id="0fb18-156">Id 統合用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0fb18-156">Microsoft Defender for Identity integration</span></span>  |
| | | |


## <a name="review-prerequisites"></a><span data-ttu-id="0fb18-157">前提条件の確認</span><span class="sxs-lookup"><span data-stu-id="0fb18-157">Review prerequisites</span></span>

<span data-ttu-id="0fb18-158">Defender for Identity では、オンプレミスの ID とネットワーク コンポーネントが最小要件を満たしていることを確認するために、いくつかの前提条件となる作業が必要です。</span><span class="sxs-lookup"><span data-stu-id="0fb18-158">Defender for Identity requires some prerequisite work to ensure that your on-premises identity and networking components meet minimum requirements.</span></span> <span data-ttu-id="0fb18-159">この記事をチェックリストとして使用して、環境の準備ができていることを確認します [。Microsoft Defender for Identity の前提条件](/defender-for-identity/prerequisites)です。</span><span class="sxs-lookup"><span data-stu-id="0fb18-159">Use this article as a checklist to ensure your environment is ready: [Microsoft Defender for Identity prerequisites](/defender-for-identity/prerequisites).</span></span>


## <a name="next-steps"></a><span data-ttu-id="0fb18-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="0fb18-160">Next steps</span></span>

<span data-ttu-id="0fb18-161">手順 2/3: [評価環境 Defender for Identity を有効にする](eval-defender-identity-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="0fb18-161">Step 2 of 3: [Enable the evaluation environment Defender for Identity](eval-defender-identity-enable-eval.md)</span></span>

<span data-ttu-id="0fb18-162">Id の Microsoft Defender の [評価の概要に戻る](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0fb18-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="0fb18-163">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0fb18-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span> 