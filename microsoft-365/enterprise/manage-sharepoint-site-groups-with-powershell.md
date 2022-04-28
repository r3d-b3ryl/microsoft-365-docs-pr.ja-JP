---
title: PowerShell を使用して SharePoint Online サイト グループを管理する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/17/2019
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
description: この記事では、PowerShell for Microsoft 365を使用してSharePoint Online サイト グループを管理する手順について説明します。
ms.openlocfilehash: 411ab477668b7956a63843d0b58b8d6d9bfc9059
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096438"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>PowerShell を使用して SharePoint Online サイト グループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 管理センターを使用できますが、Microsoft 365用の PowerShell を使用して、SharePoint Online サイト グループを管理することもできます。

## <a name="before-you-begin"></a>開始する前に

この記事の手順では、SharePoint Online に接続する必要があります。 手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>PowerShell for Microsoft 365 でオンラインSharePointを表示する

SharePoint Online 管理センターには、サイト グループを管理するための使いやすい方法がいくつかあります。 たとえば、サイトのグループとグループ メンバー `https://litwareinc.sharepoint.com/sites/finance` を確認するとします。 次の操作を行う必要があります。

1. SharePoint管理センターで [<a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**アクティブなサイト**</a>] を選択し、サイトの URL を選択します。
2. サイト ページで <a href="https://go.microsoft.com/fwlink/?linkid=2185072" target="_blank">**設定 (ページ**</a>の右上隅にある) を選択し、[**サイトのアクセス許可**] を選択します。

参照する次のサイトでも、このプロセスを繰り返します。

PowerShell for Microsoft 365 でグループの一覧を取得するには、次のコマンドを使用します。

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

SharePoint Online Management Shell コマンド プロンプトでこのコマンド セットを実行するには、次の 2 つの方法があります。

- コマンドをメモ帳 (または別のテキスト エディター) にコピーし、**$siteURL** 変数の値を変更し、コマンドを選択して、SharePoint Online Management Shell コマンド プロンプトに貼り付けます。 これを行うと、PowerShell はプロンプトで **>>** 停止します。 Enter キーを押してコマンドを `foreach` 実行します。<br/>
- コマンドをメモ帳 (または別のテキスト エディター) にコピーし、**$siteURL** 変数の値を変更してから、このテキスト ファイルを .ps1 という拡張子の付いた名前で適切なフォルダーに保存します。 次に、パスとファイル名を指定して、SharePoint Online Management Shell コマンド プロンプトからスクリプトを実行します。 コマンド例を次に示します。

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

どちらの場合も、次のように表示されるはずです。

![オンライン サイト グループをSharePointします。](../media/SPO-site-groups.png)

これらは、サイト `https://litwareinc.sharepoint.com/sites/finance`に対して作成されたすべてのグループと、それらのグループに割り当てられたすべてのユーザーです。 グループ名とメンバーの見分けがつくように、グループ名は黄色で表示されます。

もう 1 つの例として、すべてのSharePoint Online サイトのグループとすべてのグループ メンバーシップを一覧表示するコマンド セットを次に示します。

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
