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
ms.openlocfilehash: 1e62446054f91ff5d2c99520ca65c1681d899ac9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272074"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a>SharePoint Portal 起動スケジューラを使用してポータルを起動する

ポータルは、トラフィックが多いイントラネット上の SharePoint コミュニケーション サイトです。これは、数週間の間に 10,000 人から 100,000 人を超える視聴者を持つサイトです。 ポータル起動スケジューラを使用してポータルを起動し、新しい SharePoint ポータルにアクセスするときにユーザーがスムーズに表示できます。
<br>
<br>
ポータル起動スケジューラは、ウェーブでビューアーをバッチ処理し、新しいポータルの URL リダイレクトを管理することで、段階的なロールアウトアプローチに従うのに役立ちます。 各ウェーブの起動中に、ユーザーフィードバックを収集し、ポータルのパフォーマンスを監視し、起動を一時停止して問題を解決してから、次のウェーブに進みます。 SharePoint でポータルの起動 [を計画する方法の詳細について説明します](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)。 

**リダイレクトには、次の 2 種類があります。**

- **双方向**: 新しい最新の SharePoint ポータルを起動して、既存の SharePoint クラシック ポータルまたはモダン ポータルを置き換える
- **一時ページへのリダイレクト**: 既存の SharePoint ポータルを使用して新しい最新の SharePoint ポータルを起動する

サイトのアクセス許可は、起動の一環としてウェーブとは別に設定する必要があります。 たとえば、組織全体のポータルをリリースする場合は、アクセス許可を "外部ユーザーを除くすべてのユーザー" に設定し、セキュリティ グループを使用してユーザーをウェーブに分けられます。 ウェーブにセキュリティ グループを追加しても、そのセキュリティ グループはサイトにアクセスできます。 


> [!NOTE]
> - この機能は、2021年 5 月から対象リリースのお客様向け SharePoint コミュニケーション サイトのホーム ページの [設定] パネルからアクセス可能になり、2021 年 7 月までにはすべてのお客様が利用できる予定です。
> - このツールの PowerShell バージョンは現在利用できます
> - この機能は、最新の SharePoint 通信サイトでのみ使用できます。
> - ポータルの起動をカスタマイズおよびスケジュールするには、サイトのサイト所有者のアクセス許可が必要です
> - 起動は少なくとも 7 日前にスケジュールする必要があります。各ウェーブは 1 日から 7 日間続く場合があります。
> - 必要なウェーブの数は、予想されるユーザー数によって自動的に決定されます。 
> - ポータルの起動をスケジュールする前に、サイトのホーム ページが正常な状態にあるか確認するために [、SharePoint](https://aka.ms/perftool) 用ページ診断ツールを実行する必要があります。
> - 起動の最後に、サイトへのアクセス許可を持つすべてのユーザーが新しいサイトにアクセスできます
> - 組織で Viva [Connections](https://docs.microsoft.com/SharePoint/viva-connections)を使用している場合、Microsoft Teams アプリ バーに組織のアイコンが表示される場合があります。ただし、アイコンが選択されている場合、ユーザーはウェーブが起動するまでポータルにアクセスできません。
> - この機能は、Office 365 ドイツ、Office 365 21Vianet (中国)、または Microsoft 365 US Government プランでは使用できません。

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a>ポータル起動スケジューラ オプションの違いを理解します。

以前は、ポータルの起動は SharePoint PowerShell を通じてのみスケジュールできます。 これで、ポータルの起動のスケジュールと管理に役立つ 2 つのオプションがあります。 両方のツールの主な違いについて説明します。

**SharePoint PowerShell のバージョン:**

- SharePoint PowerShell を使用するには、 [管理者の資格情報が必要です](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) 
- 1 つのウェーブの最小要件 
- 協定世界時 (UTC) タイム ゾーンに基づいて起動をスケジュールする

**製品内バージョン:**

- サイト所有者の資格情報が必要です 
- 2 つのウェーブの最小要件
- 地域の設定に示されているポータルのローカル タイム ゾーンに基づいて起動をスケジュールする



## <a name="get-started-using-the-portal-launch-scheduler"></a>ポータル起動スケジューラの使用を開始する

1.  ポータル起動スケジューラ ツールを使用する[](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658)前に、サイトの所有者、サイト メンバー、または訪問者としてサイトのアクセス許可を使用して、このサイトにアクセスする必要があるすべてのユーザーを追加します。

2.  次に、ポータル起動スケジューラにアクセスして、次のいずれかの方法でポータルの起動のスケジュールを開始します。

    **オプション 1:** ホーム ページへの変更を編集して再発行する最初の数回 (またはホーム ページ バージョン 3.0 まで) は、ポータル起動スケジューラ ツールの使用を求めるメッセージが表示されます。 [起動 **のスケジュール] を** 選択して、スケジュールを進め続けろ。 または、[ **再公開] を選択** して、起動をスケジュールせずにページの編集内容を再発行します。
    
    ![ホーム ページの再発行時にポータル起動スケジューラを使用するプロンプトのイメージ](../media/portal-launch-republish-2.png)
    
    **オプション 2**: いつでも SharePoint コミュニケーション サイトのホーム ページに移動し、[設定] を選択し、[サイトの起動のスケジュール] を選択して、ポータルの起動をスケジュールできます。
    
    ![[サイトの起動をスケジュールする] が強調表示された [設定] ウィンドウのイメージ](../media/portal-launch-settings-2.png)

3.  次に、ポータルの正常性スコアを確認し、ポータルが正常なスコアを受け取るまで [、必要](https://aka.ms/perftool) に応じて SharePoint 用ページ診断ツールを使用してポータルを **改善** します。 さらに **[次へ]** を選択します。

    ![ポータル起動スケジューラ ツールのイメージ](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > サイト名と説明をポータル起動スケジューラから編集することはできません。代わりに、[設定] を選択し、ホーム ページから [サイト情報] を選択して変更できます。
 
4.  ドロップダウンから **[予想されるユーザー数** ] を選択します。 この図は、サイトへのアクセスが必要な可能性が高いユーザーの数を表しています。 ポータル起動スケジューラは、次のような予想されるユーザーに応じて、最適なウェーブ数を自動的に決定します。
    
    - 10k 未満のユーザー: 2 つのウェーブ
    - 10k ~ 30k のユーザー: 3 つの波 
    - 30k 以上から 100k のユーザー: 5 つのウェーブ
    - 100,000 人を超えるユーザー: 5 つのウェーブと Microsoft アカウント チームに問い合わせ

5.  次に、必要な **リダイレクトの種類を** 決定します。

    **オプション 1:** ユーザーを既存の SharePoint ページに送信する (双方向) – 新しい最新の SharePoint ポータルを起動して既存の SharePoint ポータルを置き換える場合は、このオプションを使用します。 アクティブなウェーブのユーザーは、古いサイトと新しいサイトに移動するかどうかに関係なく、新しいサイトにリダイレクトされます。 新しいサイトにアクセスしようとする起動されていないウェーブのユーザーは、ウェーブが起動されるまで古いサイトにリダイレクトされます。
    
    > [!NOTE] 
    > 双方向オプションを使用する場合、起動をスケジュールするユーザーは、他の SharePoint ポータルに対するサイト所有者のアクセス許可も持っている必要があります。
       
    **オプション 2: 自動** 生成された一時ページ (一時ページリダイレクト) にユーザーを送信する – 既存の SharePoint ポータルが存在しない場合は、一時的なページ リダイレクトを使用する必要があります。 ユーザーは新しい最新の SharePoint ポータルに移動し、ユーザーが起動されていないウェーブの場合は、一時的なページにリダイレクトされます。
    
    **オプション 3: ユーザーを外部ページ** に送信する – ユーザーのウェーブが開始されるまで、一時的なランディング ページ エクスペリエンスに外部 URL を提供します。
    
6.  対象ユーザーをウェーブに分割します。 ウェーブごとに最大 20 のセキュリティ グループを追加します。 ウェーブの詳細は、各ウェーブが起動するまで編集できます。 各ウェーブは、少なくとも 1 日 (24 時間) および最大 7 日間続きます。 これにより、SharePoint と技術環境は、大量のサイト ユーザーに順化して拡張できます。 UI を使用して起動をスケジュールする場合、タイム ゾーンはサイトの地域設定に基づいて行います。 

    >[!NOTE] 
    > - ポータル起動スケジューラは、最小 2 ウェーブに自動的に既定で設定されます。 ただし、このツールの PowerShell バージョンでは、1 ウェーブが許可されます。
    >  - Microsoft 365 グループは、このバージョンのポータル起動スケジューラではサポートされていません。

7. サイトをすぐ表示する必要があるユーザーを特定し、[ウェーブから除外するユーザー] フィールドに情報 **を入力** します。 これらのユーザーはウェーブから除外され、起動前、起動中、または起動後にはリダイレクトされません。

8.  ポータルの起動の詳細を確認し、[スケジュール] を **選択します**。 起動がスケジュールされると、SharePoint ポータルのホーム ページに対する変更は、ポータルの起動が再開される前に、正常な診断結果を受け取る必要があります。


## <a name="make-changes-to-a-scheduled-portal-launch"></a>スケジュールされたポータルの起動に変更を加える

起動の詳細は、ウェーブの起動日までウェーブごとに編集できます。 

1.  ポータルの起動の詳細を編集するには、[設定] に移動 **し、[** サイトの起動のスケジュール **] を選択します**。
2.  次に、[編集] **を選択します**。
3.  編集が完了したら、[更新] を **選択します**。


## <a name="delete-a-scheduled-portal-launch"></a>スケジュールされたポータルの起動を削除する

ポータル起動スケジューラ ツールを使用してスケジュールされた起動は、一部のウェーブが既に起動されている場合でも、いつでもキャンセルまたは削除できます。

1.  ポータルの起動をキャンセルするには、[設定] と [サイト **の起動の** スケジュール **] に移動します**。

2.  次に、[ **削除] を選択** し、下にメッセージが表示された場合は、[削除] を再度 **選択** します。

    ![ポータル起動スケジューラ ツールのイメージ](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a>PowerShell Portal 起動スケジューラを使用する

SharePoint Portal 起動スケジューラ ツールは、もともと [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) 経由でのみ利用可能であり、この方法を好むお客様には PowerShell を通じて引き続きサポートされます。 この記事の冒頭の同じメモは、ポータル起動スケジューラの両方のバージョンに適用されます。 

>[!NOTE]
> SharePoint PowerShell を使用するには、管理者のアクセス許可が必要です。
> PowerShell で作成された起動のポータル起動の詳細が表示され、SharePoint の新しいポータル起動スケジューラ ツールで管理できます。


### <a name="app-setup-and-connecting-to-sharepoint-online"></a>アプリのセットアップと SharePoint Online への接続
1. [最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > SharePoint Online 管理シェルの以前のバージョンがインストールされている場合は、[プログラムの追加と削除] に移動して、"SharePoint Online 管理シェル" をアンインストールします。 <br>ダウンロード センター ページで言語を選択して、[ダウンロード] ボタンをクリックします。 x64 .msi ファイルまたは x86 .msi ファイルのどちらをダウンロードするかを選択するよう求められます。 Windows の 64 ビット版を実行している場合は x64 ファイルを、32 ビット版を実行している場合は x86 ファイルをそれぞれダウンロードします。 不明な場合には、「[実行している Windows オペレーティング システムの確認方法](https://support.microsoft.com/help/13443/windows-which-operating-system)」を参照してください。 ファイルをダウンロードしたら、それを実行して、セットアップ ウィザードの手順に従います。

2. Microsoft 365 の[グローバル管理者または SharePoint 管理者](/sharepoint/sharepoint-admin-role)として SharePoint Online に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。


### <a name="view-any-existing-portal-launch-setups"></a>既存のポータル起動セットアップを表示する

既存のポータル起動構成がある場合は、次の情報を参照してください。

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a>サイトでのポータルの起動をスケジュールする

必要なウェーブの数は、予想される起動サイズによって異なります。 
- 10k 未満のユーザー: 1 ウェーブ
- 10k ~ 30k のユーザー: 3 つの波 
- 30k 以上から 100k のユーザー: 5 つのウェーブ
- 100,000 人を超えるユーザー: 5 つのウェーブと Microsoft アカウント チームに問い合わせ

#### <a name="steps-for-bidirectional-redirection"></a>双方向リダイレクトの手順

双方向リダイレクトでは、新しい最新の SharePoint Online ポータルを起動して、既存の SharePoint クラシック ポータルまたはモダン ポータルを置き換える必要があります。 アクティブなウェーブのユーザーは、古いサイトと新しいサイトに移動するかどうかに関係なく、新しいサイトにリダイレクトされます。 新しいサイトにアクセスしようとする起動されていないウェーブのユーザーは、ウェーブが起動されるまで古いサイトにリダイレクトされます。 

古いサイトの既定のホーム ページと新しいサイトの既定のホーム ページとの間のリダイレクトのみをサポートします。 リダイレクトせずに古いサイトと新しいサイトにアクセスする必要がある管理者または所有者が必要な場合は、パラメーターを使用して一覧に表示 `WaveOverrideUsers` してください。

ユーザーを既存の SharePoint サイトから新しい SharePoint サイトにステージ上で移行するには、次の方法で行います。

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

#### <a name="steps-for-redirection-to-temporary-page"></a>一時ページへのリダイレクトの手順

既存の SharePoint ポータルが存在しない場合は、一時ページリダイレクトを使用する必要があります。 ユーザーは、新しい最新の SharePoint Online ポータルに、ステージ上の方法で指示されます。 ユーザーが起動されていないウェーブの場合、ユーザーは一時ページ (任意の URL) にリダイレクトされます。 

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

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a>サイトでのポータルの起動を一時停止または再起動する

1. 進行中のポータルの起動を一時停止し、今後のウェーブの進行を一時的に防止するには、次のコマンドを実行します。

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. すべてのユーザーが古いサイトにリダイレクトされるのを確認します。 

3. 一時停止されているポータルの起動を再開するには、次のコマンドを実行します。

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. リダイレクトが復元されたのを確認します。 

### <a name="delete-a-portal-launch-on-the-site"></a>サイト上のポータルの起動を削除する

1. 次のコマンドを実行して、サイトのスケジュール済みまたは進行中のポータル起動を削除します。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. すべてのユーザーに対してリダイレクトが実行されなかろうと検証します。

## <a name="learn-more"></a>詳細情報

[SharePoint Online でポータルの起動ロールアウト計画を計画する](./planportallaunchroll-out.md)

[コミュニケーション サイトを計画する](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)