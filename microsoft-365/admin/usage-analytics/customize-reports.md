---
title: Microsoft 365 usage analytics でレポートをカスタマイズする
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
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: ブラウザーと Power BI デスクトップでレポートをカスタマイズする方法について説明します。
ms.openlocfilehash: 121a9be4a83570b7fcf358c48bf558d3bc7c1131
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402932"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="b918b-103">Microsoft 365 usage analytics でレポートをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b918b-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b918b-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="b918b-104">The admin center is changing.</span></span> <span data-ttu-id="b918b-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b918b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b918b-106">Microsoft 365 usage analytics は、ユーザーが Microsoft 365 を採用して使用する方法についての洞察を提供する Power BI のダッシュボードを提供します。</span><span class="sxs-lookup"><span data-stu-id="b918b-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="b918b-107">このダッシュボードは、利用状況データを利用するための開始点に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="b918b-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="b918b-108">レポートをカスタマイズし、洞察機能を個人に合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="b918b-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="b918b-109">また、Power BI デスクトップを使用し、レポートをさらにカスタマイズできます。レポートを他のデータ ソースに接続することで事業に関してさらに深い洞察が得られます。</span><span class="sxs-lookup"><span data-stu-id="b918b-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="b918b-110">ブラウザーでレポートをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b918b-110">Customizing reports in the browser</span></span>

<span data-ttu-id="b918b-111">次の 2 つの例は、既存のビジュアルを変更する方法と新しいビジュアルを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b918b-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="b918b-112">既存のビジュアルを変更する</span><span class="sxs-lookup"><span data-stu-id="b918b-112">Modify an existing visual</span></span>

<span data-ttu-id="b918b-113">この例では、**アクティブ化/ライセンス**レポート内の [**アクティブ化**] タブを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b918b-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="b918b-114">ライセンス**認証**レポートで、[**アクティブ化**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b918b-114">Within the **Activation/Licensing** report, click on the **Activation** tab.</span></span>
    
2. <span data-ttu-id="b918b-115">**Edit** ![ Power BI ボタンの [その他のページ] ボタンをクリックして、編集モードに入り ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) ます。</span><span class="sxs-lookup"><span data-stu-id="b918b-115">Enter the edit mode by clicking the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="b918b-117">右上にある [**このページを複製**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b918b-117">On the top right, click **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="b918b-119">右下で、Android、iOS、Mac などの OS に基づいてライセンス認証されたユーザーの数を示す棒グラフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b918b-119">In the bottom right, click on any of the bar charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="b918b-120">ビジュアルから**Mac 数**を削除するために、右側の [**視覚エフェクト**] 領域で、その横にある [ **X** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b918b-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, click on the **X** next to it.</span></span>

    ![Mac カウントの削除](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="b918b-122">新しいビジュアルを作成する</span><span class="sxs-lookup"><span data-stu-id="b918b-122">Create a new visual</span></span>

<span data-ttu-id="b918b-123">次の例は、新しい Yammer ユーザーを月単位で追跡記録する新しいビジュアルの作成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b918b-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="b918b-124">左側のナビゲーションを使用して**製品の使用状況**レポートに移動し、[ **Yammer** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b918b-124">Go to the **Product Usage** report using the left nav and click on **Yammer** tab.</span></span>
    
2. <span data-ttu-id="b918b-125">![POWER BI および edit の [その他のページ] ボタンをクリックして、編集モードに切り替え ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) ます。 **Edit**</span><span class="sxs-lookup"><span data-stu-id="b918b-125">Switch to edit mode by clicking on ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="b918b-126">ページの下部にある [</span><span class="sxs-lookup"><span data-stu-id="b918b-126">At the bottom of the page, click on</span></span> ![Power BI の [ページの追加] ボタン](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="b918b-128">新しいページを作成します。</span><span class="sxs-lookup"><span data-stu-id="b918b-128">to create a new page.</span></span>
  
4. <span data-ttu-id="b918b-129">右にある [**視覚エフェクト**] 領域で、**積み上げ横棒グラフ**(上から最初に左から) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b918b-129">In the **Visualizations** area to the right, click the **Stacked bar chart** (top row, first from left).</span></span>

    ![棒グラフの選択](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="b918b-131">その視覚エフェクトの右下をクリックし、ドラッグして大きくします。</span><span class="sxs-lookup"><span data-stu-id="b918b-131">Click the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="b918b-132">右側の [**フィールド**] 領域で、**予定**表テーブルを展開します。</span><span class="sxs-lookup"><span data-stu-id="b918b-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="b918b-133">[ **MonthName**] を [フィールド] 領域までドラッグします。[ **視覚エフェクト**] 領域の [ **軸**] 見出しのすぐ下にあります。</span><span class="sxs-lookup"><span data-stu-id="b918b-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![月名をドラッグします。](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="b918b-135">右にある [ **フィールド**] 領域の [ **TenantProductUsage**] テーブルを展開します。</span><span class="sxs-lookup"><span data-stu-id="b918b-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="b918b-136">[ **FirstTimeUsers**] を [フィールド] 領域までドラッグします。[ **値**] 見出しのすぐ下にあります。</span><span class="sxs-lookup"><span data-stu-id="b918b-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="b918b-137">[ **Product**] を [ **フィールド**] 領域までドラッグします。[ **ビジュアル レベル フィルター**] 見出しのすぐ下にあります。</span><span class="sxs-lookup"><span data-stu-id="b918b-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="b918b-138">[ **フィルターの種類**] 領域が表示されたら、[ **Yammer**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b918b-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Yammer チェックボックスの選択](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="b918b-140">視覚エフェクトの一覧のすぐ下にある**Format** 、 ![ Power BI Visualizaions の [書式] アイコンの形式アイコンをクリックし ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) ます。</span><span class="sxs-lookup"><span data-stu-id="b918b-140">Just below the list of visualizations, click the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="b918b-141">[タイトル] を展開し、[ **タイトル テキスト**] 値を [ **月別の新規 Yammer ユーザー**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="b918b-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="b918b-142">[ **テキストのサイズ**] 値を [ **12**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="b918b-142">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="b918b-143">右下のページの名前を編集して、新しいページのタイトルを変更します。</span><span class="sxs-lookup"><span data-stu-id="b918b-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="b918b-144">[**閲覧ビュー** ] の上部にある [**保存**] をクリックしてレポートを保存します。</span><span class="sxs-lookup"><span data-stu-id="b918b-144">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="b918b-145">Power BI Desktop のレポートをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b918b-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="b918b-p103">ほとんどのお客様にとっては、Power BI Web のレポートとグラフ ビジュアルを変更すれば十分です。ただし、場合によっては、自社の事業という文脈において深い洞察を得るには、このデータを他のデータ ソースと接続する必要があります。その場合、Power BI デスクトップを利用して追加のレポートをカスタマイズしたり、ビルドしたりできます。[Power BI デスクトップ](https://go.microsoft.com/fwlink/p/?linkid=849797)は無料でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b918b-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="b918b-149">レポート API を使用する</span><span class="sxs-lookup"><span data-stu-id="b918b-149">Use the reporting APIs</span></span>

<span data-ttu-id="b918b-150">開始するには、Microsoft 365 から ODATA レポート Api に直接接続して、これらのレポートを出力します。</span><span class="sxs-lookup"><span data-stu-id="b918b-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="b918b-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span><span class="sxs-lookup"><span data-stu-id="b918b-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="b918b-152">[URL] ウィンドウで、「https:// <i></i> reports.office.com/pbi/v1.0/」と入力します。 \<tenantid\></span><span class="sxs-lookup"><span data-stu-id="b918b-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="b918b-153">**注:** レポート Api はプレビュー段階にあり、運用に入るまで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b918b-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="b918b-155">プロンプトが表示されたら、microsoft 365 (組織または学校) 管理者の資格情報を入力して、Microsoft 365 に認証します。</span><span class="sxs-lookup"><span data-stu-id="b918b-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="b918b-156">Microsoft 365 導入テンプレートアプリレポートへのアクセスが許可されるユーザーの詳細については、 [FAQ](usage-analytics.md#faq)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b918b-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="b918b-157">接続が承認されると、[ナビゲーター] ウィンドウが表示されます。このウィンドウに、接続先として利用できるデータセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b918b-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="b918b-158">すべてを選択し、[ **読み込む**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b918b-158">Select all and click on **Load**.</span></span>
    
    <span data-ttu-id="b918b-p104">これで Power BI デスクトップにデータがダウンロードされます。このファイルを保存すれば、必要なレポートの作成を開始できます。</span><span class="sxs-lookup"><span data-stu-id="b918b-p104">This will download the data into your Power BI Desktop. Save this file and then you can start creating the reports you need.</span></span>
    
    ![レポート API で使用可能な ODATA 値](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="b918b-162">Microsoft 365 usage analytics テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="b918b-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="b918b-163">データに接続する開始点として、Microsoft 365 usage analytics レポートに対応する Power BI テンプレートファイルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b918b-163">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="b918b-164">pbit ファイルを利用することの長所は、接続文字列が既に確立されていることです。</span><span class="sxs-lookup"><span data-stu-id="b918b-164">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="b918b-165">基本スキーマが返すデータに加え、作成されたあらゆるカスタム メジャーを活用し、基本スキーマの上にさらに構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="b918b-165">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="b918b-166">Power BI テンプレートファイルは、[ダウンロードセンター](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)から Microsoft ダウンロードセンターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b918b-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="b918b-167">Power BI テンプレート ファイルをダウンロードしたら、次の手順から開始します。</span><span class="sxs-lookup"><span data-stu-id="b918b-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="b918b-168">pbit ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b918b-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="b918b-169">ダイアログにテナント ID 値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b918b-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="b918b-171">メッセージが表示されたら、管理者の資格情報を入力して Microsoft 365 に認証します。</span><span class="sxs-lookup"><span data-stu-id="b918b-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="b918b-172">Microsoft 365 利用状況分析レポートへのアクセスが許可されるユーザーの詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b918b-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="b918b-173">承認された後に、Power BI ファイルのデータが更新されます。</span><span class="sxs-lookup"><span data-stu-id="b918b-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="b918b-174">データの読み込みには時間がかかることがあります。完了後、ファイルを .pbix ファイルとして保存し、レポートのカスタマイズを続けたり、このレポートにデータ ソースを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="b918b-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="b918b-p107">レポートを作成する方法、Power BI サービスにレポートを公開する方法、組織と共有する方法を理解するには、「[Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802)」 (Power BI を始める) ドキュメントをご覧ください。この方法でカスタマイズと共有を行う場合、追加の Power BI ライセンスが必要になることがあります。詳細については、Power BI の[ライセンスに関するページ](https://go.microsoft.com/fwlink/p/?linkid=849803)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b918b-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

