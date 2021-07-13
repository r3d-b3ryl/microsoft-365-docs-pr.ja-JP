---
title: Microsoft 365 利用状況分析を有効にする
f1.keywords:
- CSH
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: テナントのデータ収集を開始する方法については、Microsoft 365 Usage Analytics テンプレート アプリを使用Power BI。
ms.openlocfilehash: c0e39a307ee75c661e0f91fcbbcfeae3d95c7257
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394751"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="2e7c0-103">Microsoft 365 利用状況分析を有効にする</span><span class="sxs-lookup"><span data-stu-id="2e7c0-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="2e7c0-104">Microsoft 365の使用状況分析は、米国政府機関向けMicrosoft 365まだCommunity。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2e7c0-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="2e7c0-105">Before you begin</span></span>

<span data-ttu-id="2e7c0-106">使用状況分析をMicrosoft 365するには、まずデータを Microsoft 365 管理センター で使用し、次にテンプレート アプリを開始する必要Power BI。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>

## <a name="get-power-bi"></a><span data-ttu-id="2e7c0-107">Power BI を取得する</span><span class="sxs-lookup"><span data-stu-id="2e7c0-107">Get Power BI</span></span>

<span data-ttu-id="2e7c0-108">まだインストールしていない場合は[Power BIにサインアップ](https://go.microsoft.com/fwlink/p/?linkid=845347)Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="2e7c0-109">[**無料で試** 用] を選択して試用版にサインアップするか、[今すぐ購入] を選択して、Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>


<span data-ttu-id="2e7c0-110">[ **製品**] を展開して Power BI のバージョンを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-110">You can also expand **Products** to buy a version of Power BI.</span></span>

> [!NOTE]
> <span data-ttu-id="2e7c0-111">テンプレート アプリをインストールPower BI Pro配布するには、ユーザー ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="2e7c0-112">詳細については、「前提条件」を [参照してください](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="2e7c0-113">データを共有するには、ユーザーとデータを共有するユーザー、Power BI Pro ライセンスが必要、またはコンテンツが Power BI プレミアム サービスの[ワークスペースにある必要があります](/power-bi/service-premium-what-is)。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span>

## <a name="enable-the-template-app"></a><span data-ttu-id="2e7c0-114">テンプレート アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="2e7c0-114">Enable the template app</span></span>

<span data-ttu-id="2e7c0-115">テンプレート アプリを有効にするには、グローバル管理者である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-115">To enable the template app, you have to be a **Global administrator**.</span></span>

<span data-ttu-id="2e7c0-116">詳細 [については、「管理者の役割」](../add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span>

1. <span data-ttu-id="2e7c0-117">管理センターで、[組織設定サービス] タブ **設定** \> **に** \> **移動** します。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span>

2. <span data-ttu-id="2e7c0-118">[サービス] **タブで** 、[レポート] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-118">On the **Services** tab, select  **Reports**.</span></span>

3. <span data-ttu-id="2e7c0-119">開く [レポート] パネルで、[レポート データを有効にする] を [Microsoft 365の使用状況分析で使用Power BI] を [**保存中**]**に** \> **設定します**。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span>

<span data-ttu-id="2e7c0-120">データ収集プロセスは、テナントのサイズに応じて 2 ~ 48 時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="2e7c0-121">データ **収集が完了Power BI[** 移動] ボタンが有効になります (灰色は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span>

## <a name="start-the-template-app"></a><span data-ttu-id="2e7c0-122">テンプレート アプリを起動する</span><span class="sxs-lookup"><span data-stu-id="2e7c0-122">Start the template app</span></span>

<span data-ttu-id="2e7c0-123">テンプレート アプリを起動するには、グローバル管理者、レポートリーダー、Exchange管理者、Skype for Business管理者、または管理者SharePoint **する必要があります**。 </span><span class="sxs-lookup"><span data-stu-id="2e7c0-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span>

1. <span data-ttu-id="2e7c0-124">テナント ID をコピーし、[移動]**を選択Power BI。**</span><span class="sxs-lookup"><span data-stu-id="2e7c0-124">Copy the tenant ID and select **Go to Power BI**.</span></span>

2. <span data-ttu-id="2e7c0-125">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="2e7c0-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="2e7c0-126">次に **、[アプリ]** -> **ナビゲーション メニューから**[アプリを取得する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>

3. <span data-ttu-id="2e7c0-127">[アプリ **] タブ** で、検索ボックスにMicrosoft 365を入力し、[使用状況分析Microsoft 365今すぐ取得する] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="2e7c0-128">[![[今すぐ取得] を選択します。](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="2e7c0-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>

4. <span data-ttu-id="2e7c0-129">アプリがインストールされた後。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-129">Once the app is installed.</span></span> <span data-ttu-id="2e7c0-130">タイルを選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-130">Select the tile to open it.</span></span>

5. <span data-ttu-id="2e7c0-131">[アプリ **の探索] を** 選択して、サンプル データを使用してアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="2e7c0-132">**[Connect]** を選択して、アプリを組織のデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6. <span data-ttu-id="2e7c0-133">[Connect] を選択し、[Connect から Microsoft 365 利用状況分析] 画面で、手順 (1) でコピーしたテナント ID (ダッシュなし) を入力し、[次へ] を選択します。  </span><span class="sxs-lookup"><span data-stu-id="2e7c0-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>

7. <span data-ttu-id="2e7c0-134">次の画面で、[認証]**メソッドとして [OAuth2]** **を選択します** \> 。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="2e7c0-135">他の認証方法を選択すると、テンプレート アプリへの接続が失敗します。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>

    ![認証方法として Microsoft アカウントを選択する](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. <span data-ttu-id="2e7c0-137">テンプレート アプリがインスタンス化されると、Microsoft 365分析ダッシュボードが web 上Power BIで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="2e7c0-138">ダッシュボードの初期読み込みには 2 ~ 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>

<span data-ttu-id="2e7c0-139">テナント レベルの集計は、オプトイン後にすべてのレポートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="2e7c0-140">**ユーザー レベルの詳細は、オプトイン後の次の暦月の 5 日の周りにのみ利用できます**。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="2e7c0-141">これは、[ユーザー アクティビティ] の下のすべての[](navigate-and-utilize-reports.md)レポートに影響します (これらのレポートを表示および使用する方法のヒントについては、「Microsoft 365 利用状況分析のレポートを移動して利用する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>

## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="2e7c0-142">収集されたデータを匿名にする</span><span class="sxs-lookup"><span data-stu-id="2e7c0-142">Make the collected data anonymous</span></span>

<span data-ttu-id="2e7c0-143">すべてのレポート用に収集されるデータを匿名にするためには、グローバル管理者になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="2e7c0-144">これにより、レポートやテンプレート アプリのユーザー名、グループ名、サイト名などの識別可能な情報が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>

1. <span data-ttu-id="2e7c0-145">管理センターで、[組織] の[組織設定] 設定[サービス] タブで \> **、[** レポート] を選択 **します**。 </span><span class="sxs-lookup"><span data-stu-id="2e7c0-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>

2. <span data-ttu-id="2e7c0-146">[ **レポート] を** 選択し、[匿名識別子の **表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="2e7c0-147">この設定は、使用状況レポートとテンプレート アプリの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>

3. <span data-ttu-id="2e7c0-148">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e7c0-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="2e7c0-149">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="2e7c0-149">Related content</span></span>

<span data-ttu-id="2e7c0-150">[利用状況分析について](usage-analytics.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="2e7c0-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="2e7c0-151">[使用状況分析の最新バージョンを取得](get-the-latest-version-of-usage-analytics.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="2e7c0-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="2e7c0-152">[使用状況分析のレポートを移動Microsoft 365活用する](navigate-and-utilize-reports.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="2e7c0-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>