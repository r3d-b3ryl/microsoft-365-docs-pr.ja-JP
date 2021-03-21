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
description: '概要: PowerShell を使用して Microsoft 365 を管理する必要がある理由を理解します。場合によっては、より効率的に、必要に応じて他の場合も管理できます。'
ms.openlocfilehash: a60220001a148b3a24a996bb6e0154f80214b019
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924590"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="da709-103">Microsoft 365 で PowerShell を使用する理由</span><span class="sxs-lookup"><span data-stu-id="da709-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="da709-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="da709-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="da709-105">Microsoft 365 管理センターを使用すると、Microsoft 365 のユーザー アカウントとライセンスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="da709-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="da709-106">また、Exchange Online、Teams、SharePoint Online などの Microsoft 365 サービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="da709-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="da709-107">代わりに PowerShell を使用してこれらのサービスを管理する場合は、コマンド ラインとスクリプト言語環境を利用して、速度、自動化、追加機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="da709-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="da709-108">この記事では、PowerShell を使用して Microsoft 365 を管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="da709-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="da709-109">Microsoft 365 管理センターで表示できない追加情報を表示する</span><span class="sxs-lookup"><span data-stu-id="da709-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="da709-110">PowerShell でのみ可能な機能と設定を構成する</span><span class="sxs-lookup"><span data-stu-id="da709-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="da709-111">一括操作を実行する</span><span class="sxs-lookup"><span data-stu-id="da709-111">Do bulk operations</span></span>
    
- <span data-ttu-id="da709-112">データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="da709-112">Filter data</span></span>
    
- <span data-ttu-id="da709-113">データの印刷または保存</span><span class="sxs-lookup"><span data-stu-id="da709-113">Print or save data</span></span>
    
- <span data-ttu-id="da709-114">複数のサービスを管理する</span><span class="sxs-lookup"><span data-stu-id="da709-114">Manage across services</span></span>
    
<span data-ttu-id="da709-115">PowerShell for Microsoft 365 は、windows ベースのサービスとプラットフォームのコマンド ライン環境である Windows PowerShell のモジュールのセットです。</span><span class="sxs-lookup"><span data-stu-id="da709-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="da709-116">この環境では、追加のモジュールで拡張できるコマンド シェル言語を作成します。</span><span class="sxs-lookup"><span data-stu-id="da709-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="da709-117">単純なコマンドまたは複雑なコマンドまたはスクリプトを実行する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="da709-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="da709-118">たとえば、PowerShell for Microsoft 365 モジュールをインストールして Microsoft 365 サブスクリプションに接続した後、次のコマンドを実行して、次のコマンドを実行して、すべてのユーザー メールボックスを一覧表示Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="da709-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="da709-119">また、Microsoft 365 管理センターを使用してメールボックスのリストを取得することもできますが、すべての Web アプリのすべてのサイトのすべてのリストのアイテムを数えるのは簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="da709-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="da709-120">Microsoft 365 用 PowerShell は、Microsoft 365 管理センターを置き換えるのではなく、Microsoft 365 の管理を支援するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="da709-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="da709-121">Microsoft 365 の PowerShell コマンドでのみ実行できる構成手順がいくつかあるため、管理者は Microsoft 365 用の PowerShell を使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="da709-122">このような場合は、次の方法を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="da709-123">PowerShell for Microsoft 365 モジュールをインストールします (管理者コンピューターごとに 1 回だけ実行)。</span><span class="sxs-lookup"><span data-stu-id="da709-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="da709-124">Microsoft 365 サブスクリプションに接続します (PowerShell セッションごとに 1 回)。</span><span class="sxs-lookup"><span data-stu-id="da709-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="da709-125">Microsoft 365 コマンドに必要な PowerShell を実行するために必要な情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="da709-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="da709-126">Microsoft 365 コマンドの PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="da709-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="da709-127">これらの基本的なスキルを習得した後は **、[Get-Mailbox]** コマンドを使用してメールボックス ユーザーを一覧表示する必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="da709-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="da709-128">また、すべての Web アプリのすべてのサイトのすべてのリストのすべての項目をカウントするために、前に引用したコマンドのような新しいコマンドを作成する方法も理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="da709-129">Microsoft と管理者のコミュニティは、必要に応じてこのようなタスクを支援できます。</span><span class="sxs-lookup"><span data-stu-id="da709-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="da709-130">Microsoft 365 用 PowerShell では、Microsoft 365 管理センターでは表示できない情報を表示できます</span><span class="sxs-lookup"><span data-stu-id="da709-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="da709-131">Microsoft 365 管理センターには、多くの有用な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da709-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="da709-132">ただし、Microsoft 365 がユーザー、ライセンス、メールボックス、およびサイトに関して保存する可能性があるすべての情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="da709-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="da709-133">Microsoft 365 管理 *センターのユーザーと* グループの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Microsoft 365 管理センターでのユーザーとグループの表示例。](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="da709-135">このビューは、多くの場合必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="da709-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="da709-136">しかし、もっと多くの情報が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="da709-136">However, there are times when you need more.</span></span> <span data-ttu-id="da709-137">たとえば、Microsoft 365 ライセンス (およびユーザーが利用できる Microsoft 365 の機能) は、ユーザーの地理的な場所によって一部異なります。</span><span class="sxs-lookup"><span data-stu-id="da709-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="da709-138">米国に住むユーザーに拡張できるポリシーと機能は、インドまたはベルギーのユーザーに拡張できるポリシーと機能と同じではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da709-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="da709-139">Microsoft 365 管理センターの次の手順に従って、ユーザーの地理的な場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="da709-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="da709-140">ユーザーの **表示名** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="da709-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="da709-141">ユーザー プロパティの表示ウィンドウで、[詳細] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="da709-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="da709-142">詳細表示で、追加の詳細 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da709-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="da709-143">[国] または [地域] という見出し **が表示されるまでスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="da709-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Microsoft 365 管理センターのユーザーの地域情報の例。](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="da709-145">ユーザーの表示名と場所を紙に書き留めるか、コピーしてメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="da709-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="da709-146">この手順をユーザーごとに繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="da709-147">ユーザーが多い場合、このプロセスは時間のかかっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da709-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="da709-148">PowerShell for Microsoft 365 では、次のコマンドを使用して、すべてのユーザーに対してこの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="da709-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="da709-149">PowerShell Core は、名前に *Msol* が含Windows PowerShellモジュールとコマンドレットの Microsoft Azure Active Directory モジュールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="da709-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="da709-150">これらのコマンドレットは、次の手順で実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="da709-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="da709-151">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="da709-152">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション **(Get-AzureADUser)** のすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示します **([DisplayName, UsageLocation** の選択] )。</span><span class="sxs-lookup"><span data-stu-id="da709-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="da709-153">PowerShell for Microsoft 365 はコマンド シェル言語をサポートしていますので **、Get-AzureADUser** コマンドで取得した情報をさらに操作できます。</span><span class="sxs-lookup"><span data-stu-id="da709-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="da709-154">たとえば、これらのユーザーを場所別に並べ替え、すべてのブラジル人ユーザーをグループ化し、すべての米国ユーザーをまとめてグループ化する場合などです。</span><span class="sxs-lookup"><span data-stu-id="da709-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="da709-155">コマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="da709-156">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="da709-157">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示し、最初にユーザーの場所で並べ替え、次に名前 (Sort **UsageLocation, DisplayName)** を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="da709-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="da709-158">追加のフィルター処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="da709-158">You can also use additional filtering.</span></span> <span data-ttu-id="da709-159">たとえば、ブラジル在住のユーザーに関する情報のみを表示する場合には、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="da709-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="da709-160">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="da709-161">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション内の場所がブラジルであるすべてのユーザーを取得する (**場所 {$ ) です \_ 。UsageLocation -eq "BR"}**) をクリックし、各ユーザーの名前と場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="da709-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="da709-162">**大規模なドメインに関するメモ**</span><span class="sxs-lookup"><span data-stu-id="da709-162">**A note about large domains**</span></span>
  
<span data-ttu-id="da709-163">数万人のユーザーを持つ大規模なドメインがある場合は、この記事で示す例の一部を試してみようとすると、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da709-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="da709-164">計算能力や利用可能なネットワーク帯域幅のような要因に基づいて、一度に実行しすぎようとしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da709-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="da709-165">大規模な組織では、これらの PowerShell 操作の一部を 2 つのコマンドに分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="da709-166">たとえば、次のコマンドは、すべてのユーザー アカウントを返し、それぞれの名前と場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="da709-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="da709-167">このコマンドは、規模が小さいドメインには最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="da709-167">That works great for smaller domains.</span></span> <span data-ttu-id="da709-168">ただし、大規模な組織では、その操作を変数にユーザー アカウント情報を格納するコマンドと、必要な情報を表示する 2 つのコマンドに分割できます。</span><span class="sxs-lookup"><span data-stu-id="da709-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="da709-169">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="da709-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="da709-170">この一連の PowerShell コマンドの解釈は次の場合です。</span><span class="sxs-lookup"><span data-stu-id="da709-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="da709-171">現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得し、$x ( $x **= Get-AzureADUser)** という名前の変数に情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="da709-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="da709-172">変数の内容を表示 *$x、各* ユーザーの名前と **場所のみを含$x |[DisplayName, UsageLocation] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da709-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="da709-173">Microsoft 365 には、PowerShell for Microsoft 365 でのみ構成できる機能があります。</span><span class="sxs-lookup"><span data-stu-id="da709-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="da709-174">Microsoft 365 管理センターは、ほとんどの環境に適用される一般的で有用な管理タスクへのアクセスを提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="da709-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="da709-175">つまり、Microsoft 365 管理センターは、一般的な管理者が最も一般的な管理タスクを実行できるよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="da709-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="da709-176">ただし、管理センターでは実行できないタスクもあります。</span><span class="sxs-lookup"><span data-stu-id="da709-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="da709-177">たとえば、Skype for Business Online 管理センターには、カスタム会議出席依頼を作成するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="da709-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Skype for Business Online 管理センターでカスタムの会議出席依頼を表示する例です。](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="da709-179">これらの設定を使用すると、会議出席依頼にパーソナルでプロフェッショナルな風合いを加えることができます。</span><span class="sxs-lookup"><span data-stu-id="da709-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="da709-180">ただし、会議構成の設定には、単にカスタムの会議出席依頼を作成するよりも多くがあります。</span><span class="sxs-lookup"><span data-stu-id="da709-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="da709-181">たとえば、既定では会議に関して以下の事柄が許可されています。</span><span class="sxs-lookup"><span data-stu-id="da709-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="da709-182">匿名ユーザーが、各会議に自動的に参加すること。</span><span class="sxs-lookup"><span data-stu-id="da709-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="da709-183">参加者が、会議を記録すること。</span><span class="sxs-lookup"><span data-stu-id="da709-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="da709-184">組織のすべてのユーザーが、会議に参加するときに発表者として指定されること。</span><span class="sxs-lookup"><span data-stu-id="da709-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="da709-185">これらの設定は、Skype for Business Online 管理センターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="da709-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="da709-186">PowerShell for Microsoft 365 から制御できます。</span><span class="sxs-lookup"><span data-stu-id="da709-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="da709-187">次の 3 つの設定を無効にするコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="da709-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="da709-188">このコマンドを実行するには [、Skype for Business Online PowerShell モジュールをインストールする必要があります ](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="da709-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="da709-189">この PowerShell コマンドの解釈は次の場合です。</span><span class="sxs-lookup"><span data-stu-id="da709-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="da709-190">新しい Skype for Business Online 会議 **(Set-CsMeetingConfiguration)** の設定で、匿名ユーザーが会議への自動参加を許可することを無効にします **(-AdmitAnonymousUsersByDefault**$False)。</span><span class="sxs-lookup"><span data-stu-id="da709-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="da709-191">出席者が会議を記録する機能を無効にします **(-AllowConferenceRecording**$False)。</span><span class="sxs-lookup"><span data-stu-id="da709-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="da709-192">組織のすべてのユーザーを発表者として指定しない (**-DesignateAsPresenter "None"**)。</span><span class="sxs-lookup"><span data-stu-id="da709-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="da709-193">これらの既定の設定を復元する (オプションを有効にする) には、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da709-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="da709-194">他にも同様のシナリオがあります。そのため、管理者は Microsoft 365 コマンド用に PowerShell を実行する方法を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="da709-195">Microsoft 365 用 PowerShell は一括操作に最適です</span><span class="sxs-lookup"><span data-stu-id="da709-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="da709-196">Microsoft 365 管理センターのようなビジュアル インターフェイスは、単一の操作を行う場合に最も重要です。</span><span class="sxs-lookup"><span data-stu-id="da709-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="da709-197">たとえば、1 つのユーザー アカウントを無効にする必要がある場合は、管理センターを使用して、チェック ボックスをすばやく見つけてクリアできます。</span><span class="sxs-lookup"><span data-stu-id="da709-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="da709-198">これは、PowerShell で同様の操作を実行するよりも簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="da709-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="da709-199">ただし、他の大きなセット内で多くの変更や選択した項目を変更する必要がある場合は、Microsoft 365 管理センターが最適なツールではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da709-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="da709-200">たとえば、数千の電話番号のプレフィックスを変更するか、特定のユーザー *Ken Myer* をすべての SharePoint Online サイトから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="da709-201">Microsoft 365 管理センターでどのように行いますか?</span><span class="sxs-lookup"><span data-stu-id="da709-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="da709-202">最後の例では、SharePoint Online サイトが数百あるとしますが、Ken Meyer がメンバーであるかどうかはわかりません。</span><span class="sxs-lookup"><span data-stu-id="da709-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="da709-203">Microsoft 365 管理センターから開始し、サイトごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="da709-204">サイト **の URL** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da709-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="da709-205">[サイト コレクション **のプロパティ] ボックス** で **、[Web サイト** アドレス] リンクを選択してサイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="da709-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="da709-206">サイトで、[共有] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="da709-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="da709-207">[共有 **] ダイアログ** ボックスで、サイトへのアクセス許可を持つすべてのユーザーを表示するリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="da709-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![SharePoint Online 管理センターの SharePoint Online サイトのメンバーを表示する例です。](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="da709-209">[共有する **ユーザー] ダイアログ ボックス** で、[詳細設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="da709-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="da709-210">ユーザーの一覧を下にスクロールし、Ken Myer (サイトへのアクセス許可がある場合) を見つけて選択し、[ユーザーのアクセス許可の削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da709-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="da709-211">これは、数百 *のサイト* には長い時間がかかるでしょう。</span><span class="sxs-lookup"><span data-stu-id="da709-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="da709-212">代わりに、Microsoft 365 用 PowerShell で次のコマンドを実行して、すべてのサイトから Ken Myer を削除します。</span><span class="sxs-lookup"><span data-stu-id="da709-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="da709-213">このコマンドでは [、SharePoint Online PowerShell モジュールをインストールする必要があります](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="da709-213">This command requires that you install the [SharePoint Online PowerShell module](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="da709-214">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション **(Get-SPOSite)** 内のすべての SharePoint サイトを取得し、各サイトでアクセスできるユーザーのリストから Ken Meyer を削除することです **(ForEach {Remove-SPOUser -Site $ . \_Url -LoginName "kenmyer \@ litwareinc.com"}**)。</span><span class="sxs-lookup"><span data-stu-id="da709-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="da709-215">Microsoft 365 には、アクセス権を持たなかったものも含め、すべてのサイトから Ken Meyer を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="da709-216">そのため、アクセスできないサイトのエラーが結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="da709-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="da709-217">このコマンドで追加の条件を使用して、Ken Meyer をログイン リストに登録しているサイトからのみ削除できます。</span><span class="sxs-lookup"><span data-stu-id="da709-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="da709-218">しかし、返されるエラーは、サイト自体に害を及ぼしません。</span><span class="sxs-lookup"><span data-stu-id="da709-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="da709-219">このコマンドは、Microsoft 365 管理センターでの作業時間ではなく、数百のサイトに対して実行するために数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da709-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="da709-220">別の一括操作の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-220">Here's another bulk operation example.</span></span> <span data-ttu-id="da709-221">このコマンドを使用して *、新しい* SharePoint 管理者であるボニー カーニーを組織内のすべてのサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="da709-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="da709-222">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション内のすべての SharePoint サイトを取得し、各サイトで、サイトのメンバー グループにログイン名を追加することで、ボニー カーニー アクセスを許可します **(ForEach {Add-SPOUser -Site $ \_ .Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**)。</span><span class="sxs-lookup"><span data-stu-id="da709-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="da709-223">Microsoft 365 用の PowerShell は、データのフィルター処理に最適です</span><span class="sxs-lookup"><span data-stu-id="da709-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="da709-224">Microsoft 365 管理センターには、データをフィルター処理して、対象となる情報のサブセットを簡単に見つけ出す方法がいくつか提供されています。</span><span class="sxs-lookup"><span data-stu-id="da709-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="da709-225">たとえば、Exchange では、ユーザー メールボックスのほとんどすべてのプロパティに対するフィルターを簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="da709-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="da709-226">たとえば、ブルーミントン市に住んでいるすべてのユーザーのメールボックスの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![ブルームトン市に住むすべてのユーザーのメールボックスの一覧を Microsoft 365 管理センターで高度な検索を行う例。](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="da709-228">Exchange 管理センターでは、フィルター条件を組み合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="da709-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="da709-229">たとえば、ブルーミントンに住み、財務部門で働いているすべてのユーザーのメールボックスを見つけるとします。</span><span class="sxs-lookup"><span data-stu-id="da709-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="da709-230">ただし、Exchange 管理センターで実行できる操作には制限があります。</span><span class="sxs-lookup"><span data-stu-id="da709-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="da709-231">たとえば、ブルーミントンやサン ディエゴに住むユーザーのメールボックスや、ブルーミントンに住んでいないすべてのユーザーのメールボックスを簡単に見つけられなかったとします。</span><span class="sxs-lookup"><span data-stu-id="da709-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="da709-232">次の PowerShell for Microsoft 365 コマンドを使用して、ブルーミントンまたはサン ディエゴに住むすべてのユーザーのメールボックスの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="da709-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="da709-233">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="da709-234">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプションで、サンディエゴまたはブルーミントン市にメールボックスを持つすべてのユーザーを取得します (**ここで {$ \_ .RecipientTypeDetails -eq "UserMailbox" -and ($ \_ .City -eq "San Diego" -or $ \_ .City -eq "Bloomington")}**) をクリックし、それぞれの名前と都市を表示します **([DisplayName, City] を選択します**)。</span><span class="sxs-lookup"><span data-stu-id="da709-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="da709-235">次に、ブルームトン以外の場所に住むユーザーのすべてのメールボックスを一覧表示するコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="da709-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="da709-236">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="da709-237">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得し、メールボックスがブルーミントン市にはない **(Where {$ \_ .RecipientTypeDetails -eq "UserMailbox" -and $ \_ .City -ne "Bloomington"} )** をクリックし、それぞれの名前と都市を表示します。</span><span class="sxs-lookup"><span data-stu-id="da709-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="da709-238">ワイルドカードを使用する</span><span class="sxs-lookup"><span data-stu-id="da709-238">Use wildcards</span></span>

<span data-ttu-id="da709-239">PowerShell フィルターでワイルドカード文字を使用して、名前の一部と一致することもできます。</span><span class="sxs-lookup"><span data-stu-id="da709-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="da709-240">たとえば、ユーザー アカウントを探しているとします。</span><span class="sxs-lookup"><span data-stu-id="da709-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="da709-241">覚えているのは、ユーザーの名が *Anderson* または *Henderson* または *Jorgenson である場合です*。</span><span class="sxs-lookup"><span data-stu-id="da709-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="da709-242">検索ツールを使用して 3 つの異なる検索を実行することで、Microsoft 365 管理センターのユーザーを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="da709-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="da709-243">*Anderson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="da709-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="da709-244">*Henderson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="da709-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="da709-245">*Jorgenson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="da709-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="da709-246">これらの 3 つの名前はすべて "son" で終わるので、名前が "son" で終わるすべてのユーザーを表示する PowerShell に伝えられます。</span><span class="sxs-lookup"><span data-stu-id="da709-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="da709-247">コマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="da709-248">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得しますが、姓が "son" で終わるユーザーのみを一覧表示するフィルターを使用します **(-Filter '{LastName -like " \* son"})。**</span><span class="sxs-lookup"><span data-stu-id="da709-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="da709-249">この \* 略は、ユーザーの名字の文字である任意の文字セットを表します。</span><span class="sxs-lookup"><span data-stu-id="da709-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="da709-250">Microsoft 365 用 PowerShell を使用すると、データの印刷や保存が容易になります</span><span class="sxs-lookup"><span data-stu-id="da709-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="da709-251">Microsoft 365 管理センターでは、データの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="da709-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="da709-252">Skype for Business Online が有効になっているユーザーの一覧を表示する Skype for Business Online 管理センターの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Skype for Business Online 管理センターで、Skype for Business Online に対して有効になっているユーザーの一覧を表示する例です。](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="da709-254">その情報をファイルに保存するには、ドキュメントまたは Microsoft Excel ワークシートに貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="da709-255">どちらの場合も、追加の書式設定が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da709-255">Either case might require additional formatting.</span></span> <span data-ttu-id="da709-256">さらに、Microsoft 365 管理センターでは、表示されるリストを直接印刷する方法は提供されません。</span><span class="sxs-lookup"><span data-stu-id="da709-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="da709-257">幸いなことに、PowerShell を使用すると、リストを表示するだけでなく、Excel に簡単にインポートできるファイルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="da709-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="da709-258">次に、Skype for Business Online ユーザー データをコンマ区切り値 (CSV) ファイルに保存するコマンドの例を示します。次に、Excel ワークシートのテーブルとして簡単にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="da709-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="da709-259">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-259">Here's an example of the results:</span></span>
  
![コンマ区切り値ファイルに保存された Skype for Business Online ユーザー データの Excel ワークシートにインポートされたテーブルの例。](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="da709-261">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション **(Get-CsOnlineUser)** のすべての Skype for Business Online ユーザーを取得する方法です。ユーザー名、UPN、および場所のみを取得します **(DisplayName、UserPrincipalName、UsageLocation を選択)。** その情報を C: \\ LogsSfBUsers.csv ( \\ **Export-Csv -Path "C: Logs \\ \\SfBUsers.csv" -NoTypeInformation)** という名前の CSV ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="da709-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="da709-262">オプションを使用して、このリストを XML ファイルまたは HTML ページとして保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="da709-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="da709-263">実際、PowerShell コマンドを追加すると、必要なカスタム書式を使用して、Excel ファイルとして直接保存できます。</span><span class="sxs-lookup"><span data-stu-id="da709-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="da709-264">リストを表示する PowerShell コマンドの出力を Windows の既定のプリンターに直接送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="da709-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="da709-265">コマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="da709-266">印刷されたドキュメントは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da709-266">Here's what your printed document will look like:</span></span>
  
![Windows の既定のプリンターに直接送信される PowerShell コマンドの出力である印刷されたドキュメントの例。](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="da709-268">この PowerShell コマンドの解釈は、現在の Microsoft 365 サブスクリプション内のすべての Skype for Business Online ユーザーを取得する方法です。ユーザー名、UPN、および場所のみを取得します。その情報を既定の Windows プリンター (出力プリンター)**に送信します**。</span><span class="sxs-lookup"><span data-stu-id="da709-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="da709-269">印刷されたドキュメントの書式は、PowerShell コマンド ウィンドウの表示と同じ単純な書式です。</span><span class="sxs-lookup"><span data-stu-id="da709-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="da709-270">ハード コピーを取得するには、ファイルを追加 **|コマンドの最後** にプリンターを出力します。</span><span class="sxs-lookup"><span data-stu-id="da709-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="da709-271">PowerShell for Microsoft 365 を使用すると、サーバー製品全体を管理できます</span><span class="sxs-lookup"><span data-stu-id="da709-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="da709-272">Microsoft 365 を構成するコンポーネントは、一緒に動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="da709-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="da709-273">たとえば、Microsoft 365 に新しいユーザーを追加し、ユーザーの部署や電話番号などの情報を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="da709-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="da709-274">この情報は、Microsoft 365 サービス (Skype for Business Online、Exchange、または SharePoint) でユーザーの情報にアクセスした場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="da709-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="da709-275">ただし、これは製品のスイートに共通する一般情報の場合です。</span><span class="sxs-lookup"><span data-stu-id="da709-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="da709-276">製品固有の情報 (ユーザーの Exchange メールボックスに関する情報など) は、通常、スイート全体で利用できません。</span><span class="sxs-lookup"><span data-stu-id="da709-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="da709-277">たとえば、ユーザーのメールボックスが有効になっているかどうかに関する情報は、Exchange 管理センターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="da709-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="da709-278">すべてのユーザーに関する次のような情報を示すレポートを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="da709-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="da709-279">ユーザーの表示名</span><span class="sxs-lookup"><span data-stu-id="da709-279">The user's display name</span></span>
    
- <span data-ttu-id="da709-280">ユーザーが Microsoft 365 のライセンスを取得するかどうか</span><span class="sxs-lookup"><span data-stu-id="da709-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="da709-281">ユーザーの Exchange メールボックスが有効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="da709-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="da709-282">ユーザーが Skype for Business Online に対して有効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="da709-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="da709-283">このようなレポートは、Microsoft 365 管理センターでは簡単に作成できない。</span><span class="sxs-lookup"><span data-stu-id="da709-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="da709-284">代わりに、Excel ワークシートなどの情報を格納するために別のドキュメントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da709-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="da709-285">次に、Microsoft 365 管理センターからすべてのユーザー名とライセンス情報を取得し、Exchange 管理センターからメールボックス情報を取得し、Skype for Business Online 管理センターから Skype for Business Online 情報を取得し、その情報を組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="da709-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="da709-286">もう 1 つの方法は、PowerShell スクリプトを使用してレポートをコンパイルする方法です。</span><span class="sxs-lookup"><span data-stu-id="da709-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="da709-287">次のスクリプト例は、この記事でこれまでに見たコマンドよりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="da709-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="da709-288">ただし、PowerShell を使用して、それ以外の場合は取得が困難な情報ビューを作成する可能性を示しています。</span><span class="sxs-lookup"><span data-stu-id="da709-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="da709-289">必要なリストをコンパイルして表示するスクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="da709-290">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da709-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="da709-291">この PowerShell スクリプトの解釈は次の場合です。</span><span class="sxs-lookup"><span data-stu-id="da709-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="da709-292">現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得し、$x *(* $x **= Get-AzureADUser)** という名前の変数に情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="da709-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="da709-293">変数 $x **(foreach ($i)** 内のすべてのユーザーを$iループを$xします。</span><span class="sxs-lookup"><span data-stu-id="da709-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="da709-294">$y という *名前* の変数を定義し、その中にユーザーのメールボックス情報を格納します **($y = Get-Mailbox-Identity $i.UserPrincipalName)。**</span><span class="sxs-lookup"><span data-stu-id="da709-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="da709-295">*IsMailBoxEnabled* という名前のユーザー情報に新しいプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="da709-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="da709-296">ユーザーのメールボックスの IsMailBoxEnabled プロパティ **($i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled)** の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="da709-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="da709-297">*$y という* 名前の変数を定義し、ユーザーの Skype for Business Online 情報をその中に格納します **($y = Get-CsOnlineUser -Identity $i.UserPrincipalName)。**</span><span class="sxs-lookup"><span data-stu-id="da709-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="da709-298">EnabledForSfB という名前のユーザー情報に新しい *プロパティを追加します*。</span><span class="sxs-lookup"><span data-stu-id="da709-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="da709-299">ユーザーの Skype for Business Online 情報 **($i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled)** の Enabled プロパティの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="da709-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="da709-300">ユーザーの一覧を表示しますが、名前、ライセンスを取得するかどうか、およびメールボックスが有効になっているかどうか、および Skype for Business Online ($x |) でメールボックスが有効になっているかどうかを示す 2 つの新しいプロパティ **のみを含$x |[DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da709-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da709-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="da709-301">See also</span></span>

[<span data-ttu-id="da709-302">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="da709-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da709-303">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="da709-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da709-304">Windows PowerShell を使用して Microsoft 365 でレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="da709-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)