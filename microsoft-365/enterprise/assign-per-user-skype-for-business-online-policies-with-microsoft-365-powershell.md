---
title: PowerShell for Microsoft 365 でユーザーごとの Skype for Business Online ポリシーを割り当てる
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: '概要: PowerShell for Microsoft 365 を使用して、Skype for Business Online ポリシーでユーザー単位の通信設定を割り当てる。'
ms.openlocfilehash: 6ee237e5d2ee0c9f472f372a6aa66c9612336265
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514982"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="dbfba-103">PowerShell for Microsoft 365 でユーザーごとの Skype for Business Online ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dbfba-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="dbfba-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="dbfba-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dbfba-105">PowerShell for Microsoft 365 を使用すると、Skype for Business Online ポリシーを使用してユーザー単位の通信設定を効率的に割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="dbfba-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="dbfba-106">PowerShell コマンドの実行の準備</span><span class="sxs-lookup"><span data-stu-id="dbfba-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="dbfba-107">次の手順にしたがってコマンドを実行するためのセットアップを行います (すでに終わっている場合はこれらの手順は省略可能です)。</span><span class="sxs-lookup"><span data-stu-id="dbfba-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="dbfba-108">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="dbfba-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="dbfba-109">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dbfba-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="dbfba-110">Teams [PowerShell モジュールをインストールします](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="dbfba-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="dbfba-111">Windows PowerShell コマンド プロンプトを開いて次のコマンドを実行します:</span><span class="sxs-lookup"><span data-stu-id="dbfba-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="dbfba-112">ダイアログ ボックスが表示されたら、Skype for Business Online 管理者のアカウント名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="dbfba-113">ユーザー アカウントの外部通信設定を更新する</span><span class="sxs-lookup"><span data-stu-id="dbfba-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="dbfba-p102">ユーザー アカウントの外部通信設定を変更するとします。たとえば、Alex がフェデレーション ユーザーと通信できるようにする (EnableFederationAccess を True に設定) と同時に、Windows Live ユーザーとは通信できないようにするとします (EnablePublicCloudAccess を False に設定)。この場合、次の 2 つの手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="dbfba-p102">Suppose you want to change external communication settings on a user account. For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False). To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="dbfba-117">この条件を満たす外部アクセス ポリシーを探す。</span><span class="sxs-lookup"><span data-stu-id="dbfba-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="dbfba-118">その外部アクセス ポリシーを Alex に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dbfba-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="dbfba-119">Alex を割り当てる外部アクセス ポリシーを決定する方法</span><span class="sxs-lookup"><span data-stu-id="dbfba-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="dbfba-120">次のコマンドは、EnableFederationAccess が True に設定され、EnablePublicCloudAccess が False に設定されたすべての外部アクセス ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="dbfba-121">ExternalAccessPolicy のカスタム インスタンスを作成しない限り、そのコマンドは条件 (FederationOnly) を満たす 1 つのポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="dbfba-122">次に例を示します：</span><span class="sxs-lookup"><span data-stu-id="dbfba-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="dbfba-p105">これで、Alex に割り当てるポリシーが特定されたため、このポリシーを [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) コマンドレットを使用して割り当てることができます。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-p105">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) cmdlet. Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="dbfba-125">ポリシーの割り当ては簡単にでき、割り当てるユーザーの ID とポリシー名を指定するだけでポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dbfba-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="dbfba-p106">ポリシーとポリシー割り当てに関して言えば、一度に処理するユーザー アカウントの数は 1 つに制限されません。たとえば、フェデレーション パートナーおよび Windows Live ユーザーとの通信が許可されているすべてのユーザーのリストが必要だとします。このようなユーザーには外部ユーザー アクセス ポリシーの FederationAndPICDefault が割り当てられていることはすでにわかっています。それがわかっているため、1 つの単純なコマンドを実行するだけで、このようなすべてのユーザーのリストを表示することができます。以下にコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-p106">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time. For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users. We already know that those users have been assigned the external user access policy FederationAndPICDefault. Because we know that, you can display a list of all those users by running one simple command. Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="dbfba-p107">つまり、ExternalAccessPolicy プロパティが FederationAndPICDefault に設定されているすべてのユーザーが表示されます (画面上に表示される情報量を制限するには、Select-Object コマンドレットを使用して各ユーザーの表示名だけを出力するようにします)。</span><span class="sxs-lookup"><span data-stu-id="dbfba-p107">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault. (And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="dbfba-133">すべてのユーザー アカウントが同じポリシーを使用するように構成する場合は次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="dbfba-134">このコマンドでは、Get-CsOnlineUser を使用して、Lync に対して有効になっているすべてのユーザーのコレクションを返します。その後、そのすべての情報が Grant-CsExternalAccessPolicy に送信され、FederationAndPICDefault ポリシーがコレクション内のすべてのユーザーそれぞれに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dbfba-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="dbfba-135">もう一つの例として、Alex にすでに FederationAndPICDefault ポリシーを割り当てていたものの、グローバルな外部アクセス ポリシーで管理することにしたとします。</span><span class="sxs-lookup"><span data-stu-id="dbfba-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="dbfba-136">グローバル ポリシーは誰かに明示的に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="dbfba-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="dbfba-137">代わりに、そのユーザーにユーザーごとのポリシーが割り当てられていない場合は、特定のユーザーに対してグローバル ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dbfba-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="dbfba-138">つまり、Alex をグローバル ポリシーで管理する場合は、事前に彼に割り当てられたユーザーごとのポリシーを *解除する*  必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbfba-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="dbfba-139">コマンドの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="dbfba-p109">このコマンドでは、Alex に割り当てられた外部アクセス ポリシーの名前を Null 値 ($Null) に設定します。Null は "何もない" という意味です。言い換えれば、どの外部アクセス ポリシーも Alex に割り当てられていないということになります。どの外部アクセス ポリシーもユーザーに割り当てられていなければ、そのユーザーはグローバル ポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="dbfba-p109">This command sets the name of the external access policy assigned to Alex to a null value ($Null). Null means "nothing". In other words, no external access policy is assigned to Alex. When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="dbfba-144">多数のユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="dbfba-144">Managing large numbers of users</span></span>

<span data-ttu-id="dbfba-145">多数のユーザー (1000 以上) を管理するには、Invoke-Command コマンドレットを使用してスクリプト ブロックを介してコマンドを [バッチ処理する必要](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) があります。</span><span class="sxs-lookup"><span data-stu-id="dbfba-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="dbfba-146">前の例では、コマンドレットを実行する度に、呼び出しをセットアップし、結果を待って戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbfba-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="dbfba-147">スクリプト ブロックを使用すると、コマンドレットをリモートで実行し、完了したらデータを送り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="dbfba-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="dbfba-148">これにより、一度に 500 人のユーザーがクライアント ポリシーを持たないユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="dbfba-149">クライアント ポリシー "ClientPolicyNoIMURL" と外部アクセス ポリシー "FederationAndPicDefault" を付与します。</span><span class="sxs-lookup"><span data-stu-id="dbfba-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="dbfba-150">結果は 50 のグループにバッチ処理され、50 の各バッチはリモート コンピューターに送信されます。</span><span class="sxs-lookup"><span data-stu-id="dbfba-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dbfba-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbfba-151">See also</span></span>

[<span data-ttu-id="dbfba-152">PowerShell を使用して Skype for Business Online を管理する</span><span class="sxs-lookup"><span data-stu-id="dbfba-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="dbfba-153">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="dbfba-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="dbfba-154">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="dbfba-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
