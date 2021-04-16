---
title: Microsoft 365 セキュリティ センターのユーザーを調査する
description: Microsoft 365 セキュリティ センターのユーザーを調査する
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、モニター、レポート、ID、データ、デバイス、アプリ
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
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861275"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターのユーザーを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

インシデント調査の一部には、ユーザー アカウントを含めできます。 [インシデント]**からインシデント** の [ユーザー] タブから開始し、&**ユーザー** >*通知>***します**。 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例":::

インシデントのユーザー アカウントの概要を簡単に取得するには、ユーザー アカウント名の横にあるチェック マークを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウント概要ウィンドウの例":::

ここから、[ユーザー に移動] **ページを選択して** 、ユーザー アカウントの詳細を表示できます。 次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 セキュリティ センターのインシデントのユーザー アカウント ページの例":::

[ユーザー] ページの一覧からユーザー アカウントの名前を選択すると、このページを **確認** することもできます。

Microsoft 365 セキュリティ センターのユーザー ページでは、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Cloud App Security の情報を組み合わせたもの (ライセンスに応じて異なる)。 

このページには、ユーザー アカウントのセキュリティ リスクに固有の情報が表示されます。 これには、ユーザーの全体的なリスクに寄与したリスクと最近のイベントやアラートを評価するのに役立つスコアが含まれます。

このページでは、次の追加アクションを実行できます。 

- ユーザー アカウントを侵害済みとしてマークする
- ユーザーにもう一度サインインを要求する
- ユーザー アカウントを中断する
- Azure Active Directory (Azure AD) ユーザー アカウントの設定を参照してください。
- ユーザー アカウントが所有するファイルを表示する
- このユーザーと共有されているファイルを表示します。 

次に例を示します。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 セキュリティ センターのインシデントに対するユーザー アカウントでのアクションの例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)