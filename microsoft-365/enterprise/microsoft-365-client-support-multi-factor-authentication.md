---
title: 'Microsoft 365 クライアント アプリのサポート: 多要素認証'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 の多要素認証をサポートするプラットフォーム、クライアント、および PowerShell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097470"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="aa47f-103">Microsoft 365 クライアント アプリのサポート: 多要素認証</span><span class="sxs-lookup"><span data-stu-id="aa47f-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="aa47f-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="aa47f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="aa47f-105">サインインの追加レベルのセキュリティを提供するために、クライアントは多要素認証 (MFA) を使用するように構成できます。MFA は、次に基づいてユーザー パスワードと追加のユーザー検証方法の両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa47f-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and an additional user verification method based on:</span></span>

- <span data-ttu-id="aa47f-106">スマートフォンなど、簡単に複製できない所有物。</span><span class="sxs-lookup"><span data-stu-id="aa47f-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="aa47f-107">指紋、顔、その他の生体認証属性など、ユーザーが独自に持っているもの</span><span class="sxs-lookup"><span data-stu-id="aa47f-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="aa47f-108">多要素認証 [について詳しくは、次のリンクを参照してください](/azure/active-directory/authentication/multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="aa47f-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="aa47f-109">サポートされているクライアント&プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="aa47f-109">Supported clients & platforms</span></span>

<span data-ttu-id="aa47f-110">次のクライアントとプラットフォームの最新バージョンは、多要素認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aa47f-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="aa47f-111">Microsoft 365 でのプラットフォーム サポートの詳細については [、「Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)のシステム要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa47f-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

| <span data-ttu-id="aa47f-112">クライアント</span><span class="sxs-lookup"><span data-stu-id="aa47f-112">Clients</span></span> | <span data-ttu-id="aa47f-113">Android</span><span class="sxs-lookup"><span data-stu-id="aa47f-113">Android</span></span> | <span data-ttu-id="aa47f-114">iOS</span><span class="sxs-lookup"><span data-stu-id="aa47f-114">iOS</span></span> | <span data-ttu-id="aa47f-115">Mac</span><span class="sxs-lookup"><span data-stu-id="aa47f-115">Mac</span></span>| <span data-ttu-id="aa47f-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="aa47f-116">Windows 10</span></span> <br> <span data-ttu-id="aa47f-117">最新のアプリ</span><span class="sxs-lookup"><span data-stu-id="aa47f-117">Modern Apps</span></span>| <span data-ttu-id="aa47f-118">Windows 10</span><span class="sxs-lookup"><span data-stu-id="aa47f-118">Windows 10</span></span> <br> <span data-ttu-id="aa47f-119">Desktop</span><span class="sxs-lookup"><span data-stu-id="aa47f-119">Desktop</span></span> |
|:---|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="aa47f-120">Azure Active Directory 管理者</span><span class="sxs-lookup"><span data-stu-id="aa47f-120">Azure Active Directory Admin</span></span> | <span data-ttu-id="aa47f-121">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-121">N/A</span></span> | <span data-ttu-id="aa47f-122">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-122">N/A</span></span> | <span data-ttu-id="aa47f-123">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-123">N/A</span></span> | <span data-ttu-id="aa47f-124">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-124">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-126">Access</span><span class="sxs-lookup"><span data-stu-id="aa47f-126">Access</span></span> | <span data-ttu-id="aa47f-127">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-127">N/A</span></span> | <span data-ttu-id="aa47f-128">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-128">N/A</span></span> | <span data-ttu-id="aa47f-129">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-129">N/A</span></span> | <span data-ttu-id="aa47f-130">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-130">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-132">Azure Admin</span><span class="sxs-lookup"><span data-stu-id="aa47f-132">Azure Admin</span></span> | <span data-ttu-id="aa47f-133">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-133">N/A</span></span> | <span data-ttu-id="aa47f-134">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-134">N/A</span></span> | <span data-ttu-id="aa47f-135">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-135">N/A</span></span> | <span data-ttu-id="aa47f-136">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-136">N/A</span></span> | <span data-ttu-id="aa47f-137">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-137">N/A</span></span> |
| <span data-ttu-id="aa47f-138">ポータル サイト</span><span class="sxs-lookup"><span data-stu-id="aa47f-138">Company portal</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-143">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-143">N/A</span></span> |
| <span data-ttu-id="aa47f-144">Cortana</span><span class="sxs-lookup"><span data-stu-id="aa47f-144">Cortana</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-147">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-147">N/A</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-149">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-149">N/A</span></span> |
| <span data-ttu-id="aa47f-150">Delve</span><span class="sxs-lookup"><span data-stu-id="aa47f-150">Delve</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-153">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-153">N/A</span></span> | <span data-ttu-id="aa47f-154">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-154">N/A</span></span> | <span data-ttu-id="aa47f-155">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-155">N/A</span></span> |
| <span data-ttu-id="aa47f-156">Edge</span><span class="sxs-lookup"><span data-stu-id="aa47f-156">Edge</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-159">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-159">N/A</span></span> | <span data-ttu-id="aa47f-160">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-160">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-162">Excel</span><span class="sxs-lookup"><span data-stu-id="aa47f-162">Excel</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-168">Exchange Online 管理者</span><span class="sxs-lookup"><span data-stu-id="aa47f-168">Exchange Online Admin</span></span> | <span data-ttu-id="aa47f-169">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-169">N/A</span></span> | <span data-ttu-id="aa47f-170">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-170">N/A</span></span> | <span data-ttu-id="aa47f-171">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-171">N/A</span></span> | <span data-ttu-id="aa47f-172">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-172">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-174">Forms</span><span class="sxs-lookup"><span data-stu-id="aa47f-174">Forms</span></span> | <span data-ttu-id="aa47f-175">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-175">N/A</span></span> | <span data-ttu-id="aa47f-176">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-176">N/A</span></span> | <span data-ttu-id="aa47f-177">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-177">N/A</span></span> | <span data-ttu-id="aa47f-178">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-178">N/A</span></span> | <span data-ttu-id="aa47f-179">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-179">N/A</span></span> |
| <span data-ttu-id="aa47f-180">Office 365 管理</span><span class="sxs-lookup"><span data-stu-id="aa47f-180">Office 365 Admin</span></span> | <span data-ttu-id="aa47f-181">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-181">N/A</span></span> | <span data-ttu-id="aa47f-182">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-182">N/A</span></span> | <span data-ttu-id="aa47f-183">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-183">N/A</span></span> | <span data-ttu-id="aa47f-184">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-184">N/A</span></span> | ![サポート](../media/check-mark.png) |  |
| <span data-ttu-id="aa47f-186">Kaizala</span><span class="sxs-lookup"><span data-stu-id="aa47f-186">Kaizala</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-189">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-189">N/A</span></span> | <span data-ttu-id="aa47f-190">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-190">N/A</span></span> | <span data-ttu-id="aa47f-191">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-191">N/A</span></span> |
| <span data-ttu-id="aa47f-192">Office Lens</span><span class="sxs-lookup"><span data-stu-id="aa47f-192">Office Lens</span></span>| ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-195">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-195">N/A</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-197">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-197">N/A</span></span> |
| <span data-ttu-id="aa47f-198">Office モバイル</span><span class="sxs-lookup"><span data-stu-id="aa47f-198">Office mobile</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-201">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-201">N/A</span></span> | <span data-ttu-id="aa47f-202">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-202">N/A</span></span> | <span data-ttu-id="aa47f-203">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-203">N/A</span></span> |
| <span data-ttu-id="aa47f-204">Office ポータル</span><span class="sxs-lookup"><span data-stu-id="aa47f-204">Office portal</span></span> | <span data-ttu-id="aa47f-205">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-205">N/A</span></span> | <span data-ttu-id="aa47f-206">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-206">N/A</span></span> | <span data-ttu-id="aa47f-207">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-207">N/A</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-209">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-209">N/A</span></span> |
| <span data-ttu-id="aa47f-210">OneDrive</span><span class="sxs-lookup"><span data-stu-id="aa47f-210">OneDrive</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-216">OneNote</span><span class="sxs-lookup"><span data-stu-id="aa47f-216">OneNote</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-222">Outlook</span><span class="sxs-lookup"><span data-stu-id="aa47f-222">Outlook</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-228">Planner</span><span class="sxs-lookup"><span data-stu-id="aa47f-228">Planner</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-231">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-231">N/A</span></span> | <span data-ttu-id="aa47f-232">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-232">N/A</span></span> | <span data-ttu-id="aa47f-233">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-233">N/A</span></span> |
| <span data-ttu-id="aa47f-234">Power アプリ</span><span class="sxs-lookup"><span data-stu-id="aa47f-234">Power Apps</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-237">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-237">N/A</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-239">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-239">N/A</span></span> |
| <span data-ttu-id="aa47f-240">Power Automate</span><span class="sxs-lookup"><span data-stu-id="aa47f-240">Power Automate</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-243">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-243">N/A</span></span> | <span data-ttu-id="aa47f-244">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-244">N/A</span></span> | <span data-ttu-id="aa47f-245">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-245">N/A</span></span> |
| <span data-ttu-id="aa47f-246">Power BI</span><span class="sxs-lookup"><span data-stu-id="aa47f-246">Power BI</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-249">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-249">N/A</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-252">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="aa47f-252">PowerPoint</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-258">Project</span><span class="sxs-lookup"><span data-stu-id="aa47f-258">Project</span></span> | <span data-ttu-id="aa47f-259">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-259">N/A</span></span> | <span data-ttu-id="aa47f-260">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-260">N/A</span></span> | <span data-ttu-id="aa47f-261">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-261">N/A</span></span> | <span data-ttu-id="aa47f-262">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-262">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-264">Publisher</span><span class="sxs-lookup"><span data-stu-id="aa47f-264">Publisher</span></span> | <span data-ttu-id="aa47f-265">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-265">N/A</span></span> | <span data-ttu-id="aa47f-266">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-266">N/A</span></span> | <span data-ttu-id="aa47f-267">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-267">N/A</span></span> | <span data-ttu-id="aa47f-268">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-268">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-270">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aa47f-270">Skype for Business</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-274">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-274">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-276">Skype for Business 管理者</span><span class="sxs-lookup"><span data-stu-id="aa47f-276">Skype for Business Admin</span></span> | <span data-ttu-id="aa47f-277">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-277">N/A</span></span> | <span data-ttu-id="aa47f-278">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-278">N/A</span></span> | <span data-ttu-id="aa47f-279">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-279">N/A</span></span> | <span data-ttu-id="aa47f-280">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-280">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-282">SharePoint</span><span class="sxs-lookup"><span data-stu-id="aa47f-282">SharePoint</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-285">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-285">N/A</span></span> | <span data-ttu-id="aa47f-286">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-286">N/A</span></span> | <span data-ttu-id="aa47f-287">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-287">N/A</span></span> |
| <span data-ttu-id="aa47f-288">SharePoint Online 管理者</span><span class="sxs-lookup"><span data-stu-id="aa47f-288">SharePoint Online Admin</span></span> | <span data-ttu-id="aa47f-289">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-289">N/A</span></span> | <span data-ttu-id="aa47f-290">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-290">N/A</span></span> | <span data-ttu-id="aa47f-291">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-291">N/A</span></span> | <span data-ttu-id="aa47f-292">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-292">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-294">付箋</span><span class="sxs-lookup"><span data-stu-id="aa47f-294">Sticky Notes</span></span> | <span data-ttu-id="aa47f-295">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-295">N/A</span></span> | <span data-ttu-id="aa47f-296">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-296">N/A</span></span> | <span data-ttu-id="aa47f-297">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-297">N/A</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-299">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-299">N/A</span></span> |
| <span data-ttu-id="aa47f-300">Stream</span><span class="sxs-lookup"><span data-stu-id="aa47f-300">Stream</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-303">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-303">N/A</span></span> | <span data-ttu-id="aa47f-304">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-304">N/A</span></span> | <span data-ttu-id="aa47f-305">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-305">N/A</span></span> |
| <span data-ttu-id="aa47f-306">Sway</span><span class="sxs-lookup"><span data-stu-id="aa47f-306">Sway</span></span> | <span data-ttu-id="aa47f-307">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-307">N/A</span></span> | <span data-ttu-id="aa47f-308">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-308">N/A</span></span> | <span data-ttu-id="aa47f-309">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-309">N/A</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-311">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-311">N/A</span></span> |
| <span data-ttu-id="aa47f-312">Teams</span><span class="sxs-lookup"><span data-stu-id="aa47f-312">Teams</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-316">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-316">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-318">To Do</span><span class="sxs-lookup"><span data-stu-id="aa47f-318">To Do</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-323">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-323">N/A</span></span> |
| <span data-ttu-id="aa47f-324">Visio</span><span class="sxs-lookup"><span data-stu-id="aa47f-324">Visio</span></span> | <span data-ttu-id="aa47f-325">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-325">N/A</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-327">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-327">N/A</span></span> | <span data-ttu-id="aa47f-328">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-328">N/A</span></span> | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-330">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="aa47f-330">Whiteboard</span></span> | <span data-ttu-id="aa47f-331">計画済み</span><span class="sxs-lookup"><span data-stu-id="aa47f-331">Planned</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-333">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-333">N/A</span></span> | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-335">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-335">N/A</span></span> |
| <span data-ttu-id="aa47f-336">Word</span><span class="sxs-lookup"><span data-stu-id="aa47f-336">Word</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| <span data-ttu-id="aa47f-342">職場の分析</span><span class="sxs-lookup"><span data-stu-id="aa47f-342">Workplace analysis</span></span> | <span data-ttu-id="aa47f-343">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-343">N/A</span></span> | <span data-ttu-id="aa47f-344">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-344">N/A</span></span> | <span data-ttu-id="aa47f-345">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-345">N/A</span></span> | <span data-ttu-id="aa47f-346">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-346">N/A</span></span> | <span data-ttu-id="aa47f-347">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-347">N/A</span></span> |
| <span data-ttu-id="aa47f-348">Yammer</span><span class="sxs-lookup"><span data-stu-id="aa47f-348">Yammer</span></span> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | <span data-ttu-id="aa47f-352">N/A</span><span class="sxs-lookup"><span data-stu-id="aa47f-352">N/A</span></span> | ![サポート](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a><span data-ttu-id="aa47f-354">サポートされている PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="aa47f-354">Supported PowerShell modules</span></span>

- [<span data-ttu-id="aa47f-355">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa47f-355">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="aa47f-356">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa47f-356">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="aa47f-357">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa47f-357">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)