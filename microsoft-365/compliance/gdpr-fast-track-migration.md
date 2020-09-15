---
title: GDPR
description: Microsoft 技術的なガイダンス - 削除要求を送信するための FastTrack 移行ツールセット
keywords: FastTrack 移行、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 10a983297640ac4b65aaf181ef35ac19918e74fe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547388"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="ec2f4-104">削除要求を送信するための FastTrack 移行ツールセット</span><span class="sxs-lookup"><span data-stu-id="ec2f4-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="ec2f4-105">ツールセットの目的</span><span class="sxs-lookup"><span data-stu-id="ec2f4-105">Toolset purpose</span></span>

<span data-ttu-id="ec2f4-p101">FastTrack 移行に関与しているお客様の場合は、ユーザー アカウントを削除しても、Microsoft FastTrack チームが保持しているデータ コピーは削除されません。このデータ コピーは移行を完了する目的でのみ保持されています。移行時に Microsoft FastTrack チームにデータ コピーの削除も依頼する場合は、このツールセットを介してリクエストを送信してください。通常の業務において、移行が完了した時点で、Microsoft FastTrack がすべてのデータ コピーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="ec2f4-109">サポートされるプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="ec2f4-109">Supported platforms</span></span>

<span data-ttu-id="ec2f4-p102">Microsoft は、Windows プラットフォームと PowerShell コンソールでこのツールセットの初期リリースをサポートしています。以下の既知のプラットフォームがこのツールセットでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>

<span data-ttu-id="ec2f4-112">***表 1 - このツールセットでサポートされているプラットフォーム***</span><span class="sxs-lookup"><span data-stu-id="ec2f4-112">***Table 1 — Platforms supported by this toolset***</span></span>

****

|<span data-ttu-id="ec2f4-113">PowerShell バージョン</span><span class="sxs-lookup"><span data-stu-id="ec2f4-113">PowerShell version</span></span>|<span data-ttu-id="ec2f4-114">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ec2f4-114">Windows 7</span></span>|<span data-ttu-id="ec2f4-115">Windows 8</span><span class="sxs-lookup"><span data-stu-id="ec2f4-115">Windows 8</span></span>|<span data-ttu-id="ec2f4-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ec2f4-116">Windows 10</span></span>|<span data-ttu-id="ec2f4-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec2f4-117">Windows Server 2012</span></span>|<span data-ttu-id="ec2f4-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ec2f4-118">Windows Server 2016</span></span>|
|:---:|:---:|:---:|:---:|:---:|:---:|
|<span data-ttu-id="ec2f4-119">5.0</span><span class="sxs-lookup"><span data-stu-id="ec2f4-119">5.0</span></span>|<span data-ttu-id="ec2f4-120">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="ec2f4-120">Not Supported</span></span>|<span data-ttu-id="ec2f4-121">サポートされます</span><span class="sxs-lookup"><span data-stu-id="ec2f4-121">Supported</span></span>|<span data-ttu-id="ec2f4-122">サポート</span><span class="sxs-lookup"><span data-stu-id="ec2f4-122">Supported</span></span>|<span data-ttu-id="ec2f4-123">サポート</span><span class="sxs-lookup"><span data-stu-id="ec2f4-123">Supported</span></span>|<span data-ttu-id="ec2f4-124">サポート</span><span class="sxs-lookup"><span data-stu-id="ec2f4-124">Supported</span></span>|
|<span data-ttu-id="ec2f4-125">5.1</span><span class="sxs-lookup"><span data-stu-id="ec2f4-125">5.1</span></span>|<span data-ttu-id="ec2f4-126">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="ec2f4-126">Not Supported</span></span>|<span data-ttu-id="ec2f4-127">サポートされます</span><span class="sxs-lookup"><span data-stu-id="ec2f4-127">Supported</span></span>|<span data-ttu-id="ec2f4-128">サポート</span><span class="sxs-lookup"><span data-stu-id="ec2f4-128">Supported</span></span>|<span data-ttu-id="ec2f4-129">サポート</span><span class="sxs-lookup"><span data-stu-id="ec2f4-129">Supported</span></span>|<span data-ttu-id="ec2f4-130">サポート済み</span><span class="sxs-lookup"><span data-stu-id="ec2f4-130">Supported</span></span>|
|

### <a name="obtaining-the-toolset"></a><span data-ttu-id="ec2f4-131">ツールセットの取得</span><span class="sxs-lookup"><span data-stu-id="ec2f4-131">Obtaining the toolset</span></span>

<span data-ttu-id="ec2f4-p103">このツールセットは、PowerShell コンソール アプリケーション上の PowerShell ギャラリーで入手できます。このコマンドレット モジュールを検索して読み込むには、まず、PowerShell を管理者モードで開いて、モジュールをインストールするための適切なアクセス許可が付与されるようにします。過去に PowerShell を使用したことがない場合は、Windows のタスク バーに移動して、検索ボックスに「PowerShell」と入力します。右クリックを使用してコンソール アプリケーションを選択し、**[管理者として実行]** を選択してから、**[はい]** をクリックして Windows PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell - 管理者として実行](../media/fasttrack-powershell_image.png)

![PowerShell - アプリケーションに変更を許可する](../media/fasttrack-run-powershell_image.png)

<span data-ttu-id="ec2f4-138">コンソールが開いたところで、スクリプトの実行のアクセス許可を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-138">Now that the console is open, you need to set permissions for script execution.</span></span> <span data-ttu-id="ec2f4-139">次のコマンドを入力して、スクリプトの実行を許可します。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-139">Type the following command to allow the scripts to run:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

<span data-ttu-id="ec2f4-140">この操作の確認が要求されます。これは、管理者が自分の判断で範囲を変更できるためです。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-140">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="ec2f4-141">***実行ポリシーの設定***</span><span class="sxs-lookup"><span data-stu-id="ec2f4-141">***Set Execution Policy***</span></span>

![PowerShell での実行ポリシー変更の設定](../media/powershell-set-execution-policy_image.png)

<span data-ttu-id="ec2f4-143">これで、スクリプトを許可するようにコンソールが設定されたので、次のコマンドを実行してモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-143">Now that the console is set to allow the script, run this next command to install the module:</span></span>

```powershell
Install-Module -Name Microsoft.FastTrack -Repository PSGallery -WarningAction SilentlyContinue -Force
```

### <a name="prerequisites-for-module"></a><span data-ttu-id="ec2f4-144">モジュールの前提条件</span><span class="sxs-lookup"><span data-stu-id="ec2f4-144">Prerequisites for module</span></span>

<span data-ttu-id="ec2f4-p105">このモジュールが正常に動作するためには、まだインストールされていない依存モジュールをインストールする必要があります。PowerShell を再起動しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>

<span data-ttu-id="ec2f4-147">DSR を送信するには、最初に Office 365 の資格情報を使用してログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-147">In order to submit a DSR, you must first log in using your Office 365 credentials.</span></span> <span data-ttu-id="ec2f4-148">正しい資格情報を入力すると、グローバル管理者のステータスが検証され、テナントの情報が収集されます。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-148">Entering the proper credentials will validate your global administrator status and collect tenant information.</span></span>

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM>
```

<span data-ttu-id="ec2f4-149">ログインに成功すると、資格情報とキーが保存され、現在の PowerShell セッションの残りの部分に対して FastTrack モジュールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-149">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="ec2f4-150">商用以外のクラウド環境に接続する必要がある場合は、次の有効な環境のいずれかを使用して、*-Environment* を *Login* コマンドに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-150">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>

- <span data-ttu-id="ec2f4-151">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="ec2f4-151">AzureCloud</span></span>
- <span data-ttu-id="ec2f4-152">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="ec2f4-152">AzureChinaCloud</span></span>
- <span data-ttu-id="ec2f4-153">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="ec2f4-153">AzureGermanCloud</span></span>
- <span data-ttu-id="ec2f4-154">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="ec2f4-154">AzureUSGovernmentCloud</span></span>

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM> -Environment <cloud environment>
```

<span data-ttu-id="ec2f4-155">DSR 要求を送信するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-155">To submit a DSR request, run the following command:</span></span>

```powershell
Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail SubjectUserEmail@mycompany.com
```

<span data-ttu-id="ec2f4-156">成功した場合、コマンドレットによってトランザクション ID オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-156">On success, the cmdlet will return a Transaction ID object.</span></span> <span data-ttu-id="ec2f4-157">このトランザクション ID は、保管してください。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-157">Please retain the Transaction ID.</span></span>

#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="ec2f4-158">要求トランザクションの状態の確認</span><span class="sxs-lookup"><span data-stu-id="ec2f4-158">Checking the status of a request transaction</span></span>

<span data-ttu-id="ec2f4-159">先ほど取得したトランザクション ID を使用して、次の関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-159">Run the following function using the previously obtained Transaction ID:</span></span>

```powershell
Get-FastTrackGdprDsrRequest -TransactionID "YourTransactionID"
```

#### <a name="transaction-status-codes"></a><span data-ttu-id="ec2f4-160">トランザクション状態コード</span><span class="sxs-lookup"><span data-stu-id="ec2f4-160">Transaction Status Codes</span></span>

|<span data-ttu-id="ec2f4-161">トランザクション</span><span class="sxs-lookup"><span data-stu-id="ec2f4-161">Transaction</span></span>|<span data-ttu-id="ec2f4-162">状態</span><span class="sxs-lookup"><span data-stu-id="ec2f4-162">Status</span></span>|
|---|---|
|<span data-ttu-id="ec2f4-163">**Created**</span><span class="sxs-lookup"><span data-stu-id="ec2f4-163">**Created**</span></span>|<span data-ttu-id="ec2f4-164">要求が作成されました。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-164">Request has been created.</span></span>|
|<span data-ttu-id="ec2f4-165">**Failed**</span><span class="sxs-lookup"><span data-stu-id="ec2f4-165">**Failed**</span></span>|<span data-ttu-id="ec2f4-166">要求を作成できませんでした。再送信するか、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-166">Request failed to create, please resubmit, or contact support.</span></span>|
|<span data-ttu-id="ec2f4-167">**Completed**</span><span class="sxs-lookup"><span data-stu-id="ec2f4-167">**Completed**</span></span>|<span data-ttu-id="ec2f4-168">要求が完了してサニタイズされました。</span><span class="sxs-lookup"><span data-stu-id="ec2f4-168">Request has been completed and sanitized.</span></span>|
|

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->

## <a name="learn-more"></a><span data-ttu-id="ec2f4-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ec2f4-169">Learn more</span></span>

[<span data-ttu-id="ec2f4-170">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="ec2f4-170">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
