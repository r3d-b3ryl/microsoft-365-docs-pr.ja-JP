---
title: ユーザーを調査Microsoft 365 Defender
description: ポータル内のインシデントについてユーザー Microsoft 365 Defenderします。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、監視、レポート、ID、データ、デバイス、アプリ、インシデント、分析、応答
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: bfb8e1fb42dcde1a3140e0990221536c1b76b4f8
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2022
ms.locfileid: "62904009"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>ユーザーを調査Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

インシデント調査の一部には、ユーザー アカウントを含めできます。 インシデントポータルのインシデントのアラートで識別されたユーザー アカウントの詳細は、インシデントMicrosoft 365 Defender **&**\>アラートインシデント ***_ \> _* Users から確認できます**。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例。" lightbox="../../media/investigate-incidents/incident-users.png":::

インシデントのユーザー アカウントの概要を簡単に取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="インシデントのユーザー アカウントの概要ウィンドウの例。" lightbox="../../media/investigate-users/incidents-ss-user-pane.png":::

> [!NOTE]
> ユーザー ページには、Azure Active Directory (Azure AD) 組織とグループが表示され、ユーザーに関連付けられているグループとアクセス許可を理解できます。

このウィンドウでは、現在のインシデント、アクティブなアラート、リスク レベル、ユーザーの露出、アカウント、デバイスなど、ユーザーの脅威情報を確認できます。

さらに、Microsoft 365 Defender ポータルで直接アクションを実行して、ユーザー アカウントが侵害されたか、新しいサインインが必要な場合など、侵害されたユーザーに対処できます。

ここから、[ユーザー に移動] **ページを選択して** 、ユーザー アカウントの詳細を表示できます。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="インシデントのユーザー アカウント ページの例。" lightbox="../../media/investigate-users/incidents-ss-user-details.png":::

[ユーザー] ページの一覧からユーザー アカウントの名前を選択すると、このページを **確認** することもできます。

[グループ] で番号を選択すると、ユーザーのグループ メンバーシップを確認 **できます**。

:::image type="content" source="../../media/investigate-users/user-group-membership.png" alt-text="ユーザーのグループ メンバーシップの例。" lightbox="../../media/investigate-users/user-group-membership.png":::

[マネージャー] の下 **のアイコンを** 選択すると、ユーザーが組織ツリー内の場所を確認できます。

[Microsoft 365 Defender ポータル ユーザー ページには、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps の情報が組み合わせ込まれています (ライセンスに応じて異なる)。

このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。これには、リスクの評価に役立つスコアや、全体的なリスクに寄与した最近のイベントやアラートが含まれます。

このページでは、次の追加アクションを実行できます。

- ユーザー アカウントを侵害済みとしてマークする
- ユーザーにもう一度サインインを要求する
- ユーザー アカウントを中断する
- ユーザー アカウントのAzure ADを参照してください。
- ユーザー アカウントが所有するファイルを表示する
- このユーザーと共有されているファイルを表示します。

次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="インシデントのユーザー アカウントでのアクションの例。" lightbox="../../media/investigate-users/incidents-ss-user-details-actions.png":::

## <a name="view-lateral-movement-paths"></a>横方向の移動パスを表示する

[横方向の移動パス] タブを選択すると、ネットワークに侵入するために使用できる、このユーザーとの間の横方向の移動パスを視覚的に表現できる、完全に動的でクリック可能なマップを表示できます。

このマップでは、機密アカウントを侵害するために攻撃者がこのユーザーとの間で必要となるコンピューターまたはユーザー間のホップ数の一覧を提供し、ユーザーが機密性の高いアカウントを持っている場合は、直接接続されているリソースとアカウントの数を確認できます。

過去 2 日間にエンティティの潜在的な横方向の移動パスが検出されない場合、グラフは表示されません。 [別の日付を表示する] を使用して別の日付を選択して、このエンティティで検出された前の横方向の移動パスグラフを表示します。 横方向の移動パス レポートは、検出された潜在的な横方向の移動パスに関する情報を提供するために常に使用できます。また、時間によってカスタマイズできます。

:::image type="content" source="../../media/investigate-users/lateral-movement-path.png" alt-text="ユーザーの横方向の移動パスの例。" lightbox="../../media/investigate-users/lateral-movement-path.png":::

詳細については、「横方向の移動 [パス」を参照してください](/defender-for-identity/use-case-lateral-movement-path)。

## <a name="next-steps"></a>次の手順

インプロセス インシデントの場合は、必要に応じて調査を続行 [します](investigate-incidents.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)
