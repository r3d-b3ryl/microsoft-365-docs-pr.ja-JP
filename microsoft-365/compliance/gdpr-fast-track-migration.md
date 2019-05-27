---
title: GDPR
description: Microsoft 技術的なガイダンス - 削除要求を送信するための FastTrack 移行ツールセット
keywords: FastTrack 移行、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
author: MohitKumar
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: mohitku
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 0ef1a23d69ae91b9d94c4587f1912c4171fe84d3
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431418"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="f853d-104">削除要求を送信するための FastTrack 移行ツールセット</span><span class="sxs-lookup"><span data-stu-id="f853d-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="f853d-105">ツールセットの目的</span><span class="sxs-lookup"><span data-stu-id="f853d-105">Toolset purpose</span></span>

<span data-ttu-id="f853d-p101">FastTrack 移行に関与しているお客様の場合は、Office 365 ユーザー アカウントを削除しても、Microsoft FastTrack チームが保持しているデータ コピーは削除されません。このデータ コピーは移行を完了する目的でのみ保持されるものです。移行時に Microsoft FastTrack チームにデータ コピーの削除も依頼する場合は、このツールセットを介して要求を送信してください。通常の業務において、移行が完了した時点で、Microsoft FastTrack がすべてのデータ コピーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f853d-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the Office 365 user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If, during the migration, you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this toolset. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="f853d-109">サポートされるプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="f853d-109">Supported platforms</span></span>
<span data-ttu-id="f853d-p102">Microsoft は、Windows プラットフォームと PowerShell コンソールでこのツールセットの初期リリースをサポートしています。以下の既知のプラットフォームがこのツールセットでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f853d-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="f853d-112">***表 1 - このツールセットでサポートされているプラットフォーム***</span><span class="sxs-lookup"><span data-stu-id="f853d-112">***Table 1 - Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="f853d-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="f853d-113">**Windows 7**</span></span>|<span data-ttu-id="f853d-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="f853d-114">**Windows 8**</span></span>|<span data-ttu-id="f853d-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="f853d-115">**Windows 10**</span></span>|<span data-ttu-id="f853d-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="f853d-116">**Windows Server 2012**</span></span>|<span data-ttu-id="f853d-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="f853d-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="f853d-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="f853d-118">PS 5.0</span></span>|<span data-ttu-id="f853d-119">未サポート</span><span class="sxs-lookup"><span data-stu-id="f853d-119">Not</span></span><br/><span data-ttu-id="f853d-120">サポート済み</span><span class="sxs-lookup"><span data-stu-id="f853d-120">Supported</span></span>|<span data-ttu-id="f853d-121">サポート</span><span class="sxs-lookup"><span data-stu-id="f853d-121">Supported</span></span>|<span data-ttu-id="f853d-122">サポート</span><span class="sxs-lookup"><span data-stu-id="f853d-122">Supported</span></span>|<span data-ttu-id="f853d-123">サポート</span><span class="sxs-lookup"><span data-stu-id="f853d-123">Supported</span></span>|<span data-ttu-id="f853d-124">サポート済み</span><span class="sxs-lookup"><span data-stu-id="f853d-124">Supported</span></span>|
|<span data-ttu-id="f853d-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="f853d-125">PS 5.1</span></span>|<span data-ttu-id="f853d-126">未サポート</span><span class="sxs-lookup"><span data-stu-id="f853d-126">Not</span></span><br/><span data-ttu-id="f853d-127">サポート済み</span><span class="sxs-lookup"><span data-stu-id="f853d-127">Supported</span></span>|<span data-ttu-id="f853d-128">サポート</span><span class="sxs-lookup"><span data-stu-id="f853d-128">Supported</span></span>|<span data-ttu-id="f853d-129">サポート</span><span class="sxs-lookup"><span data-stu-id="f853d-129">Supported</span></span>|<span data-ttu-id="f853d-130">サポート</span><span class="sxs-lookup"><span data-stu-id="f853d-130">Supported</span></span>|<span data-ttu-id="f853d-131">サポート済み</span><span class="sxs-lookup"><span data-stu-id="f853d-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="f853d-132">ツールセットの取得</span><span class="sxs-lookup"><span data-stu-id="f853d-132">Obtaining the toolset</span></span>

<span data-ttu-id="f853d-p103">このツールセットは、PowerShell コンソール アプリケーション上の PowerShell ギャラリーで入手できます。このコマンドレット モジュールを検索して読み込むには、まず、PowerShell を管理者モードで開いて、モジュールをインストールするための適切なアクセス許可が付与されるようにします。過去に PowerShell を使用したことがない場合は、Windows のタスク バーに移動して、検索ボックスに「PowerShell」と入力します。右クリックを使用してコンソール アプリケーションを選択し、**[管理者として実行]** を選択してから、**[はい]** をクリックして Windows PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="f853d-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell - 管理者として実行](media/fasttrack-powershell_image.png)

![PowerShell - アプリケーションに変更を許可する](media/fasttrack-run-powershell_image.png)

<span data-ttu-id="f853d-p104">これでコンソールが開きましたので、スクリプト実行のアクセス許可を設定する必要があります。次のコマンドを入力して、スクリプトの実行を許可します。‘Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope: Process’</span><span class="sxs-lookup"><span data-stu-id="f853d-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process’</span></span>

<span data-ttu-id="f853d-141">この操作の確認が要求されます。これは、管理者が自分の判断で範囲を変更できるためです。</span><span class="sxs-lookup"><span data-stu-id="f853d-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion..</span></span>

<span data-ttu-id="f853d-142">***実行ポリシーの設定***</span><span class="sxs-lookup"><span data-stu-id="f853d-142">***Set Execution Policy***</span></span>

![PowerShell での実行ポリシー変更の設定](media/powershell-set-execution-policy_image.png)

<span data-ttu-id="f853d-144">これで、スクリプトを許可するようにコンソールが設定されたため、次のコマンドを実行してモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f853d-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="f853d-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span><span class="sxs-lookup"><span data-stu-id="f853d-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="f853d-146">モジュールの前提条件</span><span class="sxs-lookup"><span data-stu-id="f853d-146">Prerequisites for module</span></span>
<span data-ttu-id="f853d-p105">このモジュールが正常に動作するためには、まだインストールされていない依存モジュールをインストールする必要があります。PowerShell を再起動しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f853d-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="f853d-149">DSR を送信するには、まず、Office 365 認証情報を使用してログインする必要があります。適切な認証情報を入力すれば、全体管理者の状態が検証され、テナント情報が収集されます。</span><span class="sxs-lookup"><span data-stu-id="f853d-149">In order to submit a DSR, you must first login using your Office 365 credentials – entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="f853d-150">**Login-FastTrackAccount -ApiKey: \<FastTrack MVM から提供される API キー\>**</span><span class="sxs-lookup"><span data-stu-id="f853d-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="f853d-151">ログインに成功すると、資格情報とキーが保存され、現在の PowerShell セッションの残りの部分に対して FastTrack モジュールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="f853d-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="f853d-152">商用以外のクラウド環境に接続する必要がある場合は、次の有効な環境のいずれかを使用して、*-Environment* を *Login* コマンドに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f853d-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will needed to be added to *Login* command with one of the following valid environments:</span></span>
- <span data-ttu-id="f853d-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="f853d-153">AzureCloud</span></span>
- <span data-ttu-id="f853d-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="f853d-154">AzureChinaCloud</span></span>
- <span data-ttu-id="f853d-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="f853d-155">AzureGermanCloud</span></span>
- <span data-ttu-id="f853d-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="f853d-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="f853d-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span><span class="sxs-lookup"><span data-stu-id="f853d-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="f853d-158">DSR 要求を送信するには、次のコマンドを実行します。Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span><span class="sxs-lookup"><span data-stu-id="f853d-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="f853d-p106">成功した場合 - コマンドレットが、トランザクション ID オブジェクトを返します。トランザクション ID を保管してください。</span><span class="sxs-lookup"><span data-stu-id="f853d-p106">On success – the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="f853d-161">要求トランザクションの状態の確認</span><span class="sxs-lookup"><span data-stu-id="f853d-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="f853d-162">取得したトランザクション ID を使用して、次の関数を実行します。Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span><span class="sxs-lookup"><span data-stu-id="f853d-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="f853d-163">トランザクション状態コード</span><span class="sxs-lookup"><span data-stu-id="f853d-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="f853d-164">**トランザクション**</span><span class="sxs-lookup"><span data-stu-id="f853d-164">**Transaction**</span></span> |<span data-ttu-id="f853d-165">**状態**</span><span class="sxs-lookup"><span data-stu-id="f853d-165">**Status**</span></span>|
|<span data-ttu-id="f853d-166">**作成済み**</span><span class="sxs-lookup"><span data-stu-id="f853d-166">**Created**</span></span> |<span data-ttu-id="f853d-167">要求が作成されました。</span><span class="sxs-lookup"><span data-stu-id="f853d-167">Request has been created</span></span>|
|<span data-ttu-id="f853d-168">**失敗**</span><span class="sxs-lookup"><span data-stu-id="f853d-168">**Failed**</span></span>|<span data-ttu-id="f853d-169">要求を作成できませんでした。再送信するか、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f853d-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="f853d-170">**完了**</span><span class="sxs-lookup"><span data-stu-id="f853d-170">**Completed**</span></span>|<span data-ttu-id="f853d-171">要求が完了してサニタイズされました。</span><span class="sxs-lookup"><span data-stu-id="f853d-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="f853d-172">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f853d-172">Learn more</span></span>
[<span data-ttu-id="f853d-173">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="f853d-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)