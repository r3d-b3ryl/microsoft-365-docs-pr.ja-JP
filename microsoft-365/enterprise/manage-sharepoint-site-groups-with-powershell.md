---
title: PowerShell を使用して SharePoint Online サイト グループを管理する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/17/2019
audience: Admin
ms.topic: hub-page
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
description: この記事では、PowerShell を使用してオンライン サイト グループMicrosoft 365管理SharePointを見つける。
ms.openlocfilehash: deef41118789a9df4353fa188c88d827909dc863
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328779"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>PowerShell を使用して SharePoint Online サイト グループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

このサイトを使用Microsoft 365 管理センター、PowerShell を使用してオンライン サイト Microsoft 365を管理SharePointすることもできます。

## <a name="before-you-begin"></a>始める前に

この記事の手順では、オンラインからオンラインに接続するSharePoint必要があります。 手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>PowerShell SharePointを使用してオンラインを表示Microsoft 365

オンラインSharePoint管理センターには、サイト グループを管理するための使いやすい方法があります。 たとえば、サイトのグループとグループ メンバーを確認すると `https://litwareinc.sharepoint.com/sites/finance` します。 次の操作を実行する必要があります。

1. 管理センター SharePoint[アクティブ なサイト] <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**を**</a>選択し、サイトの URL を選択します。
2. サイト ページで、[設定 <a href="https://go.microsoft.com/fwlink/?linkid=2185072" target="_blank">**] を選択**</a>し (ページの右上隅にあります)、[サイトのアクセス許可 **] を選択します**。

参照する次のサイトでも、このプロセスを繰り返します。

PowerShell を使用してグループの一覧を取得するにはMicrosoft 365コマンドを使用します。

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

[オンライン管理シェル] コマンド プロンプトでこのコマンド セットを実行SharePoint 2 つの方法があります。

- コマンドを メモ帳 (または別のテキスト エディター) にコピーし、**$siteURL** 変数の値を変更し、コマンドを選択し、SharePoint Online 管理シェル コマンド プロンプトに貼り付けます。 この操作を行うと、PowerShell はプロンプトで停止 **>>** します。 Enter キーを押してコマンドを実行 `foreach` します。<br/>
- コマンドをメモ帳 (または別のテキスト エディター) にコピーし、**$siteURL** 変数の値を変更してから、このテキスト ファイルを .ps1 という拡張子の付いた名前で適切なフォルダーに保存します。 次に、パスとファイル名をSharePointして、オンライン管理シェルのコマンド プロンプトからスクリプトを実行します。 コマンド例を次に示します。

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

どちらの場合も、次のように表示されるはずです。

![SharePoint オンライン サイト グループ。](../media/SPO-site-groups.png)

これらは、サイト用に作成されたグループ `https://litwareinc.sharepoint.com/sites/finance`すべて、およびそれらのグループに割り当てられているすべてのユーザーです。 グループ名とメンバーの見分けがつくように、グループ名は黄色で表示されます。

別の例として、すべてのオンライン サイトのグループとすべてのグループ メンバーシップを一覧表示するコマンド SharePointします。

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```

## <a name="see-also"></a>関連項目

[SharePoint Online PowerShell に接続する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[PowerShell を使用して SharePoint Online サイトを作成し、ユーザーを追加する](create-sharepoint-sites-and-add-users-with-powershell.md)

[PowerShell を使用して SharePoint Online のユーザーとグループを管理する](manage-sharepoint-users-and-groups-with-powershell.md)

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
