---
title: 地域管理者を追加または削除する
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: 地理的な場所ごとに個別の管理者を構成する必要がありますか? Microsoft 365 Multi-Geo で地域管理者を追加または削除する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218764"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo で地域管理者を追加または削除する

テナント内にある地域の場所ごとに個別の管理者を構成することができます。 これらの管理者は、各自の地域の場所に固有の SharePoint Online と OneDrive の設定にアクセスすることができます。

用語ストアなどの一部のサービスは、中央の場所から管理され、サテライトの場所にレプリケートされます。 中央の場所の地域管理者は、これらのサービスにアクセスできますが、サテライトの場所の地理管理者はアクセスできません。

グローバル管理者と SharePoint Online 管理者は、中央の場所とすべてのサテライトの場所の設定に引き続きアクセスできます。

## <a name="configuring-geo-administrators"></a>地域管理者の構成

地域管理者の構成には、SharePoint Online PowerShell モジュールが必要です。

[Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) を使用して、地域管理者を追加する地域の場所の管理センターに接続します。(例: Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)

場所の既存の地域管理者を表示するには、`Get-SPOGeoAdministrator` を実行します。

### <a name="adding-a-user-as-a-geo-admin"></a>地域管理者としてのユーザーの追加

地域管理者としてのユーザーを追加するには、`Add-SPOGeoAdministrator -UserPrincipalName <UPN>` を実行します。

場所の地域管理者としてのユーザーを削除するには、`Remove-SPOGeoAdministrator -UserPrincipalName <UPN>` を実行します。

### <a name="adding-a-group-as-a-geo-admin"></a>地域管理者としてのグループの追加

地域管理者として、セキュリティ グループまたはメールが有効なセキュリティ グループを追加できます。(配布グループと Microsoft 365 グループはサポートされていません。)

地域管理者としてグループを追加するには、`Add-SPOGeoAdministrator -GroupAlias <alias>` を実行します。

地域管理者としてのグループを削除するには、`Remove-SPOGeoAdministrator -GroupAlias <alias>` を実行します。

一部のセキュリティ グループにはグループ エイリアスがないことに注意してください。 エイリアスがないセキュリティ グループを追加する場合は、[Get-MsolGroup](/powershell/module/msonline/get-msolgroup) を実行して、グループの一覧を取得し、セキュリティ グループの ObjectID を検索して、次を実行します。

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

ObjectID を使用してグループを削除するには、`Remove-SPOGeoAdministrator -ObjectID <ObjectID>` を実行します。

## <a name="related-topics"></a>関連項目

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[セキュリティ グループのエイリアス (MailNickName) を設定する](/powershell/module/azuread/set-azureadgroup)