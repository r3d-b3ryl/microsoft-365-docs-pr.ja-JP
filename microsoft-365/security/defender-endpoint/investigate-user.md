---
title: Microsoft Defender for Endpointでユーザー アカウントを調査する
description: 調査中に、侵害された可能性がある資格情報をユーザー アカウントで調査するか、関連付けられたユーザー アカウントでピボットします。
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
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでユーザー アカウントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>ユーザー アカウント エンティティを調査する

最もアクティブなアラートを持つユーザー アカウント (ダッシュボードに "危険なユーザー" として表示されます) を特定し、侵害された可能性がある資格情報のケースを調査するか、アラートまたはデバイスを調査するときに関連付けられたユーザー アカウントをピボットして、そのユーザー アカウントを持つデバイス間の横移動の可能性を特定します。

ユーザー アカウント情報は、次のビューで確認できます。

- ダッシュボード
- アラート キュー
- デバイスの詳細ページ

これらのビューでは、クリック可能なユーザー アカウントのリンクを使用できます。これにより、ユーザー アカウントの詳細ページに移動し、ユーザー アカウントの詳細が表示されます。

ユーザー アカウント エンティティを調査すると、次の内容が表示されます。

- ユーザー アカウントの詳細、Microsoft Defender for Identityアラート、ログオンしているデバイス、ロール、ログオンの種類、その他の詳細
- インシデントとユーザーのデバイスの概要
- このユーザーに関連するアラート
- 組織で観察される (ログオン先のデバイス)

:::image type="content" source="images/atp-user-details-view.png" alt-text="ユーザー アカウント エンティティの詳細ページ" lightbox="images/atp-user-details-view.png":::

### <a name="user-details"></a>ユーザーの詳細

左側の **[ユーザーの詳細**] ウィンドウには、関連する開いているインシデント、アクティブなアラート、SAM 名、SID、Microsoft Defender for Identityアラート、ユーザーがログオンしているデバイスの数、ユーザーが最初と最後に表示されたとき、ロール、ログオンの種類など、ユーザーに関する情報が表示されます。 有効にした統合機能に応じて、他の詳細が表示されます。 たとえば、ビジネス統合のSkypeを有効にすると、ポータルからユーザーに連絡できます。 **Azure ATP アラート** セクションには、Microsoft Defender for Identity機能を有効にしていて、ユーザーに関連するアラートがある場合に、Microsoft Defender for Identity ページに移動するリンクが含まれています。 Microsoft Defender for Identity ページには、アラートに関する詳細情報が表示されます。

> [!NOTE]
> この機能を使用するには、Microsoft Defender for Identityと Defender for Endpoint の両方で統合を有効にする必要があります。 Defender for Endpoint では、高度な機能でこの機能を有効にすることができます。 高度な機能を有効にする方法の詳細については、「高度な機能 [を有効にする」](advanced-features.md)を参照してください。

組織の概要、アラート、および監視は、ユーザー アカウントに関するさまざまな属性を表示するさまざまなタブです。


>[!NOTE]
>Linux デバイスの場合、ログインしているユーザーに関する情報は表示されません。


### <a name="overview"></a>概要

[ **概要** ] タブには、インシデントの詳細と、ユーザーがログオンしたデバイスの一覧が表示されます。 これらを展開して、各デバイスのログオン イベントの詳細を表示できます。

### <a name="alerts"></a>アラート

[ **アラート]** タブには、ユーザー アカウントに関連付けられているアラートの一覧が表示されます。 この一覧は [、アラート キュー](alerts-queue.md)のフィルター処理されたビューであり、ユーザー コンテキストが選択されたユーザー アカウントであるアラート、最後のアクティビティが検出された日付、アラートの簡単な説明、アラートに関連付けられているデバイス、アラートの重大度、キュー内のアラートの状態、およびアラートが割り当てられているユーザーを示します。

### <a name="observed-in-organization"></a>組織内で観察される

[ **組織の監視** ] タブでは、このユーザーがログオンして観察されたデバイスの一覧を表示する日付範囲を指定できます。これらのデバイスごとにログオンしたユーザー アカウントが最も頻度が高く、最も頻度が低く、各デバイスで監視されたユーザーの合計数が表示されます。

[組織の監視] テーブルで項目を選択すると、アイテムが展開され、デバイスの詳細が表示されます。 アイテム内のリンクを直接選択すると、対応するページに移動します。

## <a name="search-for-specific-user-accounts"></a>特定のユーザー アカウントを検索する

1. **[検索] バー** のドロップダウン メニューから [**ユーザー]** を選択します。
2. **[検索**] フィールドにユーザー アカウントを入力します。
3. 検索アイコンをクリックするか、 **Enter** キーを押します。

クエリ テキストに一致するユーザーの一覧が表示されます。 ユーザー アカウントのドメインと名前、ユーザー アカウントが最後に表示されたとき、および過去 30 日間にログオンしたデバイスの合計数が表示されます。

結果は、次の期間でフィルター処理できます。

- 1 日
- 3 日間
- 7 日間
- 30 日間
- 6 か月

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint アラート キューを表示して整理する](alerts-queue.md)
- [Microsoft Defender for Endpointアラートを管理する](manage-alerts.md)
- [Microsoft Defender for Endpointアラートを調査する](investigate-alerts.md)
- [Defender for Endpoint アラートに関連付けられているファイルを調査する](investigate-files.md)
- [Defender for Endpoint Devices の一覧のデバイスを調査する](investigate-machines.md)
- [Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
