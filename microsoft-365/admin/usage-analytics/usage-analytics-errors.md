---
title: 使用状況分析Microsoft 365トラブルシューティング
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: 使用状況分析テンプレート アプリに関する問題のトラブルシューティングMicrosoft 365説明します。
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293737"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="4267d-103">使用状況分析Microsoft 365トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4267d-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="4267d-104">次のエラー メッセージの一覧を参照して、使用状況分析に関する最も一般的な問題Microsoft 365確認してください。</span><span class="sxs-lookup"><span data-stu-id="4267d-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="4267d-105">リクエストを処理できません。</span><span class="sxs-lookup"><span data-stu-id="4267d-105">We are unable to process your request.</span></span> <span data-ttu-id="4267d-106">最初に管理センターからこのデータをサブスクライブするMicrosoft 365があります</span><span class="sxs-lookup"><span data-stu-id="4267d-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="4267d-107">**エラー コード:** 422</span><span class="sxs-lookup"><span data-stu-id="4267d-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="4267d-108">**このメッセージが表示される場所:** このPower BI Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出す場合Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="4267d-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4267d-109">**原因:** アプリに接続する前に、管理センターからデータをサブスクライブMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="4267d-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="4267d-110">この手順を最初に行わなくても、テナント ID を指定した場合でも、テンプレート アプリMicrosoft 365できません。</span><span class="sxs-lookup"><span data-stu-id="4267d-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="4267d-111">**このエラーを修正するには、次の手順を実行します。** データをサブスクライブするには、管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード ページで [Microsoft 365利用状況分析 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>] タイルを探します。</span><span class="sxs-lookup"><span data-stu-id="4267d-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="4267d-112">[作業の **開始]** ボタンを選択し、開く [レポート] ウィンドウで、[データの使用状況分析でデータを使用Microsoft 365する] Power BIをオンにし、[保存]**を\*\*\*\*オンにします**。</span><span class="sxs-lookup"><span data-stu-id="4267d-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="4267d-113">データを処理しています</span><span class="sxs-lookup"><span data-stu-id="4267d-113">We are processing your data</span></span>

 <span data-ttu-id="4267d-114">**このメッセージが表示される場所:** 管理センター **Microsoft 365の** 利用状況ダッシュボードの [使用状況分析] Microsoft 365表示されます。</span><span class="sxs-lookup"><span data-stu-id="4267d-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="4267d-115">**原因:** Microsoft 365 管理 [センター](enable-usage-analytics.md)からテンプレート アプリのデータを表示することを選択すると、Microsoft 365 システムは組織の使用状況履歴データの生成を開始します。</span><span class="sxs-lookup"><span data-stu-id="4267d-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="4267d-116">テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="4267d-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="4267d-117">**これを修正するには、次の手順を実行します。** お待ちください。ただし、メッセージが 3日後にデータに変更されない場合は、Microsoft 365 [に問い合わせください](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="4267d-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="4267d-p105">現在、リクエストを処理できません。引き続き組織のデータを準備しています。</span><span class="sxs-lookup"><span data-stu-id="4267d-p105">We are unable to process your request at this time. We are still preparing the data for your organization</span></span>

 <span data-ttu-id="4267d-120">**エラー コード:** 423</span><span class="sxs-lookup"><span data-stu-id="4267d-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="4267d-121">**このメッセージが表示される場所:** このPower BI、 Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出Microsoft 365場合。</span><span class="sxs-lookup"><span data-stu-id="4267d-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4267d-122">**原因:** 管理センター [からテンプレート](enable-usage-analytics.md)アプリのデータを表示することを選択すると、Microsoft 365システムは組織の使用状況履歴データの生成を開始します。</span><span class="sxs-lookup"><span data-stu-id="4267d-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="4267d-123">テナントのサイズに応じて、この手順は 2 時間から 48 時間の間の任意の場所で実行できます。</span><span class="sxs-lookup"><span data-stu-id="4267d-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="4267d-124">**これを修正するには、次の手順を実行します。** お待ちください。ただし、メッセージが開始から 3 日経ってもデータが変更されない場合は、ビジネス サポートMicrosoft 365 [問い合わせください](../../business-video/get-help-support.md)。 </span><span class="sxs-lookup"><span data-stu-id="4267d-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="4267d-125">入力したテナント ID の形式が間違っています</span><span class="sxs-lookup"><span data-stu-id="4267d-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="4267d-126">**エラー コード:** 400</span><span class="sxs-lookup"><span data-stu-id="4267d-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="4267d-127">**このメッセージが表示される場所:** このPower BI、 Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出Microsoft 365場合。</span><span class="sxs-lookup"><span data-stu-id="4267d-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4267d-128">**原因:** テナント ID は guid であり、xxxxxxxx-xxxx-xxxx-xxxx-xxx の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4267d-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="4267d-129">テナント入力ボックスに他の文字列を入力すると、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4267d-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="4267d-130">**このエラーを修正するには、次の手順を実行します。** 管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード Microsoft 365の [使用状況分析 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>] タイルを探します。</span><span class="sxs-lookup"><span data-stu-id="4267d-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="4267d-131">テナント ID がタイルに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4267d-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="4267d-132">ここからコピーして、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4267d-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="4267d-133">入力したテナント ID が弊社のシステムで認識されません</span><span class="sxs-lookup"><span data-stu-id="4267d-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="4267d-134">**エラー コード:** 404</span><span class="sxs-lookup"><span data-stu-id="4267d-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="4267d-135">**このメッセージが表示される場所:** このPower BI Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出す場合Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="4267d-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4267d-136">**原因:** 指定したテナント ID が無効か、存在しません。</span><span class="sxs-lookup"><span data-stu-id="4267d-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="4267d-137">**このエラーを修正するには、次の手順を実行します。** 管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード Microsoft 365の [使用状況分析 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>] タイルを探します。</span><span class="sxs-lookup"><span data-stu-id="4267d-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="4267d-138">テナント ID がタイルに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4267d-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="4267d-139">ここからコピーして、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4267d-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="4267d-140">資格情報を再入力して Power BI にもう一度サインインしてください</span><span class="sxs-lookup"><span data-stu-id="4267d-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="4267d-141">エラー コード:302</span><span class="sxs-lookup"><span data-stu-id="4267d-141">Error Code: 302</span></span>
  
 <span data-ttu-id="4267d-142">**このメッセージが表示される場所:** このPower BI Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出す場合Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="4267d-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4267d-143">**原因:** 認証コードが不合格となり、資格情報の再入力が求められている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4267d-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="4267d-144">**修正方法:** Power BI からサインアウトし、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="4267d-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="4267d-p110">このデータにアクセスする権限がありません。このサービスからデータにアクセスする権限を取得できるようにするには、グローバル管理者か、いずれかの製品管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4267d-p110">You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="4267d-147">**エラー コード:** 403</span><span class="sxs-lookup"><span data-stu-id="4267d-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="4267d-148">**このメッセージが表示される場所:** このPower BI Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出す場合Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="4267d-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4267d-149">**原因:** テンプレート アプリに接続しようとしたユーザーが、このデータにアクセスするための適切なレベルの承認を持たないので、承認コードは失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4267d-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="4267d-150">**このエラーを修正するには、次の手順を実行します。** グローバル管理者 **、Exchange 管理者、Skype for Business** **管理者、SharePoint** 管理者、グローバル リーダー、レポート リーダーのいずれかであるユーザーの資格情報を入力して、テンプレート アプリに接続します。</span><span class="sxs-lookup"><span data-stu-id="4267d-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="4267d-151">詳細については [、「管理者ロールについて](../add-users/about-admin-roles.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4267d-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="4267d-152">更新が失敗しました</span><span class="sxs-lookup"><span data-stu-id="4267d-152">Refresh failed</span></span>

 <span data-ttu-id="4267d-153">**このメッセージが表示される場所:** Power BI からの電子メールまたは更新履歴の失敗した状態。</span><span class="sxs-lookup"><span data-stu-id="4267d-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="4267d-154">**原因:** テンプレート アプリに接続したユーザーの資格情報がリセットされ、テンプレート アプリの接続設定で更新されないと、更新エラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4267d-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="4267d-155">**このエラーを修正するには、次の手順を実行します。**[Power BI、 Usage Analytics テンプレート アプリに対応するデータセットをMicrosoft 365更新のスケジュールを選択し、管理者資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="4267d-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="4267d-156">それでも問題が生じなかった場合は、キャッシュをクリアし、テンプレート アプリを再作成します。</span><span class="sxs-lookup"><span data-stu-id="4267d-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
