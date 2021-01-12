---
title: 脅威の調査&対応機能 - Microsoft Defender for Office 365 プラン 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
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
description: Microsoft Defender for Office 365 プランの脅威の調査と対応の機能について説明します。
ms.openlocfilehash: dc6a3dec096b6834d024cc4ff74a5b7600c33d45
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794234"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="511ad-103">脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="511ad-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="511ad-104">[Office 365](office-365-atp.md)向け Microsoft Defender の脅威の調査および対応機能は、セキュリティ アナリストと管理者が次の方法で組織のビジネス ユーザー向け Microsoft 365 を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="511ad-104">Threat investigation and response capabilities in [Microsoft Defender for Office 365](office-365-atp.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="511ad-105">サイバー攻撃の特定、監視、および理解を容易に</span><span class="sxs-lookup"><span data-stu-id="511ad-105">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="511ad-106">Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams の脅威に迅速に対処する</span><span class="sxs-lookup"><span data-stu-id="511ad-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="511ad-107">セキュリティ運用が組織に対するサイバー攻撃を防ぐのに役立つ洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="511ad-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="511ad-108">電子メール [ベースの重要な脅威に対する Office 365 での](automated-investigation-response-office.md) 自動調査と対応の採用</span><span class="sxs-lookup"><span data-stu-id="511ad-108">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="511ad-109">脅威の調査と対応の機能は、セキュリティ/コンプライアンス センターで利用可能な脅威と関連する対応アクション&提供します。</span><span class="sxs-lookup"><span data-stu-id="511ad-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Security & Compliance Center.</span></span> <span data-ttu-id="511ad-110">これらの分析情報は、組織のセキュリティ チームが電子メールまたはファイル ベースの攻撃からユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="511ad-110">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="511ad-111">この機能は、ユーザーアクティビティ、認証、電子メール、侵害された PC、セキュリティ インシデントなど、シグナルを監視し、複数のソースからデータを収集するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="511ad-111">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="511ad-112">ビジネス意思決定者とセキュリティ運用チームは、この情報を使用して、組織に対する脅威を理解して対応し、知的財産を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="511ad-112">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="511ad-113">脅威の調査と対応のツールについて知る</span><span class="sxs-lookup"><span data-stu-id="511ad-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="511ad-114">脅威の調査と対応の機能は、セキュリティ & コンプライアンス センターに、次のような一連のツールと対応ワークフローとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="511ad-114">Threat investigation and response capabilities surface in the Security & Compliance Center, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="511ad-115">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="511ad-115">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="511ad-116">Explorer</span><span class="sxs-lookup"><span data-stu-id="511ad-116">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="511ad-117">インシデント</span><span class="sxs-lookup"><span data-stu-id="511ad-117">Incidents</span></span>](#incidents)
- [<span data-ttu-id="511ad-118">攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="511ad-118">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="511ad-119">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="511ad-119">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="511ad-120">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="511ad-120">Threat dashboard</span></span>

<span data-ttu-id="511ad-121">脅威ダッシュボード (これはセキュリティ ダッシュボードとも呼 [ばれます)](security-dashboard.md)を使用して、対処された脅威をすばやく確認し、Microsoft 365 サービスがビジネスをセキュリティで保護している方法をビジネスの意思決定者に視覚的に報告する方法として使用します。</span><span class="sxs-lookup"><span data-stu-id="511ad-121">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Microsoft 365 services are securing your business.</span></span>

![脅威ダッシュボード](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

<span data-ttu-id="511ad-123">このダッシュボードを表示して使用するには、セキュリティ & コンプライアンス センターで、脅威管理 **ダッシュボードに移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="511ad-123">To view and use this dashboard, in the Security & Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

### <a name="threat-explorer"></a><span data-ttu-id="511ad-124">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="511ad-124">Threat Explorer</span></span>

<span data-ttu-id="511ad-125">脅威 [エクスプローラー (および](threat-explorer.md) リアルタイムの検出) を使用して、脅威の分析、時間の中での攻撃の量の確認、脅威ファミリや攻撃者のインフラストラクチャなどのデータの分析を行います。</span><span class="sxs-lookup"><span data-stu-id="511ad-125">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="511ad-126">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティ アナリストの調査ワークフローの開始場所です。</span><span class="sxs-lookup"><span data-stu-id="511ad-126">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![脅威エクスプローラー](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="511ad-128">このレポートを表示して使用するには、セキュリティ & コンプライアンス センターで、脅威管理 **エクスプローラーに移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="511ad-128">To view and use this report, in the Security & Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="511ad-129">インシデント</span><span class="sxs-lookup"><span data-stu-id="511ad-129">Incidents</span></span>

<span data-ttu-id="511ad-130">インシデント リスト (これは調査とも呼ばれる) を使用して、フライト中のセキュリティ インシデントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="511ad-130">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="511ad-131">インシデントは、疑わしい電子メール メッセージなどの脅威を追跡し、さらに調査と修復を行うのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="511ad-131">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![Office 365 の現在の脅威インシデントのリスト](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="511ad-133">組織の現在のインシデントの一覧を表示するには、セキュリティ/コンプライアンス センターで、[脅威&レビュー インシデント] に \>  \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="511ad-133">To view the list of current incidents for your organization, in the Security & Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>

![セキュリティ/コンプライアンス センターで&管理レビューを選択 \> します。](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="511ad-135">攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="511ad-135">Attack Simulator</span></span>

<span data-ttu-id="511ad-136">攻撃シミュレータを使用して、組織で現実的なサイバー攻撃を設定して実行し、実際のサイバー攻撃がビジネスに影響を与える前に脆弱なユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="511ad-136">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="511ad-137">詳細については、「Office [365」を参照](attack-simulator.md)してください。</span><span class="sxs-lookup"><span data-stu-id="511ad-137">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="511ad-138">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="511ad-138">Automated investigation and response</span></span>

<span data-ttu-id="511ad-139">自動調査および対応 (AIR) 機能を使用して、組織内の脅威から危険にさらされているコンテンツ、デバイス、およびユーザーを関連付ける時間と労力を節約します。</span><span class="sxs-lookup"><span data-stu-id="511ad-139">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="511ad-140">AIR プロセスは、特定のアラートがトリガーされた場合や、セキュリティ運用チームによって開始された場合に開始できます。</span><span class="sxs-lookup"><span data-stu-id="511ad-140">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="511ad-141">詳細については、Office [365 での自動調査と対応を参照](automated-investigation-response-office.md)してください。</span><span class="sxs-lookup"><span data-stu-id="511ad-141">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="511ad-142">脅威インテリジェンス ウィジェット</span><span class="sxs-lookup"><span data-stu-id="511ad-142">Threat intelligence widgets</span></span>

<span data-ttu-id="511ad-143">Microsoft Defender for Office 365 プラン 2 サービスの一部として、セキュリティ アナリストは既知の脅威に関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="511ad-143">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="511ad-144">これは、ユーザーの安全を確保するために実行できる追加の予防手段/手順が含まれるかどうかを判断する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="511ad-144">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![最近の脅威に関する情報を示すセキュリティの傾向](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="511ad-146">これらの機能を取得する方法</span><span class="sxs-lookup"><span data-stu-id="511ad-146">How do we get these capabilities?</span></span>

<span data-ttu-id="511ad-147">Microsoft 365 脅威の調査および対応機能は、Enterprise E5 または特定のサブスクリプションのアドオンとして含まれる Office 365 プラン 2 の Microsoft Defender に含まれています。</span><span class="sxs-lookup"><span data-stu-id="511ad-147">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="511ad-148">詳細については [、「Defender for Office 365 プラン 1 およびプラン 2」を参照してください](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。</span><span class="sxs-lookup"><span data-stu-id="511ad-148">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="511ad-149">必要な役割と権限</span><span class="sxs-lookup"><span data-stu-id="511ad-149">Required roles and permissions</span></span>

<span data-ttu-id="511ad-150">Microsoft Defender for Office 365 は、役割ベースのアクセス制御を使用します。</span><span class="sxs-lookup"><span data-stu-id="511ad-150">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="511ad-151">アクセス許可は、Azure Active Directory、Microsoft 365 管理センター、またはセキュリティ/コンプライアンス センターの特定のロール&割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="511ad-151">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="511ad-152">セキュリティ管理者などの一部の役割はセキュリティ & コンプライアンス センターで割り当てることができますが、代わりに Microsoft 365 管理センターまたは Azure Active Directory の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="511ad-152">Although some roles, such as Security Administrator, can be assigned in the Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="511ad-153">役割、役割グループ、およびアクセス許可の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="511ad-153">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="511ad-154">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="511ad-154">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
>
> - [<span data-ttu-id="511ad-155">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="511ad-155">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|<span data-ttu-id="511ad-156">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="511ad-156">Activity</span></span>|<span data-ttu-id="511ad-157">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="511ad-157">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="511ad-158">脅威ダッシュボード (または新しいセキュリティ ダッシュボード)[を使用する](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="511ad-158">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="511ad-159">最近または現在の脅威に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="511ad-159">View information about recent or current threats</span></span>|<span data-ttu-id="511ad-160">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="511ad-160">One of the following:</span></span> <ul><li><span data-ttu-id="511ad-161">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="511ad-161">**Global Administrator**</span></span></li><li><span data-ttu-id="511ad-162">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="511ad-162">**Security Administrator**</span></span></li><li><span data-ttu-id="511ad-163">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="511ad-163">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="511ad-164">これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="511ad-164">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="511ad-165">脅威 [エクスプローラー (およびリアルタイムの検出) を使用して](threat-explorer.md) 脅威を分析する</span><span class="sxs-lookup"><span data-stu-id="511ad-165">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="511ad-166">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="511ad-166">One of the following:</span></span> <ul><li><span data-ttu-id="511ad-167">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="511ad-167">**Global Administrator**</span></span></li><li><span data-ttu-id="511ad-168">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="511ad-168">**Security Administrator**</span></span></li><li><span data-ttu-id="511ad-169">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="511ad-169">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="511ad-170">これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="511ad-170">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="511ad-171">インシデントの表示 (調査とも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="511ad-171">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="511ad-172">インシデントに電子メール メッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="511ad-172">Add email messages to an incident</span></span>|<span data-ttu-id="511ad-173">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="511ad-173">One of the following:</span></span> <ul><li><span data-ttu-id="511ad-174">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="511ad-174">**Global Administrator**</span></span></li><li><span data-ttu-id="511ad-175">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="511ad-175">**Security Administrator**</span></span></li><li><span data-ttu-id="511ad-176">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="511ad-176">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="511ad-177">これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="511ad-177">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="511ad-178">インシデントでメール アクションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="511ad-178">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="511ad-179">不審な電子メール メッセージを検索して削除する</span><span class="sxs-lookup"><span data-stu-id="511ad-179">Find and delete suspicious email messages</span></span>|<span data-ttu-id="511ad-180">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="511ad-180">One of the following:</span></span> <ul><li><span data-ttu-id="511ad-181">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="511ad-181">**Global Administrator**</span></span></li><li><span data-ttu-id="511ad-182">**セキュリティ管理者** と **"Search and Purge/検索と消去" 役割**</span><span class="sxs-lookup"><span data-stu-id="511ad-182">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="511ad-183">グローバル **管理者ロールと\*\*\*\*セキュリティ** 管理者ロールは、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="511ad-183">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="511ad-184">Search **and Purge 役割は** 、セキュリティ/コンプライアンス センター () &割り当てられている必要があります <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="511ad-184">The **Search and Purge** role must be assigned in the Security & Compliance Center (<https://protection.office.com>).</span></span>|
|<span data-ttu-id="511ad-185">Microsoft Defender for Office 365 プラン 2 と Microsoft Defender for Endpoint の統合</span><span class="sxs-lookup"><span data-stu-id="511ad-185">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span>  <p> <span data-ttu-id="511ad-186">Microsoft Defender for Office 365 プラン 2 と SIEM サーバーの統合</span><span class="sxs-lookup"><span data-stu-id="511ad-186">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="511ad-187">Azure  Active Directory  ( ) または Microsoft 365 管理センター ( ) で割り当てられたグローバル管理者または <https://portal.azure.com> セキュリティ管理者の役割のいずれか <https://admin.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="511ad-187">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="511ad-188">--- **plus** --- </span><span class="sxs-lookup"><span data-stu-id="511ad-188">--- **plus** --- </span></span><p> <span data-ttu-id="511ad-189">追加のアプリケーション [(Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) セキュリティ センターや SIEM サーバーなど) で割り当てられた適切な役割。</span><span class="sxs-lookup"><span data-stu-id="511ad-189">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="511ad-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="511ad-190">Next steps</span></span>

- [<span data-ttu-id="511ad-191">脅威トラッカーの詳細 - 新機能と注目すべき機能</span><span class="sxs-lookup"><span data-stu-id="511ad-191">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="511ad-192">配信された悪意のあるメールを検索して調査する (Office 365 脅威の調査と対応)</span><span class="sxs-lookup"><span data-stu-id="511ad-192">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="511ad-193">Office 365 脅威の調査と対応を Microsoft Defender for Endpoint と統合する</span><span class="sxs-lookup"><span data-stu-id="511ad-193">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-wdatp.md)

- [<span data-ttu-id="511ad-194">攻撃シミュレータの詳細</span><span class="sxs-lookup"><span data-stu-id="511ad-194">Learn about Attack Simulator</span></span>](attack-simulator.md)
