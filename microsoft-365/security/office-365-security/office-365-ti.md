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
ms.openlocfilehash: b0a9ff9c06f7e97d6f74c901c156bfae6c9eb91d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083706"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="c349b-103">脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="c349b-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c349b-104">**対象**</span><span class="sxs-lookup"><span data-stu-id="c349b-104">**Applies To**</span></span>
- [<span data-ttu-id="c349b-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="c349b-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="c349b-106">[Microsoft Defender](defender-for-office-365.md) for Office 365の脅威調査と対応機能は、セキュリティ アナリストと管理者が、次の方法で組織のMicrosoft 365を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c349b-106">Threat investigation and response capabilities in [Microsoft Defender for Office 365](defender-for-office-365.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="c349b-107">サイバー攻撃の特定、監視、および理解を容易に行う</span><span class="sxs-lookup"><span data-stu-id="c349b-107">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="c349b-108">オンライン、オンライン、オンライン、Exchange Online、SharePointの脅威に迅速OneDrive for Business対処Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c349b-108">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="c349b-109">セキュリティ操作が組織に対するサイバー攻撃を防ぐのに役立つ洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="c349b-109">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="c349b-110">電子メール[ベースの重大な脅威に対するOffice 365](automated-investigation-response-office.md)の自動調査と対応を採用する</span><span class="sxs-lookup"><span data-stu-id="c349b-110">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="c349b-111">脅威の調査と対応機能は、脅威と関連する対応アクションに関する分析情報を提供します。これは、Microsoft 365 Defenderポータルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="c349b-111">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c349b-112">これらの分析情報は、組織のセキュリティ チームが電子メールまたはファイル ベースの攻撃からユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c349b-112">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="c349b-113">この機能は、信号を監視し、ユーザーアクティビティ、認証、電子メール、侵害された PC、セキュリティ インシデントなど、複数のソースからのデータを収集するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c349b-113">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="c349b-114">ビジネス上の意思決定者とセキュリティ運用チームは、この情報を使用して、組織に対する脅威を理解し、対応し、知的財産を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="c349b-114">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="c349b-115">脅威の調査と対応ツールについて知る</span><span class="sxs-lookup"><span data-stu-id="c349b-115">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="c349b-116">脅威の調査と対応機能は、Microsoft 365 Defenderを含むツールと応答ワークフローのセットとして、Microsoft 365 Defender ポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c349b-116">Threat investigation and response capabilities surface in the Microsoft 365 Defender portal, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="c349b-117">Explorer</span><span class="sxs-lookup"><span data-stu-id="c349b-117">Explorer</span></span>](#explorer)
- [<span data-ttu-id="c349b-118">インシデント</span><span class="sxs-lookup"><span data-stu-id="c349b-118">Incidents</span></span>](#incidents)
- [<span data-ttu-id="c349b-119">攻撃シミュレーションのトレーニング</span><span class="sxs-lookup"><span data-stu-id="c349b-119">Attack simulation training</span></span>](attack-simulation-training.md)
- [<span data-ttu-id="c349b-120">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="c349b-120">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="explorer"></a><span data-ttu-id="c349b-121">エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="c349b-121">Explorer</span></span>

<span data-ttu-id="c349b-122">[エクスプローラー (およびリアルタイム](threat-explorer.md)の検出) を使用して、脅威を分析し、時間の当たって攻撃の量を確認し、脅威ファミリ、攻撃者インフラストラクチャなどによってデータを分析します。</span><span class="sxs-lookup"><span data-stu-id="c349b-122">Use [Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="c349b-123">エクスプローラー (脅威エクスプローラーとも呼ばれます) は、セキュリティ アナリストの調査ワークフローの開始場所です。</span><span class="sxs-lookup"><span data-stu-id="c349b-123">Explorer (also referred to as Threat Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![脅威エクスプローラー](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="c349b-125">このレポートを表示して使用するには、Microsoft 365 Defenderポータルで、[電子メール] &**に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="c349b-125">To view and use this report, in the Microsoft 365 Defender portal, go to **Email & collaboration** > **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="c349b-126">インシデント</span><span class="sxs-lookup"><span data-stu-id="c349b-126">Incidents</span></span>

<span data-ttu-id="c349b-127">フライト セキュリティ インシデントの一覧を表示するには、[インシデント] リスト (これは [調査] とも呼ばれる) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c349b-127">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="c349b-128">インシデントは、疑わしい電子メール メッセージなどの脅威を追跡し、さらに調査と修復を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c349b-128">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![現在の脅威インシデントの一覧 (Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="c349b-130">組織の現在のインシデントの一覧を表示するには、Microsoft 365 Defenderポータルで、[インシデント] &**通知します**  >  。</span><span class="sxs-lookup"><span data-stu-id="c349b-130">To view the list of current incidents for your organization, in the Microsoft 365 Defender portal, go to **Incidents & alerts** > **Incidents**.</span></span>

![セキュリティ コンプライアンス センターで&の管理レビューを選択 \> します。](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulation-training"></a><span data-ttu-id="c349b-132">攻撃シミュレーションのトレーニング</span><span class="sxs-lookup"><span data-stu-id="c349b-132">Attack simulation training</span></span>

<span data-ttu-id="c349b-133">攻撃シミュレーション トレーニングを使用して、組織内で現実的なサイバー攻撃を設定して実行し、実際のサイバー攻撃がビジネスに影響を与える前に脆弱なユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="c349b-133">Use Attack simulation training to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="c349b-134">詳細については、「フィッシング攻撃 [をシミュレートする」を参照してください](attack-simulation-training.md)。</span><span class="sxs-lookup"><span data-stu-id="c349b-134">To learn more, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

<span data-ttu-id="c349b-135">この機能を Microsoft 365 Defenderポータルで表示および使用するには、「メール &**攻撃シミュレーション トレーニング**」  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c349b-135">To view and use this feature in the Microsoft 365 Defender portal, go to **Email & collaboration** > **Attack simulation training**.</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="c349b-136">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="c349b-136">Automated investigation and response</span></span>

<span data-ttu-id="c349b-137">自動調査と応答 (AIR) 機能を使用して、組織内の脅威から危険にさらされているコンテンツ、デバイス、およびユーザーを関連付ける時間と労力を節約します。</span><span class="sxs-lookup"><span data-stu-id="c349b-137">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="c349b-138">AIR プロセスは、特定のアラートがトリガーされるたびに、またはセキュリティ運用チームによって開始されるたびに開始できます。</span><span class="sxs-lookup"><span data-stu-id="c349b-138">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="c349b-139">詳細については、「自動調査[と応答」を参照Office 365。](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="c349b-139">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="c349b-140">脅威インテリジェンス ウィジェット</span><span class="sxs-lookup"><span data-stu-id="c349b-140">Threat intelligence widgets</span></span>

<span data-ttu-id="c349b-141">Microsoft Defender for Office 365プラン 2 の提供の一環として、セキュリティ アナリストは既知の脅威に関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c349b-141">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="c349b-142">これは、ユーザーを安全に保つために実行できる追加の予防措置/手順が含まれるかどうかを判断する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c349b-142">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![最近の脅威に関する情報を示すセキュリティの傾向](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="c349b-144">これらの機能を取得する方法</span><span class="sxs-lookup"><span data-stu-id="c349b-144">How do we get these capabilities?</span></span>

<span data-ttu-id="c349b-145">Microsoft 365の脅威調査と対応機能は、Enterprise E5 または特定のサブスクリプションのアドオンとして含まれる Office 365 プラン 2 の Microsoft Defender に含まれています。</span><span class="sxs-lookup"><span data-stu-id="c349b-145">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="c349b-146">詳細については[、「Defender for Office 365 1」および「Plan 2」を参照してください](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。</span><span class="sxs-lookup"><span data-stu-id="c349b-146">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="c349b-147">必要な役割と権限</span><span class="sxs-lookup"><span data-stu-id="c349b-147">Required roles and permissions</span></span>

<span data-ttu-id="c349b-148">Microsoft Defender for Office 365ロール ベースのアクセス制御を使用します。</span><span class="sxs-lookup"><span data-stu-id="c349b-148">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="c349b-149">アクセス許可は、Azure Active Directory、Microsoft 365 管理センター、またはMicrosoft 365 Defenderされます。</span><span class="sxs-lookup"><span data-stu-id="c349b-149">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Microsoft 365 Defender portal.</span></span>

> [!TIP]
> <span data-ttu-id="c349b-150">セキュリティ管理者などの一部の役割は、Microsoft 365 Defender ポータルで割り当てることができますが、代わりに、Microsoft 365 管理センターまたはAzure Active Directory使用してください。</span><span class="sxs-lookup"><span data-stu-id="c349b-150">Although some roles, such as Security Administrator, can be assigned in the Microsoft 365 Defender portal, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="c349b-151">役割、役割グループ、およびアクセス許可の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c349b-151">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="c349b-152">Microsoft 365 Defender ポータルのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c349b-152">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
> - [<span data-ttu-id="c349b-153">Azure Active Directory での管理者ロールのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c349b-153">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

<br>

****

|<span data-ttu-id="c349b-154">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="c349b-154">Activity</span></span>|<span data-ttu-id="c349b-155">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="c349b-155">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="c349b-156">[脅威の管理&管理] ダッシュボード (または新しい[セキュリティ ダッシュボード) を使用する](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="c349b-156">Use the Threat & Vulnerability Management dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="c349b-157">最近または現在の脅威に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="c349b-157">View information about recent or current threats</span></span>|<span data-ttu-id="c349b-158">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="c349b-158">One of the following:</span></span> <ul><li><span data-ttu-id="c349b-159">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="c349b-159">**Global Administrator**</span></span></li><li><span data-ttu-id="c349b-160">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="c349b-160">**Security Administrator**</span></span></li><li><span data-ttu-id="c349b-161">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="c349b-161">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="c349b-162">これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c349b-162">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="c349b-163">エクスプローラー [(およびリアルタイムの検出) を使用して](threat-explorer.md) 脅威を分析する</span><span class="sxs-lookup"><span data-stu-id="c349b-163">Use [Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="c349b-164">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="c349b-164">One of the following:</span></span> <ul><li><span data-ttu-id="c349b-165">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="c349b-165">**Global Administrator**</span></span></li><li><span data-ttu-id="c349b-166">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="c349b-166">**Security Administrator**</span></span></li><li><span data-ttu-id="c349b-167">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="c349b-167">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="c349b-168">これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c349b-168">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="c349b-169">インシデントの表示 (調査とも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="c349b-169">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="c349b-170">インシデントへの電子メール メッセージの追加</span><span class="sxs-lookup"><span data-stu-id="c349b-170">Add email messages to an incident</span></span>|<span data-ttu-id="c349b-171">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="c349b-171">One of the following:</span></span> <ul><li><span data-ttu-id="c349b-172">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="c349b-172">**Global Administrator**</span></span></li><li><span data-ttu-id="c349b-173">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="c349b-173">**Security Administrator**</span></span></li><li><span data-ttu-id="c349b-174">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="c349b-174">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="c349b-175">これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c349b-175">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="c349b-176">インシデントで電子メール アクションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="c349b-176">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="c349b-177">疑わしいメール メッセージの検索と削除</span><span class="sxs-lookup"><span data-stu-id="c349b-177">Find and delete suspicious email messages</span></span>|<span data-ttu-id="c349b-178">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="c349b-178">One of the following:</span></span> <ul><li><span data-ttu-id="c349b-179">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="c349b-179">**Global Administrator**</span></span></li><li><span data-ttu-id="c349b-180">**セキュリティ管理者** と検索 **と削除の役割**</span><span class="sxs-lookup"><span data-stu-id="c349b-180">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="c349b-181">グローバル **管理者とセキュリティ\*\*\*\*管理者の** 役割は、管理者 ( ) または Azure Active Directory ( <https://portal.azure.com> ) で割りMicrosoft 365 管理センターできます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c349b-181">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="c349b-182">検索 **と削除の役割** は、Microsoft 36 Defender ポータル () のメール & **グループ** の役割に割り当てる必要があります <https://security.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c349b-182">The **Search and Purge** role must be assigned in the **Email & collaboration roles** in the Microsoft 36 Defender portal (<https://security.microsoft.com>).</span></span>|
|<span data-ttu-id="c349b-183">Microsoft Defender for Office 365プラン 2 と Microsoft Defender for Endpoint を統合する</span><span class="sxs-lookup"><span data-stu-id="c349b-183">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span> <p> <span data-ttu-id="c349b-184">Microsoft Defender for Office 365プラン 2 を SIEM サーバーに統合する</span><span class="sxs-lookup"><span data-stu-id="c349b-184">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="c349b-185">[グローバル **管理者] または** **[セキュリティ管理者**] の役割が 、Azure Active Directory ( ) または [セキュリティ管理者] Microsoft 365 管理センター <https://portal.azure.com> のいずれかです <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c349b-185">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="c349b-186">--- **plus** --- </span><span class="sxs-lookup"><span data-stu-id="c349b-186">--- **plus** --- </span></span><p> <span data-ttu-id="c349b-187">追加のアプリケーションで割り当てられた適切な役割[](/windows/security/threat-protection/microsoft-defender-atp/user-roles)(Microsoft Defender セキュリティ センター SIEM サーバーなど)。</span><span class="sxs-lookup"><span data-stu-id="c349b-187">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="c349b-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="c349b-188">Next steps</span></span>

- [<span data-ttu-id="c349b-189">脅威トラッカーの詳細 - 新機能と注目に値する</span><span class="sxs-lookup"><span data-stu-id="c349b-189">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
- [<span data-ttu-id="c349b-190">配信された悪意のある電子メールを検索して調査する (Office 365の調査と応答)</span><span class="sxs-lookup"><span data-stu-id="c349b-190">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="c349b-191">脅威Office 365と対応を Microsoft Defender for Endpoint と統合する</span><span class="sxs-lookup"><span data-stu-id="c349b-191">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-mde.md)
- [<span data-ttu-id="c349b-192">フィッシング攻撃をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="c349b-192">Simulate a phishing attack</span></span>](attack-simulation-training.md)
