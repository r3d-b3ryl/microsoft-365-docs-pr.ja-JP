---
title: 従来の電子情報開示検索と保持を Microsoft 365 コンプライアンス センターに移行する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ef5562aa6f5c7519d19452100b55dd4bc30d4126
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926325"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="ab722-102">従来の電子情報開示検索と保持を Microsoft 365 コンプライアンス センターに移行する</span><span class="sxs-lookup"><span data-stu-id="ab722-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="ab722-103">Microsoft 365 コンプライアンス センターでは、電子情報開示の使用に関するエクスペリエンスが向上しています。信頼性の向上、パフォーマンスの向上、電子情報開示ワークフローに合わせた機能の多くは、重要なコンテンツを整理するケース、コンテンツと分析を確認するためのレビュー セットなど、ほぼ重複グループ化、電子メール スレッド、テーマ分析、予測コーディングなどのデータを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ab722-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="ab722-104">お客様が新機能と強化された機能を利用するために、この記事では、In-Place 電子情報開示の検索と保持を Exchange 管理センターから Microsoft 365 コンプライアンス センターに移行する方法に関する基本的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ab722-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="ab722-105">さまざまなシナリオが考えられますので、この記事では、検索を移行し、Microsoft 365 コンプライアンス センターのコア電子情報開示ケースに移行する一般的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ab722-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ab722-106">電子情報開示ケースの使用は必ずしも必要とは限らないが、組織内の電子情報開示ケースにアクセスできるユーザーを制御するためのアクセス許可を割り当て、セキュリティの層を追加します。</span><span class="sxs-lookup"><span data-stu-id="ab722-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ab722-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="ab722-107">Before you begin</span></span>

- <span data-ttu-id="ab722-108">この記事で説明する PowerShell コマンドを実行するには、セキュリティ & コンプライアンス センターの電子情報開示マネージャー役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab722-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="ab722-109">また、Exchange 管理センターの探索管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab722-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="ab722-110">この記事では、電子情報開示ホールドを作成する方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ab722-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="ab722-111">保持ポリシーは、非同期プロセスを通じてメールボックスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ab722-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="ab722-112">電子情報開示ホールドを作成する場合は、CaseHoldPolicy と CaseHoldRule の両方を作成する必要があります。それ以外の場合、保留は作成されません。コンテンツの場所は保留にされません。</span><span class="sxs-lookup"><span data-stu-id="ab722-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="ab722-113">手順 1: Exchange Online PowerShell とセキュリティ & コンプライアンス センター PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="ab722-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="ab722-114">最初の手順は、コンプライアンス センター PowerShell に Exchange Online PowerShell とセキュリティ &接続します。</span><span class="sxs-lookup"><span data-stu-id="ab722-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="ab722-115">次のスクリプトをコピーし、PowerShell ウィンドウに貼り付け、実行できます。</span><span class="sxs-lookup"><span data-stu-id="ab722-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="ab722-116">接続する組織の資格情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab722-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="ab722-117">この PowerShell セッションでは、次の手順でコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab722-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="ab722-118">手順 2: 電子情報開示検索の一In-Placeを使用して取得Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ab722-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="ab722-119">認証後 **、Get-MailboxSearch** コマンドレットを実行In-Place電子情報開示検索の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ab722-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="ab722-120">次のコマンドをコピーして PowerShell に貼り付け、実行します。</span><span class="sxs-lookup"><span data-stu-id="ab722-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="ab722-121">検索の一覧には、その名前と保留リストの状態In-Placeされます。</span><span class="sxs-lookup"><span data-stu-id="ab722-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="ab722-122">コマンドレットの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ab722-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell の例Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="ab722-124">手順 3: 移行する電子情報開示In-Placeと保持In-Place情報を取得する</span><span class="sxs-lookup"><span data-stu-id="ab722-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="ab722-125">ここでも **Get-MailboxSearch** コマンドレットを使用しますが、今回は検索のプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab722-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="ab722-126">これらのプロパティは、後で使用するために変数に格納できます。</span><span class="sxs-lookup"><span data-stu-id="ab722-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="ab722-127">次の使用例は **、Get-MailboxSearch** コマンドレットの結果を変数に格納し、検索のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="ab722-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="ab722-128">これら 2 つのコマンドの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ab722-128">The output of these two commands will be similar to the following:</span></span>

![個々の検索に使用する PowerShell Get-MailboxSearch出力の例](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="ab722-130">この例の保留In-Place期間は無期限です *(ItemHoldPeriod: Unlimited)。*</span><span class="sxs-lookup"><span data-stu-id="ab722-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="ab722-131">これは、電子情報開示と法的調査のシナリオで一般的です。</span><span class="sxs-lookup"><span data-stu-id="ab722-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="ab722-132">保留期間の値が無期限とは異なる場合、保持が保持シナリオでコンテンツを保持するために使用されている可能性が高い理由です。</span><span class="sxs-lookup"><span data-stu-id="ab722-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="ab722-133">保持シナリオでセキュリティ & コンプライアンス センター PowerShell の電子情報開示コマンドレットを使用する代わりに [、New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) と [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) を使用してコンテンツを保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ab722-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="ab722-134">これらのコマンドレットを使用した結果は **、New-CaseHoldPolicy** と **New-CaseHoldRule** の使用と似ていますが、保持期間の有効期限が切れた後にコンテンツを削除するなどの保持期間と保持アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ab722-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="ab722-135">また、保持コマンドレットを使用しても、保持保持を電子情報開示ケースに関連付ける必要は一切ない。</span><span class="sxs-lookup"><span data-stu-id="ab722-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="ab722-136">手順 4: Microsoft 365 コンプライアンス センターでケースを作成する</span><span class="sxs-lookup"><span data-stu-id="ab722-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="ab722-137">電子情報開示ホールドを作成するには、保留リストを関連付ける電子情報開示ケースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab722-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="ab722-138">次の使用例は、選択した名前を使用して電子情報開示ケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab722-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="ab722-139">後で使用するために、新しいケースのプロパティを変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="ab722-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="ab722-140">これらのプロパティは、ケースの作成後に `$case | FL` コマンドを実行して表示できます。</span><span class="sxs-lookup"><span data-stu-id="ab722-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![コマンドの実行New-ComplianceCase例](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="ab722-142">手順 5: 電子情報開示ホールドを作成する</span><span class="sxs-lookup"><span data-stu-id="ab722-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="ab722-143">ケースを作成したら、保持を作成し、前の手順で作成したケースに関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="ab722-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="ab722-144">ケースホールド ポリシーとケースホールドルールの両方を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab722-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="ab722-145">ケースホールド ポリシーの作成後にケースホールド ルールが作成されない場合、電子情報開示ホールドは作成されません。コンテンツは保留にされません。</span><span class="sxs-lookup"><span data-stu-id="ab722-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="ab722-146">次のコマンドを実行して、移行する電子情報開示ホールドを再作成します。</span><span class="sxs-lookup"><span data-stu-id="ab722-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="ab722-147">これらの例では、移行する手順 3 In-Placeのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab722-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="ab722-148">最初のコマンドは、新しいケース保持ポリシーを作成し、プロパティを変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="ab722-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="ab722-149">2 番目のコマンドは、対応するケース保持ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab722-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![NewCaseHoldPolicy コマンドレットと NewCaseHoldRule コマンドレットの使用例](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="ab722-151">手順 6: 電子情報開示の保持を確認する</span><span class="sxs-lookup"><span data-stu-id="ab722-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="ab722-152">保留リストの作成に問題が発生しなかった場合は、保留配布の状態が正常に終了した状態を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ab722-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="ab722-153">配布とは、前の手順で *ExchangeLocation* パラメーターで指定されたコンテンツの場所すべてに保留が適用されたという意味です。</span><span class="sxs-lookup"><span data-stu-id="ab722-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="ab722-154">これを行うには **、Get-CaseHoldPolicy コマンドレットを実行** できます。</span><span class="sxs-lookup"><span data-stu-id="ab722-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="ab722-155">前の手順で作成した *$policy* 変数に保存されたプロパティは変数内で自動的に更新されないので、配布が成功したと確認するには、コマンドレットを再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab722-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="ab722-156">ケース保持ポリシーが正常に配布されるには、5 分から 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab722-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="ab722-157">次のコマンドを実行して、電子情報開示ホールドが正常に配布されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab722-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="ab722-158">*DistributionStatus* プロパティ **の** Success の値は、保留がコンテンツの場所に正常に配置されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ab722-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="ab722-159">配布がまだ完了していない場合は、値 **Pending が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab722-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell のGet-CaseHoldPolicy例](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="ab722-161">手順 7: 検索を作成する</span><span class="sxs-lookup"><span data-stu-id="ab722-161">Step 7: Create the search</span></span>

<span data-ttu-id="ab722-162">最後の手順は、手順 3 で識別した検索を再作成し、ケースに関連付けることです。</span><span class="sxs-lookup"><span data-stu-id="ab722-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="ab722-163">検索を作成した後 **、Start-ComplianceSearch** コマンドレットを使用して実行するか、後で実行できます。</span><span class="sxs-lookup"><span data-stu-id="ab722-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell のNew-ComplianceSearch例](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="ab722-165">手順 8: Microsoft 365 コンプライアンス センターでケース、ホールド、検索を確認する</span><span class="sxs-lookup"><span data-stu-id="ab722-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="ab722-166">すべてが正しく設定されていることを確認するには、Microsoft 365 コンプライアンス センターの [電子情報開示] をクリックし、[コア] [https://compliance.microsoft.com](https://compliance.microsoft.com) **>します**。</span><span class="sxs-lookup"><span data-stu-id="ab722-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 コンプライアンス センターの電子情報開示](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="ab722-168">手順 3 で作成したケースは、[コア電子情報開示] ページ **に一覧表示** されます。</span><span class="sxs-lookup"><span data-stu-id="ab722-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="ab722-169">ケースを開き、[保持] タブの一覧にある手順 4 で作成した保留リスト **に気付** きます。保留リストをクリックすると、保留リストが適用されているメールボックスの数や配布状態などの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab722-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![電子情報開示が Microsoft 365 コンプライアンス センターに保持される](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="ab722-171">手順 7 で作成した検索は、電子情報開示ケースの [検索] タブに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab722-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![Microsoft 365 コンプライアンス センターでの電子情報開示ケース検索](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="ab722-173">電子情報開示検索を移行In-Place電子情報開示ケースに関連付けなかった場合は、Microsoft 365 コンプライアンス センターの [コンテンツ検索] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab722-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="ab722-174">詳細</span><span class="sxs-lookup"><span data-stu-id="ab722-174">More information</span></span>

- <span data-ttu-id="ab722-175">Exchange 管理センターの電子情報開示In-Place保持&詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab722-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="ab722-176">インプレース電子情報開示 (eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="ab722-176">In-Place eDiscovery</span></span>](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="ab722-177">インプレース保持と訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="ab722-177">In-Place Hold and Litigation Hold</span></span>](/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="ab722-178">この記事で使用される PowerShell コマンドレットの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab722-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="ab722-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ab722-179">Get-MailboxSearch</span></span>](/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="ab722-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="ab722-180">New-ComplianceCase</span></span>](/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="ab722-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="ab722-181">New-CaseHoldPolicy</span></span>](/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="ab722-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="ab722-182">New-CaseHoldRule</span></span>](/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="ab722-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="ab722-183">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="ab722-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ab722-184">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="ab722-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ab722-185">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="ab722-186">Microsoft 365 コンプライアンス センターの詳細については [、「Microsoft 365 コンプライアンス](microsoft-365-compliance-center.md)センターの概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab722-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>