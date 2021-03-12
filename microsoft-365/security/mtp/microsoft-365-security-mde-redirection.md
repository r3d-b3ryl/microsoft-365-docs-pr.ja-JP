---
title: Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト
description: Defender for Endpoint から Microsoft 365 セキュリティ センターにアカウントとセッションをリダイレクトする方法。
keywords: Microsoft 365 セキュリティ センター、Microsoft 365 セキュリティ センターの使用開始、セキュリティ センターのリダイレクト
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 626bc9950512438bfa43e6500adf72940ddcbfec
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727567"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="536fc-104">Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="536fc-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="536fc-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="536fc-105">**Applies to:**</span></span>
- <span data-ttu-id="536fc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="536fc-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="536fc-107">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="536fc-107">Defender for Endpoint</span></span>

<span data-ttu-id="536fc-108">SIEM と拡張検出および応答 (XDR) による脅威保護に対する Microsoft のクロスドメインアプローチに合わせ、Microsoft Defender Advanced Threat Protection を Microsoft Defender for Endpoint として再ブランド化し、それを単一の統合ポータルである Microsoft 365 セキュリティ センターに統合しました。</span><span class="sxs-lookup"><span data-stu-id="536fc-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="536fc-109">このガイドでは、以前の Microsoft Defender for Endpoint ポータル (securitycenter.windows.com または securitycenter.microsoft.com) から Microsoft 365 セキュリティ センター ポータル (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 セキュリティ センターにルーティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="536fc-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="536fc-110">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は[、Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access)セキュリティ センターでアクセスを許可する方法と同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="536fc-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="536fc-111">何を期待する</span><span class="sxs-lookup"><span data-stu-id="536fc-111">What to expect</span></span>
<span data-ttu-id="536fc-112">自動リダイレクトが有効になると、securitycenter.windows.com または securitycenter.microsoft.com の元の Microsoft Defender for Endpoint ポータルにアクセスするアカウントが、security.microsoft.com の Microsoft 365 セキュリティ センター ポータルに自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="536fc-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="536fc-113">変更点について詳しくは [、Microsoft 365](microsoft-365-security-center-mde.md)セキュリティ センターの Microsoft Defender for Endpoint をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="536fc-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="536fc-114">これには、以前の securitycenter.windows.com ポータルを指すリンク (電子メール通知のリンクなど) や SIEM API 呼び出しによって返されるリンクなど、ブラウザー経由で以前のポータルに直接アクセスするリダイレクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="536fc-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="536fc-115">メール通知または SIEM API からの外部リンクには、現在、両方のポータルへのリンクが含まれている。</span><span class="sxs-lookup"><span data-stu-id="536fc-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="536fc-116">リダイレクトが有効になると、古いリンクが最終的に削除されるまで、両方のリンクが Microsoft 365 セキュリティ センターを指します。</span><span class="sxs-lookup"><span data-stu-id="536fc-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="536fc-117">Microsoft 365 セキュリティ センターを指す新しいリンクを採用してください。</span><span class="sxs-lookup"><span data-stu-id="536fc-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="536fc-118">リンクとルーティングの詳細については、以下の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="536fc-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="536fc-119">SIEM API ルーティング</span><span class="sxs-lookup"><span data-stu-id="536fc-119">SIEM API routing</span></span>

|<span data-ttu-id="536fc-120">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="536fc-120">**Property**</span></span>  |<span data-ttu-id="536fc-121">**リダイレクトが OFF の場合の宛先**</span><span class="sxs-lookup"><span data-stu-id="536fc-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="536fc-122">**リダイレクトが ON の場合の宛先**</span><span class="sxs-lookup"><span data-stu-id="536fc-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="536fc-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="536fc-123">LinkToWDATP</span></span> | <span data-ttu-id="536fc-124">[アラート] ページ (securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="536fc-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="536fc-125">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="536fc-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="536fc-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="536fc-127">[インシデント] ページ (securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="536fc-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="536fc-128">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="536fc-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="536fc-129">LinkToMTP</span></span> | <span data-ttu-id="536fc-130">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="536fc-131">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="536fc-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="536fc-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="536fc-133">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="536fc-134">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="536fc-135">電子メールアラート通知</span><span class="sxs-lookup"><span data-stu-id="536fc-135">Email alert notifications</span></span>

|<span data-ttu-id="536fc-136">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="536fc-136">**Property**</span></span>  |<span data-ttu-id="536fc-137">**リダイレクトが OFF の場合の宛先**</span><span class="sxs-lookup"><span data-stu-id="536fc-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="536fc-138">**リダイレクトが ON の場合の宛先**</span><span class="sxs-lookup"><span data-stu-id="536fc-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="536fc-139">[アラート] ページ</span><span class="sxs-lookup"><span data-stu-id="536fc-139">Alert page</span></span>  | <span data-ttu-id="536fc-140">[アラート] ページ (securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="536fc-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="536fc-141">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="536fc-142">インシデント ページ</span><span class="sxs-lookup"><span data-stu-id="536fc-142">Incident page</span></span>  |<span data-ttu-id="536fc-143">[インシデント] ページ (securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="536fc-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="536fc-144">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="536fc-145">セキュリティ センター ポータルの [アラート] ページ</span><span class="sxs-lookup"><span data-stu-id="536fc-145">Alert page in security center portal</span></span> | <span data-ttu-id="536fc-146">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="536fc-147">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="536fc-148">セキュリティ センター ポータルのインシデント ページ</span><span class="sxs-lookup"><span data-stu-id="536fc-148">Incident page in security center portal</span></span> | <span data-ttu-id="536fc-149">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="536fc-150">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="536fc-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="536fc-151">これはいつ有効になりますか?</span><span class="sxs-lookup"><span data-stu-id="536fc-151">When does this take effect?</span></span> 
<span data-ttu-id="536fc-152">有効にすると、この更新プログラムは一部のアカウントでほぼ直ちに有効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="536fc-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="536fc-153">ただし、リダイレクトが組織内のすべてのアカウントに伝達されるのに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="536fc-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="536fc-154">この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出されません。現在のセッションを終了して再びサインインした後にのみ、Microsoft 365 セキュリティ センターにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="536fc-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="536fc-155">ポータルリダイレクトの設定</span><span class="sxs-lookup"><span data-stu-id="536fc-155">Set up portal redirection</span></span>
<span data-ttu-id="536fc-156">Microsoft 365 セキュリティ センターへのアカウントのルーティングを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="536fc-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="536fc-157">Azure Active directory でグローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="536fc-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="536fc-158">[](https://security.microsoft.com/) Microsoft 365 セキュリティ センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="536fc-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="536fc-159">[設定エンドポイント **]**  >  **[全般ポータル]**  >  **リダイレクト**  >  **に移動するか、**[ここをクリックします](https://security.microsoft.com/preferences2/portal_redirection)。</span><span class="sxs-lookup"><span data-stu-id="536fc-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="536fc-160">[自動リダイレクト] 設定を [オン] に **切り替える**。</span><span class="sxs-lookup"><span data-stu-id="536fc-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="536fc-161">[ **有効にする]** をクリックして、Microsoft 365 セキュリティ センター ポータルに自動リダイレクトを適用します。</span><span class="sxs-lookup"><span data-stu-id="536fc-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="536fc-162">この設定を有効にすると、アクティブなユーザー セッションは終了しません。</span><span class="sxs-lookup"><span data-stu-id="536fc-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="536fc-163">この設定が適用されている間にアクティブ なセッションに参加しているアカウントは、現在のセッションを終了して再度サインインした後にのみ、Microsoft 365 セキュリティ センターに移動されます。</span><span class="sxs-lookup"><span data-stu-id="536fc-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="536fc-164">この設定を有効または無効にするには、グローバル管理者または Azure Active Directory のセキュリティ管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="536fc-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="536fc-165">以前のポータルを使用して戻ってみませんか?</span><span class="sxs-lookup"><span data-stu-id="536fc-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="536fc-166">何かが機能していない場合、または Microsoft 365 セキュリティ センター ポータルで完了できないものがある場合は、その点について説明します。</span><span class="sxs-lookup"><span data-stu-id="536fc-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="536fc-167">リダイレクトに関する問題が発生した場合は、[フィードバックの送信] フォームを使用してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="536fc-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="536fc-168">元の Microsoft Defender for Endpoint ポータルに戻すには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="536fc-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="536fc-169">[](https://security.microsoft.com/) Microsoft 365 セキュリティ センターにグローバル管理者としてサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を使用してアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="536fc-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="536fc-170">[設定エンドポイント **]**  >  **[全般ポータル]**  >  **リダイレクト**  >  **に移動するか、**[ここでページを開きます](https://security.microsoft.com/preferences2/portal_redirection)。</span><span class="sxs-lookup"><span data-stu-id="536fc-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="536fc-171">[自動リダイレクト] 設定を [オフ] に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="536fc-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="536fc-172">メッセージが **表示されたら** 、[&フィードバックを共有する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="536fc-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="536fc-173">この設定は、いつでも再度有効にできます。</span><span class="sxs-lookup"><span data-stu-id="536fc-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="536fc-174">無効にすると、アカウントは security.microsoft.com にルーティングされ、以前のポータル (securitycenter.windows.com または securitycenter.microsoft.com) に再びアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="536fc-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="536fc-175">関連情報</span><span class="sxs-lookup"><span data-stu-id="536fc-175">Related information</span></span>
- [<span data-ttu-id="536fc-176">Microsoft 365 セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="536fc-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="536fc-177">Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="536fc-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="536fc-178">Microsoft は、セキュリティ操作を最新化するために統合された SIEM と XDR を提供します。</span><span class="sxs-lookup"><span data-stu-id="536fc-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="536fc-179">XDR と SIEM のインフォグラフィック</span><span class="sxs-lookup"><span data-stu-id="536fc-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="536fc-180">新しい Defender</span><span class="sxs-lookup"><span data-stu-id="536fc-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="536fc-181">Microsoft 365 Defender について</span><span class="sxs-lookup"><span data-stu-id="536fc-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="536fc-182">Microsoft セキュリティ ポータルと管理センター</span><span class="sxs-lookup"><span data-stu-id="536fc-182">Microsoft security portals and admin centers</span></span>](portals.md)