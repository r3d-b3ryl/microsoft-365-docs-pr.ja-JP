---
title: ポータル起動スケジューラを使用してポータルを起動する
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: この記事では、ポータルの起動スケジューラを使用してポータルを起動する方法について説明します。
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999598"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>ポータル起動スケジューラを使用してポータルを起動する

ポータルの起動スケジューラを使用してポータルを起動するには、最初にテナント管理者が新しいポータルのウェーブをセットアップできるかどうかを検証します。 その後、管理者は、アクティブな wave 内のユーザーの存在に基づいて、要求のリダイレクトを検証できます。

ポータルを正常に起動する方法の詳細については、「基本的な原則、プラクティス、および [正常なポータルの作成、起動](https://go.microsoft.com/fwlink/?linkid=2105838)、および保守」で詳細に説明されている手順を実行してください。 

## <a name="app-setup"></a>アプリのセットアップ
1. コントロールパネルを使用してコンピューターに既存のがある場合は、アンインストール `Microsoft.Online.SharePoint.PowerShell` します。
2. PowerShell パス `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` 。

## <a name="connect-to-sharepoint-online"></a>SharePoint Online に接続する
1. Windows で [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) を開きます。
2. 管理者としてテナントに接続します。
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  プロンプトが表示されたら、パスワードを入力します。

## <a name="command-to-get-an-existing-setup"></a>既存の設定を取得するコマンド

既存のポータル起動構成を表示するには、次のようにします。

1. 合格 `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` です。
2. `-DisplayFormat Raw`生の入力形式として書式設定された wave コレクションを表示する場合は、追加のパラメーターを渡します。

## <a name="commands-for-bi-directional-redirection"></a>双方向リダイレクトのコマンド

古いサイトユーザーを段階的な方法で新しいサイトに移行するには、次のようにします。

1. ポータルの発表波を作成します。
   - これは、早期リリースのテストフェーズでのみ適用されます。
   - 変更の影響をすぐにテストするには、最初の wave `LaunchDateUtc` が現在の日付に設定されていることを確認します。 このフラグを指定しないと、エラーメッセージが表示されます。 このエラーは、運用環境での起動を少なくとも7日前にスケジュールする必要があるために発生します。

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 検証を完了します。
  - リダイレクトがサービス全体にわたる構成を完了するには最大5分かかる場合があるため、続行する前にお待ちください。
  - として指定されたユーザーでログインした場合は `WaveOverrideUsers` 、何も変更されません。 移動先のサイトが表示されるようにする必要があります。
  - 閲覧者の *SG1* の一部であるユーザーを使用してログインします。
    - 古いサイトに移動し、新しいサイトにリダイレクトする必要があります。
    - 新しいサイトに移動して、新しいサイトにとどまる必要があります。
    - *閲覧者 SG2* でユーザーと共にログオンし、古いサイトに移動して古いサイトを維持します。
    - 新しいサイトに移動して、古いサイトにリダイレクトする必要があります。

3. ポータルの起動を一時停止します。
  - 発表波を一時停止する必要がある場合は、[x] 個の日数の間、一時停止することができます。 `Status`フラグを pause に設定すると、すべての今後の wave progressions が禁止されます。 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - これにより、すべてのユーザーが古いサイトにリダイレクトされることを検証します。

4. ポータルの起動の進行状況を再起動します。 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - リダイレクトが復元されるようになったことを検証します。

5. ポータル起動セットアップを削除します。
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - すべてのユーザーに対してリダイレクトが発生しないことを検証します。

## <a name="commands-for-redirection-to-temporary-page"></a>一時ページにリダイレクトするためのコマンド

以前のサイトがなく、新しいポータルページのランディングからのユーザーではないユーザーを省略する場合は、次の手順を実行します。

任意のサイトに一時ページを作成するには、次のようにします。

1. ポータルの起動波形を作成します。
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 検証を完了します。

  - 処理が完了するまでに最大5分かかる場合があるため、5分間待機してから続行します。
  - *ビューアー* の一部であるユーザーとログを記録します。
     - 新しいサイトに移動して、新しいサイトにとどまる必要があります。
     - Temp ページに移動すると、temp ページが表示されたままになります。
  - *ビューアーの SG2* の一部であるユーザーとログを記録します。
     - 新しいサイトに移動し、temp ページにリダイレクトされる必要があります。
     - Temp ページに移動すると、temp ページが表示されたままになります。

3. ポータル起動セットアップを削除します。
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - すべてのユーザーに対してリダイレクトが発生しないことを検証します。

## <a name="learn-more"></a>詳細情報
[SharePoint Online でポータルの起動ロールアウトプランを計画する](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)