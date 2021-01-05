---
title: Exchange Online メールボックスに格納されているコンテンツ
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 のクラウドベースのアプリによって生成されたデータは、ユーザーの Exchange Online メールボックスに保存または関連付けられる。
ms.openlocfilehash: f7bd5b00e8219f382078eb2d4f8aa25bd4c54d69
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750748"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Exchange Online メールボックスに格納されているコンテンツ

Exchange Online のメールボックスは、主に、メッセージ、予定表アイテム、タスク、メモなどの電子メール関連のアイテムを格納するために使用されます。 しかし、クラウドベースのアプリがユーザーのメールボックスにもデータを格納するほど、この変更は変化しています。 メールボックスにデータを保存する利点の 1 つは、コンテンツ検索、コア電子情報開示、Advanced eDiscovery の検索ツールを使用して、クラウドベースのアプリからデータを検索、表示、エクスポートできるという方法です。 これらのアプリの一部のデータは、メールボックス内の非対人メッセージ (非 IPM) サブツリーにある隠しフォルダーに格納されます。 他のクラウドベースのアプリのデータはメールボックスに格納されていない可能性がありますが、メールボックスに関連付けられているので、検索で返されます (そのデータが検索クエリと一致する場合)。 クラウドベースのデータがユーザー メールボックスに保存されているのか、ユーザー メールボックスに関連付けられているかに関係なく、ユーザーがメールボックスを開くと、そのデータは通常、電子メール クライアントに表示されません。

次の表に、データをクラウドベースのメールボックスに格納または関連付けるアプリを示します。 この表では、各アプリが生成するコンテンツの種類も示します。

|Microsoft 365 アプリ|説明|
|:---------|:---------|
|フォーム|フォームとフォームへの応答は、電子メール メッセージに添付され、フォームを作成したユーザーのメールボックスの隠しフォルダーに保存されるファイルに格納されます。 2020 年 4 月より前に作成されたフォームは、PDF ファイルとして保存されます。 2020 以降に作成されたフォームは、JSON ファイルとして保存されます。  フォームへの応答は、CSV ファイルに格納されます。 WHEN you export content from Forms in a PST file, this data is located in the **ApplicationDataRoot** folder in a subfolder named with the following globally unique identified (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Microsoft 365 グループ|電子メール メッセージ、予定表アイテム、連絡先 (人)、メモ、およびタスクは、Microsoft 365 グループに関連付けられているメールボックスに格納されます。|
|Outlook/Exchange Online|電子メール メッセージ、予定表アイテム、連絡先 (人)、メモ、およびタスクは、ユーザーのメールボックスに格納されます。|
|ユーザー|People アプリの連絡先 (Outlook でアクセス可能な連絡先と同じ連絡先) は、ユーザーのメールボックスに保存されます。|
|クラス スケジュール|クラス スケジュールで作成されたプランは、新しいプランの作成時にプロビジョニングされる対応する Microsoft 365 グループのメールボックスに格納されます。 グループ メールボックスのエイリアスは、プランの名前です。|
|Skype for Business|Skype for Business の会話は、ユーザーのメールボックスの [会話履歴] フォルダーに保存されます。 Skype 会議の参加者のメールボックスが訴訟ホールドの対象にされている場合、またはアイテム保持ポリシーに割り当てられている場合、会議に添付されたファイルは参加者のメールボックスに保持されます。|
|Sway|Sway は、電子メール メッセージに添付され、Sway を作成したユーザーのメールボックス内の隠しフォルダーに格納される HTML ファイルとして保存されます。 PST ファイル内の Sway からコンテンツをエクスポートする場合、このデータは、次の GUID で指定されたサブフォルダーの **ApplicationDataRoot** フォルダーにあります) **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|タスク|タスク アプリのタスク (Outlook でアクセス可能なタスクと同じタスク) は、ユーザーのメールボックスに保存されます。|
|Teams|Teams チャネルの一部である会話は、Teams メールボックスに関連付けされます。 Teams のチャット リストの一部である会話 *(1 x N* チャットとも呼ばれる) は、チャットに参加するユーザーのメールボックスに関連付けられる。 また、Teams チャネルでの会議と通話の概要情報は、会議または通話にダイヤルしたユーザーのメールボックスに関連付けされます。 そのため、Teams のコンテンツを検索する場合は、チャネル会話のコンテンツを Teams メールボックスで検索し、1 x N チャットのコンテンツについてユーザーメールボックスを検索します。| 
|To-Do|タスク *(To Do* リストに保存される To Do と呼ばれる) は、To-Do ユーザーのメールボックスに保存されます。|
|Yammer|Yammer コミュニティ内の会話とコメントは、Microsoft 365 グループ メールボックス、作成者のユーザー メールボックス、および任意の名前付き受信者 (@mentioned または cc のユーザー) に関連付けられている。 Yammer コミュニティの外部で送信されたプライベート メッセージは、プライベート メッセージに参加するユーザーのメールボックスに保存されます。|  
||||

> [!NOTE]
> 現時点では、(電子情報開示および Advanced eDiscovery のケースでホールドを使用して) メールボックスにホールドが適用されている場合、Forms および Sway のコンテンツは保持されません。 
