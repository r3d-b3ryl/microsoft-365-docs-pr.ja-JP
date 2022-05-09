---
title: Microsoft Defender for Endpoint抑制ルールを管理する
description: 抑制ルールを使用して、ポータルにアラートが表示されないようにする必要がある場合があります。 Microsoft Defender for Endpointで抑制ルールを管理する方法について説明します。
keywords: 抑制、ルール、ルール名、スコープ、アクション、アラートの管理、オン、オフ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee488256363cbb008f670bb8c88d3fb88d7c4090
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166796"
---
# <a name="manage-suppression-rules"></a>抑制ルールの管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


ポータルにアラートが表示されないようにする必要があるシナリオが考えられます。 組織内の既知のツールやプロセスなど、無害であることがわかっている特定のアラートに対して抑制ルールを作成できます。 アラートを抑制する方法の詳細については、「アラートを [抑制](manage-alerts.md)する」を参照してください。

すべての抑制ルールの一覧を表示し、それらを 1 か所で管理できます。 アラート抑制ルールをオンまたはオフにすることもできます。


1. ナビゲーション ウィンドウで、**設定**\>エンドポイント **ルール** \> **アラート抑制****を**\>選択します。 組織内のユーザーが作成した抑制ルールの一覧が表示されます。

2. ルール名の横にあるチェック ボックスをクリックして、ルールを選択します。

3. [ **ルールを有効にする]**、[ **ルールの編集]**、または  **[ルールの削除]** をクリックします。 ルールに変更を加える場合は、これらのアラートが新しい条件と一致するかどうかに関係なく、既に抑制されているアラートをリリースすることを選択できます。 


## <a name="view-details-of-a-suppression-rule"></a>抑制ルールの詳細を表示する

1. ナビゲーション ウィンドウで、**設定**\>エンドポイント **ルール** \> **アラート抑制****を**\>選択します。 組織内のユーザーが作成した抑制ルールの一覧が表示されます。

2. ルール名をクリックします。 ルールの詳細が表示されます。 ルールの詳細 (状態、スコープ、アクション、一致するアラートの数、作成元、ルールが作成された日付など) が表示されます。 関連付けられているアラートとルールの条件を表示することもできます。

## <a name="related-topics"></a>関連項目

- [アラートの管理](manage-alerts.md)
