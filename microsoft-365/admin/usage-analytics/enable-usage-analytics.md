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
description: Power BI の Microsoft 365 Usage Analytics テンプレートアプリを使用して、テナントのデータの収集を開始する方法について説明します。
ms.openlocfilehash: 347256fa7acaae18cd31f0c8c6b7eca20ad2e9dd
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941333"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="01d64-103">Microsoft 365 利用状況分析を有効にする</span><span class="sxs-lookup"><span data-stu-id="01d64-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="01d64-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="01d64-104">The admin center is changing.</span></span> <span data-ttu-id="01d64-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d64-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="01d64-106">Microsoft 365 usage analytics は、Microsoft 365 US Government Community ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="01d64-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="01d64-107">Microsoft 365 usage analytics を有効にする手順</span><span class="sxs-lookup"><span data-stu-id="01d64-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="01d64-108">Microsoft 365 usage analytics の使用を開始するには、まず、Microsoft 365 管理センターでデータを利用できるようにし、次に Power BI でテンプレートアプリを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d64-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="01d64-109">Power BI を取得する</span><span class="sxs-lookup"><span data-stu-id="01d64-109">Get Power BI</span></span>

<span data-ttu-id="01d64-110">Power BI をまだ持っていない場合は、 [POWER Bi Pro にサインアップ](https://go.microsoft.com/fwlink/p/?linkid=845347)できます。</span><span class="sxs-lookup"><span data-stu-id="01d64-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="01d64-111">[ **無料** ] を選択して試用版にサインアップするか、 **今すぐ購入** して power BI Pro を入手します。</span><span class="sxs-lookup"><span data-stu-id="01d64-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="01d64-112">[ **製品** ] を展開して Power BI のバージョンを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="01d64-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="01d64-113">テンプレートアプリをインストール、カスタマイズ、および配布するには、Power BI Pro ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="01d64-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="01d64-114">詳細については、「 [前提条件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d64-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="01d64-115">データを共有するには、お客様とデータを共有しているユーザーの両方が Power BI Pro ライセンスを必要とするか、 [POWER bi プレミアムサービス](https://docs.microsoft.com/power-bi/service-premium-what-is)のワークスペースにコンテンツが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d64-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="01d64-116">テンプレートアプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="01d64-116">Enable the template app</span></span>

<span data-ttu-id="01d64-117">テンプレートアプリを有効にするには、 **全体管理者** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d64-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="01d64-118">詳細については、「 [管理者ロールについ](../add-users/about-admin-roles.md) て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d64-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="01d64-119">管理センターで、[ **レポート** ] \> [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="01d64-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="01d64-120">[ **使用法** ] ページで、 **Microsoft 365 Usage analytics** カードを見つけて、[ **開始** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01d64-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="01d64-121">表示された [レポート] パネルで、Power BI to Save **On** the **Microsoft 365 usage analytics が [データを利用できるようにする** ] を設定し \> **Save** ます。</span><span class="sxs-lookup"><span data-stu-id="01d64-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="01d64-122">テナントのサイズに応じて、データ収集プロセスは 2 ~ 48 時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="01d64-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="01d64-123">データ収集が完了すると、 **[POWER BI に移動** ] ボタンが有効になります (灰色ではなくなります)。</span><span class="sxs-lookup"><span data-stu-id="01d64-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="01d64-124">テンプレートアプリを開始する</span><span class="sxs-lookup"><span data-stu-id="01d64-124">Start the template app</span></span>

<span data-ttu-id="01d64-125">テンプレートアプリを開始するには、 **全体管理者** 、 **レポート閲覧** 者、 **Exchange 管理者** 、 **Skype For business 管理** 者、または **SharePoint 管理者** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d64-125">To start the template app, you have to be either a **global administrator** , **report reader** , **Exchange administrator** , **Skype for Business administrator** , or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="01d64-126">テナント ID をコピーして、[ **POWER BI に移動] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="01d64-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="01d64-127">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="01d64-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="01d64-128">次 **Select Apps** -> に、[ナビゲーション] メニューから [アプリの **取得** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01d64-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="01d64-129">[ **アプリ** ] タブで、[検索] ボックスに「microsoft 365」と入力し、[ **microsoft 365 usage analytics** \> **Get now** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01d64-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="01d64-130">[![[今すぐ取得] を選択する](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="01d64-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="01d64-131">アプリがインストールされると、</span><span class="sxs-lookup"><span data-stu-id="01d64-131">Once the app is installed.</span></span> <span data-ttu-id="01d64-132">タイルを選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="01d64-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="01d64-133">[ **アプリの検索** ] を選択して、サンプルデータを含むアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="01d64-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="01d64-134">[ **接続** ] を選択して、アプリを組織のデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="01d64-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="01d64-135">[ **Microsoft 365 usage analytics に接続** します] 画面で [ **接続** ] を選択し、手順 (1) でコピーしたテナント ID を (ダッシュなしで) 入力して、[ **次へ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01d64-135">Choose **Connect** , on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="01d64-136">次の画面で、 **認証方法** にサインインして **OAuth2** を選択し \> **Sign in** ます。</span><span class="sxs-lookup"><span data-stu-id="01d64-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="01d64-137">他の認証方法を選択した場合は、テンプレートアプリへの接続が失敗します。</span><span class="sxs-lookup"><span data-stu-id="01d64-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![認証方法として Microsoft アカウントを選択する](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="01d64-139">テンプレートアプリがインスタンス化されると、Microsoft 365 usage analytics ダッシュボードが web 上の Power BI で利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="01d64-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="01d64-140">ダッシュボードの最初の読み込みには、2 ~ 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="01d64-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="01d64-141">テナントレベル集計は、すべてのレポートで使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="01d64-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="01d64-142">**ユーザーレベルの詳細は、カレンダー月の最初または15日以降にのみ使用可能に** なります。</span><span class="sxs-lookup"><span data-stu-id="01d64-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="01d64-143">これは、ユーザーアクティビティの下にあるすべてのレポートに影響します。</span><span class="sxs-lookup"><span data-stu-id="01d64-143">This will impact all reports under User Activity.</span></span> <span data-ttu-id="01d64-144">これらのレポートを表示および使用する方法に関するヒントについて [は、「Microsoft 365 usage analytics のレポートをナビゲートして利用](navigate-and-utilize-reports.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d64-144">See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports.</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="01d64-145">収集されたデータを匿名にする</span><span class="sxs-lookup"><span data-stu-id="01d64-145">Make the collected data anonymous</span></span>

<span data-ttu-id="01d64-146">すべてのレポート用に収集されるデータを匿名にするためには、グローバル管理者になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d64-146">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="01d64-147">これにより、レポートおよびテンプレートアプリ内のユーザー、グループ、サイト名など、識別可能な情報が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="01d64-147">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="01d64-148">管理センターで、[設定] [ **Settings** \> **組織設定** ] に移動し、[ **サービス** ] タブの [ **レポート** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01d64-148">In the admin center, go to the **Settings** \> **Org Settings** , and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="01d64-149">[ **レポート** ] を選択し、 **匿名識別子を表示** するように選択します。</span><span class="sxs-lookup"><span data-stu-id="01d64-149">Select **Reports** , and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="01d64-150">この設定は、利用状況レポートだけでなく、テンプレートアプリにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="01d64-150">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="01d64-151">[ **変更の保存** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01d64-151">Select **Save changes**.</span></span>
