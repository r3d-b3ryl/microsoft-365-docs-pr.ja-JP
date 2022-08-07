---
title: GCC High 環境で Microsoft Whiteboard の共有を管理する
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
description: GCC High 環境で Microsoft Whiteboard の共有を管理する方法について説明します。
ms.openlocfilehash: ae658b49fc2e712735e8a7e7cb94e8b71f9a2fc2
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67275014"
---
# <a name="manage-sharing-for-microsoft-whiteboard-in-gcc-high-environments"></a>GCC High 環境で Microsoft Whiteboard の共有を管理する

> [!NOTE]
> このガイダンスは、米国政府機関コミュニティ クラウド (GCC) の High 環境に適用されます。 共有エクスペリエンスは、使用されているデバイスとクライアントによって異なります。

## <a name="share-in-teams-meetings"></a>Teams 会議で共有する

Teams 会議でホワイトボードを共有すると、ホワイトボードによって共有リンクが作成されます。 このリンクには、組織内のすべてのユーザーがアクセスできます。 ホワイトボードは、会議内のすべてのテナント内ユーザーと共有されます。 ホワイトボードは、既定の設定に関係なく、会社が共有できるリンクを使用して共有されます。 既定の共有リンクの種類のサポートが計画されています。

会議中に、ほとんどの外部および共有デバイス アカウントによる一時的なコラボレーションの機能が強化されています。 ユーザーは、teams 会議で共有されている場合(PowerPoint Live共有と同様)、ホワイトボードで一時的に表示および共同作業できます。

この場合、ホワイトボードは Teams 会議中にのみホワイトボードに一時的な表示とコラボレーションを提供します。 共有リンクは作成されておらず、Whiteboard はファイルへのアクセスを許可しません。

OneDrive for Businessに対して外部共有が有効になっている場合は、それ以上のアクションは必要ありません。

OneDrive for Businessの外部共有を制限する場合は、制限を維持し、外部および共有デバイス アカウントを機能させるために新しい設定を有効にするだけで済みます。 そのために、以下の手順に従ってください。

1. 組織で Whiteboard が有効になっていることを確認します。 詳細については、「 [ホワイトボードへのアクセスの管理](manage-whiteboard-access-gcc-high.md)」を参照してください。

2. PowerShell を使用してテナントに接続し、次のコマンドを実行して SharePoint Online モジュールが更新されていることを確認します。

   ```powershell
   Update-Module -Name Microsoft.Online.SharePoint.PowerShell
   ```

3. 次に、次の **Set-SPOTenant コマンドを** 実行します。

   ```powershell
   Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On
   ```

この設定はホワイトボードにのみ適用され、以前に共有された設定である **OneDriveLoopSharingCapability** と **CoreLoopSharingCapability** に置き換えられます。 これらの設定は適用されなくなり、無視できます。

> [!NOTE]
> これは、ゲストとフェデレーション ユーザーにのみ適用されます。 現時点では、匿名会議ユーザーには適用されません。

これらの変更は、テナント全体に適用されるまでに約 60 分かかります。

|シナリオ|ストレージと所有権|共有設定|共有エクスペリエンス|
|---|---|---|---|
|デスクトップまたはモバイル デバイスからホワイトボードを起動する|ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー|有効|テナント内ユーザー: 作成、表示、および共同作業が可能<br><br>外部ユーザー: 会議中にのみ表示および共同作業できます (ホワイトボードを共有するボタンは外部ユーザーには表示されません)<br><br>共有デバイス アカウント: 会議中にのみ表示および共同作業できます|
|Surface Hub またはMicrosoft Teams Roomsからホワイトボードを起動する|まだ利用できません。|||

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams チャネルとチャットでタブとして追加する

Teams チャネルまたはチャットのタブとしてホワイトボードを追加すると、ホワイトボードは組織内のすべてのユーザーがアクセスできる共有リンクを作成します。

|シナリオ|ストレージと所有権|共有設定|共有エクスペリエンス|
|---|---|---|---|
|デスクトップまたはモバイル デバイスからホワイトボードをチャネルまたはチャットに追加する|ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー|対象外|テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: サポートされていません|

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard ネイティブ クライアントでの作成と共有

Web、デスクトップ、またはモバイル クライアントからホワイトボードを共有する場合は、特定のユーザーを選択できます。 組織内のすべてのユーザーがアクセスできる共有リンクを作成することもできます。

>[!NOTE]
> Teams 会議中の外部共有はまだ利用できませんが、今後のリリースで追加される予定です。

|シナリオ|ストレージと所有権|共有設定|共有エクスペリエンス|
|---|---|---|---|
|デスクトップまたはモバイル デバイスからホワイトボードを作成する|ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー|対象外|テナント内ユーザー: 組織内で共有できる<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません|
|Surface Hub からホワイトボードを作成する|ストレージ: ローカル<br><br>所有者: なし|対象外|テナント内のユーザー (近日公開予定): ユーザーはサインインしてボードを保存して共有できるようになります<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません|
|Microsoft Teams Roomsからホワイトボードを作成する|まだ利用できません。|||

## <a name="see-also"></a>関連項目

[Whiteboard へのアクセスを管理する - GCC High](manage-whiteboard-access-gcc-high.md)

[Whiteboard のデータを管理する - GCC High](manage-data-gcc-high.md)

[Whiteboard のクライアントを管理する - GCC High](manage-clients-gcc-high.md)
