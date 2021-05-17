---
title: Microsoft 365 で PowerShell を使用する理由
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: '概要: PowerShell を使用して管理する必要がある理由Microsoft 365場合によっては、より効率的に、必要に応じて他の場合にも説明します。'
ms.openlocfilehash: a60220001a148b3a24a996bb6e0154f80214b019
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924590"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="22e66-103">Microsoft 365 で PowerShell を使用する理由</span><span class="sxs-lookup"><span data-stu-id="22e66-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="22e66-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="22e66-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="22e66-105">管理者センター Microsoft 365、ユーザー アカウントとライセンスMicrosoft 365管理できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="22e66-106">また、オンライン、Microsoft 365、オンラインなどのExchange OnlineサービスTeams管理SharePointできます。</span><span class="sxs-lookup"><span data-stu-id="22e66-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="22e66-107">代わりに PowerShell を使用してこれらのサービスを管理する場合は、コマンド ラインとスクリプト言語環境を利用して、速度、自動化、追加機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="22e66-108">この記事では、PowerShell を使用して次の情報を管理するMicrosoft 365示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="22e66-109">管理センターで表示できない追加情報をMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="22e66-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="22e66-110">PowerShell でのみ可能な機能と設定を構成する</span><span class="sxs-lookup"><span data-stu-id="22e66-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="22e66-111">一括操作を実行する</span><span class="sxs-lookup"><span data-stu-id="22e66-111">Do bulk operations</span></span>
    
- <span data-ttu-id="22e66-112">データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="22e66-112">Filter data</span></span>
    
- <span data-ttu-id="22e66-113">データの印刷または保存</span><span class="sxs-lookup"><span data-stu-id="22e66-113">Print or save data</span></span>
    
- <span data-ttu-id="22e66-114">複数のサービスを管理する</span><span class="sxs-lookup"><span data-stu-id="22e66-114">Manage across services</span></span>
    
<span data-ttu-id="22e66-115">PowerShell for Microsoft 365 は Windows PowerShell の一連のモジュールであり、Windows ベースのサービスとプラットフォームのコマンドライン環境です。</span><span class="sxs-lookup"><span data-stu-id="22e66-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="22e66-116">この環境では、追加のモジュールで拡張できるコマンド シェル言語を作成します。</span><span class="sxs-lookup"><span data-stu-id="22e66-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="22e66-117">単純なコマンドまたは複雑なコマンドまたはスクリプトを実行する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="22e66-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="22e66-118">たとえば、Microsoft 365 モジュール用の PowerShell をインストールし、Microsoft 365 サブスクリプションに接続した後、次のコマンドを実行して、すべてのユーザー メールボックスを一覧表示Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="22e66-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="22e66-119">Microsoft 365 管理センターを使用してメールボックスのリストを取得することもできますが、すべての Web アプリのすべてのサイトのすべてのリスト内のアイテムを数えるのは簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="22e66-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="22e66-120">PowerShell for Microsoft 365管理センターを置き換えるのではなく、Microsoft 365管理を管理Microsoft 365設計されています。</span><span class="sxs-lookup"><span data-stu-id="22e66-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="22e66-121">管理者は、PowerShell を使用して Microsoft 365 コマンドを実行する場合にのみ実行できる構成手順がいくつかあるため、Microsoft 365 必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="22e66-122">このような場合は、次の方法を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="22e66-123">PowerShell for Microsoft 365モジュールをインストールします (管理者コンピューターごとに 1 回のみ実行)。</span><span class="sxs-lookup"><span data-stu-id="22e66-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="22e66-124">ConnectサブスクリプションにMicrosoft 365します (PowerShell セッションごとに 1 回)。</span><span class="sxs-lookup"><span data-stu-id="22e66-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="22e66-125">コマンドの実行に必要な PowerShell を実行するために必要なMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="22e66-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="22e66-126">PowerShell を実行して、Microsoft 365コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="22e66-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="22e66-127">これらの基本的なスキルを習得した後は **、[Get-Mailbox]** コマンドを使用してメールボックス ユーザーを一覧表示する必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="22e66-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="22e66-128">また、すべての Web アプリのすべてのサイトのすべてのリストのすべての項目をカウントするために、前に引用したコマンドのような新しいコマンドを作成する方法も理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="22e66-129">Microsoft と管理者のコミュニティは、必要に応じてこのようなタスクを支援できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="22e66-130">PowerShell for Microsoft 365管理センターで表示できない情報をMicrosoft 365できます</span><span class="sxs-lookup"><span data-stu-id="22e66-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="22e66-131">管理Microsoft 365には、多くの有用な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="22e66-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="22e66-132">ただし、ユーザー、ライセンス、メールボックス、およびサイトにMicrosoft 365できる情報はすべて表示されません。</span><span class="sxs-lookup"><span data-stu-id="22e66-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="22e66-133">次に、管理センター *のユーザー* とグループMicrosoft 365示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![管理センターでのユーザーとグループの表示Microsoft 365例。](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="22e66-135">このビューは、多くの場合必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="22e66-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="22e66-136">しかし、もっと多くの情報が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="22e66-136">However, there are times when you need more.</span></span> <span data-ttu-id="22e66-137">たとえば、Microsoft 365 (およびユーザーがMicrosoft 365使用できる機能) は、ユーザーの地理的な場所によって一部異なります。</span><span class="sxs-lookup"><span data-stu-id="22e66-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="22e66-138">米国に住むユーザーに拡張できるポリシーと機能は、インドまたはベルギーのユーザーに拡張できるポリシーと機能と同じではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="22e66-139">管理者センターの次のMicrosoft 365に従って、ユーザーの地理的な場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="22e66-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="22e66-140">ユーザーの **表示名** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="22e66-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="22e66-141">ユーザー プロパティの表示ウィンドウで、[詳細] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="22e66-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="22e66-142">詳細表示で、追加の詳細 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="22e66-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="22e66-143">[国] または [地域] という見出し **が表示されるまでスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="22e66-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![管理センターのユーザーの地域情報Microsoft 365例です。](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="22e66-145">ユーザーの表示名と場所を紙に書き留めるか、コピーしてメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="22e66-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="22e66-146">この手順をユーザーごとに繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="22e66-147">ユーザーが多い場合、このプロセスは時間のかかっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="22e66-148">PowerShell for Microsoft 365、次のコマンドを使用して、すべてのユーザーに対してこの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="22e66-149">PowerShell Core では、Msol を名前に含Microsoft Azure Active DirectoryモジュールWindows PowerShellコマンドレットのモジュール *モジュールは* サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="22e66-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="22e66-150">これらのコマンドレットは、次の手順で実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="22e66-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="22e66-151">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-151">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

<span data-ttu-id="22e66-152">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション **(Get-AzureADUser)** のすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示します (Select **DisplayName, UsageLocation)。**</span><span class="sxs-lookup"><span data-stu-id="22e66-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="22e66-153">PowerShell for Microsoft 365コマンド シェル言語をサポートしている場合 **、Get-AzureADUser** コマンドで取得した情報をさらに操作できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="22e66-154">たとえば、これらのユーザーを場所別に並べ替え、すべてのブラジル人ユーザーをグループ化し、すべての米国ユーザーをまとめてグループ化する場合などです。</span><span class="sxs-lookup"><span data-stu-id="22e66-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="22e66-155">コマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="22e66-156">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-156">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

<span data-ttu-id="22e66-157">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示し、最初にユーザーの場所で並べ替え、次に名前 **(Sort UsageLocation,DisplayName)** で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="22e66-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="22e66-158">追加のフィルター処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-158">You can also use additional filtering.</span></span> <span data-ttu-id="22e66-159">たとえば、ブラジル在住のユーザーに関する情報のみを表示する場合には、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="22e66-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="22e66-160">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="22e66-161">この PowerShell コマンドの解釈は、現在のサブスクリプションのすべてのユーザーを取得しMicrosoft 365場所がブラジル ( Where **{$ \_ ) です。UsageLocation -eq "BR"}**) をクリックし、各ユーザーの名前と場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="22e66-162">**大規模なドメインに関するメモ**</span><span class="sxs-lookup"><span data-stu-id="22e66-162">**A note about large domains**</span></span>
  
<span data-ttu-id="22e66-163">数万人のユーザーを持つ大規模なドメインがある場合は、この記事で示す例の一部を試してみようとすると、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="22e66-164">計算能力や利用可能なネットワーク帯域幅のような要因に基づいて、一度に実行しすぎようとしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="22e66-165">大規模な組織では、これらの PowerShell 操作の一部を 2 つのコマンドに分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="22e66-166">たとえば、次のコマンドは、すべてのユーザー アカウントを返し、それぞれの名前と場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="22e66-167">このコマンドは、規模が小さいドメインには最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="22e66-167">That works great for smaller domains.</span></span> <span data-ttu-id="22e66-168">ただし、大規模な組織では、その操作を変数にユーザー アカウント情報を格納するコマンドと、必要な情報を表示する 2 つのコマンドに分割できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="22e66-169">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="22e66-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="22e66-170">この一連の PowerShell コマンドの解釈は次の場合です。</span><span class="sxs-lookup"><span data-stu-id="22e66-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="22e66-171">現在のサブスクリプション内のすべてのユーザー Microsoft 365取得し、$x ( $x **= Get-AzureADUser)** という名前の変数に情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="22e66-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="22e66-172">変数の内容を表示 *$x、各* ユーザーの名前と **場所のみを含$x |[DisplayName, UsageLocation] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="22e66-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="22e66-173">Microsoft 365 PowerShell でのみ構成できる機能が含Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22e66-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="22e66-174">管理Microsoft 365は、ほとんどの環境に適用される一般的で有用な管理タスクへのアクセスを提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="22e66-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="22e66-175">つまり、管理センター Microsoft 365、一般的な管理者が最も一般的な管理タスクを実行できるよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="22e66-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="22e66-176">ただし、管理センターでは実行できないタスクもあります。</span><span class="sxs-lookup"><span data-stu-id="22e66-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="22e66-177">たとえば、Skype for Business管理センターには、カスタム会議出席依頼を作成するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="22e66-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Skype for Business Online 管理センターでカスタムの会議出席依頼を表示する例です。](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="22e66-179">これらの設定を使用すると、会議出席依頼にパーソナルでプロフェッショナルな風合いを加えることができます。</span><span class="sxs-lookup"><span data-stu-id="22e66-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="22e66-180">ただし、会議構成の設定には、単にカスタムの会議出席依頼を作成するよりも多くがあります。</span><span class="sxs-lookup"><span data-stu-id="22e66-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="22e66-181">たとえば、既定では会議に関して以下の事柄が許可されています。</span><span class="sxs-lookup"><span data-stu-id="22e66-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="22e66-182">匿名ユーザーが、各会議に自動的に参加すること。</span><span class="sxs-lookup"><span data-stu-id="22e66-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="22e66-183">参加者が、会議を記録すること。</span><span class="sxs-lookup"><span data-stu-id="22e66-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="22e66-184">組織のすべてのユーザーが、会議に参加するときに発表者として指定されること。</span><span class="sxs-lookup"><span data-stu-id="22e66-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="22e66-185">これらの設定は、オンライン管理センター Skype for Business使用できません。</span><span class="sxs-lookup"><span data-stu-id="22e66-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="22e66-186">PowerShell からこれらのコントロールを制御して、Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="22e66-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="22e66-187">次の 3 つの設定を無効にするコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="22e66-188">このコマンドを実行するには、オンライン[PowerShell モジュールSkype for Businessインストールする必要があります](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="22e66-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="22e66-189">この PowerShell コマンドの解釈は次の場合です。</span><span class="sxs-lookup"><span data-stu-id="22e66-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="22e66-190">新しい Skype for Business Online 会議 **(Set-CsMeetingConfiguration)** の設定で、匿名ユーザーが会議への自動入り口を取得できるように無効にします **(-AdmitAnonymousUsersByDefault**$False)。</span><span class="sxs-lookup"><span data-stu-id="22e66-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="22e66-191">出席者が会議を記録する機能を無効にします **(-AllowConferenceRecording**$False)。</span><span class="sxs-lookup"><span data-stu-id="22e66-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="22e66-192">組織のすべてのユーザーを発表者として指定しない (**-DesignateAsPresenter "None"**)。</span><span class="sxs-lookup"><span data-stu-id="22e66-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="22e66-193">これらの既定の設定を復元する (オプションを有効にする) には、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="22e66-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="22e66-194">他にも同様のシナリオがあります。そのため、管理者は PowerShell を実行してコマンドを実行する方法Microsoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="22e66-195">PowerShell for Microsoft 365一括操作に最適</span><span class="sxs-lookup"><span data-stu-id="22e66-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="22e66-196">管理センターのようなビジュアル Microsoft 365は、単一の操作を実行する場合に最も重要です。</span><span class="sxs-lookup"><span data-stu-id="22e66-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="22e66-197">たとえば、1 つのユーザー アカウントを無効にする必要がある場合は、管理センターを使用して、チェック ボックスをすばやく見つけてクリアできます。</span><span class="sxs-lookup"><span data-stu-id="22e66-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="22e66-198">これは、PowerShell で同様の操作を実行するよりも簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="22e66-199">ただし、他の大きなセット内で多くの変更や選択した項目を変更する必要がある場合は、Microsoft 365管理センターが最適なツールではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="22e66-200">たとえば、何千もの電話番号のプレフィックスを変更するか、特定のユーザー *Ken Myer* をすべてのオンライン サイトから削除する必要SharePointします。</span><span class="sxs-lookup"><span data-stu-id="22e66-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="22e66-201">管理センターでどのようにMicrosoft 365しますか?</span><span class="sxs-lookup"><span data-stu-id="22e66-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="22e66-202">最後の例では、数百のオンライン サイトSharePoint、Ken Meyer がメンバーであるかどうかがわかりません。</span><span class="sxs-lookup"><span data-stu-id="22e66-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="22e66-203">管理センターの管理者センターからMicrosoft 365し、サイトごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="22e66-204">サイト **の URL** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22e66-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="22e66-205">[サイト コレクション **のプロパティ] ボックス** で **、[Web サイト** アドレス] リンクを選択してサイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="22e66-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="22e66-206">サイトで、[共有] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="22e66-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="22e66-207">[共有 **] ダイアログ** ボックスで、サイトへのアクセス許可を持つすべてのユーザーを表示するリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="22e66-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![SharePoint Online 管理センターの SharePoint Online サイトのメンバーを表示する例です。](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="22e66-209">[共有する **ユーザー] ダイアログ ボックス** で、[詳細設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="22e66-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="22e66-210">ユーザーの一覧を下にスクロールし、Ken Myer (サイトへのアクセス許可がある場合) を見つけて選択し、[ユーザーのアクセス許可の削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="22e66-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="22e66-211">これは、数百 *のサイト* には長い時間がかかるでしょう。</span><span class="sxs-lookup"><span data-stu-id="22e66-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="22e66-212">もう 1 つの方法は、PowerShell で次のコマンドを実行して、Microsoft 365 Ken Myer をすべてのサイトから削除する方法です。</span><span class="sxs-lookup"><span data-stu-id="22e66-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="22e66-213">このコマンドでは、オンライン PowerShell モジュールSharePoint[インストールする必要があります](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="22e66-213">This command requires that you install the [SharePoint Online PowerShell module](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="22e66-214">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション **(Get-SPOSite)** 内のすべての SharePoint サイトを取得し、各サイトでアクセスできるユーザーの一覧から Ken Meyer を削除することです **(ForEach {Remove-SPOUser -Site $ . \_Url -LoginName "kenmyer \@ litwareinc.com"}**)。</span><span class="sxs-lookup"><span data-stu-id="22e66-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="22e66-215">Ken Meyer Microsoft 365アクセス権を持たなかったサイトを含め、すべてのサイトから Ken Meyer を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="22e66-216">そのため、アクセスできないサイトのエラーが結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="22e66-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="22e66-217">このコマンドで追加の条件を使用して、Ken Meyer をログイン リストに登録しているサイトからのみ削除できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="22e66-218">しかし、返されるエラーは、サイト自体に害を及ぼしません。</span><span class="sxs-lookup"><span data-stu-id="22e66-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="22e66-219">このコマンドは、管理センターで作業する時間ではなく、数百のサイトに対して実行Microsoft 365場合があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="22e66-220">別の一括操作の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-220">Here's another bulk operation example.</span></span> <span data-ttu-id="22e66-221">次のコマンドを使用して、新しい管理者である *ボ* ニー SharePointを組織内のすべてのサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="22e66-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="22e66-222">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション内のすべての SharePoint サイトを取得し、各サイトで、サイトの Members グループにログイン名を追加することで、ボニー カーニー アクセスを許可します **(ForEach {Add-SPOUser -Site $ \_ .Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**)。</span><span class="sxs-lookup"><span data-stu-id="22e66-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="22e66-223">PowerShell for Microsoft 365データのフィルター処理に最適</span><span class="sxs-lookup"><span data-stu-id="22e66-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="22e66-224">管理Microsoft 365には、データをフィルター処理して、対象となる情報のサブセットを簡単に見つけ出す方法がいくつか提供されています。</span><span class="sxs-lookup"><span data-stu-id="22e66-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="22e66-225">たとえば、Exchange では、ユーザー メールボックスのほとんどすべてのプロパティに対するフィルターを簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="22e66-226">たとえば、ブルーミントン市に住んでいるすべてのユーザーのメールボックスの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![ブルームトン市に住んでいるすべてのユーザー Microsoft 365メールボックスの一覧を管理センターで高度な検索を行う例。](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="22e66-228&quot;>Exchange 管理センターでは、フィルター条件を組み合わせることもできます。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22e66-228&quot;>The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id=&quot;22e66-229&quot;>たとえば、ブルーミントンに住み、財務部門で働いているすべてのユーザーのメールボックスを見つけるとします。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22e66-229&quot;>For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id=&quot;22e66-230&quot;>ただし、管理センターで実行できる操作にはExchangeがあります。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22e66-230&quot;>But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id=&quot;22e66-231&quot;>たとえば、ブルーミントンやサン ディエゴに住むユーザーのメールボックスや、ブルーミントンに住んでいないすべてのユーザーのメールボックスを簡単に見つけられなかったとします。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22e66-231&quot;>For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id=&quot;22e66-232&quot;>次の PowerShell を使用して、Microsoft 365またはサンディエゴに住んでいるすべてのユーザーのメールボックスの一覧を取得できます。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22e66-232&quot;>You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq &quot;UserMailbox&quot; -and ($_.City -eq &quot;San Diego&quot; -or $_.City -eq &quot;Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="22e66-233">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="22e66-234">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプションで、サンディエゴまたはブルーミントン市にメールボックスを持つすべてのユーザーを取得します **(Where {$ \_ .RecipientTypeDetails -eq "UserMailbox" -and ($ \_ .City -eq "San Diego" -or $ \_ .City -eq "Bloomington")}**) をクリックし、それぞれの名前と都市を表示します **([DisplayName, City] を選択します**)。</span><span class="sxs-lookup"><span data-stu-id="22e66-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="22e66-235">次に、ブルームトン以外の場所に住むユーザーのすべてのメールボックスを一覧表示するコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="22e66-236">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-236">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

<span data-ttu-id="22e66-237">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得し、メールボックスがブルーミントン市にはない ( Where **{$ \_ .RecipientTypeDetails -eq "UserMailbox" -and $ \_ .City -ne "Bloomington"} )** をクリックし、それぞれの名前と都市を表示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="22e66-238">ワイルドカードを使用する</span><span class="sxs-lookup"><span data-stu-id="22e66-238">Use wildcards</span></span>

<span data-ttu-id="22e66-239">PowerShell フィルターでワイルドカード文字を使用して、名前の一部と一致することもできます。</span><span class="sxs-lookup"><span data-stu-id="22e66-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="22e66-240">たとえば、ユーザー アカウントを探しているとします。</span><span class="sxs-lookup"><span data-stu-id="22e66-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="22e66-241">覚えているのは、ユーザーの名が *Anderson* または *Henderson* または *Jorgenson である場合です*。</span><span class="sxs-lookup"><span data-stu-id="22e66-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="22e66-242">検索ツールを使用して 3 つの異なるMicrosoft 365を実行することで、管理センターのユーザーを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="22e66-243">*Anderson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="22e66-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="22e66-244">*Henderson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="22e66-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="22e66-245">*Jorgenson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="22e66-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="22e66-246">これらの 3 つの名前はすべて "son" で終わるので、名前が "son" で終わるすべてのユーザーを表示する PowerShell に伝えられます。</span><span class="sxs-lookup"><span data-stu-id="22e66-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="22e66-247">コマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="22e66-248">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得しますが、姓が "son" で終わるユーザーのみを一覧表示するフィルターを使用します **(-Filter '{LastName -like " \* son"})。**</span><span class="sxs-lookup"><span data-stu-id="22e66-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="22e66-249">この \* 略は、ユーザーの名字の文字である任意の文字セットを表します。</span><span class="sxs-lookup"><span data-stu-id="22e66-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="22e66-250">PowerShell for Microsoft 365を使用すると、データの印刷や保存が容易になります</span><span class="sxs-lookup"><span data-stu-id="22e66-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="22e66-251">管理Microsoft 365を使用すると、データの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="22e66-252">オンライン管理センターでオンラインを有効Skype for Businessユーザーの一覧を表示する例を次にSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="22e66-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Skype for Business Online 管理センターで、Skype for Business Online に対して有効になっているユーザーの一覧を表示する例です。](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="22e66-254">その情報をファイルに保存するには、ドキュメントまたはワークシートに貼りMicrosoft Excel必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="22e66-255">どちらの場合も、追加の書式設定が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22e66-255">Either case might require additional formatting.</span></span> <span data-ttu-id="22e66-256">また、管理センター Microsoft 365、表示されるリストを直接印刷する方法は提供されません。</span><span class="sxs-lookup"><span data-stu-id="22e66-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="22e66-257">幸いなことに、PowerShell を使用すると、リストを表示するだけでなく、そのリストをファイルに簡単にインポートできるファイルに保存Excel。</span><span class="sxs-lookup"><span data-stu-id="22e66-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="22e66-258">次に、Skype for Business Online ユーザー データをコンマ区切り値 (CSV) ファイルに保存するコマンドの例を示します。このコマンドは、ワークシート内のテーブルExcelできます。</span><span class="sxs-lookup"><span data-stu-id="22e66-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="22e66-259">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-259">Here's an example of the results:</span></span>
  
![コンマ区切り値ファイルに保存Excelオンライン ユーザー データSkype for Businessワークシートにインポートされたテーブルの例。](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="22e66-261">この PowerShell コマンドの解釈は、現在のサブスクリプション **(Get-CsOnlineUser)** Skype for Business Online ユーザー全員を取得Microsoft 365です。ユーザー名、UPN、および場所のみを取得します **(DisplayName、UserPrincipalName、UsageLocation を選択)。** その情報を C: \\ LogsSfBUsers.csv ( \\ **Export-Csv -Path "C: Logs \\ \\SfBUsers.csv" -NoTypeInformation)** という名前の CSV ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="22e66-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="22e66-262">オプションを使用して、このリストを XML ファイルまたは HTML ページとして保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="22e66-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="22e66-263">実際、追加の PowerShell コマンドを使用すると、必要なカスタム書式を使用して、Excelファイルとして直接保存できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="22e66-264">また、リストを表示する PowerShell コマンドの出力を、既定のプリンターに直接送信Windows。</span><span class="sxs-lookup"><span data-stu-id="22e66-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="22e66-265">コマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="22e66-266">印刷されたドキュメントは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="22e66-266">Here's what your printed document will look like:</span></span>
  
![PowerShell コマンドの出力である印刷済みドキュメントの例は、既定のプリンターに直接送信Windows。](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="22e66-268">この PowerShell コマンドの解釈は、現在のサブスクリプションSkype for Businessオンライン ユーザー全員を取得Microsoft 365です。ユーザー名、UPN、および場所のみを取得します。その情報を既定のプリンター (Windowsプリンター)**に送信します**。</span><span class="sxs-lookup"><span data-stu-id="22e66-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="22e66-269">印刷されたドキュメントの書式は、PowerShell コマンド ウィンドウの表示と同じ単純な書式です。</span><span class="sxs-lookup"><span data-stu-id="22e66-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="22e66-270">ハード コピーを取得するには、ファイルを追加 **|コマンドの最後** にプリンターを出力します。</span><span class="sxs-lookup"><span data-stu-id="22e66-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="22e66-271">PowerShell for Microsoft 365サーバー製品間で管理できます</span><span class="sxs-lookup"><span data-stu-id="22e66-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="22e66-272">これらのコンポーネントを構成するMicrosoft 365は、一緒に動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="22e66-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="22e66-273">たとえば、ユーザーに新しいユーザーをMicrosoft 365、ユーザーの部署や電話番号などの情報を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="22e66-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="22e66-274">この情報は、Microsoft 365 サービス (Skype for Business Online、Exchange、または SharePoint) でユーザーの情報にアクセスした場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="22e66-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="22e66-275">ただし、これは製品のスイートに共通する一般情報の場合です。</span><span class="sxs-lookup"><span data-stu-id="22e66-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="22e66-276">ユーザーのメールボックスに関する情報などの製品固有のExchangeは、通常、スイート全体では使用できません。</span><span class="sxs-lookup"><span data-stu-id="22e66-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="22e66-277">たとえば、ユーザーのメールボックスが有効になっているかどうかに関する情報は、管理者センターでのみExchangeできます。</span><span class="sxs-lookup"><span data-stu-id="22e66-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="22e66-278">すべてのユーザーに関する次のような情報を示すレポートを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="22e66-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="22e66-279">ユーザーの表示名</span><span class="sxs-lookup"><span data-stu-id="22e66-279">The user's display name</span></span>
    
- <span data-ttu-id="22e66-280">ユーザーがユーザーのライセンスを取得Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22e66-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="22e66-281">ユーザーの Exchange メールボックスが有効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="22e66-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="22e66-282">ユーザーが Skype for Business Online に対して有効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="22e66-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="22e66-283">管理センターでこのようなレポートを簡単Microsoft 365作成できない。</span><span class="sxs-lookup"><span data-stu-id="22e66-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="22e66-284">代わりに、別のドキュメントを作成して、ワークシートなどの情報を保存Excelがあります。</span><span class="sxs-lookup"><span data-stu-id="22e66-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="22e66-285">次に、Microsoft 365 管理センターからすべてのユーザー名とライセンス情報を取得し、Exchange 管理センターからメールボックス情報を取得し、Skype for Business Online 管理センターから Skype for Business Online 情報を取得し、その情報を組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="22e66-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="22e66-286">もう 1 つの方法は、PowerShell スクリプトを使用してレポートをコンパイルする方法です。</span><span class="sxs-lookup"><span data-stu-id="22e66-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="22e66-287">次のスクリプト例は、この記事でこれまでに見たコマンドよりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="22e66-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="22e66-288">ただし、PowerShell を使用して、それ以外の場合は取得が困難な情報ビューを作成する可能性を示しています。</span><span class="sxs-lookup"><span data-stu-id="22e66-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="22e66-289">必要なリストをコンパイルして表示するスクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-289">Here's the script to compile and display the list you need:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="22e66-290">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e66-290">Here's an example of the results:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="22e66-291">この PowerShell スクリプトの解釈は次の場合です。</span><span class="sxs-lookup"><span data-stu-id="22e66-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="22e66-292">現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得し、$x *(* $x **= Get-AzureADUser)** という名前の変数に情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="22e66-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="22e66-293">変数 $x **(foreach ($i)** 内のすべてのユーザーを$iループを$xします。</span><span class="sxs-lookup"><span data-stu-id="22e66-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="22e66-294">$y という *名前* の変数を定義し、その中にユーザーのメールボックス情報を格納します **($y = Get-Mailbox-Identity $i.UserPrincipalName)。**</span><span class="sxs-lookup"><span data-stu-id="22e66-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="22e66-295">*IsMailBoxEnabled* という名前のユーザー情報に新しいプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="22e66-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="22e66-296">ユーザーのメールボックスの IsMailBoxEnabled プロパティ **($i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled)** の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="22e66-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="22e66-297">*$y という名前* の変数を定義し、ユーザーの Skype for Business Online 情報をその中に格納します **($y = Get-CsOnlineUser -Identity $i.UserPrincipalName)。**</span><span class="sxs-lookup"><span data-stu-id="22e66-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="22e66-298">EnabledForSfB という名前のユーザー情報に新しい *プロパティを追加します*。</span><span class="sxs-lookup"><span data-stu-id="22e66-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="22e66-299">ユーザーの Skype for Business Online 情報 **($i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled)** の Enabled プロパティの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="22e66-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="22e66-300">ユーザーの一覧を表示しますが、名前、ライセンスを取得するかどうか、およびメールボックスが有効になっているかどうか、およびユーザーが Skype for Business Online ( $x | で有効になっているかどうかを示す 2 つの新しいプロパティのみを **含$x |[DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="22e66-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="22e66-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="22e66-301">See also</span></span>

[<span data-ttu-id="22e66-302">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="22e66-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="22e66-303">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="22e66-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="22e66-304">Windows PowerShell を使用して Microsoft 365 でレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="22e66-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)