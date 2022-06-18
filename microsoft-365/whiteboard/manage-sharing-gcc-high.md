---
title: GCC High 環境でMicrosoft Whiteboardの共有を管理する
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: GCC High 環境でMicrosoft Whiteboardの共有を管理する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3c4df9c8bda42e8cda84729dc17506f6d808c582
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159890"
---
# <a name="manage-sharing-for-microsoft-whiteboard-in-gcc-high-environments"></a>GCC High 環境でMicrosoft Whiteboardの共有を管理する

>[!NOTE]
> このガイダンスは、米国Government Community Cloud (GCC) の高い環境に適用されます。

共有エクスペリエンスは、使用されているデバイスとクライアントによって異なります。 

## <a name="share-in-teams-meetings"></a>Teams会議で共有する

Teams会議でホワイトボードを共有すると、ホワイトボードは組織内のすべてのユーザーがアクセスできる共有リンクを作成します。 その後、会議のテナント内ユーザーとホワイトボードを自動的に共有します。

>[!NOTE]
> Teams会議中の外部共有はまだ利用できませんが、今後のリリースで追加される予定です。

|シナリオ |Storageと所有権 |共有設定 |共有エクスペリエンス |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードを起動する |Storage: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー |まだ利用できません。 |テナント内ユーザー: 作成、表示、および共同作業が可能<br><br>外部ユーザー: まだ使用できません<br><br>共有デバイス アカウント: まだ使用できません |
|Surface HubまたはMicrosoft Teams Roomsからホワイトボードを開始する |まだ利用できません。 |         |         |

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams チャネルとチャットのタブとして追加する

Teams チャネルまたはチャットのタブとしてホワイトボードを追加すると、ホワイトボードは組織内のすべてのユーザーがアクセスできる共有リンクを作成します。

|シナリオ  |Storageと所有権  |共有設定  |共有エクスペリエンス  |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードをチャネルまたはチャットに追加する  |Storage: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |該当なし  |テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: サポートされていません  |

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard ネイティブ クライアントでの作成と共有

Web、デスクトップ、またはモバイル クライアントからホワイトボードを共有する場合は、特定のユーザーを選択できます。 組織内のすべてのユーザーがアクセスできる共有リンクを作成することもできます。 

>[!NOTE]
> Teams会議中の外部共有はまだ利用できませんが、今後のリリースで追加される予定です。

|シナリオ  |Storageと所有権  |共有設定  |共有エクスペリエンス  |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードを作成する  |Storage: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |該当なし  |テナント内ユーザー: 組織内で共有できる<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません  |
|Surface Hubからホワイトボードを作成する  |Storage: ローカル<br><br>所有者: なし  |該当なし  |テナント内のユーザー (近日公開予定): ユーザーはサインインしてボードを保存して共有できるようになります<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません |
|Microsoft Teams Roomsからホワイトボードを作成する  |まだ利用できません。         |         |         |

## <a name="see-also"></a>関連項目

[Whiteboard へのアクセスを有効にして管理する - GCC High](enable-whiteboard-access-gcc-high.md)

[Whiteboard のデータを管理する - GCC High](manage-data-gcc-high.md)

[Whiteboard のクライアントを管理する - GCC High](manage-clients-gcc-high.md)
