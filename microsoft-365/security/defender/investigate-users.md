---
title: Microsoft 365 Defender でユーザーを調査する
description: Microsoft 365 セキュリティ センターでのインシデントのユーザーを調査します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティセンター, モニター, レポート, ID, データ, デバイス, アプリ, インシデント, 分析, 応答
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572803"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Microsoft 365 Defender でユーザーを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

インシデント調査の一部には、ユーザー アカウントを含めることができます。 & インシデントの警告>インシデント>**ユーザー**]**のインシデント** の [**ユーザー** ] タブから開始します。 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントのユーザー ページの例":::

インシデントのユーザー アカウントの概要を簡単に取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウントの概要ウィンドウの例":::

> [!NOTE]
> [ユーザー] ページには、グループとAzure Active Directory (Azure AD) 組織が表示され、ユーザーに関連付けられているグループとアクセス許可を理解するのに役立ちます。

このフライアウト ページでは、現在のインシデント、アクティブなアラート、およびリスク レベル、ユーザーの露出、アカウント、デバイスなど、ユーザーの脅威情報を確認できます。

さらに、侵害されたユーザーに対処するために、Microsoft 365 セキュリティ センターで直接アクションを実行したり、ユーザーが侵害されたことを確認したり、再度サインインを要求したりできます。

ここから[ **ユーザー ページへ移動** ]を選択すると、ユーザー アカウントの詳細を表示できます。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウント ページの例":::

このページは、[ユーザー] ページの一覧からユーザー アカウントの名前を **選択** して表示することもできます。

Microsoft 365 セキュリティ センターのユーザー ページは、エンドポイントの Microsoft Defender、Id 用 Microsoft Defender、およびMicrosoft Cloud App Security (お持ちのライセンスに応じて) からの情報を組み合わせています。 

このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。 これには、リスクと、ユーザーの全体的なリスクに寄与した最近のイベントとアラートを評価するのに役立つスコアが含まれます。

このページから、次の追加アクションを実行できます。 

- ユーザー アカウントを侵害済みとしてマークする
- ユーザーに再びサインインを要求する
- ユーザー アカウントを中断する
- Azure Active Directory (Azure AD) ユーザー アカウント設定を参照してください。
- ユーザー アカウントが所有するファイルを表示する
- このユーザーと共有されているファイルを表示します。 

次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 セキュリティ センターでのインシデントに対するユーザー アカウントのアクションの例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>次の手順

インプロセス インシデントの必要に応じて、 [調査](investigate-incidents.md)を続行します。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)