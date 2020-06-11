---
title: 組織内のデータプライバシーインシデントを監視して応答する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 監査およびアラートポリシーとデータ主体要求を使用して、個人データインシデントを監視して応答します。
ms.openlocfilehash: 5760bb40eb26e2ff0636ea9604cc7c45b7d0ca63
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695069"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="ef361-103">組織内のデータプライバシーインシデントを監視して応答する</span><span class="sxs-lookup"><span data-stu-id="ef361-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="ef361-104">Microsoft 365 の機能は、operationalize 関連の機能を使用して、組織内のデータプライバシーインシデントの監視、調査、および対応に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="ef361-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="ef361-105">これらのプロセス、手順、およびその他のドキュメントについては、規制機関に準拠していることを示すためにも重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef361-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="ef361-106">これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ef361-106">These include:</span></span> 

- <span data-ttu-id="ef361-107">監査と警告ポリシー</span><span class="sxs-lookup"><span data-stu-id="ef361-107">Auditing and alert policies</span></span>
- <span data-ttu-id="ef361-108">データ主体要求 (コンテンツ検索と電子情報開示を含む)</span><span class="sxs-lookup"><span data-stu-id="ef361-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="ef361-109">その他の調査ツールおよびレポート</span><span class="sxs-lookup"><span data-stu-id="ef361-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="ef361-110">監視および応答ツールの使用に影響を与えるデータプライバシーの規制</span><span class="sxs-lookup"><span data-stu-id="ef361-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="ef361-111">以下は、情報ガバナンス統制に関連する可能性があるデータプライバシー規制の例です。</span><span class="sxs-lookup"><span data-stu-id="ef361-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="ef361-112">LGPD 記事46</span><span class="sxs-lookup"><span data-stu-id="ef361-112">LGPD Article 46</span></span>
- <span data-ttu-id="ef361-113">LGPD 記事48</span><span class="sxs-lookup"><span data-stu-id="ef361-113">LGPD Article 48</span></span>
- <span data-ttu-id="ef361-114">GDPR 記事 (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="ef361-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="ef361-115">GDPR 記事 (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="ef361-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="ef361-116">HIPAA のエコー (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="ef361-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="ef361-117">164.308 (a) (1) (ii) (D))</span><span class="sxs-lookup"><span data-stu-id="ef361-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="ef361-118">HIPAA のエコー (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="ef361-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="ef361-119">164.308 (a) (6.0) (ii)</span><span class="sxs-lookup"><span data-stu-id="ef361-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="ef361-120">HIPAA のエコー (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="ef361-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="ef361-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="ef361-121">164.312(b))</span></span>
- <span data-ttu-id="ef361-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="ef361-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="ef361-123">詳細については、「[データプライバシーのリスクを評価し、機密情報を識別](information-protection-deploy-assess.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef361-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="ef361-124">データのプライバシーに関する規制では、通常、次のものが監視と対応のために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ef361-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="ef361-125">個人データの保存、共有、処理に関連するアクティビティの監査、警告、およびレポート</span><span class="sxs-lookup"><span data-stu-id="ef361-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="ef361-126">データ主体要求 (DSR) に応答する機能と、場合によっては、調査やその他の管理手段を実行してそのような要求に準拠することができます。</span><span class="sxs-lookup"><span data-stu-id="ef361-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="ef361-127">組織では、他の法令遵守やビジネス上の理由など、他の目的のために監視と応答のアクティビティを実行することも必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef361-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="ef361-128">データのプライバシーに関する監視および応答スキームの確立は、全体的な監視および応答の計画、実装、および管理の一環として行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef361-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="ef361-129">データプライバシー規制に関する Microsoft 365 の監視と応答のスキームを開始するために、この記事では、次のような質問に回答するために Microsoft 365 の便利な機能を示します。</span><span class="sxs-lookup"><span data-stu-id="ef361-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="ef361-130">さまざまなデータの種類とソースについて、どのような種類の日常の監視、調査、レポートの手法を使用できますか。</span><span class="sxs-lookup"><span data-stu-id="ef361-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="ef361-131">データ主体要求 (DSRs) と、匿名化、墨消し、削除などの是正措置を処理するには、どのようなメカニズムが必要になります。</span><span class="sxs-lookup"><span data-stu-id="ef361-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="ef361-132">セキュリティ/コンプライアンスセンターの監査とアラートポリシー</span><span class="sxs-lookup"><span data-stu-id="ef361-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="ef361-133">監査、詳細な監査、およびアラートポリシーの設定については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef361-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="ef361-134">統合監査</span><span class="sxs-lookup"><span data-stu-id="ef361-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="ef361-135">メールボックスの監査</span><span class="sxs-lookup"><span data-stu-id="ef361-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="ef361-136">詳細な監査</span><span class="sxs-lookup"><span data-stu-id="ef361-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="ef361-137">通知ポリシー</span><span class="sxs-lookup"><span data-stu-id="ef361-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="ef361-138">GDPR および CCPA のデータ主体要求</span><span class="sxs-lookup"><span data-stu-id="ef361-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="ef361-139">Microsoft 365 での DSR への対応については[、「GDPR および CCPA のデータ主体要求](../compliance/gdpr-dsr-office365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef361-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="ef361-140">Microsoft Stream で削除されたユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="ef361-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="ef361-141">Microsoft Stream の場合、ユーザーが Azure Active Directory (Azure AD) から削除されると、そのユーザーの名前がその時点より前のポストされたストリームビデオに関連付けられていた場合、そのユーザーの電子メールアドレスはビデオと関連付けられたままになります。</span><span class="sxs-lookup"><span data-stu-id="ef361-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="ef361-142">削除するには、「 [Microsoft Stream から削除されたユーザーを管理](https://docs.microsoft.com/stream/managing-deleted-users)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef361-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="ef361-143">その他の調査ツール</span><span class="sxs-lookup"><span data-stu-id="ef361-143">Additional investigative tools</span></span>

<span data-ttu-id="ef361-144">以下に、組織内のデータプライバシーに関連するインシデントの監視、調査、および修復に役立つ可能性がある、次の2つのツールが追加されています。</span><span class="sxs-lookup"><span data-stu-id="ef361-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="ef361-145">Microsoft [365 の Insider リスク管理](../compliance/insider-risk-management.md)(microsoft コンプライアンス管理センター) は、組織内のリスクの高い活動を検出、調査、処理を行うことによって、内部的なリスクを最小限に抑えるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ef361-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="ef361-146">Microsoft [365 のデータ調査](../compliance/overview-data-investigations.md)。 Microsoft のコンプライアンス管理センターの機能で、microsoft の365で機密データ、悪意のあるデータ、または誤ったデータを検索し、そのインシデントを修復するための適切な処置を実行するために何が起こったかを調査します。</span><span class="sxs-lookup"><span data-stu-id="ef361-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
