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
description: サイトの移動をスケジュールする方法や、ユーザーに期待を伝える方法など、OneDrive サイトを別の地理的な場所に移動する方法について説明します。
ms.openlocfilehash: f0a9e319d20c7b56701d776e85a0618ed30e5f78
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569603"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>別の地域の場所に OneDrive サイトを移動する

OneDrive geo 移動では、ユーザーのOneDriveを別の地理的な場所に移動できます。 OneDrive geo 移動は、SharePoint Online 管理者またはMicrosoft 365 グローバル管理者によって実行されます。 OneDrive geo 移動を開始する前に、移動中のOneDriveを持つユーザーに必ず通知し、移動中にすべてのファイルを閉じることをお勧めします。 (ユーザーが移動中にOffice クライアントを使用してドキュメントを開いている場合は、移動の完了時にドキュメントを新しい場所に保存する必要があります)。必要に応じて、今後の移動をスケジュールできます。

OneDrive サービスは、Azure Blob Storageを使用してコンテンツを格納します。 ユーザーのOneDriveに関連付けられているStorage BLOB は、ユーザーが使用できる宛先OneDriveから 40 日以内に、ソースから移行先の地域の場所に移動されます。 ユーザーのOneDriveへのアクセスは、宛先OneDriveが使用可能になるとすぐに復元されます。

OneDrive geo 移動ウィンドウ (約 2 ~ 6 時間) の間、ユーザーのOneDriveは読み取り専用に設定されます。 ユーザーは引き続き、OneDrive 同期 アプリまたは SharePoint Online のOneDrive サイトを介してファイルにアクセスできます。 OneDrive geo 移動が完了すると、Microsoft 365 アプリ 起動ツールのOneDriveに移動すると、ユーザーは自動的に移動先の地域の場所でOneDriveに接続されます。 同期アプリは、新しい場所から自動的に同期を開始します。

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

OneDrive geo 移動を実行するには、テナント管理者はまず、ユーザーの優先データの場所 (PDL) を適切な地理的な場所に設定する必要があります。 PDL が設定されたら、PDL 更新プログラムが地理的な場所間で同期されるまで少なくとも 24 時間待ってから、OneDrive geo の移動を開始します。

geo move コマンドレットを使用する場合は、次の構文を使用して、ユーザーの現在のOneDrive geo の場所にある SPO Service に接続します。

```powershell
Connect-SPOService -url https://<tenantName>-admin.sharepoint.com
```

たとえば、ユーザー 'Matt@contosoenergy.onmicrosoft.com' のOneDriveを移動するには、ユーザーのOneDriveが EUR geo の場所であるため、EUR SharePoint管理センターに接続します。

```powershell
Connect-SPOService -url https://contosoenergyeur-admin.sharepoint.com
```

![connect-sposervice コマンドレットを示す PowerShell ウィンドウのスクリーンショット。](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>環境の検証

OneDrive 地域移動の開始前に、目的の環境を検証するようにお勧めします。

すべての地域の場所に互換性があることを確認するために、次のコマンドレットを実行します。

```powershell
Get-SPOGeoMoveCrossCompatibilityStatus
```

地域の場所のリストが表示され、その場所間でコンテンツを移動できるかどうかが「互換性あり」として示されます。 コマンドが「互換性なし」を返した場合は、後日、状態の検証をあとでもう一度お試しください。

たとえば、サブサイトが含まれている場合、OneDrive は移動できません。 OneDrive が移動可能かどうかを検証するには、-ValidationOnly パラメーターを指定した Start-SPOUserAndContentMove コマンドレットを使用してください。

```powershell
Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly
```

OneDrive の移動が可能な状態になっている場合は Success が返されます。移動を妨げる訴訟ホールドまたはサブサイトがある場合は Fail が返されます。OneDrive が移動できる状態になっていることを確認したら、移動を開始します。

## <a name="start-a-onedrive-geo-move"></a>OneDrive 地域移動の開始

移動を開始するには、次のコマンドレットを実行します。

```powershell
Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>
```

次に示すパラメーターを使用します。

- _UserPrincipalName_: 移動する OneDrive を所有するユーザーの UPN です。
- _DestinationDataLocation_ – OneDriveを移動する必要があるGeo-Location。 これは、ユーザーが優先するデータの場所と同じである必要があります。

たとえば、matt@contosoenergy.onmicrosoft.com の OneDrive を EUR から AUS に移動するには、次のコマンドレットを実行します。

```powershell
Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS
```

![コマンドレットを示す PowerShell ウィンドウStart-SPOUserAndContentMoveスクリーンショット。](../media/move-onedrive-between-geo-locations-image2.png)

将来の地域移動をスケジュールするには、次に示すパラメーターのいずれかを使用します。

- _PreferredMoveBeginDate_: 移動は、この指定時刻に開始されると見込まれます。時刻は、協定世界時 (UTC) で指定する必要があります。
- _PreferredMoveEndDate_: 移動は、最善努力の原則で、この指定時刻に完了すると見込まれます。時刻は、協定世界時 (UTC) で指定する必要があります。

## <a name="cancel-a-onedrive-geo-move"></a>OneDrive 地域移動のキャンセル

コマンドレットを使用して移動が進行中でなければ、または完了していない場合は、ユーザーのOneDriveの geo 移動を停止できます。

```powershell
Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>
```

_UserPrincipalName_ は、移動を停止する OneDrive の所有ユーザーの UPN です。

## <a name="determining-current-status"></a>現在の状態の確認

Get-SPOUserAndContentMoveState コマンドレットを使用して、接続している geo 内または外へのOneDrive geo の移動の状態を確認できます。

移動状況については、次に示す表で説明します。

|状態|説明|
|---|---|
|NotStarted|移動が開始されていません|
|InProgress (*n*/4)|この移動は、次のいずれかの状態で進行中です。 <ul><li>検証 (1/4)</li><li>バックアップ (2/4)</li><li>復元 (3/4)</li><li>クリーンアップ (4/4)</li></ul>|
|Success|移動は正常に完了しています。|
|Failed|移動は失敗しました。|

特定のユーザーの移動の状態を確認するには、 *UserPrincipalName* パラメーターを使用します。

```powershell
Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>
```

接続先の地理的位置に出入りするすべての移動の状態を確認するには、次のいずれかの値を指定して *MoveState* パラメーターを使用します。NotStarted、InProgress、Success、Failed、All。

```powershell
Get-SPOUserAndContentMoveState -MoveState <value>
```

移動状態の詳細な説明については、 *Verbose* パラメーターを追加することもできます。

## <a name="user-experience"></a>ユーザー エクスペリエンス

ユーザーの OneDrive を別の地域の場所に移動する場合は、OneDrive のユーザーに最小限の説明についての通知が必要です。移動中は読み取り専用の状態になることの説明に加えて、既存のリンクとアクセス許可は移動の完了後に引き続き期待どおりに動作することも説明します。

### <a name="users-onedrive"></a>ユーザーの OneDrive。

移動の進行中、ユーザーのOneDriveは読み取り専用に設定されます。 移動が完了すると、ユーザーは、Microsoft 365 アプリ起動ツールまたは Web ブラウザー OneDriveに移動すると、新しい地理的な場所のOneDriveに移動します。

### <a name="permissions-on-onedrive-content"></a>OneDrive コンテンツに対するアクセス許可

コンテンツをOneDriveするアクセス許可を持つユーザーは、移動中および完了後も引き続きコンテンツにアクセスできます。

### <a name="onedrive-sync-app"></a>OneDrive 同期 アプリ

OneDrive 同期 アプリは、OneDrive geo の移動が完了すると、同期を自動的に検出して新しいOneDriveの場所にシームレスに転送します。 ユーザーは、もう一度サインインしたり、他のアクションを実行したりする必要はありません。  (バージョン 17.3.6943.0625 以降の同期アプリが必要です。

OneDrive geo 移動の進行中にユーザーがファイルを更新した場合、同期アプリは、移動の進行中にファイルのアップロードが保留中であることを通知します。

### <a name="sharing-links"></a>共有リンク

OneDrive 地域移動の完了時に、移動されたファイルの既存の共有リンクは、新しい地域の場所に自動的にリダイレクトされるようになります。

### <a name="onenote-experience"></a>OneNote エクスペリエンス

OneNote win32 クライアントと UWP (ユニバーサル) アプリは、OneDrive 地域移動の完了後に、自動的に新しい OneDrive の場所を検出してシームレスにノートブックを同期します。ユーザーは、再度サインインするなどの操作を一切実行する必要がありません。ユーザーが認識できることは、OneDrive 地域移動が進行中のときにノートブックの同期が失敗することのみです。このエクスペリエンスは、次に示す OneNote クライアントのバージョンで利用できます。

- OneNote win32: バージョン 16.0.8326.2096 (以降)
- OneNote UWP: バージョン 16.0.8431.1006 (以降)
- OneNote モバイル アプリ: バージョン 16.0.8431.1011 (以降)

### <a name="teams-app"></a>Teams アプリ

OneDrive 地域移動の完了時に、ユーザーは Teams アプリで OneDrive ファイルにアクセスできます。さらに、地域移動の前に OneDrive から Teams チャットで共有したファイルは、移動の完了後も引き続き操作できます。

### <a name="onedrive-mobile-app-ios"></a>OneDrive モバイル アプリ (iOS)

OneDrive 地域移動の完了時に、ユーザーは、新しい OneDrive の場所に同期するために、iOS モバイル アプリでサインアウトしてから再度サインインする必要があります。

### <a name="existing-followed-groups-and-sites"></a>既存のフォロー対象グループおよびサイト

フォローしているサイトとグループは、地理的な場所に関係なく、ユーザーのOneDriveに表示されます。 別の地域でホストされているサイトとグループは、別のタブで開きます。

### <a name="delve-geo-url-updates"></a>geo URL の更新をDelveする

ユーザーは、OneDriveが新しい geo に移動された後にのみ、PDL に対応するDelve geo に送信されます。
