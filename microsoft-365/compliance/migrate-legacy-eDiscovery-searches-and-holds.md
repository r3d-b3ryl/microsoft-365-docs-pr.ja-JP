---
title: 従来の電子情報開示検索と保持を Microsoft 365 コンプライアンスセンターに移行する
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: eacbb5577c070ce463ad8e17ba6d0d19a1d8736c
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971375"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="efaac-102">従来の電子情報開示検索と保持を Microsoft 365 コンプライアンスセンターに移行する</span><span class="sxs-lookup"><span data-stu-id="efaac-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="efaac-103">Microsoft 365 コンプライアンスセンターでは、次のような電子情報開示の使用に関するエクスペリエンスが向上しています。これには、状況に応じてコンテンツを整理するケースを含む、電子情報開示ワークフローに特化された高度な機能、コンテンツと分析をレビューして、重複のグループ化、電子メールスレッド処理、テーマの分析、予測コーディングなどのレビューのためのデータのカリングに役立てます。</span><span class="sxs-lookup"><span data-stu-id="efaac-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="efaac-104">お客様が新機能と強化された機能を活用できるように、この記事では、インプレース電子情報開示の検索と保持を Exchange 管理センターから Microsoft 365 コンプライアンスセンターに移行する方法についての基本的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="efaac-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="efaac-105">さまざまなシナリオがあるため、この記事では、Microsoft 365 コンプライアンスセンターのコア電子情報開示ケースに移行するための一般的なガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="efaac-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="efaac-106">電子情報開示ケースの使用は常に必須ではありませんが、組織内の電子情報開示ケースにアクセスできるユーザーを制御するためのアクセス許可を割り当てることによって、セキュリティの追加の層が追加されます。</span><span class="sxs-lookup"><span data-stu-id="efaac-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="efaac-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="efaac-107">Before you begin</span></span>

- <span data-ttu-id="efaac-108">この記事で説明されている PowerShell コマンドを実行するには、Office 365 セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="efaac-108">You have to be a member of the eDiscovery Manager role group in the Office 365 Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="efaac-109">また、Exchange 管理センターの "Discovery Management/検出の管理" 役割グループのメンバーである必要もあります。</span><span class="sxs-lookup"><span data-stu-id="efaac-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="efaac-110">この記事では、電子情報開示の保持を作成する方法についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="efaac-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="efaac-111">保留ポリシーは、非同期プロセスによってメールボックスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="efaac-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="efaac-112">電子情報開示の保持を作成する場合は、CaseHoldPolicy と New-caseholdrule の両方を作成する必要があります。そうしないと、ホールドは作成されず、コンテンツの場所は保持されません。</span><span class="sxs-lookup"><span data-stu-id="efaac-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-office-365-security--compliance-center-powershell"></a><span data-ttu-id="efaac-113">手順 1: Exchange Online PowerShell および Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="efaac-113">Step 1: Connect to Exchange Online PowerShell and Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="efaac-114">最初の手順として、Exchange Online PowerShell および Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="efaac-114">The first step is to connect to Exchange Online PowerShell and Office 365 Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="efaac-115">次のスクリプトをコピーして、PowerShell ウィンドウに貼り付け、それを実行できます。</span><span class="sxs-lookup"><span data-stu-id="efaac-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="efaac-116">接続する組織の資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="efaac-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session -AllowClobber -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="efaac-117">この PowerShell セッションでは、次の手順でコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efaac-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="efaac-118">手順 2: Get-mailboxsearch を使用してインプレース電子情報開示検索のリストを取得する</span><span class="sxs-lookup"><span data-stu-id="efaac-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="efaac-119">認証が済んだ**ら、get-mailboxsearch**コマンドレットを実行することによって、インプレース電子情報開示検索のリストを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="efaac-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="efaac-120">次のコマンドをコピーして PowerShell に貼り付けて、そのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="efaac-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="efaac-121">検索の一覧には、その名前とインプレースホールドの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efaac-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="efaac-122">コマンドレットの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="efaac-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell の例 Get-mailboxsearch](media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="efaac-124">手順 3: 移行するインプレース電子情報開示検索とインプレース保持についての情報を取得する</span><span class="sxs-lookup"><span data-stu-id="efaac-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="efaac-125">この場合も、 **get-mailboxsearch**コマンドレットを使用しますが、今回は検索のプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="efaac-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="efaac-126">後で使用するために、これらのプロパティを変数に格納できます。</span><span class="sxs-lookup"><span data-stu-id="efaac-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="efaac-127">次の例では、 **get-mailboxsearch**コマンドレットの結果を変数に格納し、その検索のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="efaac-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="efaac-128">これら2つのコマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="efaac-128">The output of these two commands will be similar to the following:</span></span>

![個別の検索に Get-mailboxsearch を使用した場合の PowerShell 出力の例](media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="efaac-130">この例では、インプレース保持の期間は不定 (*ItemHoldPeriod: 無制限*) です。</span><span class="sxs-lookup"><span data-stu-id="efaac-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="efaac-131">これは一般的に、電子情報開示と法的調査のシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="efaac-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="efaac-132">保持期間が不定の値と異なる場合は、保持のシナリオでコンテンツを保持するために保持が使用されているため、理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="efaac-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="efaac-133">保持シナリオのために Office 365 Security & コンプライアンスセンターの PowerShell で電子情報開示のコマンドレットを使用する代わりに、 [remove-holdcompliancepolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-holdcompliancepolicy)および[remove-holdcompliancerule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-holdcompliancerule)を使用してコンテンツを保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efaac-133">Instead of using the eDiscovery cmdlets in Office 365 Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-HoldCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-holdcompliancepolicy) and [New-HoldComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-holdcompliancerule) to retain content.</span></span> <span data-ttu-id="efaac-134">これらのコマンドレットを使用した結果は、 **CaseHoldPolicy**および**new-caseholdrule**の使用に似ていますが、保持期間と保持の操作 (保持期間が経過した後にコンテンツを削除するなど) を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="efaac-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="efaac-135">また、保持コマンドレットを使用しても、保存機能を電子情報開示ケースに関連付けする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="efaac-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="efaac-136">手順 4: Microsoft 365 コンプライアンスセンターでケースを作成する</span><span class="sxs-lookup"><span data-stu-id="efaac-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="efaac-137">電子情報開示の保持を作成するには、保留リストをと関連付ける電子情報開示ケースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efaac-137">In order to create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="efaac-138">次の例では、選択した名前を使用して電子情報開示ケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="efaac-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="efaac-139">新しい case のプロパティは、後で使用するために変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="efaac-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="efaac-140">これらのプロパティは、ケースを作成`$case | FL`した後にコマンドを実行すると表示できます。</span><span class="sxs-lookup"><span data-stu-id="efaac-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```

![Get-compliancecase コマンドの実行例](media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="efaac-142">手順 5: 電子情報開示の保持を作成する</span><span class="sxs-lookup"><span data-stu-id="efaac-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="efaac-143">ケースを作成したら、ホールドを作成し、前の手順で作成したケースに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="efaac-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="efaac-144">ケース保持ポリシーとケース保持ルールの両方を作成する必要があることを覚えておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="efaac-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="efaac-145">ケース保持ポリシーを作成した後にケース保持ルールが作成されなかった場合、電子情報開示ホールドは作成されず、コンテンツは保持されません。</span><span class="sxs-lookup"><span data-stu-id="efaac-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="efaac-146">移行する電子情報開示保持を再作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="efaac-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="efaac-147">これらの例では、移行する手順3のインプレースホールドからのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="efaac-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
$rule = New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![NewCaseHoldPolicy および NewCaseHoldRule コマンドレットの使用例](media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="efaac-149">手順 6: 電子情報開示の保留を確認する</span><span class="sxs-lookup"><span data-stu-id="efaac-149">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="efaac-150">保持の作成に問題がないことを確認するには、保持配布の状態が [成功] であることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efaac-150">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="efaac-151">Distribution とは、前の手順の*Exchangelocation*パラメーターで指定されたすべてのコンテンツの場所に保留が適用されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="efaac-151">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="efaac-152">これを行うには、 **CaseHoldPolicy**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="efaac-152">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="efaac-153">前の手順で作成した *$policy*変数に保存されたプロパティは変数で自動的に更新されないため、コマンドレットを再実行して、配布が成功したことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efaac-153">Because the properties saved to the *$policy* variable that you created in the previous step are not automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="efaac-154">ケース保持ポリシーを正常に分散させるには、5 ~ 24 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="efaac-154">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="efaac-155">次のコマンドを実行して、電子情報開示の保持が正常に配布されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="efaac-155">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="efaac-156">[失敗の*状態*を正常に**完了**しました "プロパティの値は、コンテンツの場所に保持が正常に配置されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="efaac-156">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="efaac-157">配布がまだ完了していない場合は、[**保留中**] の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efaac-157">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell CaseHoldPolicy の例](media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="efaac-159">手順 7: 検索を作成する</span><span class="sxs-lookup"><span data-stu-id="efaac-159">Step 7: Create the search</span></span>

<span data-ttu-id="efaac-160">最後の手順では、手順3で識別した検索を再作成し、ケースに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="efaac-160">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="efaac-161">検索を作成した後は、 **new-compliancesearch**コマンドレットを使用して実行するか、後で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="efaac-161">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-compliancesearch の例](media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="efaac-163">手順 8: Microsoft 365 コンプライアンスセンターでケース、ホールド、検索を確認する</span><span class="sxs-lookup"><span data-stu-id="efaac-163">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="efaac-164">すべてが正しく設定されていることを確認するには、Microsoft 365 コンプライアンス[https://compliance.microsoft.com](https://compliance.microsoft.com)センターに移動し、[**電子情報開示 > コア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efaac-164">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 コンプライアンスセンターの電子情報開示](media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="efaac-166">手順3で作成したケースは、**コアの電子情報開示**ページに記載されています。</span><span class="sxs-lookup"><span data-stu-id="efaac-166">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="efaac-167">ケースを開き、[**保留**] タブの一覧にある手順4で作成したホールドを確認します。ホールドをクリックすると、保留リストが適用されているメールボックスの数や配布の状態など、詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efaac-167">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![Microsoft 365 コンプライアンスセンターでの電子情報開示の保持](media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="efaac-169">手順7で作成した検索は、電子情報開示ケースの [**検索**] タブの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="efaac-169">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![Microsoft 365 コンプライアンスセンターでの電子情報開示ケースの検索](media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="efaac-171">インプレース電子情報開示検索を移行しても、電子情報開示ケースに関連付けられていない場合は、Microsoft 365 コンプライアンスセンターの [コンテンツ検索] ページにリストされます。</span><span class="sxs-lookup"><span data-stu-id="efaac-171">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="efaac-172">詳細情報</span><span class="sxs-lookup"><span data-stu-id="efaac-172">More information</span></span>

- <span data-ttu-id="efaac-173">Exchange 管理センターでのインプレース電子情報開示 & 保持の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efaac-173">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="efaac-174">インプレース電子情報開示 (eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="efaac-174">In-Place eDiscovery</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="efaac-175">インプレース保持と訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="efaac-175">In-Place Hold and Litigation Hold</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="efaac-176">この記事で使用されている PowerShell コマンドレットの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efaac-176">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="efaac-177">Get-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="efaac-177">Get-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)
  
  - [<span data-ttu-id="efaac-178">Get-compliancecase</span><span class="sxs-lookup"><span data-stu-id="efaac-178">New-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-compliancecase)

  - [<span data-ttu-id="efaac-179">CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="efaac-179">New-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdpolicy)
  
  - [<span data-ttu-id="efaac-180">New-caseholdrule</span><span class="sxs-lookup"><span data-stu-id="efaac-180">New-CaseHoldRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdrule)

  - [<span data-ttu-id="efaac-181">CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="efaac-181">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)
  
  - [<span data-ttu-id="efaac-182">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="efaac-182">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

  - [<span data-ttu-id="efaac-183">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="efaac-183">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

- <span data-ttu-id="efaac-184">Microsoft 365 コンプライアンスセンターの詳細については、「 [microsoft 365 コンプライアンスセンターの概要](microsoft-365-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efaac-184">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>
