---
title: Microsoft 365 利用状況分析のトラブルシューティング
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
description: Microsoft 365 Usage Analytics テンプレート アプリの問題をトラブルシューティングする方法について説明します。
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580740"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="7fcb0-103">Microsoft 365 利用状況分析のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7fcb0-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="7fcb0-104">Microsoft 365 使用状況分析に関する最も一般的な問題に関するヘルプを表示するには、次のエラー メッセージの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="7fcb0-105">リクエストを処理できません。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-105">We are unable to process your request.</span></span> <span data-ttu-id="7fcb0-106">まず、Microsoft 365 管理センターからこのデータをサブスクライブする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="7fcb0-107">**エラー コード:** 422</span><span class="sxs-lookup"><span data-stu-id="7fcb0-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="7fcb0-108">**このメッセージが表示される場所:** Power BI で Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 Reporting API を直接呼び出す場合。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7fcb0-109">**原因:** アプリに接続する前に、Microsoft 365 管理センターのデータをサブスクライブする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="7fcb0-110">この手順を最初に実行しない場合は、Microsoft 365 テナント ID を指定した場合でも、テンプレート アプリに接続できません。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="7fcb0-111">**このエラーを修正するには、次の手順を実行します。** データをサブスクライブするには、管理センターの [利用状況のレポート] に移動し、メイン ダッシュボード ページで \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>[Microsoft 365 利用状況分析] タイルを探します。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="7fcb0-112">[開始 **する] ボタンを** 選択し、開く [レポート] ウィンドウで、[Power BI の **Microsoft 365** 利用状況分析でデータを使用できる] 設定をオンにし、[保存] を **オンにします**。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="7fcb0-113">データを処理しています</span><span class="sxs-lookup"><span data-stu-id="7fcb0-113">We are processing your data</span></span>

 <span data-ttu-id="7fcb0-114">**このメッセージが表示される場所:** Microsoft **365 管理** センターの利用状況ダッシュボードの[Microsoft 365 使用状況分析] タイルで指定します。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="7fcb0-115">**原因:** Microsoft [](enable-usage-analytics.md) 365 管理センターからテンプレート アプリのデータを表示することを選択すると、Microsoft 365 システムは組織の使用状況履歴データの生成を開始します。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="7fcb0-116">テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="7fcb0-117">**これを修正するには、次の手順を実行します。** お待ちください。ただし、メッセージが 3日後にデータに変更されない場合は [、Microsoft 365](../contact-support-for-business-products.md)に問い合わせ、ビジネス サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="7fcb0-118">現在、リクエストを処理できません。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="7fcb0-119">引き続き組織のデータを準備しています。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="7fcb0-120">**エラー コード:** 423</span><span class="sxs-lookup"><span data-stu-id="7fcb0-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="7fcb0-121">**このメッセージが表示される場所:** Power BI で、Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 レポート API を直接呼び出す場合。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7fcb0-122">**原因:** 管理センター [からテンプレート](enable-usage-analytics.md) アプリのデータを表示することを選択すると、Microsoft 365 システムは組織の使用状況履歴データの生成を開始します。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="7fcb0-123">テナントのサイズに応じて、この手順は 2 時間から 48 時間の間の任意の場所で実行できます。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="7fcb0-124">**これを修正するには、次の手順を実行します。** お待ちください。ただし、メッセージが開始から 3 日経ってもデータが変更されない場合は [、Microsoft 365 に](../contact-support-for-business-products.md)問い合わせ、ビジネス サポートにお問い合わせください。 </span><span class="sxs-lookup"><span data-stu-id="7fcb0-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="7fcb0-125">入力したテナント ID の形式が間違っています</span><span class="sxs-lookup"><span data-stu-id="7fcb0-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="7fcb0-126">**エラー コード:** 400</span><span class="sxs-lookup"><span data-stu-id="7fcb0-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="7fcb0-127">**このメッセージが表示される場所:** Power BI で、Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 レポート API を直接呼び出す場合。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7fcb0-128">**原因:** テナント ID は guid であり、xxxxxxxx-xxxx-xxxx-xxxx-xxx の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="7fcb0-129">テナント入力ボックスに他の文字列を入力すると、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="7fcb0-130">**このエラーを修正するには、次の手順を実行します。** 管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード ページの \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>[Microsoft 365 利用状況分析] タイルを見つける。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="7fcb0-131">テナント ID がタイルに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="7fcb0-132">ここからコピーして、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="7fcb0-133">入力したテナント ID が弊社のシステムで認識されません</span><span class="sxs-lookup"><span data-stu-id="7fcb0-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="7fcb0-134">**エラー コード:** 404</span><span class="sxs-lookup"><span data-stu-id="7fcb0-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="7fcb0-135">**このメッセージが表示される場所:** Power BI で Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 Reporting API を直接呼び出す場合。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7fcb0-136">**原因:** 指定したテナント ID が無効か、存在しません。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="7fcb0-137">**このエラーを修正するには、次の手順を実行します。** 管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード ページの \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>[Microsoft 365 利用状況分析] タイルを見つける。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="7fcb0-138">テナント ID がタイルに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="7fcb0-139">ここからコピーして、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="7fcb0-140">資格情報を再入力して Power BI にもう一度サインインしてください</span><span class="sxs-lookup"><span data-stu-id="7fcb0-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="7fcb0-141">エラー コード:302</span><span class="sxs-lookup"><span data-stu-id="7fcb0-141">Error Code: 302</span></span>
  
 <span data-ttu-id="7fcb0-142">**このメッセージが表示される場所:** Power BI で Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 Reporting API を直接呼び出す場合。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7fcb0-143">**原因:** 認証コードが不合格となり、資格情報の再入力が求められている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="7fcb0-144">**修正方法:** Power BI からサインアウトし、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="7fcb0-145">このデータにアクセスする権限がありません。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="7fcb0-146">このサービスからデータにアクセスする権限を取得できるようにするには、グローバル管理者か、いずれかの製品管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="7fcb0-147">**エラー コード:** 403</span><span class="sxs-lookup"><span data-stu-id="7fcb0-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="7fcb0-148">**このメッセージが表示される場所:** Power BI で Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 Reporting API を直接呼び出す場合。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7fcb0-149">**原因:** テンプレート アプリに接続しようとしたユーザーが、このデータにアクセスするための適切なレベルの承認を持たないので、承認コードは失敗しました。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="7fcb0-150">**このエラーを修正するには、次の手順を実行します。** グローバル管理者 **、Exchange** 管理者 **、Skype for Business** 管理者 **、SharePoint 管理者**、グローバル リーダー、またはレポートリーダーのいずれかであるユーザーの資格情報を入力して、テンプレート アプリに接続します。 </span><span class="sxs-lookup"><span data-stu-id="7fcb0-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="7fcb0-151">詳細については [、「管理者ロールについて](../add-users/about-admin-roles.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="7fcb0-152">更新が失敗しました</span><span class="sxs-lookup"><span data-stu-id="7fcb0-152">Refresh failed</span></span>

 <span data-ttu-id="7fcb0-153">**このメッセージが表示される場所:** Power BI からの電子メールまたは更新履歴の失敗した状態。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="7fcb0-154">**原因:** テンプレート アプリに接続したユーザーの資格情報がリセットされ、テンプレート アプリの接続設定で更新されないと、更新エラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="7fcb0-155">**このエラーを修正するには、次の手順を実行します。** Power BI で、Microsoft 365 Usage Analytics テンプレート アプリに対応するデータセットを検索し、[更新のスケジュール設定] を選択し、管理者資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="7fcb0-156">それでも問題が生じなかった場合は、キャッシュをクリアし、テンプレート アプリを再作成します。</span><span class="sxs-lookup"><span data-stu-id="7fcb0-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
