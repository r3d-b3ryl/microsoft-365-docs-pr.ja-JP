---
title: GCC High 環境で Microsoft Whiteboard の共有を管理する
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
description: GCC High 環境で Microsoft Whiteboard の共有を管理する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b16b55b1d8adc52318e8549a92ef703d68f548a
ms.sourcegitcommit: bc35c7826e3403f259725ac72cca5bafd36aa56a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66553896"
---
# <a name="manage-sharing-for-microsoft-whiteboard-in-gcc-high-environments"></a>GCC High 環境で Microsoft Whiteboard の共有を管理する

>[!NOTE]
> このガイダンスは、米国政府機関コミュニティ クラウド (GCC) の High 環境に適用されます。

共有エクスペリエンスは、使用されているデバイスとクライアントによって異なります。 

## <a name="share-in-teams-meetings"></a>Teams 会議で共有する

Teams 会議でホワイトボードを共有すると、ホワイトボードによって、組織内のすべてのユーザーがアクセスできる共有リンクが作成されます。 その後、会議のテナント内ユーザーとホワイトボードを自動的に共有します。

>[!NOTE]
> Teams 会議中の外部共有はまだ利用できませんが、今後のリリースで追加される予定です。

|シナリオ |ストレージと所有権 |共有設定 |共有エクスペリエンス |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードを起動する |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー |まだ利用できません。 |テナント内ユーザー: 作成、表示、および共同作業が可能<br><br>外部ユーザー: まだ使用できません<br><br>共有デバイス アカウント: まだ使用できません |
|Surface Hub またはMicrosoft Teams Roomsからホワイトボードを起動する |まだ利用できません。 |         |         |

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams チャネルとチャットでタブとして追加する

Teams チャネルまたはチャットのタブとしてホワイトボードを追加すると、ホワイトボードは組織内のすべてのユーザーがアクセスできる共有リンクを作成します。

|シナリオ  |ストレージと所有権  |共有設定  |共有エクスペリエンス  |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードをチャネルまたはチャットに追加する  |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |該当なし  |テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: サポートされていません  |

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard ネイティブ クライアントでの作成と共有

Web、デスクトップ、またはモバイル クライアントからホワイトボードを共有する場合は、特定のユーザーを選択できます。 組織内のすべてのユーザーがアクセスできる共有リンクを作成することもできます。 

>[!NOTE]
> Teams 会議中の外部共有はまだ利用できませんが、今後のリリースで追加される予定です。

|シナリオ  |ストレージと所有権  |共有設定  |共有エクスペリエンス  |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードを作成する  |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |該当なし  |テナント内ユーザー: 組織内で共有できる<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません  |
|Surface Hub からホワイトボードを作成する  |ストレージ: ローカル<br><br>所有者: なし  |該当なし  |テナント内のユーザー (近日公開予定): ユーザーはサインインしてボードを保存して共有できるようになります<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません |
|Microsoft Teams Roomsからホワイトボードを作成する  |まだ利用できません。         |         |         |

## <a name="see-also"></a>関連項目

[Whiteboard へのアクセスを管理する - GCC High](manage-whiteboard-access-gcc-high.md)

[Whiteboard のデータを管理する - GCC High](manage-data-gcc-high.md)

[Whiteboard のクライアントを管理する - GCC High](manage-clients-gcc-high.md)
