---
title: 保管担当者を Advanced eDiscovery ケースにインポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: インポート ツールを使用して、Advanced eDiscovery のケースに複数の保管担当者と関連するデータ ソースをすばやく追加します。
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740304"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="5a1eb-103">保管担当者を Advanced eDiscovery ケースにインポートする</span><span class="sxs-lookup"><span data-stu-id="5a1eb-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="5a1eb-104">多くの保管担当者が関係する Advanced eDiscovery ケースでは、ケースに追加するために必要な情報を含む CSV ファイルを使用して、一度に複数の保管担当者をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="5a1eb-105">保管担当者をインポートする</span><span class="sxs-lookup"><span data-stu-id="5a1eb-105">Import custodians</span></span>

1. <span data-ttu-id="5a1eb-106">Advanced eDiscovery ケースを開き、[データ ソース **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="5a1eb-107">[データ **ソースのインポート 保管担当者の**  >  **追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="5a1eb-108">[カ **ストディアンのインポート]** フライアウトページで、空のテンプレートをダウンロードしてカストディアン テンプレート CSV ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![[カストディアンのインポート] フライアウト ページから CSV テンプレートをダウンロードする](../media/ImportCustodians1.png)

4. <span data-ttu-id="5a1eb-110">CSV ファイルに保管情報を追加し、ローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="5a1eb-111">CSV ファイル [で必要なプロパティの](#custodian-csv-file) 詳細については、保管担当者の CSV ファイルセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="5a1eb-112">保管担当者の情報を含む CSV ファイルを準備した後、[データソース] タブに戻り、[データ ソースのインポート 保管担当者の追加] を再度クリック  >  します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="5a1eb-113">[カ **ストディアンのインポート]** フライアウト ページで、[参照] **をクリックし** 、保管担当者の情報を含む CSV ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="5a1eb-114">CSV ファイルをアップロードすると **、BulkAddCusto読** み取りという名前のジョブが作成され、[ジョブ] タブに **表示** されます。ジョブは、保管担当者と関連するデータ ソースを検証し、ケースの [データ ソース] **ページに** 追加します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="5a1eb-115">保管担当者 CSV ファイル</span><span class="sxs-lookup"><span data-stu-id="5a1eb-115">Custodian CSV file</span></span>

<span data-ttu-id="5a1eb-116">CSV カストディアン テンプレートをダウンロードした後、各行にカストディアンとそのデータ ソースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="5a1eb-117">ヘッダー行の列名は必ず変更してください。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="5a1eb-118">ワークロードの種類とワークロードの場所の列を使用して、他のデータ ソースを保管担当者に関連付ける。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="5a1eb-119">列名</span><span class="sxs-lookup"><span data-stu-id="5a1eb-119">Column name</span></span>|<span data-ttu-id="5a1eb-120">説明</span><span class="sxs-lookup"><span data-stu-id="5a1eb-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="5a1eb-121">**Custodian contactEmail**</span><span class="sxs-lookup"><span data-stu-id="5a1eb-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="5a1eb-122">保管担当者の UPN メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-122">The custodian's UPN email address.</span></span> <span data-ttu-id="5a1eb-123">たとえば、sarad@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="5a1eb-124">**Exchange Enabled**</span><span class="sxs-lookup"><span data-stu-id="5a1eb-124">**Exchange Enabled**</span></span> | <span data-ttu-id="5a1eb-125">保管担当者のメールボックスを含めるか含めるか含めない場合の TRUE/FALSE 値。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="5a1eb-126">**OneDrive の有効化**</span><span class="sxs-lookup"><span data-stu-id="5a1eb-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="5a1eb-127">保管担当者の OneDrive for Business アカウントを含めるか含めない場合の TRUE/FALSE 値。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="5a1eb-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="5a1eb-128">**Is OnHold**</span></span>        | <span data-ttu-id="5a1eb-129">保管担当者のデータ ソースを保留にするかどうかを示す TRUE または FALSE の値。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="5a1eb-130">**Workload1 の種類**</span><span class="sxs-lookup"><span data-stu-id="5a1eb-130">**Workload1 Type**</span></span>         |<span data-ttu-id="5a1eb-131">保管担当者に関連付けるデータ ソースの種類を示す文字列値。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="5a1eb-132">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-132">Possible values include:</span></span> <br/><span data-ttu-id="5a1eb-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="5a1eb-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="5a1eb-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="5a1eb-134">- SharePointSite</span></span><br/><span data-ttu-id="5a1eb-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="5a1eb-135">- TeamsMailbox</span></span><br/><span data-ttu-id="5a1eb-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="5a1eb-136">- TeamsSite</span></span><br/> <span data-ttu-id="5a1eb-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="5a1eb-137">- YammerMailbox</span></span><br/><span data-ttu-id="5a1eb-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="5a1eb-138">- YammerSite</span></span> |
|<span data-ttu-id="5a1eb-139">**Workload1 の場所**</span><span class="sxs-lookup"><span data-stu-id="5a1eb-139">**Workload1 Location**</span></span>     | <span data-ttu-id="5a1eb-140">ワークロードの種類に応じて、これはデータ ソースの場所です。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="5a1eb-141">たとえば、Exchange メールボックスの電子メール アドレスや SharePoint サイトの URL などです。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="5a1eb-142">カストディアン情報を含む CSV ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="5a1eb-143">Custodian contactEmail</span><span class="sxs-lookup"><span data-stu-id="5a1eb-143">Custodian contactEmail</span></span>      | <span data-ttu-id="5a1eb-144">Exchange Enabled</span><span class="sxs-lookup"><span data-stu-id="5a1eb-144">Exchange Enabled</span></span> | <span data-ttu-id="5a1eb-145">OneDrive の有効化</span><span class="sxs-lookup"><span data-stu-id="5a1eb-145">OneDrive Enabled</span></span> | <span data-ttu-id="5a1eb-146">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="5a1eb-146">Is OnHold</span></span> | <span data-ttu-id="5a1eb-147">Workload1 の種類</span><span class="sxs-lookup"><span data-stu-id="5a1eb-147">Workload1 Type</span></span> | <span data-ttu-id="5a1eb-148">Workload1 の場所</span><span class="sxs-lookup"><span data-stu-id="5a1eb-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="5a1eb-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a1eb-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="5a1eb-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="5a1eb-150">TRUE</span></span>             | <span data-ttu-id="5a1eb-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="5a1eb-151">TRUE</span></span>             | <span data-ttu-id="5a1eb-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="5a1eb-152">TRUE</span></span>      | <span data-ttu-id="5a1eb-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="5a1eb-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="5a1eb-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a1eb-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="5a1eb-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="5a1eb-155">TRUE</span></span>             | <span data-ttu-id="5a1eb-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="5a1eb-156">TRUE</span></span>             | <span data-ttu-id="5a1eb-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="5a1eb-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="5a1eb-158">保管担当者とデータ ソースの検証</span><span class="sxs-lookup"><span data-stu-id="5a1eb-158">Custodian and data source validation</span></span>

<span data-ttu-id="5a1eb-159">保管担当者の CSV ファイルをアップロードすると、Advanced eDiscovery は次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="5a1eb-160">保管担当者とそのデータ ソースを検証します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="5a1eb-161">各保管担当者のすべてのデータ ソースのインデックスを作成し、保留します (CSV ファイルの **Is OnHold** プロパティが TRUE に設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="5a1eb-162">カストディアンの検証</span><span class="sxs-lookup"><span data-stu-id="5a1eb-162">Custodian validation</span></span>

<span data-ttu-id="5a1eb-163">現時点では、組織の Azure Active Directory (Azure Active Directory) に含まれるカストディアンのインポートのみをサポートAD。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="5a1eb-164">保管担当者インポート ツールは、CSV ファイルの **Custodian contactEmail** 列の UPN 値を使用して、カストディアンを検索して検証します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="5a1eb-165">検証された保管担当者は、ケースに自動的に追加され、ケースの [データ ソース] **タブに** 一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="5a1eb-166">カストディアンを検証できない場合は、ケースの [ジョブ] タブに表示される BulkAddCustoian ジョブのエラー ログに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="5a1eb-167">未確認のカストディアンは、ケースに追加されないか、[データ ソース] タブ **に表示** されません。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="5a1eb-168">データ ソースの検証</span><span class="sxs-lookup"><span data-stu-id="5a1eb-168">Data source validation</span></span>

<span data-ttu-id="5a1eb-169">カストディアンが検証され、ケースに追加された後、カストディアンに関連付けられている各プライマリ メールボックスと OneDrive アカウントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="5a1eb-170">ただし、保管担当者に関連付けられている他のデータ ソース (SharePoint サイト、Microsoft Teams、Microsoft 365 グループ、Yammer グループなど) が見つからない場合は、保管担当者に割り当てられていないデータ ソースが見つかり、[データ ソース] タブの [状態]列に [検証されていない] の値が表示されます。 </span><span class="sxs-lookup"><span data-stu-id="5a1eb-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="5a1eb-171">カストディアンの検証済みデータ ソースを追加するには:</span><span class="sxs-lookup"><span data-stu-id="5a1eb-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="5a1eb-172">[ **データ ソース] タブ** で、検証されていないデータ ソースを含む保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="5a1eb-173">カストディアンのフライアウト ページで、[ **保管** 場所] セクションまでスクロールして、カストディアンに関連付けられている検証済みデータ ソースと検証されていないデータ ソースの両方を表示します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="5a1eb-174">無効 **な** データ ソースを削除するか、新しいデータ ソースを追加するには、フライアウト ページの上部にある [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="5a1eb-175">未確認のデータ ソースを削除するか、新しいデータ ソースを追加すると、[データ ソース] タブの保管担当者の [状態] 列に値 **Active** **が表示** されます。以前は無効と思だったソースを追加するには、次の修復手順に従って手動でカストディアンに追加します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="5a1eb-176">無効なデータ ソースの修復</span><span class="sxs-lookup"><span data-stu-id="5a1eb-176">Remediating invalid data sources</span></span>

<span data-ttu-id="5a1eb-177">以前に無効だったデータ ソースを手動で追加して関連付けるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="5a1eb-178">[データ ソース **] タブで** 、以前は無効だったデータ ソースを手動で追加して関連付けるカストディアンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="5a1eb-179">フライ **アウト** ページの上部にある [編集] をクリックして、メールボックス、サイト、Teams、または Yammerグループをカストディアンに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="5a1eb-180">これを行うには、適切なデータ **の場所** の種類の横にある [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="5a1eb-181">[ **次へ** ] を **クリックして保留設定** ページを表示し、追加したデータ ソースの保留設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="5a1eb-182">[**次へ]** をクリックして **[保管担当者の** 確認] ページを表示し、[送信] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5a1eb-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
