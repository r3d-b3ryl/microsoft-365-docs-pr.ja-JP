---
title: セキュリティ/コンプライアンス センターからOffice 365 Defender へのアカウントのリダイレクトMicrosoft 365する
description: Defender for Office 365 Defender Microsoft 365する方法。
keywords: Microsoft 365Defender、 Defender の使用Microsoft 365、セキュリティ センターのリダイレクト
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842522"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="18770-104">セキュリティ/コンプライアンス センターから Office 365 Defender へのアカウントMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="18770-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="18770-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="18770-105">**Applies to:**</span></span>

- <span data-ttu-id="18770-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18770-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="18770-107">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="18770-107">Defender for Office 365</span></span>

<span data-ttu-id="18770-108">この記事では、以前の Office 365 セキュリティ/コンプライアンス センター (protection.office.com) から Microsoft 365 Defender (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 Defender にルーティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18770-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="18770-109">想定される変化</span><span class="sxs-lookup"><span data-stu-id="18770-109">What to expect</span></span>
<span data-ttu-id="18770-110">自動リダイレクトが有効でアクティブになると、Office 365 Security and Compliance (protection.office.com) のセキュリティ関連機能にアクセスするユーザーは、Microsoft 365 Defender ( ) に自動的にルーティングされます https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="18770-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="18770-111">変更された変更の詳細については[、「Microsoft Defender for Office 365」をMicrosoft 365してください](microsoft-365-security-center-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="18770-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="18770-112">自動リダイレクトを有効にすると、ユーザーは Microsoft 365 セキュリティとコンプライアンス センターでセキュリティ機能を使用するときに、Office 365 Defender にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="18770-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="18770-113">これには、[脅威の管理] セクションと [脅威の管理] ダッシュボードとレポートの機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="18770-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="18770-114">セキュリティに関連Office 365セキュリティとコンプライアンス センター内のアイテムは、Defender にMicrosoft 365されません。</span><span class="sxs-lookup"><span data-stu-id="18770-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="18770-115">コンプライアンス関連のアイテムは、コンプライアンス センター Microsoft 365、メール フロー関連のアイテムは、Exchangeにあります。</span><span class="sxs-lookup"><span data-stu-id="18770-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="18770-116">コンプライアンス関連または両方に対応する機能など、他のすべての機能は、リダイレクトの影響を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="18770-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="18770-117">Office 365 Defender と Microsoft 365 コンプライアンス センターの両方Office 365、リダイレクトなしで表示されます。</span><span class="sxs-lookup"><span data-stu-id="18770-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="18770-118">ポータルリダイレクトの設定</span><span class="sxs-lookup"><span data-stu-id="18770-118">Set up portal redirection</span></span>
<span data-ttu-id="18770-119">アカウントのルーティングを開始するには、Microsoft 365で Defender に security.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="18770-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="18770-120">Azure Active directory で、グローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="18770-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="18770-121">[Defender に](https://security.microsoft.com/)サインインMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="18770-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="18770-122">[電子 **メール**  >  **設定] &に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="18770-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="18770-123">[自動リダイレクト] 設定を [オン] に **切り替える**。</span><span class="sxs-lookup"><span data-stu-id="18770-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="18770-124">[有効 **にする] を** クリックして、Defender に自動リダイレクトMicrosoft 365適用します。</span><span class="sxs-lookup"><span data-stu-id="18770-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="18770-125">リダイレクトを有効にすると、この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出され、現在のセッションを終了して再度サインインした後にのみ Microsoft 365 Defender にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="18770-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="18770-126">以前のポータルを使用して戻ってみませんか?</span><span class="sxs-lookup"><span data-stu-id="18770-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="18770-127">何かが機能していない場合、または Microsoft 365 Defender を通じて完了できないものがある場合は、ポータルフィードバックオプションを使用してそのことを聞きたいと思います。</span><span class="sxs-lookup"><span data-stu-id="18770-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="18770-128">リダイレクトに関する問題が発生した場合は、お知らせください。</span><span class="sxs-lookup"><span data-stu-id="18770-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="18770-129">以前のポータルに戻すには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18770-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="18770-130">[グローバル管理者](https://security.microsoft.com/)としてMicrosoft 365 Defender にサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="18770-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="18770-131">[電子 **メール**  >  **設定] &に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="18770-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="18770-132">[自動リダイレクト] 設定を [オフ] に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="18770-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="18770-133">メッセージが **表示されたら** 、[&フィードバックを共有する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18770-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="18770-134">この設定は、いつでも再度有効にできます。</span><span class="sxs-lookup"><span data-stu-id="18770-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="18770-135">無効にすると、アカウントは security.microsoft.com にルーティングされ、以前のポータル (securitycenter.windows.com または securitycenter.microsoft.com) に再びアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="18770-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="18770-136">関連情報</span><span class="sxs-lookup"><span data-stu-id="18770-136">Related information</span></span>
- [<span data-ttu-id="18770-137">Microsoft 365Defender の概要</span><span class="sxs-lookup"><span data-stu-id="18770-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="18770-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18770-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="18770-139">Microsoft は、セキュリティ操作を最新化するために統合された SIEM と XDR を提供します。</span><span class="sxs-lookup"><span data-stu-id="18770-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="18770-140">XDR と SIEM のインフォグラフィック</span><span class="sxs-lookup"><span data-stu-id="18770-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="18770-141">新しい Defender</span><span class="sxs-lookup"><span data-stu-id="18770-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="18770-142">Defender Microsoft 365について</span><span class="sxs-lookup"><span data-stu-id="18770-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="18770-143">Microsoft セキュリティ ポータルと管理センター</span><span class="sxs-lookup"><span data-stu-id="18770-143">Microsoft security portals and admin centers</span></span>](portals.md)
