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
ms.openlocfilehash: 26ac87fe258e0340e95be0e83710f7810bc437a8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195379"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>PowerShell を使用して SharePoint Online サイト グループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

このサイトを使用Microsoft 365 管理センター、PowerShell を使用してオンライン サイト Microsoft 365管理することもできますSharePoint管理できます。

## <a name="before-you-begin"></a>はじめに

この記事の手順では、オンラインからオンラインに接続するSharePoint必要があります。 手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>PowerShell SharePointを使用してオンラインを表示Microsoft 365

オンラインSharePoint管理センターには、サイト グループを管理するための使いやすい方法があります。 たとえば、サイトのグループとグループ メンバーを確認すると `https://litwareinc.sharepoint.com/sites/finance` します。 次の操作を実行する必要があります。

1. 管理センター SharePoint[アクティブ なサイト]**を** クリックし、サイトの URL をクリックします。
2. サイト ページで、ページ **の右上隅にある**[設定] アイコンをクリックし、[サイトのアクセス許可]**をクリックします**。

参照する次のサイトでも、このプロセスを繰り返します。

PowerShell を使用してグループの一覧を取得するには、Microsoft 365コマンドを使用します。

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

- コマンドを メモ帳 (または別のテキスト エディター) にコピーし **、$siteURL** 変数の値を変更し、コマンドを選択し、SharePoint Online Management Shell コマンド プロンプトに貼り付けます。 この操作を行うと、PowerShell はプロンプトで停止 **>>** します。 Enter キーを押してコマンドを `foreach` 実行します。<br/>
- コマンドをメモ帳 (または別のテキスト エディター) にコピーし、**$siteURL** 変数の値を変更してから、このテキスト ファイルを .ps1 という拡張子の付いた名前で適切なフォルダーに保存します。 次に、パスとファイル名を指定して、SharePoint管理シェル コマンド プロンプトからスクリプトを実行します。 コマンド例を次に示します。

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

どちらの場合も、次のように表示されるはずです。

![SharePointオンライン サイト グループ。](../media/SPO-site-groups.png)

これらは、サイト用に作成されたグループすべて、およびそれらのグループに割り当てられている `https://litwareinc.sharepoint.com/sites/finance` すべてのユーザーです。 グループ名とメンバーの見分けがつくように、グループ名は黄色で表示されます。

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
