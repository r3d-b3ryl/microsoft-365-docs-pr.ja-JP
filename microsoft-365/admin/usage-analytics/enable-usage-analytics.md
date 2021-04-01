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
ms.openlocfilehash: 734712994d47fcb234ba988bb4d185d09f3267d0
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471059"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="be069-103">Microsoft 365 利用状況分析を有効にする</span><span class="sxs-lookup"><span data-stu-id="be069-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="be069-104">Microsoft 365 使用状況分析は、Microsoft 365 US Government Community ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="be069-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="be069-105">Microsoft 365 利用状況分析を有効にする手順</span><span class="sxs-lookup"><span data-stu-id="be069-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="be069-106">Microsoft 365 利用状況分析を開始するには、まず Microsoft 365 管理センターでデータを利用し、次に Power BI でテンプレート アプリを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be069-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="be069-107">Power BI を取得する</span><span class="sxs-lookup"><span data-stu-id="be069-107">Get Power BI</span></span>

<span data-ttu-id="be069-108">Power BI をまだ持ってない場合は [、Power BI Pro にサインアップできます](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="be069-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="be069-109">[**無料で試** 用] を選択して試用版にサインアップするか、[今すぐ購入] を選択して Power BI Pro を取得します。</span><span class="sxs-lookup"><span data-stu-id="be069-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="be069-110">[ **製品**] を展開して Power BI のバージョンを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="be069-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="be069-111">テンプレート アプリをインストール、カスタマイズ、配布するには、Power BI Pro ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="be069-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="be069-112">詳細については、「前提条件」を [参照してください](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="be069-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="be069-113">データを共有するには、ユーザーとデータを共有するユーザー、Power BI Pro ライセンスが必要、またはコンテンツが Power BI プレミアム サービスのワークスペースにある [必要があります](/power-bi/service-premium-what-is)。</span><span class="sxs-lookup"><span data-stu-id="be069-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="be069-114">テンプレート アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="be069-114">Enable the template app</span></span>

<span data-ttu-id="be069-115">テンプレート アプリを有効にするには、グローバル管理者である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="be069-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="be069-116">詳細 [については、「管理者の役割」](../add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be069-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="be069-117">管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="be069-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="be069-118">[使用状況 **] ページで\*\*\*\*、Microsoft 365** 利用状況分析カードを見つけて、[開始]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be069-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="be069-119">開く [レポート] パネルで、[Power BI の **Microsoft 365** 利用状況分析でデータを使用できる] を [保存時] **に設定** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="be069-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="be069-120">データ収集プロセスは、テナントのサイズに応じて 2 ~ 48 時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="be069-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="be069-121">データ **収集が完了すると、[Power BI** に移動] ボタンが有効になります (灰色ではなくなりました)。</span><span class="sxs-lookup"><span data-stu-id="be069-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="be069-122">テンプレート アプリを起動する</span><span class="sxs-lookup"><span data-stu-id="be069-122">Start the template app</span></span>

<span data-ttu-id="be069-123">テンプレート アプリを起動するには、グローバル管理者、レポートリーダー **、Exchange 管理者、Skype** **for Business** 管理者、**または SharePoint 管理者である必要があります**。 </span><span class="sxs-lookup"><span data-stu-id="be069-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="be069-124">テナント ID をコピーし **、[Power BI に移動] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be069-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="be069-125">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="be069-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="be069-126">次に **、[アプリ]** -> **ナビゲーション メニューから**[アプリを取得する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be069-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="be069-127">[アプリ **] タブで** 、検索ボックスに「Microsoft 365」と入力し **、[Microsoft 365 利用状況** 分析] を選択します。今すぐ \> **取得します**。</span><span class="sxs-lookup"><span data-stu-id="be069-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="be069-128">[![[今すぐ取得] を選択します。](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="be069-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="be069-129">アプリがインストールされた後。</span><span class="sxs-lookup"><span data-stu-id="be069-129">Once the app is installed.</span></span> <span data-ttu-id="be069-130">タイルを選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="be069-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="be069-131">[アプリ **の探索] を** 選択して、サンプル データを使用してアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="be069-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="be069-132">[ **接続] を** 選択して、アプリを組織のデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="be069-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="be069-133">[ **接続]** を選択し **、[Microsoft 365** 利用状況分析に接続する] 画面で、手順 (1) でコピーしたテナント ID (ダッシュなし) を入力し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="be069-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="be069-134">次の画面で、[認証]**メソッドとして [OAuth2]** **を選択します** \> 。</span><span class="sxs-lookup"><span data-stu-id="be069-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="be069-135">他の認証方法を選択すると、テンプレート アプリへの接続が失敗します。</span><span class="sxs-lookup"><span data-stu-id="be069-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![認証方法として Microsoft アカウントを選択する](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="be069-137">テンプレート アプリのインスタンス化後、Microsoft 365 利用状況分析ダッシュボードは、Web 上の Power BI で使用できます。</span><span class="sxs-lookup"><span data-stu-id="be069-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="be069-138">ダッシュボードの初期読み込みには 2 ~ 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="be069-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="be069-139">テナント レベルの集計は、オプトイン後にすべてのレポートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="be069-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="be069-140">**ユーザー レベルの詳細は、オプトイン後の次の暦月の 5 日の周りにのみ利用できます**。</span><span class="sxs-lookup"><span data-stu-id="be069-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="be069-141">これは、[ユーザー アクティビティ] の下のすべてのレポートに影響します (これらのレポートを表示および使用する方法のヒントについては [、「Microsoft 365](navigate-and-utilize-reports.md) 利用状況分析のレポートを移動して利用する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="be069-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="be069-142">収集されたデータを匿名にする</span><span class="sxs-lookup"><span data-stu-id="be069-142">Make the collected data anonymous</span></span>

<span data-ttu-id="be069-143">すべてのレポート用に収集されるデータを匿名にするためには、グローバル管理者になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="be069-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="be069-144">これにより、レポートやテンプレート アプリのユーザー名、グループ名、サイト名などの識別可能な情報が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="be069-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="be069-145">管理センターで、[組織の設定] の **[設定**] に移動し、[サービス] タブの [レポート] \> を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="be069-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="be069-146">[ **レポート] を** 選択し、[匿名識別子の **表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be069-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="be069-147">この設定は、使用状況レポートとテンプレート アプリの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="be069-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="be069-148">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be069-148">Select **Save changes**.</span></span>