---
title: 脅威調査 & 応答能力-Microsoft Defender for Office 365 プラン2
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
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender for Office 365 プランの脅威の調査および応答機能について説明します。
ms.openlocfilehash: 7ae61e7ea70d8be5c31ec12443c8943f6e54bcf4
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561257"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="97e6e-103">脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="97e6e-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="97e6e-104">[Microsoft Defender For Office 365 の](office-365-atp.md)脅威の調査と応答の機能セキュリティアナリストと管理者は、次のようにして、組織の microsoft 365 をビジネスユーザーに保護します。</span><span class="sxs-lookup"><span data-stu-id="97e6e-104">Threat investigation and response capabilities in [Microsoft Defender for Office 365](office-365-atp.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="97e6e-105">Cyberattacks を容易に識別、監視、理解できるようにする</span><span class="sxs-lookup"><span data-stu-id="97e6e-105">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="97e6e-106">Exchange Online、SharePoint Online、OneDrive for Business、および Microsoft Teams での脅威への迅速な対応</span><span class="sxs-lookup"><span data-stu-id="97e6e-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="97e6e-107">組織に対する cyberattacks を防止するためにセキュリティ操作を支援するための洞察と知識の提供</span><span class="sxs-lookup"><span data-stu-id="97e6e-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="97e6e-108">メールベースの重要な脅威に対して [Office 365 で自動化された調査と応答](automated-investigation-response-office.md) を使用する</span><span class="sxs-lookup"><span data-stu-id="97e6e-108">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="97e6e-109">脅威の調査と応答の機能によって、セキュリティ & コンプライアンスセンターで利用可能な脅威と関連する応答アクションが洞察されます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Security & Compliance Center.</span></span> <span data-ttu-id="97e6e-110">これらの洞察は、組織のセキュリティチームが電子メールまたはファイルベースの攻撃からユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-110">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="97e6e-111">機能は、ユーザーアクティビティ、認証、電子メール、危険にさらされた Pc、セキュリティインシデントなど、複数のソースからのデータを監視し、データを収集するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-111">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="97e6e-112">ビジネス意思決定者およびセキュリティ運用チームは、この情報を使用して組織との脅威を理解し、知的財産権を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-112">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="97e6e-113">脅威の調査と応答のツールについて理解する</span><span class="sxs-lookup"><span data-stu-id="97e6e-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="97e6e-114">脅威の調査と応答の機能は、セキュリティ & コンプライアンスセンターで、次のような一連のツールと応答のワークフローとして提供されます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-114">Threat investigation and response capabilities surface in the Security & Compliance Center, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="97e6e-115">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="97e6e-115">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="97e6e-116">Explorer</span><span class="sxs-lookup"><span data-stu-id="97e6e-116">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="97e6e-117">インシデント</span><span class="sxs-lookup"><span data-stu-id="97e6e-117">Incidents</span></span>](#incidents)
- [<span data-ttu-id="97e6e-118">攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="97e6e-118">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="97e6e-119">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="97e6e-119">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="97e6e-120">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="97e6e-120">Threat dashboard</span></span>

<span data-ttu-id="97e6e-121">脅威ダッシュボード ( [セキュリティダッシュボード](security-dashboard.md)とも呼ばれます) を使用して、どのような脅威が解決されたかをすばやく確認し、Microsoft 365 サービスがビジネスをどのようにセキュリティ保護しているかをビジネス意思決定者に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-121">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Microsoft 365 services are securing your business.</span></span>

![脅威ダッシュボード](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

<span data-ttu-id="97e6e-123">このダッシュボードを表示して使用するには、セキュリティ & コンプライアンスセンターで、[**脅威管理**] ダッシュボードに移動し \> **Dashboard** ます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-123">To view and use this dashboard, in the Security & Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

### <a name="threat-explorer"></a><span data-ttu-id="97e6e-124">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="97e6e-124">Threat Explorer</span></span>

<span data-ttu-id="97e6e-125">脅威 [エクスプローラー (およびリアルタイム検出)](threat-explorer.md) を使用して脅威を分析し、時間の経過と共に攻撃の量を確認し、脅威ファミリ、攻撃インフラストラクチャなどによるデータの分析を行います。</span><span class="sxs-lookup"><span data-stu-id="97e6e-125">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="97e6e-126">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティアナリストの調査ワークフローの出発点です。</span><span class="sxs-lookup"><span data-stu-id="97e6e-126">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![脅威エクスプローラー](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="97e6e-128">このレポートを表示して使用するには、セキュリティ & コンプライアンスセンターで、[**脅威管理** エクスプローラー] に移動し \> **Explorer** ます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-128">To view and use this report, in the Security & Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="97e6e-129">インシデント</span><span class="sxs-lookup"><span data-stu-id="97e6e-129">Incidents</span></span>

<span data-ttu-id="97e6e-130">インシデントリスト (調査とも呼ばれます) を使用して、フライトセキュリティインシデントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="97e6e-130">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="97e6e-131">インシデントは、不審な電子メールメッセージなどの脅威を追跡し、さらに調査と修復を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-131">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![Office 365 の現在の脅威インシデントの一覧](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="97e6e-133">組織の現在のインシデントの一覧を表示するには、セキュリティ & コンプライアンスセンターで、[ **脅威管理** の \> **レビュー** \> **インシデント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97e6e-133">To view the list of current incidents for your organization, in the Security & Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>

![[セキュリティ & コンプライアンスセンター] で、[脅威管理のレビュー] を選択します。 \>](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="97e6e-135">攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="97e6e-135">Attack Simulator</span></span>

<span data-ttu-id="97e6e-136">アタックシミュレータを使用して、組織内で現実的な cyberattacks を設定して実行し、実際の cyberattack がビジネスに影響を与える前に、脆弱性のある人物を特定します。</span><span class="sxs-lookup"><span data-stu-id="97e6e-136">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="97e6e-137">詳細については、「 [Office 365 のアタックシミュレータ](attack-simulator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e6e-137">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="97e6e-138">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="97e6e-138">Automated investigation and response</span></span>

<span data-ttu-id="97e6e-139">自動化された調査と応答 (AIR) 機能を使用して、コンテンツ、デバイス、およびユーザーを組織内の脅威から危険に関連付ける時間と労力を節約します。</span><span class="sxs-lookup"><span data-stu-id="97e6e-139">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="97e6e-140">AIR プロセスは、特定の警告がトリガーされたとき、またはセキュリティ操作チームによって開始されたときに開始できます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-140">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="97e6e-141">詳細については、「 [Office 365 の自動調査と応答](automated-investigation-response-office.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e6e-141">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="97e6e-142">脅威インテリジェンスウィジェット</span><span class="sxs-lookup"><span data-stu-id="97e6e-142">Threat intelligence widgets</span></span>

<span data-ttu-id="97e6e-143">セキュリティアナリストは、Microsoft Defender for Office 365 プラン2のサービスの一部として、既知の脅威の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-143">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="97e6e-144">これは、ユーザーを安全に保つために実行できる追加の予防策/手順があるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-144">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![最近の脅威に関する情報を示すセキュリティ傾向](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="97e6e-146">これらの機能はどのように入手できますか?</span><span class="sxs-lookup"><span data-stu-id="97e6e-146">How do we get these capabilities?</span></span>

<span data-ttu-id="97e6e-147">Microsoft 365 の脅威の調査と応答の機能は、Enterprise E5 または特定のサブスクリプションのアドオンとして組み込まれている Office 365 プラン2の Microsoft Defender に含まれています。</span><span class="sxs-lookup"><span data-stu-id="97e6e-147">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="97e6e-148">詳細については、「 [Defender For Office 365 プラン1およびプラン 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e6e-148">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="97e6e-149">必要な役割と権限</span><span class="sxs-lookup"><span data-stu-id="97e6e-149">Required roles and permissions</span></span>

<span data-ttu-id="97e6e-150">Microsoft Defender for Office 365 は、役割ベースのアクセス制御を使用します。</span><span class="sxs-lookup"><span data-stu-id="97e6e-150">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="97e6e-151">アクセス許可は、Azure Active Directory、Microsoft 365 管理センター、またはセキュリティ & コンプライアンスセンターの特定の役割によって割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-151">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="97e6e-152">セキュリティ管理者などの一部の役割は、セキュリティ & コンプライアンスセンターで割り当てることができますが、代わりに Microsoft 365 管理センターまたは Azure Active Directory のどちらかを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="97e6e-152">Although some roles, such as Security Administrator, can be assigned in the Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="97e6e-153">役割、役割グループ、およびアクセス許可の詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e6e-153">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="97e6e-154">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="97e6e-154">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
>
> - [<span data-ttu-id="97e6e-155">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="97e6e-155">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|<span data-ttu-id="97e6e-156">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="97e6e-156">Activity</span></span>|<span data-ttu-id="97e6e-157">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="97e6e-157">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="97e6e-158">脅威ダッシュボード (または新しい [セキュリティダッシュボード](security-dashboard.md)) を使用する</span><span class="sxs-lookup"><span data-stu-id="97e6e-158">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <br/><span data-ttu-id="97e6e-159">最近の脅威または現在の脅威に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="97e6e-159">View information about recent or current threats</span></span>|<span data-ttu-id="97e6e-160">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="97e6e-160">One of the following:</span></span> <br/><span data-ttu-id="97e6e-161">- **グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="97e6e-161">- **Global Administrator**</span></span>  <br/> <span data-ttu-id="97e6e-162">- **セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="97e6e-162">- **Security Administrator**</span></span> <br/><span data-ttu-id="97e6e-163">- **セキュリティリーダ**</span><span class="sxs-lookup"><span data-stu-id="97e6e-163">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="97e6e-164">これらの役割は、Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) または Microsoft 365 admin center () のいずれかで割り当てることができ [https://admin.microsoft.com](https://admin.microsoft.com) ます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-164">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span>|
|<span data-ttu-id="97e6e-165">脅威 [エクスプローラー (およびリアルタイム検出)](threat-explorer.md) を使用して脅威を分析する</span><span class="sxs-lookup"><span data-stu-id="97e6e-165">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="97e6e-166">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="97e6e-166">One of the following:</span></span> <br/><span data-ttu-id="97e6e-167">- **グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="97e6e-167">- **Global Administrator**</span></span>  <br/> <span data-ttu-id="97e6e-168">- **セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="97e6e-168">- **Security Administrator**</span></span> <br/><span data-ttu-id="97e6e-169">- **セキュリティリーダ**</span><span class="sxs-lookup"><span data-stu-id="97e6e-169">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="97e6e-170">これらの役割は、Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) または Microsoft 365 admin center () のいずれかで割り当てることができ [https://admin.microsoft.com](https://admin.microsoft.com) ます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-170">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span>|
|<span data-ttu-id="97e6e-171">インシデント (調査とも呼ばれる) を表示する</span><span class="sxs-lookup"><span data-stu-id="97e6e-171">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="97e6e-172">インシデントに電子メールメッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="97e6e-172">Add email messages to an incident</span></span>|<span data-ttu-id="97e6e-173">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="97e6e-173">One of the following:</span></span> <br/><span data-ttu-id="97e6e-174">- **グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="97e6e-174">- **Global Administrator**</span></span>  <br/> <span data-ttu-id="97e6e-175">- **セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="97e6e-175">- **Security Administrator**</span></span> <br/><span data-ttu-id="97e6e-176">- **セキュリティリーダ**</span><span class="sxs-lookup"><span data-stu-id="97e6e-176">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="97e6e-177">これらの役割は、Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) または Microsoft 365 admin center () のいずれかで割り当てることができ [https://admin.microsoft.com](https://admin.microsoft.com) ます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-177">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span>|
|<span data-ttu-id="97e6e-178">インシデントで電子メールアクションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="97e6e-178">Trigger email actions in an incident</span></span> <br/> <br/> <span data-ttu-id="97e6e-179">疑わしい電子メールメッセージの検索と削除</span><span class="sxs-lookup"><span data-stu-id="97e6e-179">Find and delete suspicious email messages</span></span>|<span data-ttu-id="97e6e-180">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="97e6e-180">One of the following:</span></span> <br/><span data-ttu-id="97e6e-181">- **グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="97e6e-181">- **Global Administrator**</span></span>  <br/> <span data-ttu-id="97e6e-182">- **セキュリティ管理者** 、 **および検索と削除** の役割</span><span class="sxs-lookup"><span data-stu-id="97e6e-182">- **Security Administrator** plus the **Search and Purge** role</span></span><br/><br/><span data-ttu-id="97e6e-183">**グローバル管理** 者および **セキュリティ管理者** の役割は、Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) または Microsoft 365 admin center () のいずれかに割り当てることができ [https://admin.microsoft.com](https://admin.microsoft.com) ます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-183">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span> <br/><br/><span data-ttu-id="97e6e-184">**検索および削除** の役割は、セキュリティ & コンプライアンスセンター () で割り当てる必要があり [https://protection.office.com](https://protection.office.com) ます。</span><span class="sxs-lookup"><span data-stu-id="97e6e-184">The **Search and Purge** role must be assigned in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>|
|<span data-ttu-id="97e6e-185">エンドポイントの Microsoft Defender と Office 365 プラン2の統合</span><span class="sxs-lookup"><span data-stu-id="97e6e-185">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span>  <br/><br/> <span data-ttu-id="97e6e-186">Microsoft Defender for Office 365 プラン2を SIEM サーバーと統合する</span><span class="sxs-lookup"><span data-stu-id="97e6e-186">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="97e6e-187">**グローバル管理者** または Azure Active Directory () または Microsoft 365 admin center () のいずれかに割り当てられている **セキュリティ管理者** の役割 [https://portal.azure.com](https://portal.azure.com) [https://admin.microsoft.com](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="97e6e-187">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span><br/><span data-ttu-id="97e6e-188">--- **plus** ---</span><span class="sxs-lookup"><span data-stu-id="97e6e-188">--- **plus** ---</span></span><br/><span data-ttu-id="97e6e-189">追加のアプリケーション ( [Microsoft Defender セキュリティセンター](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) 、SIEM サーバーなど) で割り当てられている適切な役割</span><span class="sxs-lookup"><span data-stu-id="97e6e-189">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server)</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="97e6e-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="97e6e-190">Next steps</span></span>

- [<span data-ttu-id="97e6e-191">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="97e6e-191">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="97e6e-192">配信された悪意のある電子メールを検索して調査する (Office 365 の脅威の調査と応答)</span><span class="sxs-lookup"><span data-stu-id="97e6e-192">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="97e6e-193">エンドポイントの Microsoft Defender で Office 365 の脅威の調査と応答を統合する</span><span class="sxs-lookup"><span data-stu-id="97e6e-193">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-wdatp.md)

- [<span data-ttu-id="97e6e-194">アタックシミュレータについて</span><span class="sxs-lookup"><span data-stu-id="97e6e-194">Learn about Attack Simulator</span></span>](attack-simulator.md)
