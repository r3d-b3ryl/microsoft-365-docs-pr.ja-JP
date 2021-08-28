---
title: ユーザーを調査Microsoft 365 Defender
description: ポータル内のインシデントについてユーザー Microsoft 365 Defenderします。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、監視、レポート、ID、データ、デバイス、アプリ、インシデント、分析、応答
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: d8e83cfd877266bac6247246c078dbdc811368e5
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58563512"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>ユーザーを調査Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

インシデント調査の一部には、ユーザー アカウントを含めできます。 [インシデント]**からインシデント** の [ユーザー] タブから開始し、&**ユーザー** >*通知>***します**。 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例。":::

インシデントのユーザー アカウントの概要を簡単に取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="ポータル内のインシデントのユーザー アカウントの概要ウィンドウMicrosoft 365 Defender例":::

> [!NOTE]
> [ユーザー] ページにはAzure Active Directory (Azure AD) 組織とグループが表示され、ユーザーに関連付けられているグループとアクセス許可を理解できます。

このフライアウト ページでは、現在のインシデント、アクティブなアラート、リスク レベル、ユーザーの露出、アカウント、デバイスなど、ユーザーの脅威情報を確認できます。

さらに、Microsoft 365 Defender ポータルで直接アクションを実行して、侵害されたユーザーに対処し、ユーザーが侵害されたのを確認したり、再度サインインを要求したりすることもできます。

ここから、[ユーザー に移動] **ページを選択して** 、ユーザー アカウントの詳細を表示できます。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="ポータル内のインシデントのユーザー アカウント ページMicrosoft 365 Defender例":::

[ユーザー] ページの一覧からユーザー アカウントの名前を選択すると、このページを **確認** することもできます。

[Microsoft 365 Defender ポータル ユーザー ページは、Microsoft Defender for Endpoint、Microsoft Defender for Identity、および Microsoft Cloud App Security (ライセンスに応じて) を結合します。 

このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。 これには、ユーザーの全体的なリスクに寄与したリスクと最近のイベントやアラートを評価するのに役立つスコアが含まれます。

このページでは、次の追加アクションを実行できます。 

- ユーザー アカウントを侵害済みとしてマークする
- ユーザーにもう一度サインインを要求する
- ユーザー アカウントを中断する
- ユーザー アカウントAzure Active Directory (Azure AD) の設定を参照してください。
- ユーザー アカウントが所有するファイルを表示する
- このユーザーと共有されているファイルを表示します。 

次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="ポータル内のインシデントに対するユーザー アカウントでのアクションMicrosoft 365 Defender例":::


<!--
You can access this page from multiple areas in the Microsoft 365 Defender portal. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>次の手順

インプロセス インシデントの必要に応じて、調査を続行 [します](investigate-incidents.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)