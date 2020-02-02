---
title: 高度な電子情報開示レポート
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
ms.assetid: ''
description: ''
ms.openlocfilehash: 736117f62877bd0b33ae1007f00d5a32680963fb
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662251"
---
# <a name="advanced-ediscovery-reports-preview"></a><span data-ttu-id="e591c-102">高度な電子情報開示レポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e591c-102">Advanced eDiscovery reports (preview)</span></span>

<span data-ttu-id="e591c-103">高度な電子情報開示レポートを使用すると、組織全体の大文字と小文字のデータを集計し、データの分析と組織のレポート作成を簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="e591c-103">Advanced eDiscovery reports help you aggregate case data across your organization to streamline data analysis and organizational reporting.</span></span> <span data-ttu-id="e591c-104">高度な電子情報開示レポート機能には、次のような質問に答えるために役立ついくつかの組み込みレポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e591c-104">The Advanced eDiscovery reports feature includes several built-in reports to help you answer questions like:</span></span>

- <span data-ttu-id="e591c-105">組織内のすべてのケースについて、アクティブな保管担当者の数はいくつですか。</span><span class="sxs-lookup"><span data-stu-id="e591c-105">How many active custodians are there for all cases in my organization?</span></span>

- <span data-ttu-id="e591c-106">組織内のすべてのケースで保持されているデータソースの数</span><span class="sxs-lookup"><span data-stu-id="e591c-106">How many data sources are on hold for all cases in my organization?</span></span>

- <span data-ttu-id="e591c-107">組織内のすべてのケースについて、先月に発行された保留通知の数はいくつですか?</span><span class="sxs-lookup"><span data-stu-id="e591c-107">How many hold notifications have been issued in the last month for all cases in my organization?</span></span>

- <span data-ttu-id="e591c-108">組織内にアクティブなケースとクローズしたケースはいくつありますか?</span><span class="sxs-lookup"><span data-stu-id="e591c-108">How many active and closed cases are there in my organization?</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e591c-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="e591c-109">Before you begin</span></span>

- <span data-ttu-id="e591c-110">高度な電子情報開示レポートにアクセスするには、電子情報開示管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e591c-110">To access Advanced eDiscovery reports, you must be a member of the eDiscovery Admin role group.</span></span> <span data-ttu-id="e591c-111">この役割グループのメンバーである場合は、レポート内のデータを表示、フィルター処理、およびエクスポートするために必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e591c-111">Being a member of this role group provides you with the necessary permissions to view, filter, and export the data in the reports.</span></span> <span data-ttu-id="e591c-112">詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e591c-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="e591c-113">高度な電子情報開示レポートは毎日更新されます。</span><span class="sxs-lookup"><span data-stu-id="e591c-113">Advanced eDiscovery reports are refreshed daily.</span></span> <span data-ttu-id="e591c-114">そのため、新しいケース、保管担当者、データソース、および通信が作成され、対応するレポートに表示されるときに、遅延が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="e591c-114">As a result, there may be a delay when new cases, custodians, data sources, and communications are created and when they appear in the corresponding report.</span></span>

<span data-ttu-id="e591c-115">Advanced eDiscovery レポートにアクセスするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e591c-115">To access the Advanced eDiscovery reports:</span></span>

1. <span data-ttu-id="e591c-116">https://protection.office.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="e591c-116">Go to https://protection.office.com</span></span>
  
2. <span data-ttu-id="e591c-117">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e591c-117">Sign into Office 365 using your work or school account.</span></span>
  
3. <span data-ttu-id="e591c-118">[セキュリティ & コンプライアンスセンター] で、[**電子情報開示 > Advanced ediscovery**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e591c-118">In the Security & Compliance Center, click **eDiscovery > Advanced eDiscovery**.</span></span>
  
   <span data-ttu-id="e591c-119">**[Advanced eDiscovery**ホーム] ページでは、ケース、保管担当者、[データソース]、[コミュニケーションレポート] タブがページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e591c-119">On the **Advanced eDiscovery** home page, the Case, Custodian, Data Source, and Communications report tabs are displayed across the top of the page.</span></span> 
  
   ![ホームページの高度な電子情報開示レポート](media/report-home.png)

5. <span data-ttu-id="e591c-121">レポートを表示するには、レポートタブをクリックし、必要に応じて次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e591c-121">To view a report, click a report tab, and then if necessary you can do one of the following things:</span></span>

   ![レポートデータをフィルター処理またはダウンロードすることができます。](media/AeDReportsFilterDownload.png)

   <span data-ttu-id="e591c-123">a. </span><span class="sxs-lookup"><span data-stu-id="e591c-123">a.</span></span> <span data-ttu-id="e591c-124">レポートデータを絞り込むには、[**フィルター** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e591c-124">Click **Filter** to narrow the report data.</span></span> <span data-ttu-id="e591c-125">各レポートのさまざまなプロパティにフィルターを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e591c-125">You can filter on different properties for each report.</span></span>
  
   <span data-ttu-id="e591c-126">b. </span><span class="sxs-lookup"><span data-stu-id="e591c-126">b.</span></span> <span data-ttu-id="e591c-127">[ **Csv へのダウンロード**] をクリックして、レポートデータを csv ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e591c-127">Click **Download to CSV** to export the report data to a CSV file.</span></span>

## <a name="case-report"></a><span data-ttu-id="e591c-128">ケースレポート</span><span class="sxs-lookup"><span data-stu-id="e591c-128">Case report</span></span>

<span data-ttu-id="e591c-129">ケースレポートは、組織内のアクティブおよびクローズされた先行電子情報開示ケースに関する情報を集約します。</span><span class="sxs-lookup"><span data-stu-id="e591c-129">The Case report aggregates information about active and closed Advance eDiscovery cases in your organization.</span></span>

|<span data-ttu-id="e591c-130">列</span><span class="sxs-lookup"><span data-stu-id="e591c-130">Column</span></span>        |<span data-ttu-id="e591c-131">説明</span><span class="sxs-lookup"><span data-stu-id="e591c-131">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="e591c-132">ケース ID</span><span class="sxs-lookup"><span data-stu-id="e591c-132">Case ID</span></span> | <span data-ttu-id="e591c-133">各ケースの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e591c-133">The unique identifier for each case.</span></span>| 
|<span data-ttu-id="e591c-134">ケース名</span><span class="sxs-lookup"><span data-stu-id="e591c-134">Case name</span></span> | <span data-ttu-id="e591c-135">ケースのユーザー定義の名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-135">User-defined name of the case.</span></span>|
|<span data-ttu-id="e591c-136">状態</span><span class="sxs-lookup"><span data-stu-id="e591c-136">Status</span></span> | <span data-ttu-id="e591c-137">ケースがアクティブかクローズかを示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-137">Indicates if the case is active or closed.</span></span>|
|<span data-ttu-id="e591c-138">作成日</span><span class="sxs-lookup"><span data-stu-id="e591c-138">Date created</span></span> |<span data-ttu-id="e591c-139">ケースが作成された日付。</span><span class="sxs-lookup"><span data-stu-id="e591c-139">Th date when the case was created.</span></span> <span data-ttu-id="e591c-140">日付は UTC 形式です。</span><span class="sxs-lookup"><span data-stu-id="e591c-140">Dates are in UTC format.</span></span>|
|<span data-ttu-id="e591c-141">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="e591c-141">Last modified</span></span> |<span data-ttu-id="e591c-142">ケースがクローズまたは最後に更新された日付。</span><span class="sxs-lookup"><span data-stu-id="e591c-142">The date when the case was closed or last updated.</span></span> <span data-ttu-id="e591c-143">日付は UTC 形式です。</span><span class="sxs-lookup"><span data-stu-id="e591c-143">Dates are in UTC format.</span></span>| 
|||

## <a name="custodian-report"></a><span data-ttu-id="e591c-144">保管担当者レポート</span><span class="sxs-lookup"><span data-stu-id="e591c-144">Custodian report</span></span>

<span data-ttu-id="e591c-145">電子情報開示ワークフローでは、法的訴訟や調査の対象となっている個人は*data 保管担当者*(または*保管担当者*) と呼ばれ、"ドキュメントまたは電子ファイルの管理制御を持つ人" として定義されています。</span><span class="sxs-lookup"><span data-stu-id="e591c-145">In the eDiscovery workflow, individuals who are the subject of a legal case or investigation are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="e591c-146">保管担当者レポートは、組織内のすべてのケースについて、データソースが保留になっているすべての保管担当者を識別するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e591c-146">The Custodian report helps you identify all the custodians whose data sources are placed on hold for all cases in your organization.</span></span>

|<span data-ttu-id="e591c-147">列</span><span class="sxs-lookup"><span data-stu-id="e591c-147">Column</span></span>         |<span data-ttu-id="e591c-148">説明</span><span class="sxs-lookup"><span data-stu-id="e591c-148">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="e591c-149">保管担当者名</span><span class="sxs-lookup"><span data-stu-id="e591c-149">Custodian name</span></span>| <span data-ttu-id="e591c-150">Active Directory 内の保管担当者の名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-150">The name of the custodian in Active Directory.</span></span>|
|<span data-ttu-id="e591c-151">保管担当者 UPN</span><span class="sxs-lookup"><span data-stu-id="e591c-151">Custodian UPN</span></span> | <span data-ttu-id="e591c-152">保管担当者のユーザープリンシパル名。</span><span class="sxs-lookup"><span data-stu-id="e591c-152">The user principal name of the custodian.</span></span>|
|<span data-ttu-id="e591c-153">保管担当者 ID</span><span class="sxs-lookup"><span data-stu-id="e591c-153">Custodian ID</span></span> | <span data-ttu-id="e591c-154">特定のケースにおける保管担当者の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="e591c-154">The unique identifier for the custodian within a given case.</span></span> |
|<span data-ttu-id="e591c-155">ケース名</span><span class="sxs-lookup"><span data-stu-id="e591c-155">Case name</span></span> | <span data-ttu-id="e591c-156">ケースのユーザー定義の名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-156">The user-defined name of the case.</span></span>|
|<span data-ttu-id="e591c-157">保留状態</span><span class="sxs-lookup"><span data-stu-id="e591c-157">Hold status</span></span> | <span data-ttu-id="e591c-158">保管担当者が現在保留中であるか、ケースからリリースされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-158">Indicates if the custodian is currently on hold or if they have been released from the case.</span></span>|
|<span data-ttu-id="e591c-159">ケース Id</span><span class="sxs-lookup"><span data-stu-id="e591c-159">Case Id</span></span> | <span data-ttu-id="e591c-160">ケースの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="e591c-160">The unique identifier for the case.</span></span>|
|<span data-ttu-id="e591c-161">通信の状態</span><span class="sxs-lookup"><span data-stu-id="e591c-161">Communication status</span></span> |<span data-ttu-id="e591c-162">保管担当者に法的情報保留通知が発行されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-162">Indicates if the custodian was issued a legal hold notification or not.</span></span> |
|<span data-ttu-id="e591c-163">保管担当者が追加されました</span><span class="sxs-lookup"><span data-stu-id="e591c-163">Custodian added</span></span> | <span data-ttu-id="e591c-164">保管担当者がケースに追加された日付。</span><span class="sxs-lookup"><span data-stu-id="e591c-164">The date the custodian was added to the case.</span></span> <span data-ttu-id="e591c-165">日付は UTC 形式です。</span><span class="sxs-lookup"><span data-stu-id="e591c-165">Dates are in UTC format.</span></span>|
|||

## <a name="data-source-report"></a><span data-ttu-id="e591c-166">データソースレポート</span><span class="sxs-lookup"><span data-stu-id="e591c-166">Data source report</span></span>

<span data-ttu-id="e591c-167">高度な電子情報開示ケースを使用して、ケースに関連する可能性があるコンテンツを保持するための保留を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e591c-167">You can use an Advanced eDiscovery case to create holds to preserve content that may be relevant to the case.</span></span> <span data-ttu-id="e591c-168">高度な電子情報開示の保持機能を使用すると、保管担当者とそのデータソースに保持を配置できます。</span><span class="sxs-lookup"><span data-stu-id="e591c-168">Using the Advanced eDiscovery hold capabilities, you can place holds on custodians and their data sources.</span></span> <span data-ttu-id="e591c-169">さらに、メールボックスおよび OneDrive for Business アカウントに、非 wi-fi ダイヤルを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="e591c-169">Additionally, you can place a non-custodial hold on mailboxes and OneDrive for Business accounts.</span></span> <span data-ttu-id="e591c-170">データソースレポートを使用して、組織内のすべてのケースについて、保留中のコンテンツの場所に関する詳細を集約できます。</span><span class="sxs-lookup"><span data-stu-id="e591c-170">You can use the data sources report to aggregate details about content locations on hold for all cases in your organization.</span></span>

|<span data-ttu-id="e591c-171">列</span><span class="sxs-lookup"><span data-stu-id="e591c-171">Column</span></span>        |<span data-ttu-id="e591c-172">説明</span><span class="sxs-lookup"><span data-stu-id="e591c-172">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="e591c-173">ケース ID</span><span class="sxs-lookup"><span data-stu-id="e591c-173">Case ID</span></span> |<span data-ttu-id="e591c-174">各ケースの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e591c-174">The unique identifier for each case.</span></span> |
|<span data-ttu-id="e591c-175">Workload</span><span class="sxs-lookup"><span data-stu-id="e591c-175">Workload</span></span> |<span data-ttu-id="e591c-176">保持するコンテンツの場所の種類 (Exchange、SharePoint など) を示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-176">Indicates the type of content location placed on hold (for example, Exchange or SharePoint).</span></span>
|<span data-ttu-id="e591c-177">場所の名前</span><span class="sxs-lookup"><span data-stu-id="e591c-177">Location name</span></span> |<span data-ttu-id="e591c-178">コンテンツの場所の SMTP アドレス (Exchange メールボックスの場合) または URL (SharePoint サイトの場合) を示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-178">Indicates the SMTP address (for Exchange mailboxes) or the URL (for SharePoint sites) of the content location.</span></span> | 
|<span data-ttu-id="e591c-179">保管担当者 ID</span><span class="sxs-lookup"><span data-stu-id="e591c-179">Custodian ID</span></span> |<span data-ttu-id="e591c-180">データソースが保管担当者に属している場合、この列には、特定のケースにおける保管担当者の一意の識別子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e591c-180">If the data source belongs to a custodian, this column shows the unique identifier for the custodian in a given case.</span></span> <span data-ttu-id="e591c-181">この列は、非 wi-fi ダイヤルの場所の場合は null になります。</span><span class="sxs-lookup"><span data-stu-id="e591c-181">This column will be null for non-custodial locations.</span></span>|
|<span data-ttu-id="e591c-182">保管担当者名</span><span class="sxs-lookup"><span data-stu-id="e591c-182">Custodian name</span></span> |<span data-ttu-id="e591c-183">Active Directory 内の保管担当者の名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-183">The name of the custodian in Active Directory.</span></span>| 
|<span data-ttu-id="e591c-184">ケース名</span><span class="sxs-lookup"><span data-stu-id="e591c-184">Case name</span></span> |<span data-ttu-id="e591c-185">ケースのユーザー定義の名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-185">The user-defined name of the case.</span></span>| 
|<span data-ttu-id="e591c-186">状態</span><span class="sxs-lookup"><span data-stu-id="e591c-186">Status</span></span> |<span data-ttu-id="e591c-187">コンテンツの場所が現在保留中であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-187">Indicates if the content location is currently on hold.</span></span> | 
|<span data-ttu-id="e591c-188">保持ポリシー ID</span><span class="sxs-lookup"><span data-stu-id="e591c-188">Hold policy ID</span></span> |<span data-ttu-id="e591c-189">コンテンツの場所を含む保留リストの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="e591c-189">The unique identifier for the hold that contains the content location.</span></span> | 
|<span data-ttu-id="e591c-190">保持の作成日</span><span class="sxs-lookup"><span data-stu-id="e591c-190">Hold created date</span></span> |<span data-ttu-id="e591c-191">保留ポリシーが作成された日付を示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-191">Indicates the date when the hold policy was created.</span></span> <span data-ttu-id="e591c-192">日付は UTC 形式です。</span><span class="sxs-lookup"><span data-stu-id="e591c-192">Dates are in UTC format.</span></span> | 
|<span data-ttu-id="e591c-193">保持ポリシー名</span><span class="sxs-lookup"><span data-stu-id="e591c-193">Hold policy name</span></span> |<span data-ttu-id="e591c-194">コンテンツの場所を含むホールドの名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-194">The name of the hold that contains the content location.</span></span> |
|<span data-ttu-id="e591c-195">保持の変更日</span><span class="sxs-lookup"><span data-stu-id="e591c-195">Hold modified date</span></span> |<span data-ttu-id="e591c-196">保留が最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="e591c-196">The date when the hold was last modified.</span></span> <span data-ttu-id="e591c-197">日付は UTC 形式です。</span><span class="sxs-lookup"><span data-stu-id="e591c-197">Dates are in UTC format.</span></span>| 
|<span data-ttu-id="e591c-198">保持の最終更新者</span><span class="sxs-lookup"><span data-stu-id="e591c-198">Hold last modified by</span></span>|<span data-ttu-id="e591c-199">保留を最後に変更したユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-199">The name of the user that last modified the hold.</span></span>| 
|||

## <a name="communication-report"></a><span data-ttu-id="e591c-200">コミュニケーションレポート</span><span class="sxs-lookup"><span data-stu-id="e591c-200">Communication report</span></span>

<span data-ttu-id="e591c-201">組織は法的情報保留通知を発行して、法的な訴訟や調査の一環として関連情報を保持する義務を保管担当者に通知することがあります。</span><span class="sxs-lookup"><span data-stu-id="e591c-201">Your organization may issue legal hold notices to notify custodians of their obligation to preserve relevant information as part of legal case or investigation.</span></span> <span data-ttu-id="e591c-202">通信レポートを使用して、謝辞、アラーム、エスカレーション、およびその他の種類の通信の集計データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e591c-202">You can use the communications report to view aggregate data on acknowledgments, reminders, escalations, and other types of communications.</span></span>

|<span data-ttu-id="e591c-203">列</span><span class="sxs-lookup"><span data-stu-id="e591c-203">Column</span></span>         |<span data-ttu-id="e591c-204">説明</span><span class="sxs-lookup"><span data-stu-id="e591c-204">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="e591c-205">ケース ID</span><span class="sxs-lookup"><span data-stu-id="e591c-205">Case ID</span></span> | <span data-ttu-id="e591c-206">ケースの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="e591c-206">The unique identifier for the case.</span></span>|
|<span data-ttu-id="e591c-207">ケース名</span><span class="sxs-lookup"><span data-stu-id="e591c-207">Case name</span></span> | <span data-ttu-id="e591c-208">ケースのユーザー定義の名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-208">User-defined name of the case.</span></span>|
|<span data-ttu-id="e591c-209">保管担当者 ID</span><span class="sxs-lookup"><span data-stu-id="e591c-209">Custodian ID</span></span> |<span data-ttu-id="e591c-210">特定のケースにおける保管担当者の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="e591c-210">The unique identifier for the custodian in a given case.</span></span>|
|<span data-ttu-id="e591c-211">保管担当者名</span><span class="sxs-lookup"><span data-stu-id="e591c-211">Custodian name</span></span> |<span data-ttu-id="e591c-212">保管担当者の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e591c-212">The name of the custodian.</span></span>|
|<span data-ttu-id="e591c-213">通知の種類</span><span class="sxs-lookup"><span data-stu-id="e591c-213">Notice type</span></span> |<span data-ttu-id="e591c-214">保管担当者に対して発行された通知の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-214">Indicates the type of notice that was issued to the custodian.</span></span>|
|<span data-ttu-id="e591c-215">発行責任者</span><span class="sxs-lookup"><span data-stu-id="e591c-215">Issuing officer</span></span> |<span data-ttu-id="e591c-216">法的情報保持通知を発行したユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="e591c-216">The name of the user that issued the legal hold notification.</span></span>|
|<span data-ttu-id="e591c-217">通知イベント</span><span class="sxs-lookup"><span data-stu-id="e591c-217">Notification event</span></span>|<span data-ttu-id="e591c-218">ユーザーに送信される法的情報保留通知メッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-218">Indicates the legal hold notification message sent to the user.</span></span> <span data-ttu-id="e591c-219">指定できる値は、アラーム、エスカレーション、受信確認、保留の発行です。</span><span class="sxs-lookup"><span data-stu-id="e591c-219">Possible values include: Reminder, Escalation, Acknowledgment, and Hold Issuance.</span></span>|
|<span data-ttu-id="e591c-220">送信日</span><span class="sxs-lookup"><span data-stu-id="e591c-220">Date sent</span></span> |<span data-ttu-id="e591c-221">通信が発行された日付。</span><span class="sxs-lookup"><span data-stu-id="e591c-221">The date when the communication was issued.</span></span> <span data-ttu-id="e591c-222">受信確認の場合、この列は、保管担当者によって通知が受信された日時を示します。</span><span class="sxs-lookup"><span data-stu-id="e591c-222">For acknowledgments, this column indicates the time that the notice was acknowledged by the custodian.</span></span> <span data-ttu-id="e591c-223">日付は UTC 形式です。</span><span class="sxs-lookup"><span data-stu-id="e591c-223">Dates are in UTC format.</span></span>|
|||
