---
title: スクリプトを使用してコア電子情報開示ケースの保留リストにユーザーを追加する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Microsoft 365 コンプライアンス センターの電子情報開示ケースに&新しい保留リストに OneDrive for Business サイトのメールボックスを追加するスクリプトを実行する方法について説明します。
ms.openlocfilehash: 278e8e051165eca906e9b454268068cbbe6aef05
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175576"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="be02e-103">スクリプトを使用してコア電子情報開示ケースの保留リストにユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="be02e-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="be02e-104">セキュリティ & コンプライアンス センターの PowerShell には、電子情報開示ケースの作成と管理に関連する時間のかかるタスクを自動化できるコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="be02e-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="be02e-105">現在、Security & コンプライアンス センターのコア電子情報開示ケースを使用して多数の保管担当者コンテンツの場所を保留にするのに時間と準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="be02e-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="be02e-106">たとえば、保留リストを作成する前に、保留にしたい各 OneDrive for Business サイトの URL を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be02e-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="be02e-107">その後、保留にしたい各ユーザーについて、そのユーザーのメールボックスと OneDrive for Business サイトを保留リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be02e-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="be02e-108">この記事のスクリプトを使用して、このプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="be02e-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="be02e-109">スクリプトは、組織の My Site ドメインの名前 (URL、既存の電子情報開示ケースの名前、ケースに関連付けられた新しい保留リストの名前、保留にしたいユーザーの電子メール アドレスのリスト、クエリ ベースの保留リストを作成する場合に使用する検索クエリなど) を求めるプロンプトを表示します。 `contoso` https://contoso-my.sharepoint.com)</span><span class="sxs-lookup"><span data-stu-id="be02e-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="be02e-110">次に、スクリプトはリスト内の各ユーザーの OneDrive for Business サイトの URL を取得し、新しい保留リストを作成し、リスト内の各ユーザーのメールボックスと OneDrive for Business サイトを保留リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="be02e-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="be02e-111">このスクリプトは、新しい保留に関する情報を含むログ ファイルも生成します。</span><span class="sxs-lookup"><span data-stu-id="be02e-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="be02e-112">これを行う手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="be02e-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="be02e-113">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="be02e-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="be02e-114">手順 2: ユーザーのリストを生成する</span><span class="sxs-lookup"><span data-stu-id="be02e-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="be02e-115">手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="be02e-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="be02e-116">保留リストにユーザーを追加する前に</span><span class="sxs-lookup"><span data-stu-id="be02e-116">Before you add users to a hold</span></span>

- <span data-ttu-id="be02e-117">手順 3 でスクリプトを実行するには、セキュリティ & コンプライアンス センターの電子情報開示マネージャー役割グループのメンバーであり、SharePoint Online 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="be02e-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="be02e-118">詳細については、「Office [365 Security & Compliance Center」を参照してください](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="be02e-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="be02e-119">セキュリティ & コンプライアンス センターの電子情報開示ケースに関連付けられている保留リストに、最大 1,000 のメールボックスと 100 のサイトを追加できます。</span><span class="sxs-lookup"><span data-stu-id="be02e-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="be02e-120">保留にしたいすべてのユーザーに OneDrive for Business サイトがある場合は、この記事のスクリプトを使用して最大 100 人のユーザーを保留リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="be02e-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="be02e-121">手順 2 で作成したユーザーの一覧と手順 3 のスクリプトを必ず同じフォルダーに保存してください。</span><span class="sxs-lookup"><span data-stu-id="be02e-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="be02e-122">そうすると、スクリプトの実行が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="be02e-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="be02e-123">このスクリプトは、既存のケースに関連付けられている新しい保留リストにユーザーのリストを追加します。</span><span class="sxs-lookup"><span data-stu-id="be02e-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="be02e-124">スクリプトを実行する前に、保留を関連付けるケースが作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="be02e-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="be02e-125">この記事のスクリプトは、セキュリティ センターの PowerShell および SharePoint Online 管理シェル&接続するときに、最新の認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="be02e-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="be02e-126">Microsoft 365 または Microsoft 365 GCC 組織の場合は、このスクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="be02e-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="be02e-127">Office 365 Germany 組織、Microsoft 365 GCC High 組織、または Microsoft 365 DoD 組織の場合は、スクリプトを編集して正常に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be02e-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="be02e-128">具体的には、行を編集し `Connect-IPPSSession` *、ConnectionUri* パラメーターと *AzureADAuthorizationEndpointUri* パラメーター (および組織の種類に適した値) を使用して、セキュリティ & コンプライアンス センター PowerShell に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be02e-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="be02e-129">詳細については、「セキュリティセンターとコンプライアンス センター [の PowerShell への接続」&を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)。</span><span class="sxs-lookup"><span data-stu-id="be02e-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="be02e-130">このスクリプトは、コンプライアンス センター PowerShell & SharePoint Online 管理シェルから自動的に切断されます。</span><span class="sxs-lookup"><span data-stu-id="be02e-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="be02e-131">スクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be02e-131">The script includes minimal error handling.</span></span> <span data-ttu-id="be02e-132">その主な目的は、各ユーザーのメールボックスと OneDrive for Business サイトを迅速かつ簡単に保持することです。</span><span class="sxs-lookup"><span data-stu-id="be02e-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="be02e-p109">このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="be02e-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="be02e-138">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="be02e-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="be02e-139">最初の手順は、SharePoint Online 管理シェルがローカル コンピューターにまだインストールされていない場合にインストールします。</span><span class="sxs-lookup"><span data-stu-id="be02e-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="be02e-140">この手順ではシェルを使用する必要はありません。ただし、このシェルには手順 3 で実行するスクリプトで必要な前提条件が含まれているため、インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be02e-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="be02e-141">これらの前提条件により、スクリプトは SharePoint Online と通信して OneDrive for Business サイトの URL を取得できます。</span><span class="sxs-lookup"><span data-stu-id="be02e-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="be02e-142">[SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318)管理シェル Windows PowerShell 環境のセットアップに進み、手順 1 と手順 2 を実行して SharePoint Online 管理シェルをローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="be02e-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="be02e-143">手順 2: ユーザーのリストを生成する</span><span class="sxs-lookup"><span data-stu-id="be02e-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="be02e-144">手順 3 のスクリプトは、電子情報開示ケースに関連付けられた保留リストを作成し、ユーザーのリストのメールボックスと OneDrive for Business サイトを保留リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="be02e-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="be02e-145">テキスト ファイルに電子メール アドレスを入力するか、Windows PowerShell でコマンドを実行してメール アドレスの一覧を取得し、ファイル (手順 3 でスクリプトを保存するフォルダーと同じフォルダーにあります) に保存することができます。</span><span class="sxs-lookup"><span data-stu-id="be02e-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="be02e-146">組織内のすべてのユーザーの電子メール アドレスの一覧を取得し、それを HoldUsers.txt という名前のテキスト ファイルに保存する PowerShell コマンド (Exchange Online 組織に接続されたリモート PowerShell を使用して実行するコマンド) を次に示します。</span><span class="sxs-lookup"><span data-stu-id="be02e-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="be02e-147">このコマンドを実行した後、テキスト ファイルを開き、プロパティ名を含むヘッダーを削除します  `PrimarySmtpAddress` 。</span><span class="sxs-lookup"><span data-stu-id="be02e-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="be02e-148">次に、手順 3 で作成する保留リストに追加するユーザーの電子メール アドレス以外のすべての電子メール アドレスを削除します。</span><span class="sxs-lookup"><span data-stu-id="be02e-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="be02e-149">電子メール アドレスの一覧の前または後に空白の行が表示されません。</span><span class="sxs-lookup"><span data-stu-id="be02e-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="be02e-150">手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="be02e-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="be02e-151">この手順でスクリプトを実行すると、次の情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be02e-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="be02e-152">スクリプトを実行する前に、この情報を準備してください。</span><span class="sxs-lookup"><span data-stu-id="be02e-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="be02e-153">**ユーザー資格情報:** スクリプトは、資格情報を使用して、PowerShell を使用してセキュリティ & コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="be02e-153">**Your user credentials:** The script will use your credentials to connect to Security & Compliance Center with PowerShell.</span></span> <span data-ttu-id="be02e-154">また、これらの資格情報を使用して SharePoint Online にアクセスし、ユーザーのリストの OneDrive for Business URL を取得します。</span><span class="sxs-lookup"><span data-stu-id="be02e-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="be02e-155">**SharePoint ドメインの名前:** このスクリプトは、SharePoint 管理センターに接続できるよう、この名前を入力するように求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="be02e-155">**Name of your SharePoint domain:** The script prompts you to enter this name so it can connect to the SharePoint admin center.</span></span> <span data-ttu-id="be02e-156">また、組織内の OneDrive URL のドメイン名も使用します。</span><span class="sxs-lookup"><span data-stu-id="be02e-156">It also uses the domain name for the OneDrive URLs in your organization.</span></span> <span data-ttu-id="be02e-157">たとえば、管理センターの URL が OneDrive の場合、スクリプトからドメイン名の入力を求めるメッセージが表示される場合に `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` 入力します。</span><span class="sxs-lookup"><span data-stu-id="be02e-157">For example, if the URL for your admin center is `https://contoso-admin.sharepoint.com` and the URL for OneDrive is `https://contoso-my.sharepoint.com`, then you would enter `contoso` when the script prompts you for your domain name.</span></span>

- <span data-ttu-id="be02e-158">**ケースの名前:** 既存のケースの名前。</span><span class="sxs-lookup"><span data-stu-id="be02e-158">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="be02e-159">スクリプトは、このケースに関連付けられた新しい保留リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="be02e-159">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="be02e-160">**保留リストの名前:** スクリプトが作成し、指定したケースに関連付ける保留リストの名前。</span><span class="sxs-lookup"><span data-stu-id="be02e-160">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="be02e-161">**クエリ ベースの保留の検索クエリ:** クエリ ベースの保留リストを作成して、指定した検索条件を満たすコンテンツのみを保留にできます。</span><span class="sxs-lookup"><span data-stu-id="be02e-161">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="be02e-162">すべてのコンテンツを保留するには、検索クエリの入力を求めるメッセージが表示されたら **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="be02e-162">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="be02e-163">**ホールドをオンにするか、オンにしないか:** スクリプトの作成後に保留リストを有効にするか、スクリプトで有効にせずに保留リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="be02e-163">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="be02e-164">スクリプトを保留にしない場合は、後でセキュリティ & コンプライアンス センターで有効にするか、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="be02e-164">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="be02e-165">**ユーザーのリストを含** むテキスト ファイルの名前 - 保留リストに追加するユーザーのリストを含む手順 2 のテキスト ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="be02e-165">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="be02e-166">このファイルがスクリプトと同じフォルダーにある場合は、ファイルの名前 (たとえば、HoldUsers.txt) を入力します。</span><span class="sxs-lookup"><span data-stu-id="be02e-166">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="be02e-167">テキスト ファイルが別のフォルダーにある場合は、ファイルの完全なパス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="be02e-167">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="be02e-168">スクリプトの指示に従う情報を収集した後、最後の手順として、スクリプトを実行して新しい保留リストを作成し、ユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="be02e-168">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="be02e-169">ファイル名のサフィックスを使用してWindows PowerShellスクリプト ファイルに次のテキストを保存します `.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="be02e-169">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="be02e-170">たとえば、`AddUsersToHold.ps1` などです。</span><span class="sxs-lookup"><span data-stu-id="be02e-170">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="be02e-171">ローカル コンピューターで、スクリプトWindows PowerShellを開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="be02e-171">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="be02e-172">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="be02e-172">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="be02e-173">スクリプトから求める情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="be02e-173">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="be02e-174">スクリプトは Security & Compliance Center PowerShell に接続し、電子情報開示ケースに新しいホールドを作成し、リスト内のユーザーのメールボックスと OneDrive for Business を追加します。</span><span class="sxs-lookup"><span data-stu-id="be02e-174">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="be02e-175">セキュリティ/コンプライアンス センターの [電子情報開示] ページ&に移動して、新しい保留リストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="be02e-175">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="be02e-176">スクリプトの実行が完了すると、次のログ ファイルが作成され、スクリプトが格納されているフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="be02e-176">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="be02e-177">**LocationsOnHold.txt:** スクリプトが正常に保留にされたメールボックスと OneDrive for Business サイトの一覧が含まれる。</span><span class="sxs-lookup"><span data-stu-id="be02e-177">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="be02e-178">**LocationsNotOnHold.txt:** スクリプトが保留にしなかったメールボックスと OneDrive for Business サイトの一覧が含まれている。</span><span class="sxs-lookup"><span data-stu-id="be02e-178">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="be02e-179">ユーザーがメールボックスを持っているが、OneDrive for Business サイトを持たなかった場合、そのユーザーは保留にされていない OneDrive for Business サイトの一覧に含まれます。</span><span class="sxs-lookup"><span data-stu-id="be02e-179">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="be02e-180">**GetCaseHoldPolicy.txt:** 新しい保留リストの作成後にスクリプトが実行した、新しい保留リストの **Get-CaseHoldPolicy** コマンドレットの出力が含されます。</span><span class="sxs-lookup"><span data-stu-id="be02e-180">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="be02e-181">このコマンドレットによって返される情報には、メールボックスと OneDrive for Business サイトが保持されたユーザーの一覧と、ホールドが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="be02e-181">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="be02e-182">**GetCaseHoldRule.txt:** 新しい保留リストの作成後にスクリプトが実行した、新しい保留リストの **Get-CaseHoldRule** コマンドレットの出力が含されます。</span><span class="sxs-lookup"><span data-stu-id="be02e-182">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="be02e-183">このコマンドレットによって返される情報には、クエリ ベースの保持を作成するためにスクリプトを使用した場合の検索クエリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="be02e-183">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
