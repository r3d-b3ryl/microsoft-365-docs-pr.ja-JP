---
title: セキュリティ & コンプライアンスセンターのコア電子情報開示ケースで、スクリプトを使用してユーザーを保留リストに追加する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられた新しい保留リストにメールボックス & OneDrive for Business サイトを追加するスクリプトを実行する方法について説明します。
ms.openlocfilehash: cfa7e176c3974d51fbcc87866c1482277d6010e1
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016310"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="bfd34-103">スクリプトを使用して、コア電子情報開示ケースの保留リストにユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="bfd34-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="bfd34-104">セキュリティ & コンプライアンスセンターでは、電子情報開示ケースの作成と管理に関連する時間のかかるタスクを自動化できる PowerShell コマンドレットが提供されています。</span><span class="sxs-lookup"><span data-stu-id="bfd34-104">The Security & Compliance Center provides PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="bfd34-105">現時点では、セキュリティ & コンプライアンスセンターで電子情報開示ケースツールを使用して、大量の保管担当者コンテンツの場所を保持することにより、時間と準備がかかります。</span><span class="sxs-lookup"><span data-stu-id="bfd34-105">Currently, using the eDiscovery case tool in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="bfd34-106">たとえば、ホールドを作成する前に、保留にする各 OneDrive for Business サイトの URL を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfd34-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="bfd34-107">その後、保持するユーザーごとに、メールボックスとその OneDrive for Business サイトを保留リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfd34-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="bfd34-108">セキュリティ & コンプライアンスセンターの今後のリリースでは、この操作が簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="bfd34-108">In future releases of the Security & Compliance Center, this will get easier to do.</span></span> <span data-ttu-id="bfd34-109">その後、この記事のスクリプトを使用してこのプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-109">Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="bfd34-110">スクリプトでは、組織の個人用サイトドメインの名前 (たとえば、URL 内の**contoso** 、既存の https://contoso-my.sharepoint.com) 電子情報開示ケースの名前、ケースに関連付けられた新しい保留の名前、保留するユーザーの電子メールアドレスのリスト、クエリベースの保持を作成する場合に使用する検索クエリ) の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-110">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="bfd34-111">次に、スクリプトは、リスト内の各ユーザーの OneDrive for Business サイトの URL を取得し、新しいホールドを作成して、リスト内の各ユーザーのメールボックスと OneDrive for business サイトを保留リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-111">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="bfd34-112">このスクリプトは、新しいホールドに関する情報を含むログファイルも生成します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-112">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="bfd34-113">これを行うには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="bfd34-114">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="bfd34-114">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="bfd34-115">手順 2: ユーザーのリストを生成する</span><span class="sxs-lookup"><span data-stu-id="bfd34-115">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="bfd34-116">手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="bfd34-116">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="bfd34-117">ユーザーを保留リストに追加する前に</span><span class="sxs-lookup"><span data-stu-id="bfd34-117">Before you add users to a hold</span></span>

- <span data-ttu-id="bfd34-118">手順3でスクリプトを実行するには、セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。また、SharePoint Online 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfd34-118">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="bfd34-119">詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfd34-119">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="bfd34-120">セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられている保留リストには、最大1000のメールボックスと100サイトを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-120">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="bfd34-121">保持するユーザーに OneDrive for Business サイトが含まれている場合は、この記事のスクリプトを使用して、最大100ユーザーを保留リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-121">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="bfd34-122">手順2で作成したユーザーの一覧と、手順3のスクリプトを同じフォルダーに保存するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="bfd34-122">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="bfd34-123">これにより、スクリプトをより簡単に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfd34-123">That will make it easier to run the script.</span></span>

- <span data-ttu-id="bfd34-124">このスクリプトは、既存のケースに関連付けられている新しいホールドにユーザーのリストを追加します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-124">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="bfd34-125">このスクリプトを実行する前に、保持を関連付けるケースを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfd34-125">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="bfd34-126">スクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfd34-126">The script includes minimal error handling.</span></span> <span data-ttu-id="bfd34-127">その主な目的は、各ユーザーのメールボックスと OneDrive for business サイトを保持して、すばやく簡単に配置できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="bfd34-127">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="bfd34-128">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span><span class="sxs-lookup"><span data-stu-id="bfd34-128">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="bfd34-129">The sample scripts are provided AS IS without warranty of any kind.</span><span class="sxs-lookup"><span data-stu-id="bfd34-129">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="bfd34-130">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span><span class="sxs-lookup"><span data-stu-id="bfd34-130">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="bfd34-131">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span><span class="sxs-lookup"><span data-stu-id="bfd34-131">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="bfd34-132">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span><span class="sxs-lookup"><span data-stu-id="bfd34-132">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="bfd34-133">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="bfd34-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="bfd34-134">最初の手順として、SharePoint Online 管理シェルがローカルコンピューターにまだインストールされていない場合はインストールします。</span><span class="sxs-lookup"><span data-stu-id="bfd34-134">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="bfd34-135">この手順でシェルを使用する必要はありませんが、手順3で実行するスクリプトに必要な前提条件が含まれているためインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfd34-135">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="bfd34-136">これらの前提条件によって、スクリプトは SharePoint Online と通信して、OneDrive for Business サイトの Url を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-136">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="bfd34-137">「 [Sharepoint Online 管理シェル Windows PowerShell 環境をセットアップ](https://go.microsoft.com/fwlink/p/?LinkID=286318)する」に移動し、手順1と手順2を実行して、ローカルコンピューターに Sharepoint Online 管理シェルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bfd34-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="bfd34-138">手順 2: ユーザーのリストを生成する</span><span class="sxs-lookup"><span data-stu-id="bfd34-138">Step 2: Generate a list of users</span></span>

<span data-ttu-id="bfd34-139">手順3のスクリプトは、電子情報開示ケースに関連付けられているホールドを作成し、ユーザーのリストのメールボックスと OneDrive for Business サイトを保留リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-139">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="bfd34-140">テキストファイルに電子メールアドレスを入力することも、Windows PowerShell でコマンドを実行して電子メールアドレスの一覧を取得し、それをファイルに保存することもできます (手順3でスクリプトを保存するのと同じフォルダーに格納されます)。</span><span class="sxs-lookup"><span data-stu-id="bfd34-140">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="bfd34-141">次に示すのは、PowerShell コマンド (Exchange Online 組織に接続されたリモート PowerShell を使用して実行する) で、組織内のすべてのユーザーの電子メールアドレスの一覧を取得し、それを HoldUsers.txt という名前のテキストファイルに保存することです。</span><span class="sxs-lookup"><span data-stu-id="bfd34-141">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="bfd34-142">このコマンドを実行した後、テキストファイルを開いて、プロパティ名を含むヘッダーを削除し `PrimarySmtpAddress` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-142">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="bfd34-143">その後、手順3で作成するホールドに追加するユーザーのメールアドレス以外のすべてのメールアドレスを削除します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-143">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="bfd34-144">電子メールアドレスのリストの前または後に空白行がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-144">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="bfd34-145">手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="bfd34-145">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="bfd34-146">この手順でスクリプトを実行すると、次の情報を入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-146">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="bfd34-147">スクリプトを実行する前に、この情報を用意しておいてください。</span><span class="sxs-lookup"><span data-stu-id="bfd34-147">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="bfd34-148">**ユーザーの資格情報:** このスクリプトは、資格情報を使用して、リモート PowerShell を使用してセキュリティ & コンプライアンスセンターに接続します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-148">**Your user credentials:** The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="bfd34-149">また、これらの資格情報を使用して SharePoint Online にアクセスし、ユーザーリストの OneDrive for Business Url を取得します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-149">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="bfd34-150">**個人用サイトのドメインの名前:** 個人用サイトドメインは、組織内のすべての OneDrive for Business サイトを含むドメインです。</span><span class="sxs-lookup"><span data-stu-id="bfd34-150">**Name of your MySite domain:** The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="bfd34-151">たとえば、個人用サイトのドメインの URL がの場合は、 **https://contoso-my.sharepoint.com** スクリプトによって、 `contoso` 個人用サイトのドメインの名前を入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-151">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span>

- <span data-ttu-id="bfd34-152">**ケースの名前:** 既存のケースの名前。</span><span class="sxs-lookup"><span data-stu-id="bfd34-152">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="bfd34-153">このスクリプトは、このケースに関連付けられている新しいホールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-153">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="bfd34-154">**保留の名前:** スクリプトが作成し、指定されたケースに関連付けられているホールドの名前。</span><span class="sxs-lookup"><span data-stu-id="bfd34-154">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="bfd34-155">**クエリベースの保持の検索クエリ:** クエリベースの保持を作成して、指定した検索条件に一致するコンテンツのみを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-155">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="bfd34-156">すべてのコンテンツを保持するには、検索クエリの入力を求められたときに**enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-156">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="bfd34-157">**保留をオンにするかどうかを指定します。** スクリプトを作成した後でホールドを有効にしたり、スクリプトで保持を有効にせずにホールドを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-157">**Whether or not to turn on the hold:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="bfd34-158">スクリプトでホールドをオンにしていない場合は、後でセキュリティ & コンプライアンスセンターで有効にするか、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-158">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="bfd34-159">**ユーザーのリストを含むテキストファイルの名前**-手順2で保留に追加するユーザーの一覧が含まれているテキストファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="bfd34-159">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="bfd34-160">このファイルがスクリプトと同じフォルダーにある場合は、ファイルの名前 (たとえば、HoldUsers.txt) を入力するだけです。</span><span class="sxs-lookup"><span data-stu-id="bfd34-160">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="bfd34-161">テキストファイルが別のフォルダーにある場合は、ファイルの完全なパス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-161">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="bfd34-162">スクリプトが要求する情報を収集したら、最後の手順として、スクリプトを実行して新しいホールドを作成し、それにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-162">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="bfd34-163">ファイル名サフィックスを使用して、次のテキストを Windows PowerShell スクリプトファイルに保存 `.ps1` します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-163">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="bfd34-164">たとえば、`AddUsersToHold.ps1` などです。</span><span class="sxs-lookup"><span data-stu-id="bfd34-164">For example, `AddUsersToHold.ps1`.</span></span>

  ```powershell
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
      }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. <span data-ttu-id="bfd34-165">ローカルコンピューターで、Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-165">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="bfd34-166">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="bfd34-166">Run the script; for example:</span></span>

      ```powershell
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="bfd34-167">スクリプトによってプロンプトが表示される情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-167">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="bfd34-168">このスクリプトは、セキュリティ & コンプライアンスセンターの PowerShell に接続し、電子情報開示ケースで新しいホールドを作成し、リスト内のユーザーのメールボックスと OneDrive for Business を追加します。</span><span class="sxs-lookup"><span data-stu-id="bfd34-168">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="bfd34-169">セキュリティ & コンプライアンスセンターの [**電子情報開示**] ページに移動して、新しいホールドを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-169">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span> 

<span data-ttu-id="bfd34-170">スクリプトの実行が完了すると、次のログファイルが作成され、スクリプトが配置されているフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-170">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="bfd34-171">**LocationsOnHold.txt:** スクリプトが正常に停止したメールボックスと OneDrive for Business サイトの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfd34-171">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="bfd34-172">**LocationsNotOnHold.txt:** スクリプトが保留になっていないメールボックスと OneDrive for Business サイトの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfd34-172">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="bfd34-173">ユーザーがメールボックスを持っているが、OneDrive for Business サイトを持っていない場合、ユーザーは保留になっていない OneDrive for Business サイトの一覧に含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfd34-173">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="bfd34-174">**GetCaseHoldPolicy.txt:** 新しいホールドの**CaseHoldPolicy**コマンドレットの出力が含まれています。新しいホールドを作成した後にスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-174">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="bfd34-175">このコマンドレットによって返される情報には、メールボックスと OneDrive for Business サイトが保持されたユーザーの一覧、および保留が有効か無効かが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-175">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="bfd34-176">**GetCaseHoldRule.txt:** 新しいホールドの**new-caseholdrule**コマンドレットの出力が含まれています。新しいホールドを作成した後にスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bfd34-176">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="bfd34-177">このコマンドレットによって返される情報には、クエリベースの保持を作成するためにスクリプトを使用した場合の検索クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfd34-177">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
