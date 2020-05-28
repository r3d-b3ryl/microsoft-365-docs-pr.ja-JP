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
ms.openlocfilehash: fa0973521f5a5e7e8b9b0fda161a5b4779d64c68
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401508"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="24694-103">Microsoft 365 利用状況分析を有効にする</span><span class="sxs-lookup"><span data-stu-id="24694-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="24694-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="24694-104">The admin center is changing.</span></span> <span data-ttu-id="24694-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24694-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="24694-106">Microsoft 365 usage analytics は、Microsoft 365 US Government Community でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="24694-106">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="24694-107">Microsoft 365 usage analytics を有効にする手順</span><span class="sxs-lookup"><span data-stu-id="24694-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="24694-108">Microsoft 365 usage analytics の使用を開始するには、まず、Microsoft 365 管理センターでデータを利用できるようにし、次に Power BI でテンプレートアプリを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24694-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="24694-109">Power BI を取得する</span><span class="sxs-lookup"><span data-stu-id="24694-109">Get Power BI</span></span>

<span data-ttu-id="24694-110">Power BI をまだ持っていない場合は、 [POWER Bi Pro にサインアップ](https://go.microsoft.com/fwlink/p/?linkid=845347)できます。</span><span class="sxs-lookup"><span data-stu-id="24694-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="24694-111">[**無料**] を選択して試用版にサインアップするか、**今すぐ購入**して power BI Pro を入手します。</span><span class="sxs-lookup"><span data-stu-id="24694-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="24694-112">[ **製品**] を展開して Power BI のバージョンを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="24694-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="24694-113">テンプレートアプリをインストール、カスタマイズ、および配布するには、Power BI Pro ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="24694-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="24694-114">詳細については、「[前提条件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24694-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="24694-115">コンテンツを共有するには、Power BI Pro ライセンスが必要です。また、共有しているユーザーも、コンテンツを[プレミアム容量](https://docs.microsoft.com/power-bi/service-premium-what-is)のワークスペースに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24694-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="24694-116">テンプレートアプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="24694-116">Enable the template app</span></span>

<span data-ttu-id="24694-117">テンプレートアプリを有効にするには、**全体管理者**、**レポート閲覧**者、 **Exchange 管理者**、 **Skype For business 管理**者、または**SharePoint 管理者**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="24694-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="24694-118">詳細については、「[管理者ロールについ](../add-users/about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24694-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="24694-119">管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24694-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="24694-120">[**使用法**] ページで、 **Microsoft 365 Usage analytics**カードを見つけて、[**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24694-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="24694-121">表示された [レポート] パネルで、Power BI to Save **On** the **Microsoft 365 usage analytics が [データを利用できるようにする**] を設定し \> **Save**ます。</span><span class="sxs-lookup"><span data-stu-id="24694-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="24694-122">これにより、データ収集プロセスが開始され、テナントのサイズに応じて 2 ~ 48 時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="24694-122">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="24694-123">データ収集が完了すると、 **[POWER BI に移動**] ボタンが有効になります (灰色ではなくなります)。</span><span class="sxs-lookup"><span data-stu-id="24694-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="24694-124">テンプレートアプリを開始する</span><span class="sxs-lookup"><span data-stu-id="24694-124">Initiate the template app</span></span>

<span data-ttu-id="24694-125">テンプレートアプリを開始するには、**全体管理者**、**レポート閲覧**者、 **Exchange 管理者**、 **Skype For business 管理**者、または**SharePoint 管理者**のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="24694-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="24694-126">テナント Id をコピーして、[ **POWER BI に移動] を**選択します。</span><span class="sxs-lookup"><span data-stu-id="24694-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="24694-127">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="24694-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="24694-128">ナビゲーションメニューから [アプリの >取得] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24694-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="24694-129">[**アプリ**] タブで、[検索] ボックスに「microsoft 365」と入力し、[ **microsoft 365 usage analytics** \> **Get now**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24694-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="24694-130">[![[今すぐ取得] を選択する](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="24694-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="24694-131">アプリがインストールされると、</span><span class="sxs-lookup"><span data-stu-id="24694-131">Once the app is installed.</span></span> <span data-ttu-id="24694-132">タイルをクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="24694-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="24694-133">[**アプリの検索**] をクリックして、サンプルデータを含むアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="24694-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="24694-134">[**接続**] をクリックして、アプリを組織のデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="24694-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="24694-135">[**接続**] をクリックした後、[ **Microsoft 365 Usage analytics に接続**します] 画面で、手順 (1) でコピーしたテナント Id (ダッシュなし) を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24694-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="24694-136">次の画面で、**認証方法**にサインインして**oAuth2**を選択し \> **Sign in**ます。</span><span class="sxs-lookup"><span data-stu-id="24694-136">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="24694-137">他の認証方法を選択した場合は、テンプレートアプリへの接続が失敗します。</span><span class="sxs-lookup"><span data-stu-id="24694-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="24694-139">テンプレートアプリがインスタンス化されると、Microsoft 365 usage analytics ダッシュボードが web 上の Power BI で利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="24694-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="24694-140">ダッシュボードの最初の読み込みには、2 ~ 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="24694-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="24694-141">テナントレベル集計は、すべてのレポートで使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="24694-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="24694-142">**ユーザーレベルの詳細は、カレンダー月の最初または15日以降にのみ使用可能に**なります。</span><span class="sxs-lookup"><span data-stu-id="24694-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="24694-143">これにより、ユーザーアクティビティの下にあるすべてのレポートが影響を受ける可能性があります (「 [Microsoft 365 usage analytics のレポート](navigate-and-utilize-reports.md)を表示および使用する方法に関するヒント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="24694-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="24694-144">収集されたデータを匿名にする</span><span class="sxs-lookup"><span data-stu-id="24694-144">Make the collected data anonymous</span></span>

<span data-ttu-id="24694-145">すべてのレポート用に収集されるデータを匿名にするためには、グローバル管理者になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="24694-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="24694-146">これにより、レポートおよびテンプレートアプリ内のユーザー、グループ、サイト名など、識別可能な情報が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="24694-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="24694-147">管理センターで、[設定] [ **Settings** \> **組織設定**] に移動し、[**サービス**] タブの [**レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24694-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="24694-148">[**レポート**] を選択し、**匿名識別子を表示**するように選択します。</span><span class="sxs-lookup"><span data-stu-id="24694-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="24694-149">この設定は、利用状況レポートだけでなく、テンプレートアプリにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="24694-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="24694-150">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24694-150">Select **Save changes**.</span></span>
