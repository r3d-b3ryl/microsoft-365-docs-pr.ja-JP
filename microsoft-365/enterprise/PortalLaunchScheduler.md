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
description: この記事では、ポータル起動スケジューラを使用してポータルを起動する方法について説明します。
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864878"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>ポータル起動スケジューラを使用してポータルを起動する

ポータルは、イントラネット上の SharePoint サイトであり、サイト上のコンテンツを使用する多数のサイト ビューアーがいます。 ユーザーが新しい SharePoint Online ポータルにアクセスするスムーズで高パフォーマンスのエクスペリエンスを得る上で重要な部分は、ポータルをウェーブで起動する重要な部分です。 

「SharePoint Online でのポータルの立ち上げロールアウト計画の計画」で詳しく説明されている、ポータルを展開するための重要な方法は、ウェーブで起動 [する方法です](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)。 ポータル起動スケジューラは、新しいポータルのリダイレクトを管理することで、ウェーブ/段階的なロールアウトアプローチに従うのに役立ちます。 各ウェーブの間に、ユーザーフィードバックを収集し、展開の各ウェーブ中のパフォーマンスを監視できます。 これには、ポータルの導入が遅いという利点があります。次のウェーブに進む前に問題を一時停止して解決するオプションを提供し、最終的にはユーザーに良いエクスペリエンスを提供できます。 

リダイレクトには、次の 2 種類があります。 
- 双方向: 新しいモダン SharePoint Online ポータルを起動して、既存の SharePoint クラシック ポータルまたはモダン ポータルを置き換える 
- 一時ページリダイレクト: 既存の SharePoint ポータルがない新しい最新の SharePoint Online ポータルを起動する

ポータル起動スケジューラは、最新の SharePoint Online ポータル (コミュニケーション サイト) を起動する場合にのみ使用できます。 起動は少なくとも 7 日前にスケジュールする必要があります。 必要なウェーブの数は、予想されるユーザー数によって決まります。 ポータルの起動をスケジュールする前に [、SharePoint](https://aka.ms/perftool) 用ページ診断ツールを実行して、ポータルのホーム ページが正常な状態を確認する必要があります。 ポータルの起動の最後に、サイトへのアクセス許可を持つすべてのユーザーが新しいサイトにアクセスできます。 

成功したポータルの起動の詳細については、「正常なポータルの作成、起動、保守」で説明されている基本原則、プラクティス、推奨事項に [従ってください](https://docs.microsoft.com/sharepoint/portal-health)。 

> [!NOTE]
> この機能は、Office 365 Germany、21Vianet が運用している Office 365 (中国)、または Microsoft 365 US Government プランでは使用できません。

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>アプリのセットアップと SharePoint Online への接続
1. [最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > SharePoint Online 管理シェルの以前のバージョンがインストールされている場合は、[プログラムの追加と削除] に移動して、"SharePoint Online 管理シェル" をアンインストールします。 <br>ダウンロード センター ページで言語を選択して、[ダウンロード] ボタンをクリックします。 x64 .msi ファイルまたは x86 .msi ファイルのどちらをダウンロードするかを選択するよう求められます。 Windows の 64 ビット版を実行している場合は x64 ファイルを、32 ビット版を実行している場合は x86 ファイルをそれぞれダウンロードします。 不明な場合には、「[実行している Windows オペレーティング システムの確認方法](https://support.microsoft.com/help/13443/windows-which-operating-system)」を参照してください。 ファイルをダウンロードしたら、それを実行して、セットアップ ウィザードの手順に従います。

2. Microsoft 365 の[グローバル管理者または SharePoint 管理者](/sharepoint/sharepoint-admin-role)として SharePoint Online に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。


## <a name="view-any-existing-portal-launch-setups"></a>既存のポータル起動セットアップを表示する

既存のポータル起動構成が表示される場合は、次の方法を使用します。

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>サイトでポータルの起動をスケジュールする

必要なウェーブの数は、予想される起動サイズによって異なります。 
- 10k 未満のユーザー: 1 ウェーブ
- 10k から 30k ユーザー: 3 ウェーブ 
- 30k+ ~ 100,000 ユーザー: 5 ウェーブ
- 100,000 人を超えるユーザー: 5 ウェーブ、Microsoft アカウント チームに問い合わせ

### <a name="steps-for-bidirectional-redirection"></a>双方向リダイレクトの手順

双方向リダイレクトでは、新しい最新の SharePoint Online ポータルを起動して、既存の SharePoint クラシック ポータルまたはモダン ポータルを置き換える必要があります。 アクティブなウェーブのユーザーは、古いサイトに移動するか新しいサイトに移動するかに関係なく、新しいサイトにリダイレクトされます。 起動されていないウェーブで新しいサイトにアクセスしようとするユーザーは、Wave が起動されるまで古いサイトにリダイレクトされます。 

古いサイトの既定のホーム ページと新しいサイトの既定のホーム ページとの間のリダイレクトのみをサポートしています。 リダイレクトせずに古いサイトと新しいサイトにアクセスする必要がある管理者または所有者が必要な場合は、そのサイトがパラメーターを使用して一覧に表示されている必要 `WaveOverrideUsers` があります。

既存の SharePoint サイトから新しい SharePoint サイトにユーザーを段階的に移行するには、次の方法を使用します。

1. 次のコマンドを実行して、ポータル起動ウェーブを指定します。
   
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

2. 完全な検証。 リダイレクトがサービス全体で構成を完了するには、5 ~ 10 分かかる場合があります。 

### <a name="steps-for-redirection-to-temporary-page"></a>一時ページへのリダイレクトの手順

既存の SharePoint ポータルが存在しない場合は、一時的なページ リダイレクトを使用する必要があります。 ユーザーは、新しい最新の SharePoint Online ポータルに、段階を通して指示されます。 起動されていないウェーブ内のユーザーは、一時ページ (任意の URL) にリダイレクトされます。 

1. 次のコマンドを実行して、ポータル起動ウェーブを指定します。
   
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

2. 完全な検証。 リダイレクトがサービス全体で構成を完了するには、5 ~ 10 分かかる場合があります。 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>サイトでポータルの起動を一時停止または再開する

1. 進行中のポータルの起動を一時停止し、今後のウェーブの進行を一時的に防ぐには、次のコマンドを実行します。

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. すべてのユーザーが古いサイトにリダイレクトされるのを検証します。 

3. 一時停止したポータルの起動を再開するには、次のコマンドを実行します。

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. リダイレクトが復元された状態を検証します。 

## <a name="delete-a-portal-launch-on-the-site"></a>サイトでポータルの起動を削除する

1. 次のコマンドを実行して、サイトのポータル起動のスケジュールまたは進行中を削除します。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. すべてのユーザーに対してリダイレクトが実行されなにかを検証します。

## <a name="learn-more"></a>詳細情報
[SharePoint Online でポータルの起動のロールアウト計画を計画する](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
