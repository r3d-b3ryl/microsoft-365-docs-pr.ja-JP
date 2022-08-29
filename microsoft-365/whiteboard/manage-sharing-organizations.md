---
title: Microsoft Whiteboard の共有を管理する
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Microsoft Whiteboard の共有を管理する方法について説明します。
ms.openlocfilehash: b5455886067bb343a0a3bbd499f4271bc72971b6
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67383768"
---
# <a name="manage-sharing-for-microsoft-whiteboard"></a>Microsoft Whiteboard の共有を管理する

共有エクスペリエンスは、Teams 会議に参加しているかどうか、共有デバイスを使用している場合、またはテナント レベルの共有設定が有効になっているかどうかによって異なります。 次のシナリオは、Whiteboard が OneDrive for Business ストレージの使用に切り替わる後に作成された新しいホワイトボードにのみ適用されます。 以前に作成したボードは、Azure にまだ保存されている変更はありません。

## <a name="share-in-teams-meetings"></a>Teams 会議で共有する

Teams 会議でホワイトボードを共有すると、ホワイトボードによって共有リンクが作成されます。 このリンクには、組織内のすべてのユーザーがアクセスできます。 ホワイトボードは、会議内のすべてのテナント内ユーザーと共有されます。 ホワイトボードは、既定の設定に関係なく、会社が共有できるリンクを使用して共有されます。 既定の共有リンクの種類のサポートが計画されています。

Teams 会議中に、外部および共有デバイス アカウントによる一時的なコラボレーションの機能が追加されました。 ユーザーは、共有をPowerPoint Liveするのと同様に、会議で共有されているホワイトボードで一時的に表示および共同作業を行うことができます。

この場合、ホワイトボードは Teams 会議中にのみホワイトボードに一時的な表示とコラボレーションを提供します。 共有リンクは作成されておらず、Whiteboard はファイルへのアクセスを許可しません。

OneDrive for Businessに対して外部共有が有効になっている場合は、それ以上のアクションは必要ありません。

OneDrive for Businessの外部共有を制限する場合は、制限を維持し、外部および共有デバイス アカウントを機能させるために新しい設定を有効にするだけで済みます。 そのために、以下の手順に従ってください。

1. 組織で Whiteboard が有効になっていることを確認します。 詳細については、「 [ホワイトボードへのアクセスの管理](manage-whiteboard-access-organizations.md)」を参照してください。

2. PowerShell を使用してテナントに接続し、次のコマンドを実行して SharePoint Online モジュールが更新されていることを確認します。

   ```powershell
   Update-Module -Name Microsoft.Online.SharePoint.PowerShell
   ```

3. 次に、次の **Set-SPOTenant コマンドを** 実行します。

   ```powershell
   Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On
   ```

4. Teams 会議設定 **の匿名ユーザーが会議でアプリと対話できることを確認します** 。 無効にした場合、(ゲストやフェデレーション ユーザーではなく) 匿名ユーザーは会議中にホワイトボードにアクセスできません。

この設定はホワイトボードにのみ適用され、以前に共有された設定である **OneDriveLoopSharingCapability** と **CoreLoopSharingCapability** に置き換えられます。 これらの設定は適用されなくなり、無視できます。

> [!NOTE]
> 既定では、[Teams 会議] 設定 **の [匿名ユーザーは会議でアプリを操作できます** ] が有効になっています。 無効にした場合、(ゲストやフェデレーション ユーザーとは対照的に) 匿名ユーザーは会議中にホワイトボードにアクセスできません。

これらの変更は、テナント全体に適用されるまでに約 60 分かかります。

|シナリオ|ストレージと所有権|共有設定|共有エクスペリエンス|
|---|---|---|---|
|デスクトップまたはモバイル デバイスからホワイトボードを起動する|ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー|Enabled|テナント内ユーザー: 作成、表示、および共同作業が可能<br><br>外部ユーザー: 会議中にのみ表示および共同作業できます (ホワイトボードを共有するボタンは外部ユーザーには表示されません)<br><br>共有デバイス アカウント: 会議中にのみ表示および共同作業できます|
|デスクトップまたはモバイル デバイスからホワイトボードを起動する|ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー|無効|テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: 表示または共同作業できない<br><br>共有デバイス アカウント: 表示または共同作業できない|
|Surface Hub またはMicrosoft Teams Roomsからホワイトボードを起動する|ストレージ: Azure (ホワイトボード ファイルは今後OneDrive for Businessに移動される予定)<br><br>所有者: 会議の参加者|対象外|テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: 会議中にのみ表示および共同作業できます<br><br> 共有デバイス アカウント: 会議中にのみ表示および共同作業できます|

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams チャネルとチャットでタブとして追加する

Teams チャネルまたはチャットのタブとしてホワイトボードを追加すると、ホワイトボードは組織内のすべてのユーザーがアクセスできる共有リンクを作成します。

|シナリオ|ストレージと所有権|共有設定|共有エクスペリエンス|
|---|---|---|---|
|デスクトップまたはモバイル デバイスからホワイトボードをチャネルまたはチャットに追加する|ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー|適用されません (会議にのみ適用されます)|テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: サポートされていません<br><br>Teams ゲスト: サポートされていません<br><br>共有デバイス アカウント: 適用されません|

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard ネイティブ クライアントでの作成と共有

Web、デスクトップ、またはモバイル クライアントからホワイトボードを共有する場合は、特定のユーザーを選択できます。 組織内のすべてのユーザーがアクセスできる共有リンクを作成することもできます。

> [!NOTE]
> Teams 会議中の外部共有はまだ利用できませんが、今後のリリースで追加される予定です。

|シナリオ|ストレージと所有権|共有設定|共有エクスペリエンス|
|---|---|---|---|
|デスクトップまたはモバイル デバイスからホワイトボードを作成する|ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー|適用されません (会議にのみ適用されます)|テナント内ユーザー: 組織内で共有できる<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません|
|Surface Hub からホワイトボードを作成する|ストレージ: ローカル<br><br>所有者: なし (ユーザーがサインインしてボードを保存して共有しない限り、OneDrive for Businessに保存されます。 今後、簡単な共有が追加される予定です。|適用されません (会議にのみ適用されます)|テナント内ユーザー: ユーザーはサインインしてボードを保存して共有する必要があります (Easy share は今後追加される予定です)<br><br>外部ユーザー: Teams 会議の外部では、現時点では外部ユーザーとの共有はサポートされていません|
|Microsoft Teams Roomsからホワイトボードを作成する|まだサポートされていません|適用されません (会議にのみ適用されます)|まだサポートされていません|

## <a name="see-also"></a>関連項目

[ホワイトボードへのアクセスを管理する](manage-whiteboard-access-organizations.md)

[Whiteboard のデータを管理する](manage-data-organizations.md)

[Windows にホワイトボードを展開する](deploy-on-windows-organizations.md)
