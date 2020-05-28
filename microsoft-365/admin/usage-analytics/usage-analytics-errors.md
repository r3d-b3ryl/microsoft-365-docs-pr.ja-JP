---
title: Microsoft 365 usage analytics のトラブルシューティング
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Microsoft 365 Usage Analytics テンプレートアプリの問題をトラブルシューティングする方法について説明します。
ms.openlocfilehash: 4696dd0c5140cdc110781c226819fc64a90fae1b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402036"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="38e20-103">Microsoft 365 usage analytics のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="38e20-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="38e20-104">次のエラーメッセージの一覧を参照して、Microsoft 365 usage analytics の一般的な問題に関するヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="38e20-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="38e20-105">リクエストを処理できません。</span><span class="sxs-lookup"><span data-stu-id="38e20-105">We are unable to process your request.</span></span> <span data-ttu-id="38e20-106">最初に、Microsoft 365 管理センターからこのデータを購読する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38e20-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="38e20-107">**エラー コード:** 422</span><span class="sxs-lookup"><span data-stu-id="38e20-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="38e20-108">**このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。</span><span class="sxs-lookup"><span data-stu-id="38e20-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="38e20-109">**原因:** アプリに接続するには、Microsoft 365 管理センターからデータを購読する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38e20-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="38e20-110">この手順を最初に実行しないと、Microsoft 365 テナント id を提供している場合でも、テンプレートアプリに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="38e20-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="38e20-111">**このエラーを解決するには、次のようにします。** データをサブスクライブするには、管理センターの [ \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">利用状況]</a>レポートを開き、ダッシュボードのメインページで Microsoft 365 Usage analytics タイルを探します。</span><span class="sxs-lookup"><span data-stu-id="38e20-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="38e20-112">[**作業の開始**] ボタンを選択し、開いた [**レポート**] ウィンドウで、[ **Power BI のための Microsoft 365 usage analytics のためにデータを利用できるようにする**] 設定をオンにして、[**保存**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="38e20-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="38e20-113">データを処理しています</span><span class="sxs-lookup"><span data-stu-id="38e20-113">We are processing your data</span></span>

 <span data-ttu-id="38e20-114">**このメッセージが表示される場所は次のとおりです。** Microsoft 365 管理センターの**利用状況**ダッシュボードの**microsoft 365 usage analytics**タイル。</span><span class="sxs-lookup"><span data-stu-id="38e20-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="38e20-115">**原因:** Microsoft 365 管理センターから[テンプレートアプリのデータを表示することを選択](enable-usage-analytics.md)すると、microsoft 365 システムは組織の利用状況データの履歴を生成し始めます。</span><span class="sxs-lookup"><span data-stu-id="38e20-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="38e20-116">テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="38e20-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="38e20-117">**この問題を解決するには**しばらくお待ちくださいが、メッセージが3日後に**データ**に変更されない場合は、 [Microsoft 365 for business サポートにお問い合わせください](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="38e20-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="38e20-118">現在、リクエストを処理できません。</span><span class="sxs-lookup"><span data-stu-id="38e20-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="38e20-119">引き続き組織のデータを準備しています。</span><span class="sxs-lookup"><span data-stu-id="38e20-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="38e20-120">**エラー コード:** 423</span><span class="sxs-lookup"><span data-stu-id="38e20-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="38e20-121">**このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。</span><span class="sxs-lookup"><span data-stu-id="38e20-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="38e20-122">**原因:** 管理センターから[テンプレートアプリのデータを表示することを選択](enable-usage-analytics.md)すると、Microsoft 365 システムによって、組織の利用状況データの履歴生成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="38e20-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="38e20-123">テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="38e20-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="38e20-124">**この問題を解決するには**しばらくお待ちくださいが、**データの準備が完了**してから3日経っても、メッセージが変更されない場合は、 [Microsoft 365 for business サポートにお問い合わせください](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="38e20-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="38e20-125">入力したテナント ID の形式が間違っています</span><span class="sxs-lookup"><span data-stu-id="38e20-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="38e20-126">**エラー コード:** 400</span><span class="sxs-lookup"><span data-stu-id="38e20-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="38e20-127">**このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。</span><span class="sxs-lookup"><span data-stu-id="38e20-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="38e20-p107">**原因:** テナント ID は GUID であり、その形式は xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx にする必要があります。テナント入力ボックスに他の文字列を入力すると、このエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38e20-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="38e20-130">**このエラーを解決するには、次のようにします。** 管理センターの \> **レポート** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用法</a>に移動し、ダッシュボードのメインページで Microsoft 365 Usage analytics タイルを探します。</span><span class="sxs-lookup"><span data-stu-id="38e20-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="38e20-131">The tenant id is listed on the tile.</span><span class="sxs-lookup"><span data-stu-id="38e20-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="38e20-132">ここからコピーして、テンプレートアプリに接続するためのダイアログボックスに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="38e20-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="38e20-133">入力したテナント ID が弊社のシステムで認識されません</span><span class="sxs-lookup"><span data-stu-id="38e20-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="38e20-134">**エラー コード:** 404</span><span class="sxs-lookup"><span data-stu-id="38e20-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="38e20-135">**このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。</span><span class="sxs-lookup"><span data-stu-id="38e20-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="38e20-136">**原因:** 入力したテナント ID が無効であるか、存在しません。</span><span class="sxs-lookup"><span data-stu-id="38e20-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="38e20-137">**このエラーを解決するには、次のようにします。** 管理センターの \> **レポート** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用法</a>に移動し、ダッシュボードのメインページで Microsoft 365 Usage analytics タイルを探します。</span><span class="sxs-lookup"><span data-stu-id="38e20-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="38e20-138">The tenant id is listed on the tile.</span><span class="sxs-lookup"><span data-stu-id="38e20-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="38e20-139">ここからコピーして、テンプレートアプリに接続するためのダイアログボックスに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="38e20-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="38e20-140">資格情報を再入力して Power BI にもう一度サインインしてください</span><span class="sxs-lookup"><span data-stu-id="38e20-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="38e20-141">エラー コード:302</span><span class="sxs-lookup"><span data-stu-id="38e20-141">Error Code: 302</span></span>
  
 <span data-ttu-id="38e20-142">**このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。</span><span class="sxs-lookup"><span data-stu-id="38e20-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="38e20-143">**原因:** 認証コードが不合格となり、資格情報の再入力が求められている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38e20-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="38e20-144">**修正方法:** Power BI からサインアウトし、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="38e20-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="38e20-145">このデータにアクセスする権限がありません。</span><span class="sxs-lookup"><span data-stu-id="38e20-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="38e20-146">このサービスからデータにアクセスする権限を取得できるようにするには、グローバル管理者か、いずれかの製品管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="38e20-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="38e20-147">**エラー コード:** 403</span><span class="sxs-lookup"><span data-stu-id="38e20-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="38e20-148">**このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。</span><span class="sxs-lookup"><span data-stu-id="38e20-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="38e20-149">**原因:** テンプレートアプリに接続しようとしたユーザーがこのデータにアクセスするための適切な承認レベルを持っていないため、認証コードが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="38e20-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="38e20-150">**このエラーを解決するには、次のようにします。\*\*\*\*グローバル管理者**、 **Exchange 管理**者、 **Skype for business 管理者**、 **SharePoint 管理者**、**グローバルリーダ**、または**レポート**アプリに接続するユーザーの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="38e20-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="38e20-151">詳細については、「[管理者ロールについ](../add-users/about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38e20-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="38e20-152">更新が失敗しました</span><span class="sxs-lookup"><span data-stu-id="38e20-152">Refresh failed</span></span>

 <span data-ttu-id="38e20-153">**このメッセージが表示される場所:** Power BI からの電子メールまたは更新履歴の失敗した状態。</span><span class="sxs-lookup"><span data-stu-id="38e20-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="38e20-154">**原因:** テンプレートアプリに接続したユーザーの資格情報がリセットされる場合があり、テンプレートアプリの接続設定で更新されていないと、ユーザーが更新エラーエラーを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="38e20-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="38e20-155">**このエラーを解決するには、次のようにします。** Power BI で、Microsoft 365 Usage Analytics テンプレートアプリに対応するデータセットを見つけ、[**更新のスケジュール**] を選択して、管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="38e20-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="38e20-156">それでもうまくいかない場合は、キャッシュをクリアし、テンプレートアプリを再作成します。</span><span class="sxs-lookup"><span data-stu-id="38e20-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
