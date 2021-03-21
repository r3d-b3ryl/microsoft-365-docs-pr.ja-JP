---
title: 組織内のデータ プライバシー インシデントの監視と対応
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 監査ポリシーとアラート ポリシーとデータ主体要求を使用して、個人データ インシデントの監視と対応を行います。
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928426"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="6180a-103">組織内のデータ プライバシー インシデントの監視と対応</span><span class="sxs-lookup"><span data-stu-id="6180a-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="6180a-104">Microsoft 365 の機能を使用すると、関連する機能を運用する組織内のデータ プライバシー インシデントを監視、調査、および対応できます。</span><span class="sxs-lookup"><span data-stu-id="6180a-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="6180a-105">これらの各ドキュメントのプロセス、手順、その他のドキュメントを持つことは、規制機関へのコンプライアンスを実証する上でも重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6180a-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="6180a-106">これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6180a-106">These include:</span></span> 

- <span data-ttu-id="6180a-107">監査ポリシーとアラート ポリシー</span><span class="sxs-lookup"><span data-stu-id="6180a-107">Auditing and alert policies</span></span>
- <span data-ttu-id="6180a-108">データ主体要求 (コンテンツ検索および電子情報開示を含む)</span><span class="sxs-lookup"><span data-stu-id="6180a-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="6180a-109">その他の調査ツールとレポート</span><span class="sxs-lookup"><span data-stu-id="6180a-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="6180a-110">監視および応答ツールの使用に影響を与えるデータプライバシー規制</span><span class="sxs-lookup"><span data-stu-id="6180a-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="6180a-111">情報ガバナンス制御に関連する可能性があるデータプライバシー規制の一覧の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6180a-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="6180a-112">LGPD 第 46 条</span><span class="sxs-lookup"><span data-stu-id="6180a-112">LGPD Article 46</span></span>
- <span data-ttu-id="6180a-113">LGPD 第 48 条</span><span class="sxs-lookup"><span data-stu-id="6180a-113">LGPD Article 48</span></span>
- <span data-ttu-id="6180a-114">GDPR 記事 (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="6180a-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="6180a-115">GDPR 記事 (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="6180a-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="6180a-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="6180a-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="6180a-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="6180a-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="6180a-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="6180a-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="6180a-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="6180a-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="6180a-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="6180a-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="6180a-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="6180a-121">164.312(b))</span></span>
- <span data-ttu-id="6180a-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="6180a-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="6180a-123">詳細については、「データプライバシーリスク [を評価し、機密情報を特定する」を参照してください](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="6180a-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="6180a-124">一般に、データのプライバシーに関する規制では、監視と対応のために次の要求が必要です。</span><span class="sxs-lookup"><span data-stu-id="6180a-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="6180a-125">個人データのストレージ、共有、および処理に関連するアクティビティの監査、警告、およびレポート</span><span class="sxs-lookup"><span data-stu-id="6180a-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="6180a-126">データ主体要求 (DSR) に応答する機能、および場合によっては、そのような要求に準拠するための調査および他の管理措置を実行する機能。</span><span class="sxs-lookup"><span data-stu-id="6180a-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="6180a-127">組織は、他のコンプライアンスニーズやビジネス上の理由など、他の目的で監視および対応活動を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="6180a-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="6180a-128">データプライバシーの監視と対応のスキームを確立するには、全体的な監視と対応の計画、実装、および管理の一環として行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6180a-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="6180a-129">データ プライバシー規制に関する Microsoft 365 の監視と対応のスキームを開始するために、次のような質問に答える Microsoft 365 の便利な機能を示します。</span><span class="sxs-lookup"><span data-stu-id="6180a-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="6180a-130">さまざまなデータ型とソースに対して、どのような種類の監視、調査、レポートの手法が利用できますか?</span><span class="sxs-lookup"><span data-stu-id="6180a-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="6180a-131">データ主体要求 (DSR) と、匿名化、やり直し、削除などの修復アクションを処理するために必要なメカニズム。</span><span class="sxs-lookup"><span data-stu-id="6180a-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="6180a-132">セキュリティ/コンプライアンス センターの監査ポリシーとアラート ポリシー</span><span class="sxs-lookup"><span data-stu-id="6180a-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="6180a-133">監査ポリシー、高度な監査ポリシー、およびアラート ポリシーの設定については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6180a-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="6180a-134">統合監査</span><span class="sxs-lookup"><span data-stu-id="6180a-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="6180a-135">メールボックスの監査</span><span class="sxs-lookup"><span data-stu-id="6180a-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="6180a-136">高度な監査</span><span class="sxs-lookup"><span data-stu-id="6180a-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="6180a-137">通知ポリシー</span><span class="sxs-lookup"><span data-stu-id="6180a-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="6180a-138">GDPR と CCPA のデータ主体要求</span><span class="sxs-lookup"><span data-stu-id="6180a-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="6180a-139">Microsoft 365 での DSR への応答の詳細については [、「GDPR](/compliance/regulatory/gdpr-dsr-Office365) および CCPA のデータ主体要求」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6180a-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="6180a-140">Microsoft Stream で削除されたユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="6180a-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="6180a-141">Microsoft Stream の場合、ユーザーが Azure Active Directory (Azure AD) から削除された場合、その時点より前に投稿された Stream ビデオに名前が関連付けられている場合、そのユーザーの電子メール アドレスはビデオに関連付けられたままです。</span><span class="sxs-lookup"><span data-stu-id="6180a-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="6180a-142">「 [削除したユーザーを Microsoft Stream から管理して削除](/stream/managing-deleted-users) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6180a-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="6180a-143">調査ツールとしてのインサイダー リスク管理</span><span class="sxs-lookup"><span data-stu-id="6180a-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="6180a-144">[Microsoft 365](../compliance/insider-risk-management.md) の Insider リスク管理は、組織内の危険なアクティビティを検出、調査、および実行することで、内部リスクを最小限に抑えるための Microsoft コンプライアンス管理センターの機能です。</span><span class="sxs-lookup"><span data-stu-id="6180a-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>