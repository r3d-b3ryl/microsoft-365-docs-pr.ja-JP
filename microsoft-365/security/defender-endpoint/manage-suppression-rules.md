---
title: エンドポイント抑制ルールの Microsoft Defender の管理
description: 抑制ルールを使用して、ポータルにアラートが表示されるのを防ぐ必要がある場合があります。 Microsoft Defender for Endpoint で抑制ルールを管理する方法について説明します。
keywords: 抑制、ルール、ルール名、スコープ、アクション、アラートの管理、オン、オフ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e55e4c78290d84393c06f0a58ef425bad5eb4dcc
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53655949"
---
# <a name="manage-suppression-rules"></a>抑制ルールの管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


ポータルへのアラートの表示を抑制する必要がある場合があります。 組織内の既知のツールやプロセスなど、無実と知られている特定のアラートに対して抑制ルールを作成できます。 アラートを抑制する方法の詳細については、「アラートを抑制する」 [を参照してください](manage-alerts.md)。

すべての抑制ルールの一覧を表示し、1 か所で管理できます。 アラート抑制ルールをオンまたはオフに切り替えできます。


1. ナビゲーション ウィンドウで、[エンドポイント ルール]**設定**  >    >  **抑制]**  >  **を選択します**。 組織内のユーザーが作成した抑制ルールの一覧が表示されます。

2. ルール名の横にあるチェック ボックスをクリックして、ルールを選択します。

3. [ルール **を有効にする]** **、[ルールの編集]**、または [  **ルールの削除] をクリックします**。 ルールに変更を加える場合、これらのアラートが新しい条件と一致するかどうかに関係なく、既に抑制されているアラートを解放できます。 


## <a name="view-details-of-a-suppression-rule"></a>抑制ルールの詳細を表示する

1. ナビゲーション ウィンドウで、[エンドポイント ルール]**設定**  >    >  **抑制]**  >  **を選択します**。 組織内のユーザーが作成した抑制ルールの一覧が表示されます。

2. ルール名をクリックします。 ルールの詳細が表示されます。 ルールが作成された状態、スコープ、アクション、一致するアラートの数、作成日時などのルールの詳細が表示されます。 関連付けられたアラートとルールの条件を表示することもできます。

## <a name="related-topics"></a>関連項目

- [アラートの管理](manage-alerts.md)
