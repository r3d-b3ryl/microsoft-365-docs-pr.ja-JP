---
title: 別の地域の場所に OneDrive サイトを移動する
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: サイトの移動をスケジュールするOneDrive、ユーザーに期待を伝える方法など、さまざまな地域の場所にサイトを移動する方法に関する情報を確認します。
ms.openlocfilehash: 232654ac0cea95fee6dfef036ecb87768e5768d9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195355"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>別の地域の場所に OneDrive サイトを移動する 

地理OneDrive移動を使用すると、ユーザーのデータを別OneDrive場所に移動できます。 OneDriveの移動は、オンライン管理者またはSharePoint管理者によってMicrosoft 365されます。 位置情報の移動をOneDriveする前に、OneDrive が移動中のユーザーに通知し、移動中のすべてのファイルを閉じすることをお勧めします。 (ユーザーが移動中に Office クライアントを使用してドキュメントを開いている場合は、移動が完了したら、ドキュメントを新しい場所に保存する必要があります)。必要に応じて、移動を将来の時間にスケジュールできます。

サービスOneDrive Azure Blob を使用してStorageを格納します。 ユーザー Storageに関連付けられている OneDrive BLOB は、ユーザーが使用できる宛先の場所から 40 日以内に、OneDrive場所に移動されます。 ユーザーのサーバーへのアクセスはOneDriveが利用可能になるとすぐにOneDrive復元されます。

地理的OneDrive移動ウィンドウ (約 2 ~ 6 時間) の間、ユーザーのOneDriveは読み取り専用に設定されます。 ユーザーは引き続き、OneDrive 同期 オンラインのアプリまたはOneDriveサイトをSharePointできます。 地理OneDrive移動が完了すると、ユーザーが Microsoft 365 アプリ 起動ツールで OneDrive に移動すると、ユーザーは移動先の地域の場所で OneDrive に自動的に接続されます。 同期アプリは、新しい場所から自動的に同期を開始します。

この記事の手順には、[Microsoft Office SharePoint Online の PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=35588)が必要になります。

## <a name="communicating-to-your-users"></a>ユーザーへの連絡

OneDrive サイトの地理的場所を移動する際には、想定される動作についてユーザーに通知することが重要です。これは、ユーザーが混乱してヘルプ デスクに問い合わせる可能性を減らすのに役立ちます。移動の前に、次の情報について電子メールでユーザーに連絡してください。

- 移動開始予定時刻と予定所要時間
- ユーザーの OneDrive の移動先となる地理的場所、および新しい場所にアクセスするための URL
- 移動中はファイルを閉じた状態にし、編集を加えてはならないこと。
- 移動してもファイルの許可と共有は変更されないこと。
- [複数地理環境でのユーザー エクスペリエンス](multi-geo-user-experience.md)として期待されること

移動が正常に終了した時点で、ユーザーに対し、OneDrive での作業を再開できることを伝える電子メールを送信するようにしてください。

## <a name="scheduling-onedrive-site-moves"></a>OneDrive サイトの移動のスケジュール設定

OneDrive サイトの移動を事前にスケジュールすることができます (この記事の後半でご説明いたします)。少数のユーザーの移動から始め、ワークフローと連絡手順を確認することをお勧めします。プロセスが満足できるものであった場合、次のように移動をスケジュールします。

- 一度に最大 4,000 件の移動をスケジュールすることができます。
- 移動開始後はスケジュールを追加でき、常時最大 4,000 件の保留中の移動をキューに置いておけます。
- 移動できる OneDrive の最大サイズは 1 テラバイト (1 TB) です。

## <a name="moving-a-onedrive-site"></a>OneDrive サイトの移動

地域移動をOneDriveするには、テナント管理者が最初にユーザーの優先データの場所 (PDL) を適切な地理的位置に設定する必要があります。 PDL が設定された後、PDL 更新プログラムが地理的位置間で同期するまで少なくとも 24 時間待機してから、OneDriveを開始します。

geo move コマンドレットを使用する場合は、次の構文を使用して、ユーザーの現在の場所OneDrive SPO Service に接続します。

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

たとえば、ユーザー OneDrive 'Matt@contosoenergy.onmicrosoft.com' の場所を移動するには、ユーザーのOneDriveが EUR 地域の場所にあるとき、EUR SharePoint 管理センターに接続します。

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![connect-sposervice コマンドレットを示す PowerShell ウィンドウのスクリーンショット。](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>環境の検証

OneDrive 地域移動の開始前に、目的の環境を検証するようにお勧めします。

すべての地域の場所に互換性があることを確認するために、次のコマンドレットを実行します。

`Get-SPOGeoMoveCrossCompatibilityStatus`

地域の場所のリストが表示され、その場所間でコンテンツを移動できるかどうかが「互換性あり」として示されます。 コマンドが「互換性なし」を返した場合は、後日、状態の検証をあとでもう一度お試しください。

たとえば、サブサイトが含まれている場合、OneDrive は移動できません。 OneDrive が移動可能かどうかを検証するには、-ValidationOnly パラメーターを指定した Start-SPOUserAndContentMove コマンドレットを使用してください。

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

OneDrive の移動が可能な状態になっている場合は Success が返されます。移動を妨げる訴訟ホールドまたはサブサイトがある場合は Fail が返されます。OneDrive が移動できる状態になっていることを確認したら、移動を開始します。

## <a name="start-a-onedrive-geo-move"></a>OneDrive 地域移動の開始

移動を開始するには、次のコマンドレットを実行します。  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

次に示すパラメーターを使用します。

-   _UserPrincipalName_: 移動する OneDrive を所有するユーザーの UPN です。

-   _DestinationDataLocation_ – Geo-Location移動するOneDriveする必要がある場所を指定します。 これは、ユーザーの優先データの場所と同じである必要があります。

たとえば、matt@contosoenergy.onmicrosoft.com の OneDrive を EUR から AUS に移動するには、次のコマンドレットを実行します。

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![コマンドレットを示す PowerShell ウィンドウStart-SPOUserAndContentMoveします。](../media/move-onedrive-between-geo-locations-image2.png)

将来の地域移動をスケジュールするには、次に示すパラメーターのいずれかを使用します。

-   _PreferredMoveBeginDate_: 移動は、この指定時刻に開始されると見込まれます。時刻は、協定世界時 (UTC) で指定する必要があります。

-   _PreferredMoveEndDate_: 移動は、最善努力の原則で、この指定時刻に完了すると見込まれます。時刻は、協定世界時 (UTC) で指定する必要があります。 

## <a name="cancel-a-onedrive-geo-move"></a>OneDrive 地域移動のキャンセル 

コマンドレットを使用して、移動が進行中または完了していないOneDrive、ユーザーのユーザーのデータの地理的な移動を停止できます。

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

_UserPrincipalName_ は、移動を停止する OneDrive の所有ユーザーの UPN です。

## <a name="determining-current-status"></a>現在の状態の確認

このコマンドレットを使用して、OneDrive接続している geo 内または地域外に移動する場所の状態をGet-SPOUserAndContentMoveStateできます。

移動状況については、次に示す表で説明します。

<table>
<thead>
<tr class="header">
<th align="left">状態</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">NotStarted</td>
<td align="left">移動は開始されていません。</td>
</tr>
<tr class="even">
<td align="left">InProgress (<em>n</em>/4)</td>
<td align="left">移動は、検証 (1/4)、バックアップ (2/4)、復元 (3/4)、クリーンアップ (4/4) のいずれかの状態で進行中です。</td>
</tr>
<tr class="odd">
<td align="left">Success</td>
<td align="left">移動は正常に完了しています。</td>
</tr>
<tr class="even">
<td align="left">Failed</td>
<td align="left">移動は失敗しました。</td>
</tr>
</tbody>
</table>

特定のユーザーの移動の状態を確認するには、UserPrincipalName パラメーターを使用します。

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

接続している地理的位置の移動または移動の状態を確認するには、MoveState パラメーターを使用して、NotStarted、InProgress、Success、Failed、All のいずれかの値を指定します。

`Get-SPOUserAndContentMoveState -MoveState <value>`

また、より詳細な移動状態の説明が示されるように、`-Verbose` パラメーターを追加することもできます。

## <a name="user-experience"></a>ユーザー エクスペリエンス

ユーザーの OneDrive を別の地域の場所に移動する場合は、OneDrive のユーザーに最小限の説明についての通知が必要です。移動中は読み取り専用の状態になることの説明に加えて、既存のリンクとアクセス許可は移動の完了後に引き続き期待どおりに動作することも説明します。

### <a name="users-onedrive"></a>ユーザーの OneDrive。

移動が進行中に、ユーザーのOneDrive読み取り専用に設定されます。 移動が完了すると、ユーザーは OneDrive アプリ 起動ツールまたは web ブラウザーの OneDrive に移動すると、OneDrive Microsoft 365 に移動します。

### <a name="permissions-on-onedrive-content"></a>OneDrive コンテンツに対するアクセス許可

コンテンツに対するアクセスOneDriveユーザーは、移動中および完了した後もコンテンツにアクセスできます。

### <a name="onedrive-sync-app"></a>OneDrive 同期アプリ 

位置情報OneDrive 同期が完了すると、アプリは自動的に同期を検出し、新しい場所OneDrive OneDriveシームレスに転送します。 ユーザーはもう一度サインインしたり、他の操作を行う必要はありません。  (必要な同期アプリのバージョン 17.3.6943.0625 以降)。

ユーザーが位置情報の移動中にファイルを更新したOneDrive同期アプリは、移動の進行中にファイルのアップロードが保留中の状態を通知します。

### <a name="sharing-links"></a>共有リンク 

OneDrive 地域移動の完了時に、移動されたファイルの既存の共有リンクは、新しい地域の場所に自動的にリダイレクトされるようになります。

### <a name="onenote-experience"></a>OneNote エクスペリエンス 

OneNote win32 クライアントと UWP (ユニバーサル) アプリは、OneDrive 地域移動の完了後に、自動的に新しい OneDrive の場所を検出してシームレスにノートブックを同期します。ユーザーは、再度サインインするなどの操作を一切実行する必要がありません。ユーザーが認識できることは、OneDrive 地域移動が進行中のときにノートブックの同期が失敗することのみです。このエクスペリエンスは、次に示す OneNote クライアントのバージョンで利用できます。

-   OneNote win32: バージョン 16.0.8326.2096 (以降)

-   OneNote UWP: バージョン 16.0.8431.1006 (以降)

-   OneNote モバイル アプリ: バージョン 16.0.8431.1011 (以降)

### <a name="teams-app"></a>Teams アプリ

OneDrive 地域移動の完了時に、ユーザーは Teams アプリで OneDrive ファイルにアクセスできます。さらに、地域移動の前に OneDrive から Teams チャットで共有したファイルは、移動の完了後も引き続き操作できます。

### <a name="onedrive-mobile-app-ios"></a>OneDriveモバイル アプリ (iOS) 

OneDrive 地域移動の完了時に、ユーザーは、新しい OneDrive の場所に同期するために、iOS モバイル アプリでサインアウトしてから再度サインインする必要があります。

### <a name="existing-followed-groups-and-sites"></a>既存のフォロー対象グループおよびサイト

フォローされたサイトとグループは、地理的な場所に関係なく、OneDriveに表示されます。 別の地域の場所でホストされているサイトとグループは、別のタブで開きます。

### <a name="delve-geo-url-updates"></a>Delve地域 URL の更新

ユーザーは、ユーザーが新Delveに移動された後にのみ、PDL に対応する OneDriveに送信されます。
