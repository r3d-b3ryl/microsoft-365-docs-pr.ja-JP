---
title: アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする
description: Defender for Endpoint からセキュリティ センターにアカウントとセッションMicrosoft 365する方法。
keywords: Microsoft 365センター, セキュリティ センターのMicrosoft 365開始, セキュリティ センターのリダイレクト
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: db458015d8434843ec64f3c2c00d640d4c4d8ff2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760178"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="d788f-104">アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="d788f-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d788f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d788f-105">**Applies to:**</span></span>
- <span data-ttu-id="d788f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d788f-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d788f-107">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d788f-107">Defender for Endpoint</span></span>

<span data-ttu-id="d788f-108">SIEM と拡張検出と応答 (XDR) による脅威保護に対する Microsoft のクロスドメインアプローチに合わせ、Microsoft Defender Advanced Threat Protection を Microsoft Defender for Endpoint として再ブランド化し、Microsoft 365 セキュリティ センターという単一の統合ポータルに統合しました。</span><span class="sxs-lookup"><span data-stu-id="d788f-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="d788f-109">このガイドでは、以前の Microsoft Defender for Endpoint ポータル (securitycenter.windows.com または securitycenter.microsoft.com) から Microsoft 365 セキュリティ センター ポータル (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 セキュリティ センターにルーティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d788f-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="d788f-110">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は、[Microsoft Defender セキュリティ センターでアクセスが許可される](./mssp-access.md)のと同じ方法で、[マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスの許可](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d788f-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="d788f-111">想定される変化</span><span class="sxs-lookup"><span data-stu-id="d788f-111">What to expect</span></span>
<span data-ttu-id="d788f-112">自動リダイレクトが有効になると、securitycenter.windows.com または securitycenter.microsoft.com の元の Microsoft Defender for Endpoint ポータルにアクセスするアカウントが、security.microsoft.com の Microsoft 365 セキュリティ センター ポータルに自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d788f-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="d788f-113">変更点の詳細については[、「Microsoft Defender for Endpoint in the Microsoft 365」を参照してください](microsoft-365-security-center-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="d788f-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="d788f-114">これには、以前の securitycenter.windows.com ポータルを指すリンク (電子メール通知のリンクなど) や SIEM API 呼び出しによって返されるリンクなど、ブラウザー経由で以前のポータルに直接アクセスするリダイレクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d788f-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="d788f-115">メール通知または SIEM API からの外部リンクには、現在、両方のポータルへのリンクが含まれている。</span><span class="sxs-lookup"><span data-stu-id="d788f-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="d788f-116">リダイレクトが有効になると、両方のリンクは、Microsoft 365が削除されるまで、セキュリティ センターを指します。</span><span class="sxs-lookup"><span data-stu-id="d788f-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="d788f-117">セキュリティ センターを指す新しいリンクを採用Microsoft 365推奨します。</span><span class="sxs-lookup"><span data-stu-id="d788f-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="d788f-118">リンクとルーティングの詳細については、以下の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d788f-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="d788f-119">SIEM API ルーティング</span><span class="sxs-lookup"><span data-stu-id="d788f-119">SIEM API routing</span></span>

|<span data-ttu-id="d788f-120">**Property**</span><span class="sxs-lookup"><span data-stu-id="d788f-120">**Property**</span></span>  |<span data-ttu-id="d788f-121">**リダイレクトが OFF の場合の宛先**</span><span class="sxs-lookup"><span data-stu-id="d788f-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="d788f-122">**リダイレクトが ON の場合の宛先**</span><span class="sxs-lookup"><span data-stu-id="d788f-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="d788f-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="d788f-123">LinkToWDATP</span></span> | <span data-ttu-id="d788f-124">[アラート] ページ (securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="d788f-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="d788f-125">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="d788f-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="d788f-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="d788f-127">[インシデント] ページ (securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="d788f-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="d788f-128">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="d788f-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="d788f-129">LinkToMTP</span></span> | <span data-ttu-id="d788f-130">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="d788f-131">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="d788f-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="d788f-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="d788f-133">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="d788f-134">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="d788f-135">電子メールアラート通知</span><span class="sxs-lookup"><span data-stu-id="d788f-135">Email alert notifications</span></span>

|<span data-ttu-id="d788f-136">**Property**</span><span class="sxs-lookup"><span data-stu-id="d788f-136">**Property**</span></span>  |<span data-ttu-id="d788f-137">**リダイレクトが OFF の場合の宛先**</span><span class="sxs-lookup"><span data-stu-id="d788f-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="d788f-138">**リダイレクトが ON の場合の宛先**</span><span class="sxs-lookup"><span data-stu-id="d788f-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="d788f-139">[アラート] ページ</span><span class="sxs-lookup"><span data-stu-id="d788f-139">Alert page</span></span>  | <span data-ttu-id="d788f-140">[アラート] ページ (securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="d788f-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="d788f-141">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="d788f-142">インシデント ページ</span><span class="sxs-lookup"><span data-stu-id="d788f-142">Incident page</span></span>  |<span data-ttu-id="d788f-143">[インシデント] ページ (securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="d788f-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="d788f-144">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="d788f-145">セキュリティ センター ポータルの [アラート] ページ</span><span class="sxs-lookup"><span data-stu-id="d788f-145">Alert page in security center portal</span></span> | <span data-ttu-id="d788f-146">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="d788f-147">[アラート] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="d788f-148">セキュリティ センター ポータルのインシデント ページ</span><span class="sxs-lookup"><span data-stu-id="d788f-148">Incident page in security center portal</span></span> | <span data-ttu-id="d788f-149">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="d788f-150">[インシデント] ページ (security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d788f-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="d788f-151">これはいつ有効になりますか?</span><span class="sxs-lookup"><span data-stu-id="d788f-151">When does this take effect?</span></span> 
<span data-ttu-id="d788f-152">有効にすると、この更新プログラムは一部のアカウントでほぼ直ちに有効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d788f-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="d788f-153">ただし、リダイレクトが組織内のすべてのアカウントに伝達されるのに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d788f-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="d788f-154">この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出され、現在のセッションを終了して再びサインインした後にのみ Microsoft 365 セキュリティ センターにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d788f-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="d788f-155">ポータルリダイレクトの設定</span><span class="sxs-lookup"><span data-stu-id="d788f-155">Set up portal redirection</span></span>
<span data-ttu-id="d788f-156">アカウントをセキュリティ センターにルーティングMicrosoft 365するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d788f-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="d788f-157">Azure Active directory でグローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d788f-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="d788f-158">[セキュリティ センター](https://security.microsoft.com/)にサインインMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="d788f-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="d788f-159">[エンドポイントの **全般設定**  >  **リダイレクト**  >  **] に**  >  **移動するか、** ここを [クリックします](https://security.microsoft.com/preferences2/portal_redirection)。</span><span class="sxs-lookup"><span data-stu-id="d788f-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="d788f-160">[自動リダイレクト] 設定を [オン] に **切り替える**。</span><span class="sxs-lookup"><span data-stu-id="d788f-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="d788f-161">[**有効にする]** をクリックして、セキュリティ センター ポータルMicrosoft 365リダイレクトを適用します。</span><span class="sxs-lookup"><span data-stu-id="d788f-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d788f-162">この設定を有効にすると、アクティブなユーザー セッションは終了しません。</span><span class="sxs-lookup"><span data-stu-id="d788f-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="d788f-163">この設定が適用されている間にアクティブなセッションに参加しているアカウントは、現在のセッションを終了して再度サインインした後Microsoft 365セキュリティ センターにのみ移動されます。</span><span class="sxs-lookup"><span data-stu-id="d788f-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="d788f-164">この設定を有効または無効にするには、グローバル管理者またはセキュリティ管理者Azure Active Directoryアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d788f-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="d788f-165">以前のポータルを使用して戻ってみませんか?</span><span class="sxs-lookup"><span data-stu-id="d788f-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="d788f-166">何かが機能していない場合や、Microsoft 365 セキュリティ センター ポータルで完了できないものがある場合は、そのことをお知りください。</span><span class="sxs-lookup"><span data-stu-id="d788f-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="d788f-167">リダイレクトに関する問題が発生した場合は、[フィードバックの送信] フォームを使用してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="d788f-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="d788f-168">元の Microsoft Defender for Endpoint ポータルに戻すには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d788f-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="d788f-169">[Azure](https://security.microsoft.com/) Active directory で、Microsoft 365管理者として、またはセキュリティ管理者のアクセス許可を持つアカウントを使用して、セキュリティ センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="d788f-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="d788f-170">[エンドポイント全般 **設定**  >  **リダイレクト] に**  >    >  **移動するか、**[ここでページを開きます](https://security.microsoft.com/preferences2/portal_redirection)。</span><span class="sxs-lookup"><span data-stu-id="d788f-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="d788f-171">[自動リダイレクト] 設定を [オフ] に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="d788f-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="d788f-172">メッセージが **表示されたら** 、[&フィードバックを共有する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d788f-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="d788f-173">この設定は、いつでも再度有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d788f-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="d788f-174">無効にすると、アカウントは security.microsoft.com にルーティングされ、以前のポータル (securitycenter.windows.com または securitycenter.microsoft.com) に再びアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d788f-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="d788f-175">関連情報</span><span class="sxs-lookup"><span data-stu-id="d788f-175">Related information</span></span>
- [<span data-ttu-id="d788f-176">Microsoft 365 セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="d788f-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="d788f-177">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d788f-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="d788f-178">Microsoft は、セキュリティ操作を最新化するために統合された SIEM と XDR を提供します。</span><span class="sxs-lookup"><span data-stu-id="d788f-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="d788f-179">XDR と SIEM のインフォグラフィック</span><span class="sxs-lookup"><span data-stu-id="d788f-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="d788f-180">新しい Defender</span><span class="sxs-lookup"><span data-stu-id="d788f-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="d788f-181">Defender Microsoft 365について</span><span class="sxs-lookup"><span data-stu-id="d788f-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="d788f-182">Microsoft セキュリティ ポータルと管理センター</span><span class="sxs-lookup"><span data-stu-id="d788f-182">Microsoft security portals and admin centers</span></span>](portals.md)