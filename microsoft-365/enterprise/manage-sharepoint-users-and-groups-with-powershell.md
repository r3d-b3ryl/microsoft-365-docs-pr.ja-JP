---
title: PowerShell を使用して SharePoint Online のユーザーとグループを管理する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/17/2020
audience: Admin
ms.topic: landing-page
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: この記事では、PowerShell for Microsoft 365を使用して、SharePoint Online ユーザー、グループ、およびサイトを管理する方法について説明します。
ms.openlocfilehash: 78c829e476c63e435d9543b3a4175cdbbccb76e8
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100679"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>PowerShell を使用して SharePoint Online のユーザーとグループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

SharePoint Online 管理者で、ユーザー アカウントまたはグループの大規模な一覧を操作し、それらを管理する簡単な方法が必要な場合は、PowerShell を使用してMicrosoft 365できます。

開始する前に、この記事の手順でSharePoint Online に接続する必要があります。 手順については、「[オンライン PowerShell をSharePointするConnect」を](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)参照してください。

## <a name="get-a-list-of-sites-groups-and-users"></a>サイト、グループ、ユーザーの一覧を取得する

ユーザーとグループを管理する前に、サイト、グループ、ユーザーの一覧を取得する必要があります。この情報は、この記事の例全体を通して使用できます。

次のコマンドを使用して、テナント内のサイトの一覧を取得します。

```powershell
Get-SPOSite
```

次のコマンドを使用して、テナント内のグループの一覧を取得します。

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

次のコマンドを使用して、テナント内のユーザーの一覧を取得します。

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>サイト コレクション管理者グループにユーザーを追加する

このコマンドレットを `Set-SPOUser` 使用して、サイト コレクションのサイト コレクション管理者の一覧にユーザーを追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

これらのコマンドを使用するには、引用符内のすべての文字列 (<文字や>文字など) を正しい名前に置き換えます。

たとえば、この一連のコマンドは、Contoso テナントの ContosoTest サイト コレクションのサイト コレクション管理者の一覧に Opal Castillo (ユーザー名 opalc) を追加します。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

これらのコマンドをコピーしてメモ帳に貼り付け、$tenant、$site、および$userの変数値を環境の実際の値に変更し、これを SharePoint Online Management Shell ウィンドウに貼り付けて実行できます。

## <a name="add-a-user-to-other-site-collection-groups"></a>他のサイト コレクション グループにユーザーを追加する

このタスクでは、コマンドレットを`Add-SPOUser`使用して、サイト コレクションのSharePoint グループにユーザーを追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

たとえば、Contoso テナントの ContosoTest サイト コレクションの Auditors グループに、Glen Rife (ユーザー名のgler) を追加します。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>サイト コレクション グループを作成する

このコマンドレットを`New-SPOSiteGroup`使用して、新しいSharePoint グループを作成し、それをサイト コレクションに追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

アクセス許可レベルなどのグループ プロパティは、後でコマンドレットを使用 `Set-SPOSiteGroup` して更新できます。

たとえば、表示のみアクセス許可を持つ Auditors グループを contoso テナントの contosotest サイト コレクションに追加します。

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>グループからユーザーを削除する

場合によっては、あるサイトまたはすべてのサイトからユーザーを削除する必要があります。 たとえば、従業員がある部署から別の部署に異動した場合や、退職した場合などが該当します。 これは、UI で簡単に 1 人の従業員に対して行うことができますが、サイト間で完全な部門を移動する必要がある場合は、簡単には実行できません。

ただし、SharePoint Online Management Shell ファイルと CSV ファイルを使用すると、高速かつ簡単に実行できます。 このタスクでは、まず、Windows PowerShell を使用して、サイト コレクションのセキュリティ グループから 1 人のユーザーを削除します。 次に、CSV ファイルを使用して、複数の異なるサイトから多数のユーザーを削除します。

コマンド構文を確認できるように、'Remove-SPOUser' コマンドレットを使用して 1 人のMicrosoft 365 ユーザーをサイト コレクション グループから削除します。 構文の外観は次のとおりです。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

たとえば、contoso テナントの contosotest サイト コレクションのサイト コレクション監査グループから Bobby Overby を削除しましょう。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

現在のグループから Bobby を削除したかったとします。 これを行う方法を次に示します。

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> これは単なる例です。 たとえば、ユーザーが退職した場合など、ユーザーをすべてのグループから実際に削除しなければならないのでない限り、このコマンドを使用しないでください。

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>ユーザーおよびグループの大規模なリストの管理を自動化する

SharePoint サイトに多数のアカウントを追加し、アクセス許可を付与するには、Microsoft 365 管理センター、個々の PowerShell コマンド、または PowerShell と CSV ファイルを使用できます。 これらの選択肢の中では、CSV ファイルがこのタスクを自動化する最も簡単な方法になります。

基本的なプロセスは、CSV を作成し、ヘッダー (列) を Windows PowerShell スクリプトに必要なパラメーターに対応させることです。 このようなリストは、Excelで簡単に作成し、CSV ファイルとしてエクスポートできます。 次に、Windows PowerShell スクリプトを使用して CSV ファイル内のレコード (行) を反復処理し、ユーザーをグループに追加し、グループをサイトに追加します。

たとえば、サイト コレクション、グループ、およびアクセス許可のグループを定義する CSV ファイルを作成しましょう。 次に、グループにユーザーを設定する CSV ファイルを作成します。 最後に、グループを作成して設定するWindows PowerShell スクリプトを作成して実行します。

最初の CSV ファイルは、1 つ以上のグループを 1 つ以上のサイト コレクションに追加します。このファイルの構造は以下のとおりです。

ヘッダー：

```powershell
Site,Group,PermissionLevels
```

項目：

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

ファイルの例を次に示します。

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

2 番目の CSV ファイルは、1 つ以上のユーザーを 1 つ以上のグループに追加します。このファイルの構造は以下のとおりです。

ヘッダー：

```powershell
Group,LoginName,Site
```

項目：

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

ファイルの例を次に示します。

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

次の手順では、2 つの CSV ファイルをドライブに保存する必要があります。 CSV ファイルの両方を使用し、アクセス許可とグループ メンバーシップを追加するコマンドの例を次に示します。

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

スクリプトは CSV ファイルの内容をインポートし、列の値を使用して **New-SPOSiteGroup および Add-SPOUser** コマンドのパラメーター **を** 設定します。 この例では、このファイルをドライブ C の O365Admin フォルダーに保存していますが、任意の場所に保存できます。

次に、同じ CSV ファイルを使用して、異なるサイト内の複数のグループの一連のユーザーを削除しましょう。 コマンドの例を次に示します。

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>ユーザー レポートを生成する

いくつかのサイトのレポートを取得し、それらのサイトのユーザー、アクセス許可レベル、およびその他のプロパティを表示することができます。 以下に、構文の一例を示します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

上記のコードは、3 つのサイトのデータを取得して、ローカル ドライブ上のテキスト ファイルに書き込みます。 パラメーター –Append は、既存のファイルに新しいコンテンツを追加します。

たとえば、Contoso1 テナントの ContosoTest サイト、TeamSite01 サイト、および Project01 サイトでレポートを実行します。

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

**$site** 変数のみを変更する必要がありました。 **$tenant** 変数は、コマンドの 3 つの実行すべてを通じてその値を保持します。

一方、この操作をすべてのサイトに対して行うとしたら、どうなるでしょうか。以下のコードを使用すれば、すべての Web サイトを入力することなく、このコマンドを使用できます。

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

このレポートはかなり単純ですが、コードを追加すれば、より具体的なレポートや、その他の詳細情報が含まれるレポートを作成できます。 しかし、これにより、SharePoint Online Management Shell を使用して、SharePoint Online 環境でユーザーを管理する方法について説明する必要があります。

## <a name="see-also"></a>関連項目

[SharePoint Online PowerShell に接続する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[PowerShell を使用して SharePoint Online を管理する](create-sharepoint-sites-and-add-users-with-powershell.md)

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
