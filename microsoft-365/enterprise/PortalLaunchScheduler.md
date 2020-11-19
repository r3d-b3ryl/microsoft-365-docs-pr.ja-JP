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
ms.openlocfilehash: e5e5850fa7e74f3e3b342e9bb28d17f65b491664
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356669"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>ポータル起動スケジューラを使用してポータルを起動する

ポータルは、イントラネット上の SharePoint サイトであり、サイト上のコンテンツを使用する多数のサイト ビューアーがいます。 ダッシュボードを wave で開始することは、ユーザーが新しい SharePoint Online ポータルにアクセスしてスムーズかつ高性能な環境にアクセスできるようにするための重要な部分です。 

「 [SharePoint Online でポータルの起動を計画する](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)」で説明されているように、wave で起動することは、ポータルをロールアウトするための主要な方法です。 ポータル起動スケジューラは、新しいポータルのリダイレクトを管理することによって、ウェーブ/段階的なロールアウトアプローチに従うのに役立つように設計されています。 各ウェーブでは、ユーザーのフィードバックを収集し、展開の各ウェーブ時にパフォーマンスを監視することができます。 これには、ポータルをゆっくり導入するという利点があり、次の波に進む前に問題を一時停止および解決することができます。また、最終的にユーザーにとっての良好な動作を保証します。 

リダイレクトには、次の2種類があります。 
- 双方向: 新しいモダン SharePoint Online ポータルを起動して既存の SharePoint 従来またはモダンポータルを置き換えます。 
- 一時ページリダイレクト: 既存の SharePoint ポータルを使用しない新しいモダン SharePoint Online ポータルを起動します。

ポータルの起動スケジューラは、モダン SharePoint Online ポータル (つまり、コミュニケーションサイト) を起動するためにのみ使用できます。 起動は、少なくとも7日前にスケジュールする必要があります。 必要な wave の数は、予想されるユーザー数によって決まります。 ポータルの起動をスケジュールする前に、ポータルのホームページが正常であることを確認するために、 [SharePoint 用ページの診断ツール](https://aka.ms/perftool) を実行する必要があります。 ポータルの開始時に、サイトへのアクセス許可を持つすべてのユーザーが新しいサイトにアクセスできるようになります。 

ポータルを正常に起動する方法の詳細については、「基本的な原則」、「プラクティス」、および「 [正常なポータルの作成、起動、保守](https://docs.microsoft.com/sharepoint/portal-health)」に記載されている推奨事項に従ってください。 

> [!NOTE]
> この機能は、Office 365 ドイツ、21Vianet が運用している Office 365、または Microsoft 365 US Government プランでは使用できません。

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>アプリのセットアップと SharePoint Online への接続
1. [最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > SharePoint Online 管理シェルの以前のバージョンがインストールされている場合は、[プログラムの追加と削除] に移動して、"SharePoint Online 管理シェル" をアンインストールします。 <br>ダウンロード センター ページで言語を選択して、[ダウンロード] ボタンをクリックします。 x64 .msi ファイルまたは x86 .msi ファイルのどちらをダウンロードするかを選択するよう求められます。 Windows の 64 ビット版を実行している場合は x64 ファイルを、32 ビット版を実行している場合は x86 ファイルをそれぞれダウンロードします。 不明な場合には、「[実行している Windows オペレーティング システムの確認方法](https://support.microsoft.com/help/13443/windows-which-operating-system)」を参照してください。 ファイルをダウンロードしたら、それを実行して、セットアップ ウィザードの手順に従います。

2. Microsoft 365 の[グローバル管理者または SharePoint 管理者](/sharepoint/sharepoint-admin-role)として SharePoint Online に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。


## <a name="view-any-existing-portal-launch-setups"></a>既存のポータル起動セットアップを表示する

既存のポータル起動構成があるかどうかを確認するには、次のようにします。

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>サイトでポータルの起動をスケジュールする

必要な wave の数は、予想される起動サイズによって異なります。 
- 10k ユーザー未満: 1 wave
- 10k から30k ユーザー: 3 ウェーブ 
- 30k + ~ 10万ユーザー: 5 ウェーブ
- 10万人以上のユーザー: 5 つのウェーブを使用して、Microsoft アカウントチームにお問い合わせください。

### <a name="steps-for-bidirectional-redirection"></a>双方向リダイレクトの手順

双方向のリダイレクトには、既存の SharePoint クラシックまたはモダンポータルを置き換えるために新しいモダン SharePoint Online ポータルを起動する作業が含まれます。 アクティブなウェーブのユーザーは、古いサイトに移動するか、新しいサイトに移動するかに関係なく、新しいサイトにリダイレクトされます。 新しいサイトにアクセスしようとする、開始していない wave のユーザーは、wave が起動されるまで古いサイトにリダイレクトされます。 

以前のサイトと新しいサイトにリダイレクトされずにアクセスする必要がある管理者または所有者が、パラメーターを使用してリストされていることを確認する必要があり `WaveOverrideUsers` ます。 以前のサイトの既定のホームページと、新しいサイトの既定のホームページとの間のリダイレクトのみがサポートされています。

既存の SharePoint サイトから新しい SharePoint サイトにユーザーを段階的に移行するには、次のようにします。

1. ポータルの起動波を指定するには、次のコマンドを実行します。
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

例:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 検証を完了します。 リダイレクトがサービス全体にわたる構成を完了するには、5-10 分かかることがあります。 

### <a name="steps-for-redirection-to-temporary-page"></a>一時ページへのリダイレクトの手順

既存の SharePoint ポータルが存在しない場合は、一時ページリダイレクトを使用する必要があります。 ユーザーは、段階的な方法で新しいモダン SharePoint Online ポータルに転送されます。 ユーザーが起動されていない wave にある場合は、一時ページ (任意の URL) にリダイレクトされます。 

1. ポータルの起動波を指定するには、次のコマンドを実行します。
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

例:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 検証を完了します。 リダイレクトがサービス全体にわたる構成を完了するには、5-10 分かかることがあります。 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>サイトでポータルの起動を一時停止または再開する

1. 進行中のポータルの起動を一時停止し、一時的な wave progressions が発生しないようにするには、次のコマンドを実行します。

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. すべてのユーザーが古いサイトにリダイレクトされていることを確認します。 

3. 一時停止しているポータルの起動を再開するには、次のコマンドを実行します。

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. リダイレクトが復元されるようになったことを検証します。 

## <a name="delete-a-portal-launch-on-the-site"></a>サイト上のポータルの起動を削除する
1. ポータルの起動波形を作成します。
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 次のコマンドを実行して、サイトに対してスケジュールされた、または進行中のポータルの起動を削除します。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. すべてのユーザーに対してリダイレクトが発生しないことを検証します。

## <a name="learn-more"></a>詳細情報
[SharePoint Online でポータルの起動ロールアウトプランを計画する](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
