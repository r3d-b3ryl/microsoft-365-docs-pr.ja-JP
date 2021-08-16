---
title: PowerShell を使用して SharePoint Online のユーザーとグループを管理する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
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
description: この記事では、PowerShell を使用してオンライン ユーザー Microsoft 365、SharePointサイトを管理する方法について説明します。
ms.openlocfilehash: 04eb4a0e2c7d2c309ae4bbe063102293a017bbd6
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356002"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>PowerShell を使用して SharePoint Online のユーザーとグループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ユーザー アカウントまたはグループのSharePointリストを操作し、簡単に管理する方法が必要なオンライン管理者の場合は、PowerShell を Microsoft 365 に使用できます。

開始する前に、このトピックの手順では、オンラインからオンラインに接続SharePointがあります。 手順については、「オンライン[PowerShell ConnectをSharePointする」を参照してください。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

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

コマンドレットを使用して、サイト コレクションのサイト コレクション管理者の一 `Set-SPOUser` 覧にユーザーを追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

これらのコマンドを使用するには、引用符内の文字を含む<、>を正しい名前に置き換える必要があります。

たとえば、この一連のコマンドは、Contoso テナントの ContosoTest サイト コレクションのサイト コレクション管理者のリストに、Opal Castillo (ユーザー名 opalc) を追加します。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

これらのコマンドを メモ帳 にコピーして貼り付け、$tenant、$site、$user の変数値を環境の実際の値に変更してから、これを SharePoint Online 管理シェル ウィンドウに貼り付け、実行できます。

## <a name="add-a-user-to-other-site-collection-groups"></a>ユーザーを他のサイト コレクション グループに追加する

このタスクでは、コマンドレットを使用して、ユーザーをサイト コレクション上SharePoint `Add-SPOUser` グループに追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

たとえば、Contoso テナントの ContosoTest サイト コレクションの Auditors グループに、Glen Rife (ユーザー名 glenr) を追加します。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>サイト コレクション グループを作成する

コマンドレットを使用 `New-SPOSiteGroup` して新しいグループを作成SharePointサイト コレクションに追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

アクセス許可レベルなどのグループ プロパティは、コマンドレットを使用して後で更新 `Set-SPOSiteGroup` できます。

たとえば、Contoso テナントの contosotest サイト コレクションに View Only アクセス許可を持つ Auditors グループを追加します。

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>グループからユーザーを削除する

場合によっては、あるサイトまたはすべてのサイトからユーザーを削除する必要があります。たとえば、従業員がある部署から別の部署に異動した場合や、退職した場合などが該当します。対象の従業員が 1 人のみの場合は UI で簡単に削除できますが、部署全体をあるサイトから別のサイトに移動する場合は容易ではありません。

ただし、オンライン管理シェルSharePoint CSV ファイルを使用すると、高速かつ簡単に実行できます。 このタスクでは、まず、Windows PowerShell を使用して、サイト コレクションのセキュリティ グループから 1 人のユーザーを削除します。 次に、CSV ファイルを使用して、複数の異なるサイトから多数のユーザーを削除します。

'Remove-SPOUser' コマンドレットを使用して、サイト コレクション グループから 1 人の Microsoft 365 ユーザーを削除し、コマンド構文を確認します。 以下に、構文の一例を示します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

たとえば、contoso テナントの contosotest サイト コレクション内のサイト コレクション Auditors グループから Bobby Overby を削除します。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Bobby を現在彼が所属しているすべてのグループから削除するとしたら、以下の方法があります。

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> これは単なる例です。 たとえば、ユーザーが退職した場合など、ユーザーをすべてのグループから実際に削除しなければならないのでない限り、このコマンドを使用しないでください。

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>ユーザーおよびグループの大規模なリストの管理を自動化する

多数のアカウントを SharePoint サイトに追加してアクセス許可を付与するには、Microsoft 365 管理センター、個々の PowerShell コマンド、または PowerShell に CSV ファイルを使用できます。 これらの選択肢の中では、CSV ファイルがこのタスクを自動化する最も簡単な方法になります。

基本的なプロセスは、CSV を作成し、ヘッダー (列) を Windows PowerShell スクリプトに必要なパラメーターに対応させることです。 このようなリストは、ファイル内で簡単に作成Excel CSV ファイルとしてエクスポートできます。 次に、Windows PowerShellスクリプトを使用して CSV ファイル内のレコード (行) を反復処理し、ユーザーをグループに追加し、グループをサイトに追加します。

たとえば、サイト コレクション、グループ、およびアクセス許可のグループを定義する CSV ファイルを作成します。 次に、グループにユーザーを取り込むための CSV ファイルを作成します。 最後に、グループを作成してユーザーを取り込む単純な Windows PowerShell スクリプトを作成して実行します。

最初の CSV ファイルは、1 つ以上のグループを 1 つ以上のサイト コレクションに追加します。このファイルの構造は以下のとおりです。

ヘッダー:

```powershell
Site,Group,PermissionLevels
```

アイテム:

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

以下は、サンプル ファイルです。

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

ヘッダー:

```powershell
Group,LoginName,Site
```

アイテム:

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

以下は、サンプル ファイルです。

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

次の手順では、2 つの CSV ファイルをドライブに保存する必要があります。 CSV ファイルとアクセス許可とグループ メンバーシップの両方を使用するコマンドの例を次に示します。

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

スクリプトは CSV ファイルの内容をインポートし、列の値を使用して **New-SPOSiteGroup** コマンドと **Add-SPOUser** コマンドのパラメーターを設定します。 この例では、これをドライブ C のO365Admin フォルダーに保存していますが、必要な場所に保存できます。

次に、同じ CSV ファイルを使用して、さまざまなサイトの複数のグループのユーザーを削除します。 コマンド例を次に示します。

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>ユーザー レポートを生成する

いくつかのサイトに関する単純なレポートを取得して、該当するサイトのユーザーと各ユーザーのアクセス許可レベルやその他のプロパティを表示しなければならない場合があります。以下に、構文の一例を示します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

上記のコードは、3 つのサイトのデータを取得して、ローカル ドライブ上のテキスト ファイルに書き込みます。パラメーター –Append は、既存のファイルに新しいコンテンツを追加することに注意してください。

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

変数の値のみを変更 **する必要$site** 注意してください。 変数 **$tenant** は、コマンドの 3 つの実行すべてで値を保持します。

一方、この操作をすべてのサイトに対して行うとしたら、どうなるでしょうか。以下のコードを使用すれば、すべての Web サイトを入力することなく、このコマンドを使用できます。

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

このレポートはかなり単純ですが、コードを追加すれば、より具体的なレポートや、その他の詳細情報が含まれるレポートを作成できます。 ただし、これにより、オンライン管理シェルを使用してオンライン環境SharePointユーザーを管理する方法SharePointがあります。

## <a name="see-also"></a>関連項目

[SharePoint Online PowerShell に接続する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[PowerShell を使用して SharePoint Online を管理する](create-sharepoint-sites-and-add-users-with-powershell.md)

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
