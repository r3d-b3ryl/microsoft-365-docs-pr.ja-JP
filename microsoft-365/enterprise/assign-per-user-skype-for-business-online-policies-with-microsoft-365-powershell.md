---
title: PowerShell for Microsoft 365 でユーザーごとのSkype for Business オンライン ポリシーを割り当てる
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: '概要: PowerShell for Microsoft 365を使用して、Skype for Business Online ポリシーを使用してユーザーごとの通信設定を割り当てます。'
ms.openlocfilehash: 70120f6d296f958f44906a3526a7dcaa36b7eb04
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091393"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>PowerShell for Microsoft 365 でユーザーごとのSkype for Business オンライン ポリシーを割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365に PowerShell を使用すると、Skype for Business Online ポリシーを使用してユーザーごとの通信設定を割り当てる効率的な方法です。
  
## <a name="prepare-to-run-the-powershell-commands"></a>PowerShell コマンドの実行を準備する

次の手順にしたがってコマンドを実行するためのセットアップを行います (すでに終わっている場合はこれらの手順は省略可能です)。
  
  > [!Note]
   > Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。

1. [Teams PowerShell モジュール](/microsoftteams/teams-powershell-install)をインストールします。
    
2. Windows PowerShell コマンド プロンプトを開いて次のコマンドを実行します: 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   ダイアログ ボックスが表示されたら、Skype for Business Online 管理者のアカウント名とパスワードを入力します。
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>ユーザー アカウントの外部通信設定を更新する

ユーザー アカウントの外部通信設定を変更するとします。たとえば、Alex がフェデレーション ユーザーと通信できるようにする (EnableFederationAccess を True に設定) と同時に、Windows Live ユーザーとは通信できないようにするとします (EnablePublicCloudAccess を False に設定)。この場合、次の 2 つの手順が必要になります。
  
1. この条件を満たす外部アクセス ポリシーを探す。
    
2. その外部アクセス ポリシーを Alex に割り当てる。
    
Alex を割り当てる外部アクセス ポリシーを決定するにはどうすればよいですか? 次のコマンドは、EnableFederationAccess が True に設定され、EnablePublicCloudAccess が False に設定されたすべての外部アクセス ポリシーを返します。
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

ExternalAccessPolicy のカスタム インスタンスを作成していない限り、そのコマンドは条件を満たす 1 つのポリシーを返します (FederationOnly)。 次に例を示します：
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

これで、Alex に割り当てるポリシーが特定されたため、このポリシーを [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) コマンドレットを使用して割り当てることができます。以下に例を示します。
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

ポリシーの割り当ては簡単にでき、割り当てるユーザーの ID とポリシー名を指定するだけでポリシーを割り当てることができます。 
  
ポリシーとポリシー割り当てに関して言えば、一度に処理するユーザー アカウントの数は 1 つに制限されません。たとえば、フェデレーション パートナーおよび Windows Live ユーザーとの通信が許可されているすべてのユーザーのリストが必要だとします。このようなユーザーには外部ユーザー アクセス ポリシーの FederationAndPICDefault が割り当てられていることはすでにわかっています。それがわかっているため、1 つの単純なコマンドを実行するだけで、このようなすべてのユーザーのリストを表示することができます。以下にコマンドを示します。
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

つまり、ExternalAccessPolicy プロパティが FederationAndPICDefault に設定されているすべてのユーザーが表示されます (画面上に表示される情報量を制限するには、Select-Object コマンドレットを使用して各ユーザーの表示名だけを出力するようにします)。 
  
すべてのユーザー アカウントが同じポリシーを使用するように構成する場合は次のコマンドを使用します。
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

このコマンドでは、Get-CsOnlineUser を使用して、Lync に対して有効になっているすべてのユーザーのコレクションを返します。その後、そのすべての情報が Grant-CsExternalAccessPolicy に送信され、FederationAndPICDefault ポリシーがコレクション内のすべてのユーザーそれぞれに割り当てられます。
  
もう一つの例として、Alex にすでに FederationAndPICDefault ポリシーを割り当てていたものの、グローバルな外部アクセス ポリシーで管理することにしたとします。 グローバル ポリシーは誰かに明示的に割り当てることはできません。 代わりに、そのユーザーにユーザーごとのポリシーが割り当てられていない場合は、特定のユーザーに対してグローバル ポリシーが使用されます。 つまり、Alex をグローバル ポリシーで管理する場合は、事前に彼に割り当てられたユーザーごとのポリシーを *解除する*  必要があります。 コマンドの例を以下に示します。
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

このコマンドでは、Alex に割り当てられた外部アクセス ポリシーの名前を Null 値 ($Null) に設定します。Null は "何もない" という意味です。言い換えれば、どの外部アクセス ポリシーも Alex に割り当てられていないということになります。どの外部アクセス ポリシーもユーザーに割り当てられていなければ、そのユーザーはグローバル ポリシーによって管理されます。

## <a name="managing-large-numbers-of-users"></a>多数のユーザーを管理する

多数のユーザー (1,000 人以上) を管理するには、 [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) コマンドレットを使用してスクリプト ブロックを使用してコマンドをバッチ処理する必要があります。  前の例では、コマンドレットが実行されるたびに、呼び出しを設定し、結果を待機してから送信する必要があります。  スクリプト ブロックを使用する場合は、コマンドレットをリモートで実行し、完了したらデータを送信し直すことができます。

```powershell
$s = Get-PSSession | Where-Object { ($.ComputerName -like '*.online.lync.com' -or $.Computername -eq 'api.interfaces.records.teams.microsoft.com') -and $.State -eq 'Opened' -and $.Availability -eq 'Available' }

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

これにより、一度に 500 人のユーザーがクライアント ポリシーを持っていないことがわかります。 クライアント ポリシー "ClientPolicyNoIMURL" と外部アクセス ポリシー "FederationAndPicDefault" が付与されます。 結果は 50 のグループにバッチ処理され、50 の各バッチはリモート コンピューターに送信されます。
  
## <a name="see-also"></a>関連項目

[PowerShell を使用して Skype for Business Online を管理する](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
