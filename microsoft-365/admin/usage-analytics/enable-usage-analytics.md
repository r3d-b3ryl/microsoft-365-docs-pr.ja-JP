---
title: Microsoft 365 利用状況分析を有効にする
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Power BI で Microsoft 365 Usage Analytics テンプレート アプリを使用してテナントのデータ収集を開始する方法について説明します。
ms.openlocfilehash: 1ef50380041650763961ffbe6e01c63b26800ee3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913876"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="29d51-103">Microsoft 365 利用状況分析を有効にする</span><span class="sxs-lookup"><span data-stu-id="29d51-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="29d51-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="29d51-104">The admin center is changing.</span></span> <span data-ttu-id="29d51-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d51-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="29d51-106">Microsoft 365 使用状況分析は、Microsoft 365 US Government Community ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="29d51-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="29d51-107">Microsoft 365 利用状況分析を有効にする手順</span><span class="sxs-lookup"><span data-stu-id="29d51-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="29d51-108">Microsoft 365 利用状況分析を開始するには、まず Microsoft 365 管理センターでデータを利用し、次に Power BI でテンプレート アプリを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d51-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="29d51-109">Power BI を取得する</span><span class="sxs-lookup"><span data-stu-id="29d51-109">Get Power BI</span></span>

<span data-ttu-id="29d51-110">Power BI をまだ持ってない場合は [、Power BI Pro にサインアップできます](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="29d51-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="29d51-111">[**無料で試** 用] を選択して試用版にサインアップするか、[今すぐ購入] を選択して Power BI Pro を取得します。</span><span class="sxs-lookup"><span data-stu-id="29d51-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="29d51-112">[ **製品**] を展開して Power BI のバージョンを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="29d51-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="29d51-113">テンプレート アプリをインストール、カスタマイズ、配布するには、Power BI Pro ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="29d51-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="29d51-114">詳細については、「前提条件」を [参照してください](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="29d51-114">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="29d51-115">データを共有するには、ユーザーとデータを共有するユーザー、Power BI Pro ライセンスが必要、またはコンテンツが Power BI プレミアム サービスのワークスペースにある [必要があります](/power-bi/service-premium-what-is)。</span><span class="sxs-lookup"><span data-stu-id="29d51-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="29d51-116">テンプレート アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="29d51-116">Enable the template app</span></span>

<span data-ttu-id="29d51-117">テンプレート アプリを有効にするには、グローバル管理者である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="29d51-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="29d51-118">詳細 [については、「管理者の役割」](../add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d51-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="29d51-119">管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="29d51-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="29d51-120">[使用状況 **] ページで\*\*\*\*、Microsoft 365** 利用状況分析カードを見つけて、[開始]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="29d51-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="29d51-121">開く [レポート] パネルで、[Power BI の **Microsoft 365** 利用状況分析でデータを使用できる] を [保存時] **に設定** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="29d51-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="29d51-122">データ収集プロセスは、テナントのサイズに応じて 2 ~ 48 時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="29d51-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="29d51-123">データ **収集が完了すると、[Power BI** に移動] ボタンが有効になります (灰色ではなくなりました)。</span><span class="sxs-lookup"><span data-stu-id="29d51-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="29d51-124">テンプレート アプリを起動する</span><span class="sxs-lookup"><span data-stu-id="29d51-124">Start the template app</span></span>

<span data-ttu-id="29d51-125">テンプレート アプリを起動するには、グローバル管理者、レポートリーダー **、Exchange 管理者、Skype** **for Business** 管理者、**または SharePoint 管理者である必要があります**。 </span><span class="sxs-lookup"><span data-stu-id="29d51-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="29d51-126">テナント ID をコピーし **、[Power BI に移動] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="29d51-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="29d51-127">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="29d51-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="29d51-128">次に **、[アプリ]** -> **ナビゲーション メニューから**[アプリを取得する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29d51-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="29d51-129">[アプリ **] タブで** 、検索ボックスに「Microsoft 365」と入力し **、[Microsoft 365 利用状況** 分析] を選択します。今すぐ \> **取得します**。</span><span class="sxs-lookup"><span data-stu-id="29d51-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="29d51-130">[![[今すぐ取得] を選択します。](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="29d51-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="29d51-131">アプリがインストールされた後。</span><span class="sxs-lookup"><span data-stu-id="29d51-131">Once the app is installed.</span></span> <span data-ttu-id="29d51-132">タイルを選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="29d51-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="29d51-133">[アプリ **の探索] を** 選択して、サンプル データを使用してアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="29d51-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="29d51-134">[ **接続] を** 選択して、アプリを組織のデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="29d51-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="29d51-135">[ **接続]** を選択し **、[Microsoft 365** 利用状況分析に接続する] 画面で、手順 (1) でコピーしたテナント ID (ダッシュなし) を入力し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="29d51-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="29d51-136">次の画面で、[認証]**メソッドとして [OAuth2]** **を選択します** \> 。</span><span class="sxs-lookup"><span data-stu-id="29d51-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="29d51-137">他の認証方法を選択すると、テンプレート アプリへの接続が失敗します。</span><span class="sxs-lookup"><span data-stu-id="29d51-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![認証方法として Microsoft アカウントを選択する](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="29d51-139">テンプレート アプリのインスタンス化後、Microsoft 365 利用状況分析ダッシュボードは、Web 上の Power BI で使用できます。</span><span class="sxs-lookup"><span data-stu-id="29d51-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="29d51-140">ダッシュボードの初期読み込みには 2 ~ 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="29d51-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="29d51-141">テナント レベルの集計は、オプトイン後にすべてのレポートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="29d51-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="29d51-142">**ユーザー レベルの詳細は、オプトイン後の次の暦月の 5 日の周りにのみ利用できます**。</span><span class="sxs-lookup"><span data-stu-id="29d51-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="29d51-143">これは、[ユーザー アクティビティ] の下のすべてのレポートに影響します (これらのレポートを表示および使用する方法のヒントについては [、「Microsoft 365](navigate-and-utilize-reports.md) 利用状況分析のレポートを移動して利用する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="29d51-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="29d51-144">収集されたデータを匿名にする</span><span class="sxs-lookup"><span data-stu-id="29d51-144">Make the collected data anonymous</span></span>

<span data-ttu-id="29d51-145">すべてのレポート用に収集されるデータを匿名にするためには、グローバル管理者になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d51-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="29d51-146">これにより、レポートやテンプレート アプリのユーザー名、グループ名、サイト名などの識別可能な情報が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="29d51-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="29d51-147">管理センターで、[組織の設定] の **[設定**] に移動し、[サービス] タブの [レポート] \> を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="29d51-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="29d51-148">[ **レポート] を** 選択し、[匿名識別子の **表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="29d51-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="29d51-149">この設定は、使用状況レポートとテンプレート アプリの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="29d51-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="29d51-150">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29d51-150">Select **Save changes**.</span></span>