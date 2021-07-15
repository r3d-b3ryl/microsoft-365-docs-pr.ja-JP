---
title: Microsoft 365 でのアプリ ガバナンス
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Microsoft アプリ ガバナンス機能を実装し、アプリを管理します。
ms.openlocfilehash: bc8c739132de52abb69c15479cd851462e9f6ce7
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420314"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a><span data-ttu-id="aca81-103">Microsoft Cloud App Security へのアプリ ガバナンス アドオン (プレビュー版)</span><span class="sxs-lookup"><span data-stu-id="aca81-103">App governance add-on to Microsoft Cloud App Security (in preview)</span></span>

><span data-ttu-id="aca81-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="aca81-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="aca81-105">サイバー攻撃は、オンプレミスやクラウドのインフラに展開しているアプリケーションを悪用する方法がますます巧妙になっており、特権の昇格、横方向の移動、データの流出の開始点となっています。</span><span class="sxs-lookup"><span data-stu-id="aca81-105">Cyberattacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructures, establishing a starting point for privilege escalation, lateral movement, and exfiltration of your data.</span></span> <span data-ttu-id="aca81-106">潜在的なリスクを理解し、この種の攻撃を阻止するためには、組織のアプリ コンプライアンス姿勢を明確に可視化し、アプリが異常な動作を示した場合には迅速に特定し、これらの動作が環境、データ、ユーザーにリスクとなる場合には対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aca81-106">To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture to quickly identify when an app exhibits anomalous behaviors and to respond when these behaviors present risks to your environment, data, and users.</span></span>

<span data-ttu-id="aca81-107">Microsoft Cloud App Security のアドオン機能であるアプリ ガバナンスは、Microsoft Graph API 経由で Microsoft 365 のデータにアクセスする OAuth 対応アプリ向けに設計されたセキュリティおよびポリシー管理機能です。</span><span class="sxs-lookup"><span data-stu-id="aca81-107">The app governance add-on feature to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.</span></span> <span data-ttu-id="aca81-108">アプリ ガバナンスは、実用的な分析情報と自動化されたポリシー アラートおよびアクションを通して、これらのアプリとそのユーザーが Microsoft 365 に保存されている機密データにアクセスし、使用し、共有する方法について、完全な可視性、修復、およびガバナンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="aca81-108">App governance delivers full visibility, remediation, and governance into how these apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions.</span></span>

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

<span data-ttu-id="aca81-109">アプリ ガバナンスは、以下のように包括的に提供されます。</span><span class="sxs-lookup"><span data-stu-id="aca81-109">App governance provides you with comprehensive:</span></span>

- <span data-ttu-id="aca81-110">**分析情報**: テナント内の Microsoft 365 プラットフォーム向けのすべてのサードパーティ製アプリを 1 つのダッシュボードに表示します。</span><span class="sxs-lookup"><span data-stu-id="aca81-110">**Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard.</span></span> <span data-ttu-id="aca81-111">すべてのアプリの状態やアラート アクティビティを確認し、それらに反応したり対応したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="aca81-111">You can see all the apps’ status and alert activities and react or respond to them.</span></span>
- <span data-ttu-id="aca81-112">**ガヴァナンス**: アプリやユーザーのパターンや行動に対するプロアクティブまたはリアクティブなポリシーを作成し、準拠していないアプリや悪意のあるアプリの使用からユーザーを保護し、リスクのあるアプリのデータへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="aca81-112">**Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.</span></span>
- <span data-ttu-id="aca81-113">**検出**: アプリ アクティビティに異常が発生した場合や、準拠していないアプリ、悪意のあるアプリ、リスクのあるアプリが使用された場合に警告や通知が行われます。</span><span class="sxs-lookup"><span data-stu-id="aca81-113">**Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.</span></span>
- <span data-ttu-id="aca81-114">**修復**: 自動修復機能に加えて、アプリケーションの異常なアクティビティの検出に対応するために、修復制御をタイムリーに使用します。</span><span class="sxs-lookup"><span data-stu-id="aca81-114">**Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.</span></span>

<span data-ttu-id="aca81-115">アプリ ガバナンスは、Microsoft 365 アプリ エコシステムに不可欠なプラットフォームベースのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="aca81-115">App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem.</span></span> <span data-ttu-id="aca81-116">アプリ ガバナンスは、Azure Active Directory (Azure AD) に登録され、Microsoft Graph API 経由でデータにアクセスする OAuth 対応アプリを監督し、管理します。</span><span class="sxs-lookup"><span data-stu-id="aca81-116">App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API.</span></span> <span data-ttu-id="aca81-117">アプリ ガバナンスでは、アプリケーションの動作を制御することで、IT インフラストラクチャのセキュリティとコンプライアンスの態勢を強化することができます。</span><span class="sxs-lookup"><span data-stu-id="aca81-117">App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.</span></span>

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a><span data-ttu-id="aca81-118">アプリ ガバナンスを一目見る</span><span class="sxs-lookup"><span data-stu-id="aca81-118">A first glimpse at app governance</span></span>

<span data-ttu-id="aca81-119">アプリ ガバナンスのダッシュボードを表示するには、[https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="aca81-119">To see the app governance dashboard, go to [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="aca81-120">アプリ ガバナンス データを表示するには、サインイン アカウントに[管理者の役割](app-governance-get-started.md#administrator-roles)のいずれかが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="aca81-120">Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a><span data-ttu-id="aca81-121">Azure AD と Microsoft Cloud App Security を使用したアプリ ガバナンスの統合</span><span class="sxs-lookup"><span data-stu-id="aca81-121">App governance integration with Azure AD and Microsoft Cloud App Security</span></span>

<span data-ttu-id="aca81-122">App ガバナンス、Azure AD、Microsoft Cloud App Security は、以下のようなさまざまなデータセットを収集して提供します。</span><span class="sxs-lookup"><span data-stu-id="aca81-122">App governance, Azure AD, and Microsoft Cloud App Security collect and provide different data sets:</span></span>

- <span data-ttu-id="aca81-123">アプリ ガバナンスは、API レベルでのアプリのアクティビティに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="aca81-123">App governance provides detailed information about an app’s activity at the API level.</span></span>
- <span data-ttu-id="aca81-124">Azure AD は、アプリの基礎となるメタデータと、アプリへのサインインに関する詳細な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="aca81-124">Azure AD provides foundational app metadata and detailed information on sign-ins to apps.</span></span>
- <span data-ttu-id="aca81-125">Microsoft Cloud App Security は、アプリのリスク情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="aca81-125">Microsoft Cloud App Security provides app risk information.</span></span>

<span data-ttu-id="aca81-126">アプリ ガバナンス、Azure AD、Microsoft Cloud App Security で情報を共有することで、集約された情報を 1 つのポータルに表示し、詳細情報を得るために別のポータルに簡単にリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="aca81-126">By sharing information across app governance, Azure AD, and Microsoft Cloud App Security, you can display aggregate information in one portal and easily link to another portal for more information.</span></span> <span data-ttu-id="aca81-127">次に、いくつかの例を示します:</span><span class="sxs-lookup"><span data-stu-id="aca81-127">Here are some examples:</span></span>

- <span data-ttu-id="aca81-128">アプリ ガバナンスにおけるアプリのサインイン情報:</span><span class="sxs-lookup"><span data-stu-id="aca81-128">App sign-in information in app governance:</span></span>

  <span data-ttu-id="aca81-129">アプリ ガバナンス ポータルでは、各アプリの集約されたサインイン アクティビティを表示でき、サインイン イベントの詳細については Azure Active Directory 管理センターにリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="aca81-129">From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.</span></span>

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- <span data-ttu-id="aca81-130">Microsoft Cloud App Security ポータルの API 使用情報:</span><span class="sxs-lookup"><span data-stu-id="aca81-130">API usage information in the Microsoft Cloud App Security portal:</span></span>

  <span data-ttu-id="aca81-131">Microsoft Cloud App Security ポータルからは、API の使用レベルや集計データの転送を表示することができ、詳細はアプリ ガバナンス ポータルにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="aca81-131">From the Microsoft Cloud App Security portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.</span></span>

<span data-ttu-id="aca81-132">統合の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aca81-132">Here's a summary of the integration.</span></span>

![Azure AD と Microsoft Cloud App Security を使用したアプリ ガバナンスの統合](..\media\manage-app-protection-governance\mapg-integration.png)

<span data-ttu-id="aca81-134">また、アプリ ガバナンスはそのアラートをシグナルとして Microsoft Cloud App Security と Microsoft 365 Defender に送信し、アプリ ガバナンスは Microsoft Cloud App Security からのアラートを受信することで、アプリベースのセキュリティ インシデントをより詳細に分析することができます。</span><span class="sxs-lookup"><span data-stu-id="aca81-134">Additionally, app governance sends its alerts as signals to Microsoft Cloud App Security and Microsoft 365 Defender, and app governance receives alerts from Microsoft Cloud App Security, to enable more detailed analysis of app-based security incidents.</span></span>

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a><span data-ttu-id="aca81-135">アプリ ガバナンスを使用する</span><span class="sxs-lookup"><span data-stu-id="aca81-135">Using app governance</span></span>

<span data-ttu-id="aca81-136">アプリ ガバナンスを使用して、悪意のあるアプリや不適切な動作をするアプリからテナントとそのデータを保護することは、以下の 3 つのコア機能に該当します。</span><span class="sxs-lookup"><span data-stu-id="aca81-136">Using app governance to protect your tenant and its data from potentially malicious or ill-behaved apps falls into these three core capabilities:</span></span>

| <span data-ttu-id="aca81-137">機能</span><span class="sxs-lookup"><span data-stu-id="aca81-137">Capability</span></span> | <span data-ttu-id="aca81-138">説明</span><span class="sxs-lookup"><span data-stu-id="aca81-138">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="aca81-139">アプリの可視性と分析情報</span><span class="sxs-lookup"><span data-stu-id="aca81-139">App visibility and insights</span></span>](app-governance-visibility-insights-overview.md) | <span data-ttu-id="aca81-140">テナント内の Microsoft 365 アプリケーションのトラフィックとアクティビティを 360° 取得します。</span><span class="sxs-lookup"><span data-stu-id="aca81-140">Get a 360° view on traffic and activity of the Microsoft 365 applications in your tenant.</span></span> |
| [<span data-ttu-id="aca81-141">ガバナンス強化のためのアプリのポリシー</span><span class="sxs-lookup"><span data-stu-id="aca81-141">App policies for reinforced governance</span></span>](app-governance-app-policies-overview.md) | <span data-ttu-id="aca81-142">Microsoft 365 アプリのガバナンスを強化することができるプロアクティブまたはリアクティブなアプリのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aca81-142">Create proactive or reactive app policies, which will allow you to enforce governance for your Microsoft 3635 apps.</span></span> |
| [<span data-ttu-id="aca81-143">検出と修復</span><span class="sxs-lookup"><span data-stu-id="aca81-143">Detection and remediation</span></span>](app-governance-detect-remediate-overview.md) | <span data-ttu-id="aca81-144">プラットフォームの検出アラートやポリシーで生成された検出アラートに基づいて、アプリの異常な動作を監視し、アプリのポリシー設定に基づく自動修復により、または手動でアプリを修復します。</span><span class="sxs-lookup"><span data-stu-id="aca81-144">Based on platform detection alerts or policy-generated detection alerts, monitor your apps for anomalous app behavior and remediate them, either automatically based on app policy settings or manually.</span></span> |
|||
