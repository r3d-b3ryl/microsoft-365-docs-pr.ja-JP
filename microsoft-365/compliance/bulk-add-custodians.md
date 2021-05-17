---
title: 保管担当者をケースにAdvanced eDiscoveryする
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
description: インポート ツール d を使用して、複数の保管担当者と関連付けられたデータ ソースをすばやくケースに追加Advanced eDiscovery。
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421614"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="ceb9a-103">保管担当者をケースにAdvanced eDiscoveryする</span><span class="sxs-lookup"><span data-stu-id="ceb9a-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="ceb9a-104">多Advanced eDiscoveryが関係する場合は、ケースに追加するために必要な情報を含む CSV ファイルを使用して、複数の保管担当者を一度にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="ceb9a-105">保管担当者のインポート</span><span class="sxs-lookup"><span data-stu-id="ceb9a-105">Import custodians</span></span>

1. <span data-ttu-id="ceb9a-106">[データ ソース] Advanced eDiscoveryを開き、[**データ ソース] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="ceb9a-107">[データ **ソースのインポート**  >  **保管担当者の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="ceb9a-108">[保管 **担当者のインポート] フライアウト** ページで、[空のテンプレートをダウンロードする] をクリックして、カストディアン テンプレートの CSV ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![[保管担当者のインポート] フライアウト ページから CSV テンプレートをダウンロードする](../media/ImportCustodians1.png)

4. <span data-ttu-id="ceb9a-110">保管情報を CSV ファイルに追加し、ローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="ceb9a-111">CSV ファイルで [必要なプロパティの詳細については、「Custodian CSV](#custodian-csv-file) ファイル」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="ceb9a-112">保管担当者情報を含む CSV ファイルを準備した後、[データ ソース] タブに戻り、[データ ソースのインポート 保管担当者の追加] を再度  >  **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="ceb9a-113">[保管 **担当者のインポート] フライ** アウト ページで、[参照] をクリックし、保管担当者情報を含む CSV ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="ceb9a-114">CSV ファイルがアップロードされると **、BulkAddCustodian** という名前のジョブが作成され、[ジョブ] タブに **表示** されます。ジョブは、保管担当者と関連付けられたデータ ソースを検証し、ケースの **[** データ ソース] ページに追加します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="ceb9a-115">カストディアン CSV ファイル</span><span class="sxs-lookup"><span data-stu-id="ceb9a-115">Custodian CSV file</span></span>

<span data-ttu-id="ceb9a-116">CSV カストディアン テンプレートをダウンロードした後、各行に保管担当者とそのデータ ソースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="ceb9a-117">ヘッダー行の列名は必ず変更してください。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="ceb9a-118">ワークロードの種類とワークロードの場所の列を使用して、他のデータ ソースを保管担当者に関連付ける。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="ceb9a-119">列名</span><span class="sxs-lookup"><span data-stu-id="ceb9a-119">Column name</span></span>|<span data-ttu-id="ceb9a-120">説明</span><span class="sxs-lookup"><span data-stu-id="ceb9a-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="ceb9a-121">**Custodian contactEmail**</span><span class="sxs-lookup"><span data-stu-id="ceb9a-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="ceb9a-122">保管担当者の UPN メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-122">The custodian's UPN email address.</span></span> <span data-ttu-id="ceb9a-123">たとえば、sarad@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="ceb9a-124">**Exchange有効**</span><span class="sxs-lookup"><span data-stu-id="ceb9a-124">**Exchange Enabled**</span></span> | <span data-ttu-id="ceb9a-125">保管担当者のメールボックスを含めるか含めない場合の TRUE/FALSE 値。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="ceb9a-126">**OneDrive有効**</span><span class="sxs-lookup"><span data-stu-id="ceb9a-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="ceb9a-127">保管担当者のアカウントを含めるか含めない場合は TRUE/FALSE OneDrive for Businessします。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="ceb9a-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="ceb9a-128">**Is OnHold**</span></span>        | <span data-ttu-id="ceb9a-129">保管担当者データ ソースを保留にするかどうかを示す TRUE/FALSE 値。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span> <span data-ttu-id="ceb9a-130"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ceb9a-130"><sup>1</sup></span></span>     |
|<span data-ttu-id="ceb9a-131">**ワークロード 1 の種類**</span><span class="sxs-lookup"><span data-stu-id="ceb9a-131">**Workload1 Type**</span></span>         |<span data-ttu-id="ceb9a-132">保管担当者に関連付けるデータ ソースの種類を示す文字列値。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-132">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="ceb9a-133">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-133">Possible values include:</span></span> <br/><span data-ttu-id="ceb9a-134">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="ceb9a-134">- ExchangeMailbox</span></span><br/> <span data-ttu-id="ceb9a-135">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="ceb9a-135">- SharePointSite</span></span><br/><span data-ttu-id="ceb9a-136">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="ceb9a-136">- TeamsMailbox</span></span><br/><span data-ttu-id="ceb9a-137">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="ceb9a-137">- TeamsSite</span></span><br/> <span data-ttu-id="ceb9a-138">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="ceb9a-138">- YammerMailbox</span></span><br/><span data-ttu-id="ceb9a-139">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="ceb9a-139">- YammerSite</span></span> |
|<span data-ttu-id="ceb9a-140">**ワークロード 1 の場所**</span><span class="sxs-lookup"><span data-stu-id="ceb9a-140">**Workload1 Location**</span></span>     | <span data-ttu-id="ceb9a-141">ワークロードの種類に応じて、これはデータ ソースの場所です。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-141">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="ceb9a-142">たとえば、メールボックスの電子メール アドレスExchangeサイトの URL SharePointします。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-142">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

> [!NOTE]
> <span data-ttu-id="ceb9a-143"><sup>1</sup> 保管担当者のインポート プロセスと CSV ファイルを使用して、最大 1,000 のメールボックスと 100 のサイトを保留にできます。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-143"><sup>1</sup> You can place a maximum of 1,000 mailboxes and 100 sites on hold by using the custodian import process and CSV file.</span></span> <span data-ttu-id="ceb9a-144">このプロセスを使用して、ケースに 1,000 人を超える保管担当者を追加できますが、保留の制限は引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-144">You can use this process to add more than 1,000 custodians to a case, but the hold limits still apply.</span></span> <span data-ttu-id="ceb9a-145">ホールド制限の詳細については、「制限」を参照[Advanced eDiscovery。](limits-ediscovery20.md#hold-limits)</span><span class="sxs-lookup"><span data-stu-id="ceb9a-145">For more information about hold limits, see [Limits in Advanced eDiscovery](limits-ediscovery20.md#hold-limits).</span></span>

<span data-ttu-id="ceb9a-146">保管担当者情報を含む CSV ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-146">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="ceb9a-147">Custodian contactEmail</span><span class="sxs-lookup"><span data-stu-id="ceb9a-147">Custodian contactEmail</span></span>      | <span data-ttu-id="ceb9a-148">Exchange有効</span><span class="sxs-lookup"><span data-stu-id="ceb9a-148">Exchange Enabled</span></span> | <span data-ttu-id="ceb9a-149">OneDrive有効</span><span class="sxs-lookup"><span data-stu-id="ceb9a-149">OneDrive Enabled</span></span> | <span data-ttu-id="ceb9a-150">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="ceb9a-150">Is OnHold</span></span> | <span data-ttu-id="ceb9a-151">ワークロード 1 の種類</span><span class="sxs-lookup"><span data-stu-id="ceb9a-151">Workload1 Type</span></span> | <span data-ttu-id="ceb9a-152">ワークロード 1 の場所</span><span class="sxs-lookup"><span data-stu-id="ceb9a-152">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="ceb9a-153">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ceb9a-153">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="ceb9a-154">TRUE</span><span class="sxs-lookup"><span data-stu-id="ceb9a-154">TRUE</span></span>             | <span data-ttu-id="ceb9a-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="ceb9a-155">TRUE</span></span>             | <span data-ttu-id="ceb9a-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="ceb9a-156">TRUE</span></span>      | <span data-ttu-id="ceb9a-157">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="ceb9a-157">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="ceb9a-158">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ceb9a-158">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="ceb9a-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="ceb9a-159">TRUE</span></span>             | <span data-ttu-id="ceb9a-160">TRUE</span><span class="sxs-lookup"><span data-stu-id="ceb9a-160">TRUE</span></span>             | <span data-ttu-id="ceb9a-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="ceb9a-161">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="ceb9a-162">保管担当者とデータ ソースの検証</span><span class="sxs-lookup"><span data-stu-id="ceb9a-162">Custodian and data source validation</span></span>

<span data-ttu-id="ceb9a-163">保管担当者の CSV ファイルをアップロードした後、Advanced eDiscoveryを実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-163">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="ceb9a-164">保管担当者とそのデータ ソースを検証します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-164">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="ceb9a-165">各保管担当者のすべてのデータ ソースにインデックスを作成し、保持します (CSV ファイルの **Is OnHold** プロパティが TRUE に設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-165">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="ceb9a-166">カストディアン検証</span><span class="sxs-lookup"><span data-stu-id="ceb9a-166">Custodian validation</span></span>

<span data-ttu-id="ceb9a-167">現時点では、組織の管理者 (Azure Azure Active Directory) に含まれるカストディアンAD。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-167">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="ceb9a-168">保管担当者のインポート ツールは、CSV ファイルの **[Custodian contactEmail]** 列の UPN 値を使用して、保管担当者を検索して検証します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-168">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="ceb9a-169">検証された保管担当者は、ケースに自動的に追加され、ケースの [データ **ソース]** タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-169">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="ceb9a-170">保管担当者を検証できない場合は、ケースの [ジョブ] タブに表示される BulkAddCustodian ジョブのエラー ログに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-170">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="ceb9a-171">未確認の保管担当者は、ケースに追加されないか、[データ ソース] タブ **に表示** されません。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-171">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="ceb9a-172">データ ソースの検証</span><span class="sxs-lookup"><span data-stu-id="ceb9a-172">Data source validation</span></span>

<span data-ttu-id="ceb9a-173">保管担当者が検証され、ケースに追加された後、保管担当者に関連付けられている各プライマリ メールボックスと OneDrive アカウントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-173">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="ceb9a-174">ただし、保管担当者に関連付けられた他のデータ ソース (SharePoint サイト、Microsoft Teams、Microsoft 365 グループ、Yammer グループなど) が見つからない場合、それらのデータ ソースはいずれも保管担当者に割り当てられていないので、[データ ソース] タブの [カストディアン]の横にある [状態] 列に値が表示されます。 </span><span class="sxs-lookup"><span data-stu-id="ceb9a-174">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="ceb9a-175">カストディアンの検証済みデータ ソースを追加するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-175">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="ceb9a-176">[データ **ソース] タブ** で、検証されていないデータ ソースを含む保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-176">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="ceb9a-177">カストディアン のフライアウト ページで、[保管場所] セクションまでスクロールして、カストディアンに関連付けられている検証済みデータ ソースと検証されていないデータ ソースの両方を表示します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-177">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="ceb9a-178">無効 **なデータ** ソースを削除するか、新しいデータ ソースを追加するには、フライアウト ページの上部にある [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-178">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="ceb9a-179">未評価のデータ ソースを削除するか、新しいデータ ソースを追加した後、[データソース] タブのカストディアンの [状態] 列に値 Active **が表示** されます。以前は無効と思ったソースを追加するには、以下の修復手順に従って手動で保管担当者に追加します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-179">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="ceb9a-180">無効なデータ ソースの修復</span><span class="sxs-lookup"><span data-stu-id="ceb9a-180">Remediating invalid data sources</span></span>

<span data-ttu-id="ceb9a-181">以前は無効だったデータ ソースを手動で追加して関連付けるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-181">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="ceb9a-182">[データ **ソース] タブで** 、以前は無効だったデータ ソースを手動で追加して関連付ける保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-182">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="ceb9a-183">フライ **アウト ページ** の上部にある [編集] をクリックして、メールボックス、サイト、Teams、Yammerグループをカストディアンに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-183">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="ceb9a-184">これを行うには、適切なデータ **の場所** の種類の横にある [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-184">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="ceb9a-185">[ **次へ** ] をクリック **して [保留** 設定] ページを表示し、追加したデータ ソースの保留設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-185">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="ceb9a-186">[ **次へ]** をクリック **して [保管担当者の確認] ページを表示** し、[ **送信** ] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="ceb9a-186">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
