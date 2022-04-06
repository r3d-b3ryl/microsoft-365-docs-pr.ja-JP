---
title: Microsoft Defender for Endpoint のユーザー アカウントを調査する
description: 調査中に、侵害された資格情報や関連付けられたユーザー アカウントのピボットが発生する可能性があるユーザー アカウントを調査します。
keywords: 調査, アカウント, ユーザー, ユーザー エンティティ, アラート, Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 76b0b7405c8dc1c434fbc9f991903b25d8b9d4f4
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469341"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のユーザー アカウントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>ユーザー アカウント エンティティの調査

最もアクティブなアラートを持つユーザー アカウント (ダッシュボードに "危険にさらされているユーザー" と表示される) を特定し、侵害される可能性のある資格情報のケースを調査するか、関連付けられたユーザー アカウントでピボットを実行して、そのユーザー アカウントを持つデバイス間の横方向の移動の可能性を特定するアラートまたはデバイスを調査します。

ユーザー アカウント情報は、次のビューで確認できます。

- ダッシュボード
- アラート キュー
- [デバイスの詳細] ページ

クリック可能なユーザー アカウント リンクは、これらのビューで使用できます。このリンクを使用すると、ユーザー アカウントの詳細ページに移動し、ユーザー アカウントの詳細が表示されます。

ユーザー アカウント エンティティを調査すると、次の情報が表示されます。

- ユーザー アカウントの詳細、Microsoft Defender for Identity アラート、ログオンしているデバイス、役割、ログオンの種類、その他の詳細
- インシデントとユーザーのデバイスの概要
- このユーザーに関連するアラート
- 組織内で観察される (ログオンしているデバイス)

:::image type="content" source="images/atp-user-details-view.png" alt-text="ユーザー アカウント エンティティの詳細ページ" lightbox="images/atp-user-details-view.png":::

### <a name="user-details"></a>ユーザーの詳細

左側の **[** ユーザーの詳細] ウィンドウには、関連する開いているインシデント、アクティブなアラート、SAM 名、SID、Microsoft Defender for Identity アラート、ユーザーがログオンしているデバイスの数、ユーザーが最初と最後に表示された時間、役割、ログオンの種類など、ユーザーに関する情報が表示されます。 有効にした統合機能に応じて、その他の詳細が表示されます。 たとえば、ビジネス統合Skypeを有効にした場合は、ポータルからユーザーに連絡できます。 **[Azure ATP アラート**] セクションには、Microsoft Defender for Identity 機能を有効にし、ユーザーに関連するアラートがある場合は、[Microsoft Defender for Identity] ページに移動するリンクが含まれている。 Microsoft Defender for Identity ページには、アラートに関する詳細が表示されます。

> [!NOTE]
> この機能を使用するには、Microsoft Defender for Identity と Defender for Endpoint の両方で統合を有効にする必要があります。 Defender for Endpoint では、高度な機能でこの機能を有効にできます。 高度な機能を有効にする方法の詳細については、「高度な機能を有効 [にする」を参照してください](advanced-features.md)。

組織の概要、アラート、および監視は、ユーザー アカウントに関するさまざまな属性を表示するさまざまなタブです。


>[!NOTE]
>Linux デバイスの場合、ログインしているユーザーに関する情報は表示されません。


### <a name="overview"></a>概要

[ **概要]** タブには、インシデントの詳細と、ユーザーがログオンしたデバイスの一覧が表示されます。 これらを展開すると、各デバイスのログオン イベントの詳細を確認できます。

### <a name="alerts"></a>アラート

[ **アラート]** タブには、ユーザー アカウントに関連付けられているアラートの一覧が表示されます。 この一覧は、アラート キューのフィルター[](alerts-queue.md)処理されたビューであり、ユーザー コンテキストが選択されたユーザー アカウントであるアラート、最後のアクティビティが検出された日付、アラートの短い説明、アラートに関連付けられたデバイス、アラートの重大度、キュー内のアラートの状態、およびアラートが割り当てられているユーザーを示します。

### <a name="observed-in-organization"></a>組織内で観察される

**[組織** で観察] タブを使用すると、日付範囲を指定して、このユーザーがログオンしているデバイスの一覧、これらの各デバイスで最も頻繁で最も頻繁にログオンしているユーザー アカウント、および各デバイスの総観測ユーザーを表示できます。

[組織で観察] テーブルでアイテムを選択すると、アイテムが展開され、デバイスの詳細が表示されます。 アイテム内のリンクを直接選択すると、対応するページに移動します。

## <a name="search-for-specific-user-accounts"></a>特定のユーザー アカウントを検索する

1. [検索 **] バー** の **ドロップダウン メニューから** [ユーザー] を選択します。
2. [検索] フィールドにユーザー アカウント **を入力** します。
3. 検索アイコンをクリックするか、Enter キーを **押します**。

クエリ テキストに一致するユーザーの一覧が表示されます。 ユーザー アカウントのドメインと名前、ユーザー アカウントが最後に表示された時間、および過去 30 日間にログオンしたデバイスの総数が表示されます。

結果は、次の期間でフィルター処理できます。

- 1 日
- 3 日間
- 7 日間
- 30 日間
- 6 か月

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint アラート キューを表示して整理する](alerts-queue.md)
- [エンドポイント通知の Microsoft Defender の管理](manage-alerts.md)
- [Microsoft Defender for Endpoint アラートの調査](investigate-alerts.md)
- [Defender for Endpoint アラートに関連付けられたファイルを調査する](investigate-files.md)
- [Defender for Endpoint Devices リストのデバイスを調査する](investigate-machines.md)
- [Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
