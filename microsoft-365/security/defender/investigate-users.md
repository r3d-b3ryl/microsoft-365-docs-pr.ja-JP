---
title: Microsoft 365 Defenderのユーザーを調査する
description: Microsoft 365 Defender ポータルで、インシデントのユーザーを調査します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, ID, データ, デバイス, アプリ, インシデント, 分析, 応答
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 75fa4b76017c8fcb1f0ab65b5ed88440c04f47d2
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051626"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Microsoft 365 Defenderのユーザーを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

インシデント調査の一部には、ユーザー アカウントを含めることができます。 インシデントのアラートで識別されたユーザー アカウントの詳細は、インシデント&アラートインシデント ***_ \> _* Users** から **Microsoft 365 Defender** \> ポータルで確認できます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [ユーザー] ページ。" lightbox="../../media/investigate-incidents/incident-users.png":::

インシデントのユーザー アカウントの簡単な概要を取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [ユーザー] タブ" lightbox="../../media/investigate-users/incidents-ss-user-pane.png":::

> [!NOTE]
> ユーザー ページには、Azure Active Directory (Azure AD) 組織とグループが表示され、ユーザーに関連付けられているグループとアクセス許可を理解するのに役立ちます。

このウィンドウでは、現在のインシデント、アクティブなアラート、リスク レベル、ユーザーの露出、アカウント、デバイスなど、ユーザーの脅威情報を確認できます。

さらに、Microsoft 365 Defender ポータルで直接アクションを実行して、侵害されたユーザー (ユーザー アカウントが侵害されていることを確認したり、新しいサインインを要求したりするなど) に対処できます。

ここから、[ **ユーザー ページに移動** ] を選択して、ユーザー アカウントの詳細を表示できます。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 Defender ポータルのユーザー アカウントの詳細" lightbox="../../media/investigate-users/incidents-ss-user-details.png":::

このページは、[ **ユーザー** ] ページの一覧からユーザー アカウントの名前を選択して表示することもできます。

[グループ] で番号を選択すると、ユーザーの **グループ** メンバーシップを確認できます。 グループを選択すると、[ **グループ** ] ウィンドウが開きます。これには、作成日やグループ メンバーシップなどの追加情報が含まれます。

> [!NOTE]
> グループ メンバーシップには、最初の 1,000 人のグループ メンバーのみが表示されます。

:::image type="content" source="../../media/investigate-users/user-group-membership.png" alt-text="Microsoft 365 Defender ポータルでのユーザーのグループ メンバーシップに関する情報" lightbox="../../media/investigate-users/user-group-membership.png":::

**[マネージャー**] の下のアイコンを選択すると、ユーザーが組織ツリー内のどこにいるかを確認できます。

Microsoft 365 Defender ポータル のユーザー ページは、Microsoft Defender for Endpoint、Microsoft Defender for Identity、およびMicrosoft Defender for Cloud Apps (所有しているライセンスによって異なります)。

このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。これには、リスクと、全体的なリスクに貢献した最近のイベントやアラートを評価するのに役立つスコアが含まれています。

このページでは、次の追加アクションを実行できます。

- ユーザー アカウントを侵害済みとしてマークする
- ユーザーにもう一度サインインするように要求する
- ユーザー アカウントを一時停止する
- Azure AD ユーザー アカウントの設定を確認する
- ユーザー アカウントが所有するファイルを表示する
- このユーザーと共有されているファイルを表示します。

次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 Defender ポータルでインシデントのユーザー アカウントに対するアクションを説明するセクション" lightbox="../../media/investigate-users/incidents-ss-user-details-actions.png":::

## <a name="view-lateral-movement-paths"></a>横移動パスを表示する

**[横移動パス**] タブを選択すると、ネットワークへの侵入に使用できる、このユーザーとの間の横移動パスを視覚的に表現できる、完全に動的でクリック可能なマップを表示できます。

このマップには、攻撃者が機密アカウントを侵害するためにこのユーザーとの間で送受信する必要があるコンピューターまたはユーザー間のホップ数の一覧が表示されます。また、ユーザーが機密アカウントを持っている場合は、直接接続されているリソースとアカウントの数を確認できます。

過去 2 日間にエンティティに対して潜在的な横移動パスが検出されなかった場合、グラフは表示されません。 別の日付を表示を使用して別の日付を選択すると、このエンティティで検出された以前の横移動パス グラフが表示されます。 横移動パス レポートは、検出された潜在的な横移動パスに関する情報を提供するために常に使用でき、時間によってカスタマイズできます。

:::image type="content" source="../../media/investigate-users/lateral-movement-path.png" alt-text="Microsoft 365 Defender ポータルでのユーザーの横移動パス" lightbox="../../media/investigate-users/lateral-movement-path.png":::

詳細については、「 [横移動パス](/defender-for-identity/use-case-lateral-movement-path)」を参照してください。

## <a name="next-steps"></a>次の手順

インプロセス インシデントに必要な場合は、 [調査](investigate-incidents.md)を続行します。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)
