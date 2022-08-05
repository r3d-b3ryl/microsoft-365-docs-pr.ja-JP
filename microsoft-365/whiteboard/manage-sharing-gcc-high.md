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
ms.openlocfilehash: b6efeac47cec8de02487bf4526891b52c9098079
ms.sourcegitcommit: d7193ee954c01c4172e228d25b941026c8d92d30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175336"
---
# <a name="manage-sharing-for-microsoft-whiteboard-in-gcc-high-environments"></a>GCC High 環境で Microsoft Whiteboard の共有を管理する

>[!NOTE]
> このガイダンスは、米国政府機関コミュニティ クラウド (GCC) の High 環境に適用されます。

共有エクスペリエンスは、使用されているデバイスとクライアントによって異なります。 

## <a name="share-in-teams-meetings"></a>Teams 会議で共有する

Teams 会議でホワイトボードを共有すると、ホワイトボードは組織内のすべてのユーザーがアクセスできる共有リンクを作成し、会議内のテナント内のユーザーとホワイトボードを自動的に共有します。 ホワイトボードは、既定の設定に関係なく、会社が共有できるリンクを使用して共有されます。 既定の共有リンクの種類のサポートが計画されています。

会議中に、ほとんどの外部および共有デバイス アカウントによる一時的なコラボレーションのための追加機能があります。 これにより、ユーザーは teams 会議で共有されるときに、ホワイトボードで一時的に表示および共同作業を行うことができます。PowerPoint Live共有と同様です。

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
|デスクトップまたはモバイル デバイスからホワイトボードをチャネルまたはチャットに追加する  |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |対象外  |テナント内ユーザー: 開始、表示、および共同作業が可能<br><br>外部ユーザー: サポートされていません  |

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard ネイティブ クライアントでの作成と共有

Web、デスクトップ、またはモバイル クライアントからホワイトボードを共有する場合は、特定のユーザーを選択できます。 組織内のすべてのユーザーがアクセスできる共有リンクを作成することもできます。 

>[!NOTE]
> Teams 会議中の外部共有はまだ利用できませんが、今後のリリースで追加される予定です。

|シナリオ  |ストレージと所有権  |共有設定  |共有エクスペリエンス  |
|---------|---------|---------|---------|
|デスクトップまたはモバイル デバイスからホワイトボードを作成する  |ストレージ: OneDrive for Business<br><br>所有者: ホワイトボードを作成するユーザー  |対象外  |テナント内ユーザー: 組織内で共有できる<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません  |
|Surface Hub からホワイトボードを作成する  |ストレージ: ローカル<br><br>所有者: なし  |対象外  |テナント内のユーザー (近日公開予定): ユーザーはサインインしてボードを保存して共有できるようになります<br><br>外部ユーザー: 外部ユーザーとの共有は、現時点ではサポートされていません |
|Microsoft Teams Roomsからホワイトボードを作成する  |まだ利用できません。         |         |         |

## <a name="see-also"></a>関連項目

[Whiteboard へのアクセスを管理する - GCC High](manage-whiteboard-access-gcc-high.md)

[Whiteboard のデータを管理する - GCC High](manage-data-gcc-high.md)

[Whiteboard のクライアントを管理する - GCC High](manage-clients-gcc-high.md)
