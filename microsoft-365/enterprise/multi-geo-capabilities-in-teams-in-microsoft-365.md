---
title: Microsoft Teamsの Multi-Geo 機能
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
description: Microsoft 365 Multi-geo でのTeamsのしくみについて説明します。
ms.openlocfilehash: 0315a9ff0429c5e00c662bd7345a3b6a39a591c3
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62805870"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Microsoft Teamsの複数地域の機能

Teamsの複数地域機能を使用すると、Teamsチャット データを指定された地理的な場所に保存できます。 チャット データは、プライベート メッセージ、チャネル メッセージ、チャットで使用される画像など、チャット メッセージで構成されます。

Teamsは、ユーザーとグループの優先データの場所 (PDL) を使用して、データを格納する場所を決定します。 PDL が設定されていないか無効な場合、データはテナントの中央の場所に格納されます。

> [!NOTE]
> Teamsの複数地域機能は、2021 年 7 月にロールアウトされました。 チャットメッセージとチャネル メッセージは、今後数四半期にわたって自動的に正しい地域の場所に移行されます。 新しい PDL の変更は、テナントが初期同期を完了した後に処理され、その後の新しい PDL 変更は、受信した順序でキューに入れ、処理されます。

## <a name="user-chat"></a>ユーザー チャット

ユーザー チャットには、1 対 1、1 対多、プライベート会議メッセージが含まれます。

新しいユーザーが作成されると、Teamsユーザーの PDL が読み取られ、その地域の場所にすべてのチャット データが格納されます。

既存のユーザーの場合、管理者がユーザーの PDL を追加または変更すると、そのユーザーのチャット データが移行キューに追加され、指定された地理的な場所に移動されます。

1 対 1 または 1 対多のチャットの保存場所は、チャットを作成したユーザーの PDL に基づいています。 そのユーザーの PDL が変更された場合、チャットは新しい地域の場所に移行されます。 会議チャットの保存場所は、会議の開催者の PDL に基づいています。

ユーザーのTeams データの現在の場所を確認するには、[Teams PowerShell に接続](/powershell/module/teams/connect-microsoftteams)し、次のコマンドを実行します。

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>チャネル メッセージ

各Microsoft 365 グループには、関連データを格納する地理的な場所を示す優先データの場所 (PDL) があります。 Teamsは、各チームに関連付けられているグループの PDL を使用して、そのチームのチャネル メッセージング データを格納する場所を決定します。 これには、チャネル会議内で発生するプライベート チャネルとチャットが含まれます。

ユーザーが新しいチームを作成すると、そのユーザーの PDL によって、Microsoft 365 グループに割り当てられている PDL が決まります。 グループ PDL によって、そのチームのデータが格納される場所が決まります。 そのユーザーの PDL が後で変更された場合、グループの PDL は変更されません。

既存のチームの場合、管理者がチームをバックアップするMicrosoft 365 グループの PDL を追加または変更すると、そのチームのチャネル メッセージング データが移行キューに追加され、指定された地理的な場所に移動されます。

Microsoft 365 グループの PDL を変更すると、Teams データがキューに登録され、選択した場所に移行されます。 ただし、これにより、グループに関連付けられているSharePoint サイトまたはファイルが自動的に移行されることはありません。 「SharePoint サイトを[別の地理的な場所に移動する」の手順に従って、サイトを個別に移動する](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)必要があります。 異なる場所にある 1 つのグループのデータとSharePointデータをTeamsしないようにするには、必ず両方の手順を実行してください。

チームのデータの現在の場所を見つけるには、[Teams PowerShell に接続](/powershell/module/teams/connect-microsoftteams)し、次のコマンドを実行します。

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>ユーザー エクスペリエンス

Teams Multi-Geo はエンド ユーザーにシームレスです。 ユーザーまたはグループの PDL を変更すると、それぞれのデータは移行のためにキューに登録され、移行中にアクティブであっても、ユーザーまたはTeams クライアントに影響を与えない移行が自動的に行われます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Multi-Geo テナントの構成](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[複数地域環境の管理](administering-a-multi-geo-environment.md)

[複数地域環境での Exchange Online メールボックスの管理](administering-exchange-online-multi-geo.md)
