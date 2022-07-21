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
ms.openlocfilehash: 6aa0d3ba9415bba32663cd868cfc94743f354fd4
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66943026"
---
# <a name="manage-sharing-for-microsoft-whiteboard"></a>Microsoft Whiteboard の共有を管理する

共有エクスペリエンスは、Teams 会議に参加しているかどうか、共有デバイスを使用している場合、またはテナント レベルの共有設定が有効になっているかどうかによって異なります。 次のシナリオは、Whiteboard が OneDrive for Business ストレージの使用に切り替わる後に作成された新しいホワイトボードにのみ適用されます。 以前に作成したボードは、Azure にまだ保存されている変更はありません。

## <a name="share-in-teams-meetings"></a>Teams 会議で共有する

Teams 会議でホワイトボードを共有すると、ホワイトボードによって、組織内のすべてのユーザーがアクセスできる共有リンクが作成されます。 その後、会議のテナント内ユーザーとホワイトボードを自動的に共有します。

会議中に、外部および共有デバイス アカウントによる一時的なコラボレーションのための追加機能があります。 この機能を使用すると、これらのユーザーは、Teams 会議で共有されるときに、ホワイトボードで一時的に表示および共同作業を行うことができます。PowerPoint Live共有と同様です。

>[!NOTE]
> これは共有リンクではなく、ファイルへのアクセスを許可しません。 Teams 会議の期間中のみ、ホワイトボードでの一時的な表示とコラボレーションが提供されます。

OneDrive for Businessに対して外部共有が有効になっている場合は、それ以上のアクションは必要ありません。

OneDrive for Businessの外部共有を制限する場合は、制限を維持し、外部および共有デバイス アカウントを機能させるために新しい設定を有効にすることができます。 そのために、以下の手順に従ってください。

1. PowerShell を使用してテナントに接続し、次のコマンドを実行して SharePoint Online モジュールが更新されていることを確認します。

   <pre><code class="lang-powershell">Update-Module -Name Microsoft.Online.SharePoint.PowerShell</code></pre>
 
2. 次に、次のコマンドレットを実行します <code>Set-SPOTenant</code> 。

   <pre><code class="lang-powershell">Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On</code></pre>

この設定はホワイトボードにのみ適用され、以前に共有された設定 **である OneDriveLoopSharingCapability** と **CoreLoopSharingCapability** に置き換えられます。 これらの設定は適用されなくなり、無視できます。

>[!NOTE]
> 既定では、[Teams 会議] 設定 **の [匿名ユーザーは会議でアプリを操作できます** ] が有効になっています。 無効にした場合、(ゲストやフェデレーション ユーザーとは対照的に) 匿名ユーザーは会議中にホワイトボードにアクセスできません。

これらの変更は、テナント全体に適用されるまでに約 60 分かかります。 

|シナリオ  |ストレージと所有権  |共有設定  |共有エクスペリエンス  |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードを起動する  |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |Enabled  |テナント内ユーザー: 作成、表示、および共同作業が可能<br><br>外部ユーザー: 会議中にのみ表示および共同作業できます (ホワイトボードを共有するボタンは外部ユーザーには表示されません)<br><br>共有デバイス アカウント: 会議中にのみ表示および共同作業できます  |
|デスクトップまたはモバイル デバイスからホワイトボードを起動する  |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |無効  |テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: 表示または共同作業できない<br><br>共有デバイス アカウント: 表示または共同作業できない  |
|Surface Hub またはMicrosoft Teams Roomsからホワイトボードを起動する  |ストレージ: Azure (今後、OneDrive for Businessに移行される予定)<br><br>所有者: 会議の参加者   |該当なし  |テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: 会議中にのみ表示および共同作業できます<br><br>共有デバイス アカウント: 会議中にのみ表示および共同作業できます  |

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams チャネルとチャットでタブとして追加する

Teams チャネルまたはチャットのタブとしてホワイトボードを追加すると、ホワイトボードは組織内のすべてのユーザーがアクセスできる共有リンクを作成します。

|シナリオ  |ストレージと所有権  |共有設定  |共有エクスペリエンス  |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードをチャネルまたはチャットに追加する  |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |適用されません (会議にのみ適用されます)  |テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: サポートされていません<br><br>Teams ゲスト: 表示と共同作業が可能<br><br>共有デバイス アカウント: 適用されません  |

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard ネイティブ クライアントでの作成と共有

Web、デスクトップ、またはモバイル クライアントからホワイトボードを共有する場合は、特定のユーザーを選択できます。 組織内のすべてのユーザーがアクセスできる共有リンクを作成することもできます。 

>[!NOTE]
> Teams 会議中の外部共有はまだ利用できませんが、今後のリリースで追加される予定です。

|シナリオ  |ストレージと所有権  |共有設定  |共有エクスペリエンス  |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードを作成する  |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |適用されません (会議にのみ適用されます)  |テナント内ユーザー: 組織内で共有できる<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません  |
|Surface Hub からホワイトボードを作成する  |ストレージ: ローカル<br><br>所有者: なし (ユーザーがサインインしてボードを保存して共有しない限り、OneDrive for Businessに保存されます。 今後、簡単な共有が追加される予定です。  |適用されません (会議にのみ適用されます)  |テナント内ユーザー: ユーザーはサインインしてボードを保存して共有する必要があります (Easy share は今後追加される予定です)<br><br>外部ユーザー: Teams 会議の外部では、現時点では外部ユーザーとの共有はサポートされていません  |
|Microsoft Teams Roomsからホワイトボードを作成する  |まだサポートされていません  |適用されません (会議にのみ適用されます)  |まだサポートされていません  |

## <a name="see-also"></a>関連項目

[ホワイトボードへのアクセスを管理する](manage-whiteboard-access-organizations.md)

[Whiteboard のデータを管理する](manage-data-organizations.md)

[Windows にホワイトボードを展開する](deploy-on-windows-organizations.md)