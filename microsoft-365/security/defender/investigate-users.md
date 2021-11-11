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
ms.openlocfilehash: 165f1ccb1e0a059d61802e9a8e026b9dbef3efc2
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914382"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>ユーザーを調査Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

インシデント調査の一部には、ユーザー アカウントを含めできます。 インシデントからのインシデント **の [ユーザー** ]タブから開始し、& \> ***_ \> _* Users を通知します**。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例。" lightbox="../../media/investigate-incidents/incident-users.png":::

インシデントのユーザー アカウントの概要を簡単に取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="インシデントのユーザー アカウントの概要ウィンドウの例。" lightbox="../../media/investigate-users/incidents-ss-user-pane.png":::

> [!NOTE]
> [ユーザー] ページにはAzure Active Directory (Azure AD) 組織とグループが表示され、ユーザーに関連付けられているグループとアクセス許可を理解できます。

このフライアウト ページでは、現在のインシデント、アクティブなアラート、リスク レベル、ユーザーの露出、アカウント、デバイスなど、ユーザーの脅威情報を確認できます。

さらに、Microsoft 365 Defender ポータルで直接アクションを実行して、侵害されたユーザーに対処し、ユーザーが侵害されたのを確認したり、再度サインインを要求したりすることもできます。

ここから、[ユーザー に移動] **ページを選択して** 、ユーザー アカウントの詳細を表示できます。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="インシデントのユーザー アカウント ページの例。" lightbox="../../media/investigate-users/incidents-ss-user-details.png":::

[ユーザー] ページの一覧からユーザー アカウントの名前を選択すると、このページを **確認** することもできます。

[グループ] で番号を選択すると、ユーザーのグループ メンバーシップを **確認できます**。

:::image type="content" source="../../media/investigate-users/user-group-membership.png" alt-text="ユーザーのグループ メンバーシップの例。" lightbox="../../media/investigate-users/user-group-membership.png":::

[マネージャー] の下 **のアイコンを** 選択すると、ユーザーが組織ツリー内の場所を確認できます。

[Microsoft 365 Defender ポータル ユーザー ページは、Microsoft Defender for Endpoint、Microsoft Defender for Identity、および Microsoft Cloud App Security (ライセンスに応じて) を結合します。

このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。 これには、ユーザーの全体的なリスクに寄与したリスクと最近のイベントやアラートを評価するのに役立つスコアが含まれます。

このページでは、次の追加アクションを実行できます。

- ユーザー アカウントを侵害済みとしてマークする
- ユーザーにもう一度サインインを要求する
- ユーザー アカウントを中断する
- [ユーザー アカウントAzure Active Directory (Azure AD) の設定を参照してください。
- ユーザー アカウントが所有するファイルを表示する
- このユーザーと共有されているファイルを表示します。

次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="インシデントのユーザー アカウントでのアクションの例。" lightbox="../../media/investigate-users/incidents-ss-user-details-actions.png":::

<!--
You can access this page from multiple areas in the Microsoft 365 Defender portal. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

-->

## <a name="view-lateral-movement-paths"></a>横方向の移動パスを表示する

[横方向の移動パス] タブを選択すると、ネットワークに侵入するために使用できる、このユーザーとの間の横方向の移動パスを視覚的に表現できる、完全に動的でクリック可能なマップを表示できます。

このマップでは、機密アカウントを侵害するために攻撃者がこのユーザーとの間で必要となるコンピューターまたはユーザー間のホップ数の一覧を提供し、ユーザーが機密性の高いアカウントを持っている場合は、直接接続されているリソースとアカウントの数を確認できます。

過去 2 日間にエンティティの潜在的な横方向の移動パスが検出されない場合、グラフは表示されません。 [別の日付を表示する] を使用して別の日付を選択して、このエンティティで検出された前の横方向の移動パスグラフを表示します。 横方向の移動パス レポートは、検出された潜在的な横方向の移動パスに関する情報を提供するために常に使用できます。また、時間によってカスタマイズできます。

:::image type="content" source="../../media/investigate-users/lateral-movement-path.png" alt-text="ユーザーの横方向の移動パスの例。" lightbox="../../media/investigate-users/lateral-movement-path.png":::

詳細については、「横方向の移動 [パス」を参照してください](/defender-for-identity/use-case-lateral-movement-path)。

## <a name="next-steps"></a>次の手順

インプロセス インシデントの必要に応じて、調査を続行 [します](investigate-incidents.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)
