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
description: '概要: PowerShell を使用して Microsoft 365 を管理する必要がある理由について説明します。場合によっては効率的で、その他の場合は必要になることがあります。'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754108"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="74438-103">Microsoft 365 で PowerShell を使用する理由</span><span class="sxs-lookup"><span data-stu-id="74438-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="74438-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="74438-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="74438-105">Microsoft 365 管理センターを使用すると、Microsoft 365 のユーザーアカウントとライセンスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="74438-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="74438-106">また、Exchange Online、Teams、SharePoint Online などの Microsoft 365 サービスを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="74438-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="74438-107">PowerShell を使用してこれらのサービスを管理する場合は、速度、自動化、およびその他の機能を実現するために、コマンドラインおよびスクリプト言語環境を利用できます。</span><span class="sxs-lookup"><span data-stu-id="74438-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="74438-108">この記事では、PowerShell を使用して Microsoft 365 を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="74438-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="74438-109">Microsoft 365 管理センターでは表示できない追加情報を確認する</span><span class="sxs-lookup"><span data-stu-id="74438-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="74438-110">PowerShell でのみ使用可能な機能と設定を構成する</span><span class="sxs-lookup"><span data-stu-id="74438-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="74438-111">一括操作を実行する</span><span class="sxs-lookup"><span data-stu-id="74438-111">Do bulk operations</span></span>
    
- <span data-ttu-id="74438-112">データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="74438-112">Filter data</span></span>
    
- <span data-ttu-id="74438-113">データを印刷または保存する</span><span class="sxs-lookup"><span data-stu-id="74438-113">Print or save data</span></span>
    
- <span data-ttu-id="74438-114">サービス間で管理する</span><span class="sxs-lookup"><span data-stu-id="74438-114">Manage across services</span></span>
    
<span data-ttu-id="74438-115">Microsoft 365 の PowerShell は、windows PowerShell 用のモジュールのセットであることに注意してください。これは、Windows ベースのサービスとプラットフォームのコマンドライン環境です。</span><span class="sxs-lookup"><span data-stu-id="74438-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="74438-116">この環境では、追加のモジュールで拡張できるコマンドシェル言語が作成されます。</span><span class="sxs-lookup"><span data-stu-id="74438-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="74438-117">これにより、単純なまたは複雑なコマンドまたはスクリプトを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="74438-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="74438-118">たとえば、microsoft 365 モジュールの PowerShell をインストールし、Microsoft 365 サブスクリプションに接続した後、次のコマンドを実行して Microsoft Exchange Online のすべてのユーザーメールボックスを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="74438-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="74438-119">また、Microsoft 365 管理センターを使用してメールボックスの一覧を取得することもできますが、すべての web アプリケーションのすべてのサイトについて、すべてのリストのアイテムをカウントするのは簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="74438-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="74438-120">Microsoft 365 用の PowerShell は、microsoft 365 を管理することを支援するように設計されています。 microsoft 365 管理センターを置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="74438-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="74438-121">Microsoft 365 コマンドの PowerShell でしか実行できない構成手順があるため、管理者は Microsoft 365 の PowerShell を使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="74438-122">このような場合は、次の方法を知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="74438-123">Microsoft 365 モジュールの PowerShell をインストールします (管理者のコンピューターごとに1回のみ行われます)。</span><span class="sxs-lookup"><span data-stu-id="74438-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="74438-124">Microsoft 365 サブスクリプション (PowerShell セッションごとに1回) に接続します。</span><span class="sxs-lookup"><span data-stu-id="74438-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="74438-125">Microsoft 365 コマンドに必要な PowerShell を実行するために必要な情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="74438-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="74438-126">Microsoft 365 コマンドの PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="74438-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="74438-127">これらの基本的なスキルを習得した後は、メールボックスユーザーを **取得** するために、メールボックスのコマンドを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="74438-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="74438-128">また、以前に説明したコマンドを使用して、すべての web アプリのすべてのサイトのすべてのリスト内のすべてのアイテムをカウントする方法について理解する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="74438-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="74438-129">Microsoft と管理者コミュニティは、必要に応じてこれらのタスクを支援します。</span><span class="sxs-lookup"><span data-stu-id="74438-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="74438-130">Microsoft 365 用の PowerShell は、Microsoft 365 管理センターでは表示できない情報を公開することができます</span><span class="sxs-lookup"><span data-stu-id="74438-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="74438-131">Microsoft 365 管理センターには、さまざまな役に立つ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74438-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="74438-132">しかし、Microsoft 365 でユーザー、ライセンス、メールボックス、サイトに関して保存される可能性のある情報がすべて表示されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="74438-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="74438-133">Microsoft 365 管理センターの *ユーザーとグループ* の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Microsoft 365 管理センターでのユーザーとグループの表示例。](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="74438-135">このビューでは、多くの場合に必要な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="74438-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="74438-136">しかし、もっと多くの情報が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="74438-136">However, there are times when you need more.</span></span> <span data-ttu-id="74438-137">たとえば、Microsoft 365 ライセンス (およびユーザーが使用できる Microsoft 365 機能) は、ユーザーの地理的な場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="74438-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="74438-138">米国に住んでいるユーザーに拡張できるポリシーと機能は、インドまたはベルギーでユーザーに拡張できるものとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="74438-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="74438-139">Microsoft 365 管理センターで、次の手順を実行して、ユーザーの地理的な場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="74438-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="74438-140">ユーザーの **表示名** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="74438-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="74438-141">ユーザープロパティの表示ウィンドウで、[ **詳細**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74438-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="74438-142">詳細表示で、[ **追加の詳細**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74438-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="74438-143">見出しの **国または地域**が見つかるまでスクロールします。</span><span class="sxs-lookup"><span data-stu-id="74438-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Microsoft 365 管理センター内のユーザーの地域情報の例。](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="74438-145">ユーザーの表示名と場所を紙に書き留めるか、コピーしてメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="74438-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="74438-146">この手順をユーザーごとに繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="74438-147">ユーザー数が多い場合、このプロセスは退屈になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74438-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="74438-148">Microsoft 365 の PowerShell では、次のコマンドを使用して、すべてのユーザーについてこの情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="74438-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="74438-149">PowerShell Core は、Windows PowerShell モジュールの Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="74438-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="74438-150">これらのコマンドレットは、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="74438-151">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="74438-152">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプション (**set-azureaduser**) 内のすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示します (**DisplayName、使用場所の選択**)。</span><span class="sxs-lookup"><span data-stu-id="74438-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="74438-153">Microsoft 365 用の PowerShell はコマンドシェル言語をサポートしているため、 **set-azureaduser** コマンドで取得した情報をさらに操作することができます。</span><span class="sxs-lookup"><span data-stu-id="74438-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="74438-154">たとえば、これらのユーザーを場所によって並べ替えたり、すべてのブラジルユーザーを一緒にグループ化したり、すべての米国ユーザーを一緒にグループ化したりしたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="74438-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="74438-155">コマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74438-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="74438-156">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="74438-157">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプション内のすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示し、それらの場所とその名前 (**並べ替えでは、DisplayName**) を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="74438-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="74438-158">追加のフィルター処理を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="74438-158">You can also use additional filtering.</span></span> <span data-ttu-id="74438-159">たとえば、ブラジル在住のユーザーに関する情報のみを表示する場合には、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="74438-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="74438-160">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="74438-161">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションで、場所がブラジルであるすべてのユーザーを取得します (**Where {$ \_ .使用場所-eq "BR"}**) を選択して、各ユーザーの名前と場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="74438-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="74438-162">**大規模なドメインに関する注意事項**</span><span class="sxs-lookup"><span data-stu-id="74438-162">**A note about large domains**</span></span>
  
<span data-ttu-id="74438-163">多数のユーザーが含まれる大きなドメインがある場合、この記事に示されている例のいくつかを試してみると調整につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74438-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="74438-164">コンピューティングパワーや使用可能なネットワーク帯域幅などの要因に基づいて、一度に多くの操作を実行しようとしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74438-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="74438-165">大規模な組織では、これらの PowerShell 操作の一部を2つのコマンドに分割する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="74438-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="74438-166">たとえば、次のコマンドを実行すると、すべてのユーザーアカウントが返され、それぞれの名前と場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74438-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="74438-167">このコマンドは、規模が小さいドメインには最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="74438-167">That works great for smaller domains.</span></span> <span data-ttu-id="74438-168">しかし、大規模な組織では、この操作を2つのコマンドに分割する必要があります。1つは、ユーザーアカウント情報を変数に格納し、もう1つのコマンドを使用して必要な情報を表示することです。</span><span class="sxs-lookup"><span data-stu-id="74438-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="74438-169">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="74438-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="74438-170">この PowerShell コマンドのセットは次のように解釈されます。</span><span class="sxs-lookup"><span data-stu-id="74438-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="74438-171">現在の Microsoft 365 サブスクリプション内のすべてのユーザーを取得し、その情報を $x (**$x = set-azureaduser**) という名前の変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="74438-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="74438-172">変数 *$x*の内容を表示します。ただし、各ユーザーの名前と場所のみが含まれます (**$x |DisplayName、[その他] の場所) を選択**します。</span><span class="sxs-lookup"><span data-stu-id="74438-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="74438-173">Microsoft 365 には、Microsoft 365 の PowerShell でのみ構成できる機能があります。</span><span class="sxs-lookup"><span data-stu-id="74438-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="74438-174">Microsoft 365 管理センターは、ほとんどの環境に適用される一般的で便利な管理タスクへのアクセスを提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="74438-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="74438-175">つまり、Microsoft 365 管理センターは、一般的な管理者が最も一般的な管理タスクを実行できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="74438-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="74438-176">ただし、管理センターでは実行できないタスクがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="74438-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="74438-177">たとえば、Skype for Business Online 管理センターには、カスタムの会議出席依頼を作成するためのオプションがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="74438-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Skype for Business Online 管理センターでカスタムの会議出席依頼を表示する例です。](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="74438-179">これらの設定を使用すると、会議出席依頼にパーソナルでプロフェッショナルな風合いを加えることができます。</span><span class="sxs-lookup"><span data-stu-id="74438-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="74438-180">ただし、会議構成設定には、カスタムの会議出席依頼を作成するだけでなく、さらに多くのことがあります。</span><span class="sxs-lookup"><span data-stu-id="74438-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="74438-181">たとえば、既定では会議に関して以下の事柄が許可されています。</span><span class="sxs-lookup"><span data-stu-id="74438-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="74438-182">匿名ユーザーが、各会議に自動的に参加すること。</span><span class="sxs-lookup"><span data-stu-id="74438-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="74438-183">参加者が、会議を記録すること。</span><span class="sxs-lookup"><span data-stu-id="74438-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="74438-184">組織のすべてのユーザーが、会議に参加するときに発表者として指定されること。</span><span class="sxs-lookup"><span data-stu-id="74438-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="74438-185">これらの設定は、Skype for Business Online 管理センターからは使用できません。</span><span class="sxs-lookup"><span data-stu-id="74438-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="74438-186">Microsoft 365 の PowerShell を使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="74438-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="74438-187">次の3つの設定を無効にするコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="74438-188">このコマンドを実行するには、 [Skype For Business Online PowerShell モジュール ](https://www.microsoft.com/download/details.aspx?id=39366)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="74438-189">この PowerShell コマンドの解釈は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74438-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="74438-190">[新しい Skype for Business Online 会議の設定 (AdmitAnonymousUsersByDefault **)]** で、匿名ユーザーが会議への自動入り口を取得することを許可しないようにします (**-$False**)。</span><span class="sxs-lookup"><span data-stu-id="74438-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="74438-191">参加者が会議を記録する機能を無効にします (**-AllowConferenceRecording $False**)。</span><span class="sxs-lookup"><span data-stu-id="74438-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="74438-192">組織内のすべてのユーザーを発表者として指定しないでください (**-designateaspresenter "None"**)。</span><span class="sxs-lookup"><span data-stu-id="74438-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="74438-193">これらの既定の設定 (オプションを有効にする) を復元するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="74438-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="74438-194">他にも同様のシナリオがあります。これは、管理者が Microsoft 365 コマンドで PowerShell を実行する方法について理解しておく必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="74438-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="74438-195">Microsoft 365 の PowerShell は一括操作に適しています。</span><span class="sxs-lookup"><span data-stu-id="74438-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="74438-196">Microsoft 365 管理センターのようなビジュアルインターフェイスは、単一の操作を行う場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="74438-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="74438-197">たとえば、1つのユーザーアカウントを無効にする必要がある場合は、管理センターを使用してチェックボックスをすばやく見つけてクリアすることができます。</span><span class="sxs-lookup"><span data-stu-id="74438-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="74438-198">これは、PowerShell で同様の操作を実行するよりも簡単になります。</span><span class="sxs-lookup"><span data-stu-id="74438-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="74438-199">しかし、その他の多くの場合に、多数の項目や一部の選択項目を変更する必要がある場合は、Microsoft 365 管理センターが最適なツールではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74438-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="74438-200">たとえば、数千人の電話番号のプレフィックスを変更したり、すべての SharePoint Online サイトから特定のユーザー *Ken Myer* を削除したりする必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="74438-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="74438-201">Microsoft 365 管理センターでは、どのような方法を実行しますか?</span><span class="sxs-lookup"><span data-stu-id="74438-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="74438-202">最後の例では、数百の SharePoint Online サイトがあり、Ken Meyer がメンバーであるかどうかがわからないとします。</span><span class="sxs-lookup"><span data-stu-id="74438-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="74438-203">Microsoft 365 管理センターから開始して、各サイトでこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="74438-204">サイトの **URL** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74438-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="74438-205">[ **サイトコレクションのプロパティ** ] ボックスで、[ **Web サイトのアドレス** ] リンクを選択してサイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="74438-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="74438-206">サイトで、[ **共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74438-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="74438-207">[ **共有** ] ダイアログボックスで、サイトへのアクセス許可を持つすべてのユーザーを表示するリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="74438-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![SharePoint Online 管理センターの SharePoint Online サイトのメンバーを表示する例です。](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="74438-209">[ **共有相手** ] ダイアログボックスで、[ **詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74438-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="74438-210">ユーザーのリストを下にスクロールし、Ken Myer (サイトへのアクセス許可があることを前提としています) を見つけて選択し、[ **ユーザー権限の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74438-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="74438-211">これには、数百のサイトでは *長い* 時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="74438-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="74438-212">別の方法として、Microsoft 365 の PowerShell で次のコマンドを実行して、すべてのサイトから Ken Myer を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="74438-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="74438-213">このコマンドを実行するには、 [SharePoint Online PowerShell モジュール](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="74438-214">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプション (**get-sposite**) 内のすべての SharePoint サイトを取得し、各サイトについてアクセスできるユーザーのリストから Ken Meyer を削除し**ます (ForEach {Remove-Spouser-site $ \_ 。Url-ログイン "kenmyer \@ litwareinc.com"}**)。</span><span class="sxs-lookup"><span data-stu-id="74438-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="74438-215">Microsoft 365 に、ユーザーがアクセス権を持っていないものも含めて、すべてのサイトから Ken Meyer を削除するよう伝えています。</span><span class="sxs-lookup"><span data-stu-id="74438-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="74438-216">そのため、ユーザーがアクセス権を持っていないサイトに関するエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74438-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="74438-217">このコマンドで追加の条件を使用して、彼がログインリストにあるサイトから Ken Meyer のみを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="74438-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="74438-218">ただし、返されるエラーは、サイト自体に害を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="74438-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="74438-219">このコマンドは、Microsoft 365 管理センターで作業する時間ではなく、数百のサイトに対して実行されるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="74438-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="74438-220">もう1つの一括操作の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-220">Here's another bulk operation example.</span></span> <span data-ttu-id="74438-221">次のコマンドを使用して、組織内のすべてのサイトに *Bonnie Kearney*(新しい SharePoint 管理者) を追加します。</span><span class="sxs-lookup"><span data-stu-id="74438-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="74438-222">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプション内のすべての SharePoint サイトを取得します。また、サイトのメンバーグループにログイン名を追加して Bonnie Kearney access を許可することもできます (**ForEach {Add-SPOUser-site $ \_ 。Url-"bkearney \@ litwareinc.com"-グループ "Members"}**)。</span><span class="sxs-lookup"><span data-stu-id="74438-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="74438-223">Microsoft 365 の PowerShell は、データのフィルター処理に適しています。</span><span class="sxs-lookup"><span data-stu-id="74438-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="74438-224">Microsoft 365 管理センターでは、データをフィルター処理して、対象となる情報のサブセットを簡単に見つけられるようにする方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="74438-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="74438-225">たとえば、Exchange では、ユーザー メールボックスのほとんどすべてのプロパティに対するフィルターを簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="74438-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="74438-226">たとえば、ブルーミントン市に居住しているすべてのユーザーのメールボックスの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![ブルーミントンの市区町村に居住しているすべてのユーザーのメールボックスの一覧については、Microsoft 365 管理センターで高度な検索を実行する例を示します。](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="74438-228">Exchange 管理センターでは、フィルター条件を組み合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="74438-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="74438-229">たとえば、ブルーミントンに居住していて、財務部門で勤務しているすべてのユーザーのメールボックスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="74438-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="74438-230">ただし、Exchange 管理センターでできることには制限があります。</span><span class="sxs-lookup"><span data-stu-id="74438-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="74438-231">たとえば、ブルーミントン *または* サンディエゴに居住しているユーザーのメールボックスや、ブルーミントンに居住していないすべてのユーザーのメールボックスを簡単に見つけることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="74438-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="74438-232">次の Microsoft 365 コマンドの PowerShell を使用して、ブルーミントンまたはサンディディエゴに居住しているすべてのユーザーのメールボックスの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="74438-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="74438-233">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="74438-234">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションで、メールボックスが San ディエゴまたはブルーミントン (Where {$) の市区町村にあるすべてのユーザーを取得し\*\* \_ ます。[受信者] Typetypedetails-eq "UserMailbox"-and ($ \_ .City-eq "サンディエゴ"-または $ \_ 。City-eq "ブルーミントン")}**) をクリックし、それぞれの名前と市区町村を表示します (**DisplayName、City を選択\*\*)。</span><span class="sxs-lookup"><span data-stu-id="74438-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="74438-235">ブルーミントン以外の場所にいるユーザーのすべてのメールボックスを一覧表示するコマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74438-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="74438-236">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="74438-237">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションで、メールボックスがブルーミントンの city (Where {$) にないすべてのユーザーを取得し\*\* \_ ます。[受信者] Typetypedetails-eq "UserMailbox"-and $ \_ 。City-ne "ブルーミントン"}\*\*) を選択し、それぞれの名前と市区町村を表示します。</span><span class="sxs-lookup"><span data-stu-id="74438-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="74438-238">ワイルドカードを使用する</span><span class="sxs-lookup"><span data-stu-id="74438-238">Use wildcards</span></span>

<span data-ttu-id="74438-239">また、PowerShell フィルターでワイルドカード文字を使用して、名前の一部と一致させることもできます。</span><span class="sxs-lookup"><span data-stu-id="74438-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="74438-240">たとえば、ユーザーアカウントを探しているとします。</span><span class="sxs-lookup"><span data-stu-id="74438-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="74438-241">ユーザーの姓が *Anderson* か、 *Henderson* または *Jorgenson*であることを覚えておくことができます。</span><span class="sxs-lookup"><span data-stu-id="74438-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="74438-242">検索ツールを使用して、次の3つの異なる検索を実行することによって、Microsoft 365 管理センターでそのユーザーを追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="74438-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="74438-243">*Anderson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="74438-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="74438-244">*Henderson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="74438-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="74438-245">*Jorgenson*  用のもの</span><span class="sxs-lookup"><span data-stu-id="74438-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="74438-246">これらの3つの名前はすべて "son" で終わるので、名前が "son" で終わるすべてのユーザーを表示するように PowerShell に指示できます。</span><span class="sxs-lookup"><span data-stu-id="74438-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="74438-247">コマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74438-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="74438-248">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得しますが、姓が "son" で終わるユーザーの一覧のみを含むフィルターを使用します (**-filter ' {LastName-like " \* son"} '**)。</span><span class="sxs-lookup"><span data-stu-id="74438-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="74438-249">は、 \* ユーザーの姓の文字である任意の文字セットを表します。</span><span class="sxs-lookup"><span data-stu-id="74438-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="74438-250">Microsoft 365 の PowerShell を使用すると、データの印刷や保存が容易になります。</span><span class="sxs-lookup"><span data-stu-id="74438-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="74438-251">Microsoft 365 管理センターでは、データの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="74438-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="74438-252">Skype for business Online 管理センターの例では、Skype for business Online が有効になっているユーザーの一覧が表示されています。</span><span class="sxs-lookup"><span data-stu-id="74438-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Skype for Business Online 管理センターで、Skype for Business Online に対して有効になっているユーザーの一覧を表示する例です。](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="74438-254">その情報をファイルに保存するには、その情報を文書または Microsoft Excel ワークシートに貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="74438-255">どちらの場合も、追加の書式設定が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="74438-255">Either case might require additional formatting.</span></span> <span data-ttu-id="74438-256">また、Microsoft 365 管理センターでは、表示されている一覧を直接印刷する方法は使用できません。</span><span class="sxs-lookup"><span data-stu-id="74438-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="74438-257">さいわい、PowerShell を使用してリストを表示するだけでなく、Excel に簡単にインポートできるファイルに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="74438-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="74438-258">次に、Skype for Business Online ユーザーデータをコンマ区切り値 (CSV) ファイルに保存するコマンドの例を示します。これは、Excel ワークシートのテーブルとして簡単にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="74438-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="74438-259">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-259">Here's an example of the results:</span></span>
  
![コンマ区切り値ファイルに保存された Skype for Business Online ユーザーデータの Excel ワークシートにインポートされるテーブルの例です。](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="74438-261">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションのすべての Skype for Business Online ユーザーを取得します (**-Csonline ユーザー**)。ユーザー名、UPN、および場所のみを取得します (**DisplayName、UserPrincipalName、および利用場所を選択し**ます)。その情報を C: \\ logs \\SfBUsers.csv (**Export-csv-Path "c: \\ Logs \\SfBUsers.csv"-notypeinformation**) という名前の CSV ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="74438-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="74438-262">オプションを使用して、このリストを XML ファイルまたは HTML ページとして保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="74438-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="74438-263">実際には、追加の PowerShell コマンドを使用して、必要なカスタム書式設定を使用して Excel ファイルとして直接保存することができます。</span><span class="sxs-lookup"><span data-stu-id="74438-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="74438-264">また、Windows の既定のプリンターにリストを直接表示する PowerShell コマンドの出力を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="74438-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="74438-265">コマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="74438-266">印刷されたドキュメントは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="74438-266">Here's what your printed document will look like:</span></span>
  
![Windows の既定のプリンターに直接送信された PowerShell コマンドの出力であった印刷ドキュメントの例。](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="74438-268">この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションのすべての Skype for Business Online ユーザーを取得します。ユーザー名、UPN、および場所のみを取得します。その情報を既定の Windows プリンター (**出力プリンター**) に送信します。</span><span class="sxs-lookup"><span data-stu-id="74438-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="74438-269">印刷された文書の簡単な書式設定は、PowerShell コマンドウィンドウの表示と同じです。</span><span class="sxs-lookup"><span data-stu-id="74438-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="74438-270">ハードコピーを取得するには、| を追加するだけです。 **| Out-Printer**コマンドの最後に印刷します。</span><span class="sxs-lookup"><span data-stu-id="74438-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="74438-271">Microsoft 365 の PowerShell を使用すると、複数のサーバー製品を管理できます。</span><span class="sxs-lookup"><span data-stu-id="74438-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="74438-272">Microsoft 365 を構成するコンポーネントは、共同作業を行うように設計されています。</span><span class="sxs-lookup"><span data-stu-id="74438-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="74438-273">たとえば、Microsoft 365 に新しいユーザーを追加し、ユーザーの部署や電話番号などの情報を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="74438-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="74438-274">この情報は、Microsoft 365 サービスのいずれか (Skype for Business Online、Exchange、または SharePoint) でユーザーの情報にアクセスすると利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="74438-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="74438-275">ただし、これは製品のスイートに共通する一般情報の場合です。</span><span class="sxs-lookup"><span data-stu-id="74438-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="74438-276">製品固有の情報 (ユーザーの Exchange メールボックスに関する情報など) は、通常、このスイートでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="74438-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="74438-277">たとえば、ユーザーのメールボックスが有効になっているかどうかに関する情報は、Exchange 管理センターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="74438-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="74438-278">すべてのユーザーに関する次のような情報を示すレポートを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="74438-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="74438-279">ユーザーの表示名</span><span class="sxs-lookup"><span data-stu-id="74438-279">The user's display name</span></span>
    
- <span data-ttu-id="74438-280">ユーザーが Microsoft 365 用にライセンスされているかどうか</span><span class="sxs-lookup"><span data-stu-id="74438-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="74438-281">ユーザーの Exchange メールボックスが有効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="74438-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="74438-282">ユーザーが Skype for Business Online に対して有効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="74438-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="74438-283">Microsoft 365 管理センターでは、このようなレポートを簡単に作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="74438-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="74438-284">代わりに、Excel ワークシートなどの情報を格納するために別のドキュメントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74438-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="74438-285">次に、Microsoft 365 管理センターからすべてのユーザー名とライセンス情報を取得し、Exchange 管理センターからメールボックス情報を取得して、skype for business Online 管理センターから Skype for Business Online 情報を取得し、その情報を結合します。</span><span class="sxs-lookup"><span data-stu-id="74438-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="74438-286">別の方法として、PowerShell スクリプトを使用してレポートをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="74438-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="74438-287">次のスクリプト例は、この記事で説明したコマンドよりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="74438-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="74438-288">しかし、これは、PowerShell を使用して、それ以外の方法で情報ビューを作成する可能性があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="74438-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="74438-289">必要なリストをコンパイルして表示するためのスクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="74438-290">結果の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74438-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="74438-291">この PowerShell スクリプトの解釈は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74438-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="74438-292">現在の Microsoft 365 サブスクリプション内のすべてのユーザーを取得し、その情報を *$x* (**$x = set-azureaduser**) という名前の変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="74438-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="74438-293">変数 $x 内のすべてのユーザーに対して実行されるループを開始します (**foreach ($x では $i)**)。</span><span class="sxs-lookup"><span data-stu-id="74438-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="74438-294">*$Y*という名前の変数を定義し、ユーザーのメールボックス情報をそこに格納します (**$y = Get-Mailbox-Identity $i UserPrincipalName**)。</span><span class="sxs-lookup"><span data-stu-id="74438-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="74438-295">*IsMailBoxEnabled*という名前のユーザー情報に新しいプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="74438-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="74438-296">ユーザーのメールボックスの IsMailBoxEnabled プロパティの値に設定します (**$i | Add-Member-MemberType 注プロパティ-Name IsMailBoxEnabled-value $Y IsMailBoxEnabled**)。</span><span class="sxs-lookup"><span data-stu-id="74438-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="74438-297">*$Y*という名前の変数を定義し、ユーザーの Skype For business Online 情報をその変数に格納します (**$y = Get-CsOnlineUser-Identity $i UserPrincipalName**)。</span><span class="sxs-lookup"><span data-stu-id="74438-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="74438-298">*Enabledforsfb*という名前のユーザー情報に新しいプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="74438-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="74438-299">これを、ユーザーの Skype for Business Online 情報の Enabled プロパティの値 (**$i | Add-Member-MemberType 注プロパティ-Name EnabledForSfB-value $Y enabled**) の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="74438-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="74438-300">ユーザーの一覧を表示しますが、ユーザー名、ライセンスがあるかどうか、メールボックスが有効になっているかどうか、およびそれらのプロパティが Skype for Business Online に対して有効になっているかどうかを示す2つの新しいプロパティを含めます (**$x |DisplayName、IsLicensed、IsMailboxEnabled、EnabledforSfB) を選択**します。</span><span class="sxs-lookup"><span data-stu-id="74438-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="74438-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="74438-301">See also</span></span>

[<span data-ttu-id="74438-302">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="74438-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="74438-303">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="74438-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="74438-304">Windows PowerShell を使用して Microsoft 365 でレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="74438-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
