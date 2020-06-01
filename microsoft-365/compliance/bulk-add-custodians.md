---
title: 高度な電子情報開示ケースへの保管担当者の一括追加
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432440"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a><span data-ttu-id="07e05-102">高度な電子情報開示ケースへの一括追加保管担当者 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="07e05-102">Bulk-add custodians to an Advanced eDiscovery case (preview)</span></span>

<span data-ttu-id="07e05-103">保管担当者の高度な電子情報開示ケースでは、複数の保管担当者をケースに追加するために必要なすべての情報を含む CSV ファイルによって一度にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="07e05-103">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="07e05-104">一括追加保管担当者</span><span class="sxs-lookup"><span data-stu-id="07e05-104">Bulk-add custodians</span></span>

1. <span data-ttu-id="07e05-105">Case を入力し、[**ソース**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="07e05-105">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="07e05-106">[ **Import 保管担当者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07e05-106">Click **Import custodians**</span></span>

3. <span data-ttu-id="07e05-107">[ポップアップ] ページで、[**空のテンプレートをダウンロード**して CSV 保管担当者テンプレートファイルをダウンロード] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07e05-107">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="07e05-108">この CSV ファイルに custodial 情報を追加して、ローカルコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="07e05-108">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="07e05-109">CSV ファイルのプロパティに関する情報については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e05-109">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="07e05-110">[**ソース**] タブで、[ **Import 保管担当者**] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="07e05-110">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="07e05-111">[ポップアップ] ページで、[**参照**] をクリックし、CSV ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="07e05-111">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="07e05-112">CSV ファイルをアップロードすると、BulkAddCustodian ジョブが作成され、[**ジョブ**] タブに表示されます。ジョブは保管担当者とそれに対応するデータソースを検証し、ケースの [**ソース**] ページの [**保管担当者**] タブに追加します。</span><span class="sxs-lookup"><span data-stu-id="07e05-112">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="07e05-113">保管担当者 CSV ファイル</span><span class="sxs-lookup"><span data-stu-id="07e05-113">Custodian CSV file</span></span>

<span data-ttu-id="07e05-114">CSV テンプレートをダウンロードした後、保管担当者とそのデータソースを各行に追加できます。</span><span class="sxs-lookup"><span data-stu-id="07e05-114">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="07e05-115">見出し行の列名を変更しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="07e05-115">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="07e05-116">列名</span><span class="sxs-lookup"><span data-stu-id="07e05-116">Column name</span></span>|<span data-ttu-id="07e05-117">説明</span><span class="sxs-lookup"><span data-stu-id="07e05-117">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="07e05-118">**保管担当者いる**</span><span class="sxs-lookup"><span data-stu-id="07e05-118">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="07e05-119">保管担当者の UPN 電子メール。</span><span class="sxs-lookup"><span data-stu-id="07e05-119">UPN email of custodian.</span></span> <span data-ttu-id="07e05-120">例: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07e05-120">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="07e05-121">**Exchange が有効**</span><span class="sxs-lookup"><span data-stu-id="07e05-121">**Exchange Enabled**</span></span> | <span data-ttu-id="07e05-122">保管担当者のメールボックスを追加するかどうかを示す TRUE/FALSE 値。</span><span class="sxs-lookup"><span data-stu-id="07e05-122">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="07e05-123">**OneDrive の有効化**</span><span class="sxs-lookup"><span data-stu-id="07e05-123">**OneDrive Enabled**</span></span> | <span data-ttu-id="07e05-124">保管担当者の OneDrive for Business アカウントを追加するかどうかを示す TRUE/FALSE 値。</span><span class="sxs-lookup"><span data-stu-id="07e05-124">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="07e05-125">**OnHold**</span><span class="sxs-lookup"><span data-stu-id="07e05-125">**Is OnHold**</span></span>        | <span data-ttu-id="07e05-126">TRUE/FALSE 保管担当者を保留にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="07e05-126">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="07e05-127">**Workload1 の種類**</span><span class="sxs-lookup"><span data-stu-id="07e05-127">**Workload1 Type**</span></span>         | <span data-ttu-id="07e05-128">保管担当者に関連付けるデータソースの種類を示す文字列値。</span><span class="sxs-lookup"><span data-stu-id="07e05-128">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="07e05-129">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="07e05-129">Possible values include:</span></span> <br /><span data-ttu-id="07e05-130">ExchangeMailbox、SharePointSite、TeamsMailbox、Teamsmailbox、YammerMailbox、YammerSite</span><span class="sxs-lookup"><span data-stu-id="07e05-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="07e05-131">**Workload1 の場所**</span><span class="sxs-lookup"><span data-stu-id="07e05-131">**Workload1 Location**</span></span>     | <span data-ttu-id="07e05-132">ワークロードの種類に応じて、ワークロードのデータの場所 (Exchange メールボックスの電子メールアドレスや SharePoint サイトの URL など) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="07e05-132">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="07e05-133">保管担当者情報を含む CSV ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="07e05-133">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="07e05-134">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="07e05-134">ContactEmail</span></span>      | <span data-ttu-id="07e05-135">Exchange が有効</span><span class="sxs-lookup"><span data-stu-id="07e05-135">Exchange Enabled</span></span> | <span data-ttu-id="07e05-136">OneDrive の有効化</span><span class="sxs-lookup"><span data-stu-id="07e05-136">OneDrive Enabled</span></span> | <span data-ttu-id="07e05-137">OnHold</span><span class="sxs-lookup"><span data-stu-id="07e05-137">Is OnHold</span></span> | <span data-ttu-id="07e05-138">Workload1 の種類</span><span class="sxs-lookup"><span data-stu-id="07e05-138">Workload1 Type</span></span> | <span data-ttu-id="07e05-139">Workload1 の場所</span><span class="sxs-lookup"><span data-stu-id="07e05-139">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="07e05-140">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07e05-140">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="07e05-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="07e05-141">TRUE</span></span>             | <span data-ttu-id="07e05-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="07e05-142">TRUE</span></span>             | <span data-ttu-id="07e05-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="07e05-143">TRUE</span></span>      | <span data-ttu-id="07e05-144">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="07e05-144">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="07e05-145">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07e05-145">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="07e05-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="07e05-146">TRUE</span></span>             | <span data-ttu-id="07e05-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="07e05-147">TRUE</span></span>             | <span data-ttu-id="07e05-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="07e05-148">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="07e05-149">保管担当者とデータソースの検証</span><span class="sxs-lookup"><span data-stu-id="07e05-149">Custodian and data source validation</span></span>

<span data-ttu-id="07e05-150">保管担当者 CSV ファイルをアップロードすると、Advanced eDiscovery は次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="07e05-150">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="07e05-151">保管担当者とそのデータソースを検証します。</span><span class="sxs-lookup"><span data-stu-id="07e05-151">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="07e05-152">各保管担当者のすべてのデータソースのインデックスを付けて、保留中に配置します (Is OnHold プロパティが TRUE に設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="07e05-152">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="07e05-153">保管担当者の検証</span><span class="sxs-lookup"><span data-stu-id="07e05-153">Custodian validation</span></span>

<span data-ttu-id="07e05-154">現時点では、Azure Active Directory (AAD) 内の保管担当者のインポートのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="07e05-154">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="07e05-155">CSV ファイルの [**連絡先の電子メール**] 列にある UPN 値を使用して、保管担当者を検証し、検索します。</span><span class="sxs-lookup"><span data-stu-id="07e05-155">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="07e05-156">検証された保管担当者は、ケースに自動的に追加され、ケースの**ソース**ページの [**保管担当者**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="07e05-156">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="07e05-157">保管担当者を検証できない場合は、[**ジョブ**] タブに表示されている BulkAddCustodian ジョブのエラーログに、その場合はエラーログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="07e05-157">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="07e05-158">Unvalidated 保管担当者はケースに追加されません。</span><span class="sxs-lookup"><span data-stu-id="07e05-158">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="07e05-159">データソースの検証</span><span class="sxs-lookup"><span data-stu-id="07e05-159">Data source validation</span></span>

<span data-ttu-id="07e05-160">保管担当者が検証され、ケースに追加されると、保管担当者に関連付けられている各データソースが検証されます。</span><span class="sxs-lookup"><span data-stu-id="07e05-160">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="07e05-161">保管担当者のデータソースが見つからない場合、**検証されていない**値は、その保管担当者の [**保管担当者**] タブの [**検証済み**] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="07e05-161">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="07e05-162">修復 unvalidated データソース</span><span class="sxs-lookup"><span data-stu-id="07e05-162">Remediating unvalidated data sources</span></span>

<span data-ttu-id="07e05-163">Unvalidated データソースで保管担当者を修復するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="07e05-163">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="07e05-164">[**保管担当者**] タブで、検証されていない保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="07e05-164">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="07e05-165">保管担当者のポップアップページで、[**データソース**] セクションまでスクロールして、保管担当者に関連付けられているデータソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="07e05-165">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="07e05-166">検証済みデータソースと unvalidated データソースの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="07e05-166">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="07e05-167">[**データソース**] セクションで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07e05-167">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="07e05-168">[ **Custodial 所在地の選択**] ページで、unvalidated データソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="07e05-168">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="07e05-169">[**その他の場所の選択**] ページで、[**更新**] をクリックして、保管担当者の追加のデータソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="07e05-169">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
