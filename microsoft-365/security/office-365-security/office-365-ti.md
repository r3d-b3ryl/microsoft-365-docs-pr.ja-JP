---
title: 脅威調査&対応機能 - Microsoft Defender for Office 365 プラン 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender for Office 365プランの脅威調査と対応機能について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9d61da5a12882bef3ffee715bffb37ec96a18fd1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205878"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="e3148-103">脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="e3148-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e3148-104">**対象**</span><span class="sxs-lookup"><span data-stu-id="e3148-104">**Applies To**</span></span>
- [<span data-ttu-id="e3148-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="e3148-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="e3148-106">[Microsoft Defender](defender-for-office-365.md) for Office 365の脅威調査と対応機能は、セキュリティ アナリストと管理者が、次の方法で組織のMicrosoft 365を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3148-106">Threat investigation and response capabilities in [Microsoft Defender for Office 365](defender-for-office-365.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="e3148-107">サイバー攻撃の特定、監視、および理解を容易に行う</span><span class="sxs-lookup"><span data-stu-id="e3148-107">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="e3148-108">オンライン、オンライン、オンライン、Exchange Online、SharePointの脅威に迅速OneDrive for Business対処Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e3148-108">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="e3148-109">セキュリティ操作が組織に対するサイバー攻撃を防ぐのに役立つ洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="e3148-109">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="e3148-110">電子メール[ベースの重大な脅威に対するOffice 365](automated-investigation-response-office.md)の自動調査と対応を採用する</span><span class="sxs-lookup"><span data-stu-id="e3148-110">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="e3148-111">脅威の調査と対応機能は、セキュリティ コンプライアンス センターで利用可能な脅威と関連する対応アクションに関する&提供します。</span><span class="sxs-lookup"><span data-stu-id="e3148-111">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Security & Compliance Center.</span></span> <span data-ttu-id="e3148-112">これらの分析情報は、組織のセキュリティ チームが電子メールまたはファイル ベースの攻撃からユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3148-112">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="e3148-113">この機能は、信号を監視し、ユーザーアクティビティ、認証、電子メール、侵害された PC、セキュリティ インシデントなど、複数のソースからのデータを収集するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3148-113">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="e3148-114">ビジネス上の意思決定者とセキュリティ運用チームは、この情報を使用して、組織に対する脅威を理解し、対応し、知的財産を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="e3148-114">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="e3148-115">脅威の調査と対応ツールについて知る</span><span class="sxs-lookup"><span data-stu-id="e3148-115">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="e3148-116">脅威の調査と対応機能は、次&含む一連のツールと対応ワークフローとして、セキュリティ コンプライアンス センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3148-116">Threat investigation and response capabilities surface in the Security & Compliance Center, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="e3148-117">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e3148-117">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="e3148-118">Explorer</span><span class="sxs-lookup"><span data-stu-id="e3148-118">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="e3148-119">インシデント</span><span class="sxs-lookup"><span data-stu-id="e3148-119">Incidents</span></span>](#incidents)
- [<span data-ttu-id="e3148-120">攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="e3148-120">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="e3148-121">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="e3148-121">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="e3148-122">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e3148-122">Threat dashboard</span></span>

<span data-ttu-id="e3148-123">脅威ダッシュボード (これはセキュリティ ダッシュボードとも呼ばれます)[](security-dashboard.md)を使用して、対処された脅威をすばやく確認し、Microsoft 365 サービスがビジネスをセキュリティで保護している方法をビジネス意思決定者に視覚的に報告します。</span><span class="sxs-lookup"><span data-stu-id="e3148-123">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Microsoft 365 services are securing your business.</span></span>

![脅威ダッシュボード](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

<span data-ttu-id="e3148-125">このダッシュボードを表示して使用するには、セキュリティ &コンプライアンス センターで、[脅威管理ダッシュボード] **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="e3148-125">To view and use this dashboard, in the Security & Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

### <a name="threat-explorer"></a><span data-ttu-id="e3148-126">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="e3148-126">Threat Explorer</span></span>

<span data-ttu-id="e3148-127">脅威 [エクスプローラー (およびリアルタイム](threat-explorer.md) の検出) を使用して、脅威を分析し、時間の間に攻撃の量を確認し、脅威ファミリ、攻撃者インフラストラクチャなどによってデータを分析します。</span><span class="sxs-lookup"><span data-stu-id="e3148-127">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="e3148-128">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティ アナリストの調査ワークフローの開始場所です。</span><span class="sxs-lookup"><span data-stu-id="e3148-128">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![脅威エクスプローラー](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="e3148-130">このレポートを表示して使用するには、セキュリティ &コンプライアンス センターで、[脅威管理エクスプローラー] **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="e3148-130">To view and use this report, in the Security & Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="e3148-131">インシデント</span><span class="sxs-lookup"><span data-stu-id="e3148-131">Incidents</span></span>

<span data-ttu-id="e3148-132">フライト セキュリティ インシデントの一覧を表示するには、[インシデント] リスト (これは [調査] とも呼ばれる) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3148-132">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="e3148-133">インシデントは、疑わしい電子メール メッセージなどの脅威を追跡し、さらに調査と修復を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3148-133">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![現在の脅威インシデントの一覧 (Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="e3148-135">組織の現在のインシデントの一覧を表示するには、セキュリティ コンプライアンス センターで、[脅威&レビュー インシデント] に \>  \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="e3148-135">To view the list of current incidents for your organization, in the Security & Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>

![セキュリティ コンプライアンス センターで&の管理レビューを選択 \> します。](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="e3148-137">攻撃シミュレーター</span><span class="sxs-lookup"><span data-stu-id="e3148-137">Attack Simulator</span></span>

<span data-ttu-id="e3148-138">攻撃シミュレーターを使用して、組織内で現実的なサイバー攻撃を設定して実行し、実際のサイバー攻撃がビジネスに影響を与える前に脆弱なユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="e3148-138">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="e3148-139">詳細については、「攻撃シミュレーター [」を参照Office 365。](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="e3148-139">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="e3148-140">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="e3148-140">Automated investigation and response</span></span>

<span data-ttu-id="e3148-141">自動調査と応答 (AIR) 機能を使用して、組織内の脅威から危険にさらされているコンテンツ、デバイス、およびユーザーを関連付ける時間と労力を節約します。</span><span class="sxs-lookup"><span data-stu-id="e3148-141">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="e3148-142">AIR プロセスは、特定のアラートがトリガーされるたびに、またはセキュリティ運用チームによって開始されるたびに開始できます。</span><span class="sxs-lookup"><span data-stu-id="e3148-142">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="e3148-143">詳細については、「自動調査[と応答」を参照Office 365。](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="e3148-143">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="e3148-144">脅威インテリジェンス ウィジェット</span><span class="sxs-lookup"><span data-stu-id="e3148-144">Threat intelligence widgets</span></span>

<span data-ttu-id="e3148-145">Microsoft Defender for Office 365プラン 2 の提供の一環として、セキュリティ アナリストは既知の脅威に関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e3148-145">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="e3148-146">これは、ユーザーを安全に保つために実行できる追加の予防措置/手順が含まれるかどうかを判断する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3148-146">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![最近の脅威に関する情報を示すセキュリティの傾向](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="e3148-148">これらの機能を取得する方法</span><span class="sxs-lookup"><span data-stu-id="e3148-148">How do we get these capabilities?</span></span>

<span data-ttu-id="e3148-149">Microsoft 365の脅威調査と対応機能は、Enterprise E5 または特定のサブスクリプションのアドオンとして含まれる Office 365 プラン 2 の Microsoft Defender に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3148-149">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="e3148-150">詳細については[、「Defender for Office 365 1」および「Plan 2」を参照してください](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。</span><span class="sxs-lookup"><span data-stu-id="e3148-150">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="e3148-151">必要な役割と権限</span><span class="sxs-lookup"><span data-stu-id="e3148-151">Required roles and permissions</span></span>

<span data-ttu-id="e3148-152">Microsoft Defender for Office 365ロール ベースのアクセス制御を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3148-152">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="e3148-153">アクセス許可は、Azure Active Directory管理センター、Microsoft 365コンプライアンス センターの特定の役割&割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e3148-153">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="e3148-154">セキュリティ管理者などの一部の役割はセキュリティ & コンプライアンス センターで割り当てることができますが、代わりに Microsoft 365 管理センターまたはセキュリティ Azure Active Directoryを使用Azure Active Directoryしてください。</span><span class="sxs-lookup"><span data-stu-id="e3148-154">Although some roles, such as Security Administrator, can be assigned in the Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="e3148-155">役割、役割グループ、およびアクセス許可の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3148-155">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="e3148-156">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e3148-156">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
>
> - [<span data-ttu-id="e3148-157">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e3148-157">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|<span data-ttu-id="e3148-158">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e3148-158">Activity</span></span>|<span data-ttu-id="e3148-159">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="e3148-159">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="e3148-160">脅威ダッシュボード (または新しいセキュリティ ダッシュボード[) を使用する](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="e3148-160">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="e3148-161">最近または現在の脅威に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="e3148-161">View information about recent or current threats</span></span>|<span data-ttu-id="e3148-162">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="e3148-162">One of the following:</span></span> <ul><li><span data-ttu-id="e3148-163">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="e3148-163">**Global Administrator**</span></span></li><li><span data-ttu-id="e3148-164">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="e3148-164">**Security Administrator**</span></span></li><li><span data-ttu-id="e3148-165">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="e3148-165">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="e3148-166">これらの役割は、管理者センター ( ) または Azure Active Directory ( <https://portal.azure.com> ) でMicrosoft 365割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="e3148-166">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="e3148-167">脅威 [エクスプローラー (およびリアルタイム検出) を使用して脅威](threat-explorer.md) を分析する</span><span class="sxs-lookup"><span data-stu-id="e3148-167">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="e3148-168">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="e3148-168">One of the following:</span></span> <ul><li><span data-ttu-id="e3148-169">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="e3148-169">**Global Administrator**</span></span></li><li><span data-ttu-id="e3148-170">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="e3148-170">**Security Administrator**</span></span></li><li><span data-ttu-id="e3148-171">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="e3148-171">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="e3148-172">これらの役割は、管理者センター ( ) または Azure Active Directory ( <https://portal.azure.com> ) でMicrosoft 365割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="e3148-172">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="e3148-173">インシデントの表示 (調査とも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="e3148-173">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="e3148-174">インシデントへの電子メール メッセージの追加</span><span class="sxs-lookup"><span data-stu-id="e3148-174">Add email messages to an incident</span></span>|<span data-ttu-id="e3148-175">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="e3148-175">One of the following:</span></span> <ul><li><span data-ttu-id="e3148-176">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="e3148-176">**Global Administrator**</span></span></li><li><span data-ttu-id="e3148-177">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="e3148-177">**Security Administrator**</span></span></li><li><span data-ttu-id="e3148-178">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="e3148-178">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="e3148-179">これらの役割は、管理者センター ( ) または Azure Active Directory ( <https://portal.azure.com> ) でMicrosoft 365割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="e3148-179">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="e3148-180">インシデントで電子メール アクションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="e3148-180">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="e3148-181">疑わしいメール メッセージの検索と削除</span><span class="sxs-lookup"><span data-stu-id="e3148-181">Find and delete suspicious email messages</span></span>|<span data-ttu-id="e3148-182">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="e3148-182">One of the following:</span></span> <ul><li><span data-ttu-id="e3148-183">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="e3148-183">**Global Administrator**</span></span></li><li><span data-ttu-id="e3148-184">**セキュリティ管理者** と検索 **と削除の役割**</span><span class="sxs-lookup"><span data-stu-id="e3148-184">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="e3148-185">グローバル **管理者とセキュリティ\*\*\*\*管理者の** 役割は、管理者 ( ) または管理者センター ( ) でAzure Active Directory割 <https://portal.azure.com> りMicrosoft 365割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="e3148-185">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="e3148-186">検索 **と削除の役割** は、セキュリティ コンプライアンス センター () &割り当てる必要があります <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="e3148-186">The **Search and Purge** role must be assigned in the Security & Compliance Center (<https://protection.office.com>).</span></span>|
|<span data-ttu-id="e3148-187">Microsoft Defender for Office 365プラン 2 と Microsoft Defender for Endpoint を統合する</span><span class="sxs-lookup"><span data-stu-id="e3148-187">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span>  <p> <span data-ttu-id="e3148-188">Microsoft Defender for Office 365プラン 2 を SIEM サーバーに統合する</span><span class="sxs-lookup"><span data-stu-id="e3148-188">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="e3148-189">[グローバル **管理者]** または[セキュリティ管理者] の役割が 、Azure Active Directory ( ) または管理者センター ( ) にMicrosoft 365 <https://portal.azure.com> 割り当てられます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="e3148-189">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="e3148-190">--- **plus** --- </span><span class="sxs-lookup"><span data-stu-id="e3148-190">--- **plus** --- </span></span><p> <span data-ttu-id="e3148-191">追加のアプリケーションで割り当てられた適切な役割[](/windows/security/threat-protection/microsoft-defender-atp/user-roles)(Microsoft Defender セキュリティ センター SIEM サーバーなど)。</span><span class="sxs-lookup"><span data-stu-id="e3148-191">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="e3148-192">次の手順</span><span class="sxs-lookup"><span data-stu-id="e3148-192">Next steps</span></span>

- [<span data-ttu-id="e3148-193">脅威トラッカーの詳細 - 新機能と注目に値する</span><span class="sxs-lookup"><span data-stu-id="e3148-193">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="e3148-194">配信された悪意のある電子メールを検索して調査する (Office 365の調査と応答)</span><span class="sxs-lookup"><span data-stu-id="e3148-194">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="e3148-195">脅威Office 365と対応を Microsoft Defender for Endpoint と統合する</span><span class="sxs-lookup"><span data-stu-id="e3148-195">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-mde.md)

- [<span data-ttu-id="e3148-196">攻撃シミュレーターの詳細</span><span class="sxs-lookup"><span data-stu-id="e3148-196">Learn about Attack Simulator</span></span>](attack-simulator.md)