---
title: Microsoft Defender for Endpoint での SIEM ツール統合の問題のトラブルシューティング
description: Microsoft Defender for Endpoint で SIEM ツールを使用する場合に発生する可能性のある問題のトラブルシューティングを行います。
keywords: トラブルシューティング, siem, クライアント シークレット, secret
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 9c4f3da57796903fc22314574f389bcdd92ca4b3
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311990"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="ca7f7-104">SIEM ツール統合に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ca7f7-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ca7f7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ca7f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="ca7f7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ca7f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ca7f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca7f7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="ca7f7-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ca7f7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ca7f7-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="ca7f7-110">SIEM ツールで検出を引き出す際に問題のトラブルシューティングが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="ca7f7-111">このページでは、発生する可能性がある問題をトラブルシューティングするための詳細な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="ca7f7-112">新しいクライアント シークレットを取得する方法について</span><span class="sxs-lookup"><span data-stu-id="ca7f7-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="ca7f7-113">クライアント シークレットの有効期限が切れた場合、または SIEM ツール アプリケーションを有効にするときに提供されたコピーを置き忘れた場合は、新しいシークレットを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="ca7f7-114">Azure 管理ポータル [にログインします](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="ca7f7-115">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="ca7f7-116">テナントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-116">Select your tenant.</span></span>

4. <span data-ttu-id="ca7f7-117">[アプリ **の登録] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-117">Click **App registrations**.</span></span> <span data-ttu-id="ca7f7-118">次に、アプリケーションの一覧で、アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="ca7f7-119">[ **証明書と&] セクション、[** 新しいクライアント シークレット] をクリックし、説明を入力し、有効期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-119">Select **Certificates & Secrets** section, Click on New Client Secret, then provide a description and specify the validity duration.</span></span>

6. <span data-ttu-id="ca7f7-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-120">Click **Save**.</span></span> <span data-ttu-id="ca7f7-121">キー値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-121">The key value is displayed.</span></span>

7. <span data-ttu-id="ca7f7-122">値をコピーし、安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="ca7f7-123">更新アクセス トークンを取得するときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="ca7f7-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="ca7f7-124">脅威インテリジェンス API または SIEM ツールを使用するときに更新トークンを取得しようとするときにエラーが発生した場合は、関連するアプリケーションの返信 URL を Azure Active Directory に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="ca7f7-125">Azure 管理ポータル [にログインします](https://ms.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="ca7f7-126">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="ca7f7-127">テナントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-127">Select your tenant.</span></span>

4. <span data-ttu-id="ca7f7-128">[アプリ **の登録] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-128">Click **App Registrations**.</span></span> <span data-ttu-id="ca7f7-129">次に、アプリケーションの一覧で、アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="ca7f7-130">次の URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-130">Add the following URL:</span></span>
   - <span data-ttu-id="ca7f7-131">EU の場合: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="ca7f7-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="ca7f7-132">英国の場合: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="ca7f7-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="ca7f7-133">米国の場合:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="ca7f7-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="ca7f7-134">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="ca7f7-135">SIEM コネクタ アプリケーションを有効にしている間のエラー</span><span class="sxs-lookup"><span data-stu-id="ca7f7-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="ca7f7-136">SIEM コネクタ アプリケーションを有効にしようとするときにエラーが発生した場合は、ブラウザーのポップアップ ブロッカー設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="ca7f7-137">機能を有効にするときに開いている新しいウィンドウがブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="ca7f7-138">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="ca7f7-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ca7f7-139">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ca7f7-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="ca7f7-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca7f7-140">Related topics</span></span>
- [<span data-ttu-id="ca7f7-141">エンドポイント向け Microsoft Defender で SIEM 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="ca7f7-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="ca7f7-142">エンドポイント検出用の Microsoft Defender をプルする ArcSight の構成</span><span class="sxs-lookup"><span data-stu-id="ca7f7-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="ca7f7-143">SIEM ツールへの検出のプル</span><span class="sxs-lookup"><span data-stu-id="ca7f7-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="ca7f7-144">Microsoft Defender for Endpoint Detection フィールド</span><span class="sxs-lookup"><span data-stu-id="ca7f7-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="ca7f7-145">REST API を使用したエンドポイント検出用の Microsoft Defender のプル</span><span class="sxs-lookup"><span data-stu-id="ca7f7-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
