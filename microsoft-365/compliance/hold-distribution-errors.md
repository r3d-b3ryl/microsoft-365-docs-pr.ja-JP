---
title: 電子情報開示の保持エラーのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: コア電子情報開示の保管担当者および非保管データ ソースに適用される法的ホールドに関連するエラーのトラブルシューティングを行います。
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538473"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="feda8-103">電子情報開示の保持エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="feda8-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="feda8-104">この記事では、電子情報開示ホールドで発生する可能性のある一般的な問題と、それらを解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="feda8-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="feda8-105">この記事には、これらの問題を軽減または回避するための推奨プラクティスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="feda8-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="feda8-106">推奨プラクティス</span><span class="sxs-lookup"><span data-stu-id="feda8-106">Recommended practices</span></span>

<span data-ttu-id="feda8-107">電子情報開示ホールドに関連するエラーの数を減らすには、次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="feda8-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="feda8-108">保留配布がまだ保留中の場合は、保留配布が完了するまで待機してから、それ以上の更新 `On (Pending)` `Off (Pending)` を行います。</span><span class="sxs-lookup"><span data-stu-id="feda8-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="feda8-109">保留ポリシーが保留中であるかどうかを確認してから、保留ポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="feda8-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="feda8-110">次のコマンドを実行するか、PowerShell スクリプトに保存します。</span><span class="sxs-lookup"><span data-stu-id="feda8-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="feda8-111">トランザクションごとに保持ポリシーを繰り返し更新するのではなく、1 つの一括要求で更新プログラムを電子情報開示保留にマージします。</span><span class="sxs-lookup"><span data-stu-id="feda8-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="feda8-112">[たとえば、Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy)コマンドレットを使用して既存の保持ポリシーに複数のユーザー メールボックスを追加するには、コマンドを実行 (またはスクリプトにコード ブロックとして追加) して、複数のユーザーを追加するために 1 回だけ実行します。</span><span class="sxs-lookup"><span data-stu-id="feda8-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="feda8-113">**正しい例**</span><span class="sxs-lookup"><span data-stu-id="feda8-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="feda8-114">**正しくない例**</span><span class="sxs-lookup"><span data-stu-id="feda8-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="feda8-115">前の不適切な例では、コマンドレットを 5 回実行してタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="feda8-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="feda8-116">ユーザーを保留ポリシーに追加するための推奨プラクティスの詳細については、「詳細」 [セクションを参照](#more-information) してください。</span><span class="sxs-lookup"><span data-stu-id="feda8-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="feda8-117">電子情報開示ホールドの問題について Microsoft サポートに問い合わせする前に、「エラー [/問題:](#errorissue-holds-dont-sync) 保留リストは同期しない」セクションの手順に従って、保留配布を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="feda8-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="feda8-118">このプロセスでは、多くの場合、内部サーバー エラーなどの一時的な問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="feda8-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="feda8-119">エラー/問題: 保留は同期されません</span><span class="sxs-lookup"><span data-stu-id="feda8-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="feda8-120">保管担当者とデータ ソースを保留にするときに次のエラー メッセージが表示される場合は、解決手順を使用して問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="feda8-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="feda8-121">リソース: ポリシーの展開に予想以上に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="feda8-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="feda8-122">最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。</span><span class="sxs-lookup"><span data-stu-id="feda8-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="feda8-123">データセンターの一時的な問題により、ポリシーをコンテンツ ソースOffice 365できません。</span><span class="sxs-lookup"><span data-stu-id="feda8-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="feda8-124">現在のポリシーはソース内のコンテンツには適用されないので、ブロックされた展開による影響はありません。</span><span class="sxs-lookup"><span data-stu-id="feda8-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="feda8-125">この問題を解決するには、ポリシーを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="feda8-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="feda8-126">申し訳ございませんが、一時的な内部サーバー エラーのため、ポリシーに対して要求された変更を実行できません。</span><span class="sxs-lookup"><span data-stu-id="feda8-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="feda8-127">30 分後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="feda8-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="feda8-128">解決方法</span><span class="sxs-lookup"><span data-stu-id="feda8-128">Resolution</span></span>

1. <span data-ttu-id="feda8-129">Connectコンプライアンス センター [powerShell &に移動](/powershell/exchange/connect-to-scc-powershell)し、電子情報開示ホールドに対して次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="feda8-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="feda8-130">*DistributionDetail パラメーターの値を調* べてください。</span><span class="sxs-lookup"><span data-stu-id="feda8-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="feda8-131">次のようなエラーを探します。</span><span class="sxs-lookup"><span data-stu-id="feda8-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="feda8-132">エラー: リソース: ポリシーの展開に予想以上に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="feda8-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="feda8-133">最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。</span><span class="sxs-lookup"><span data-stu-id="feda8-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="feda8-134">問題の **保留ポリシーで Set-CaseHoldPolicy -RetryDistribution** コマンドを実行してみてください。例えば：</span><span class="sxs-lookup"><span data-stu-id="feda8-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="feda8-135">エラー: SharePointが読み取り専用か、アクセスできない</span><span class="sxs-lookup"><span data-stu-id="feda8-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="feda8-136">保管担当者とデータ ソースを保留にするときに次のエラー メッセージが表示される場合は、組織のグローバル管理者または[SharePoint](/sharepoint/sharepoint-admin-role)管理者がサイトをロックしているという意味です。</span><span class="sxs-lookup"><span data-stu-id="feda8-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="feda8-137">ロックされたサイトは、電子情報開示がサイトに保留を設定するのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="feda8-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="feda8-138">サイトSharePoint読み取り専用またはアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="feda8-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="feda8-139">サイトを書き込み可能にし、このポリシーを再展開するには、サイト管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="feda8-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="feda8-140">解決方法</span><span class="sxs-lookup"><span data-stu-id="feda8-140">Resolution</span></span>

<span data-ttu-id="feda8-141">この問題を解決するには、サイトのロックを解除します (または管理者にロック解除を求める)。</span><span class="sxs-lookup"><span data-stu-id="feda8-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="feda8-142">サイトのロック状態を変更する方法の詳細については、「サイトのロックとロック解除 [」を参照してください](/sharepoint/manage-lock-status)。</span><span class="sxs-lookup"><span data-stu-id="feda8-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="feda8-143">エラー: メールボックスまたはサイトSharePoint存在しない可能性があります</span><span class="sxs-lookup"><span data-stu-id="feda8-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="feda8-144">保管担当者とデータ ソースを保留にするときに次のエラー メッセージが表示される場合は、解決手順を使用して問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="feda8-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="feda8-145">メールボックスまたはサイトSharePoint存在しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="feda8-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="feda8-146">これが正しくない場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="feda8-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="feda8-147">それ以外の場合は、このポリシーから削除してください。</span><span class="sxs-lookup"><span data-stu-id="feda8-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="feda8-148">解決方法</span><span class="sxs-lookup"><span data-stu-id="feda8-148">Resolution</span></span>

- <span data-ttu-id="feda8-149">PowerShell[で Get-Mailbox](/powershell/module/exchange/get-mailbox)をExchange Online、ユーザー メールボックスが組織内に存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="feda8-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="feda8-150">オンライン[PowerShell で Get-SPOSite](/powershell/module/sharepoint-online/get-sposite)コマンドレットをSharePoint組織にサイトが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="feda8-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="feda8-151">サイトの URL が変更された場合に確認します。</span><span class="sxs-lookup"><span data-stu-id="feda8-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="feda8-152">詳細情報</span><span class="sxs-lookup"><span data-stu-id="feda8-152">More information</span></span>

<span data-ttu-id="feda8-153">「推奨されるプラクティス」セクションの複数のユーザーの保留ポリシーの更新に関するガイダンスは、システムが保留ポリシーへの同時更新をブロックしているという事実から生じます。</span><span class="sxs-lookup"><span data-stu-id="feda8-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="feda8-154">つまり、更新された保留ポリシーが新しいコンテンツの場所に適用され、保留ポリシーが保留中の状態である場合、追加のコンテンツの場所を保留ポリシーに追加できない。</span><span class="sxs-lookup"><span data-stu-id="feda8-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="feda8-155">この問題の軽減に役立ついくつかの注意が必要な情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="feda8-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="feda8-156">更新された保留が更新されるたび、保留状態に直ちに入ります。</span><span class="sxs-lookup"><span data-stu-id="feda8-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="feda8-157">保留中の状態は、保留がコンテンツの場所に適用されている状態を意味します。</span><span class="sxs-lookup"><span data-stu-id="feda8-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="feda8-158">ループを実行し、ポリシーに場所を 1 つ 1 つ追加するスクリプトがある場合 (「推奨されるプラクティス」セクションに示されている不適切な例と同様)、最初のコンテンツの場所 (ユーザー メールボックスなど) が、保留中の状態をトリガーする同期プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="feda8-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="feda8-159">つまり、後続のループでポリシーに追加された他のユーザーはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="feda8-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="feda8-160">組織がループを実行して保留ポリシーのコンテンツの場所を更新するスクリプトを使用している場合は、スクリプトを更新して、単一の一括操作で場所を更新する必要があります (「推奨されるプラクティス」セクションの正しい例に示すように)。</span><span class="sxs-lookup"><span data-stu-id="feda8-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
