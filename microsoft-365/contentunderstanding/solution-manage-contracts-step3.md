---
title: 手順 3. Power Automateを使用して、コントラクトを処理するフローを作成する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.localizationpriority: medium
ROBOTS: ''
description: Power Automateを使用してフローを作成し、Microsoft 365 ソリューションを使用してコントラクトを処理する方法について説明します。
ms.openlocfilehash: d83fb6e5ca911cbafc6f064c615ab15ae0f570c7
ms.sourcegitcommit: f3c912780bbcf5a5b47de192202adb3afbd5952b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2022
ms.locfileid: "62219007"
---
# <a name="step-3-use-power-automate-to-create-the-flow-to-process-your-contracts"></a>手順 3. Power Automateを使用して、コントラクトを処理するフローを作成する

Contract Management チャネルを作成し、SharePointドキュメント ライブラリをアタッチしました。 次の手順では、SharePoint Syntex モデルが識別および分類するコントラクトを処理するPower Automate フローを作成します。 この手順は、[SharePoint ドキュメント ライブラリにPower Automate フローを作成](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)することで行うことができます。

コントラクト管理ソリューションでは、次のアクションを実行するPower Automate フローを作成します。

-  SharePoint Syntex モデルによってコントラクトが分類されたら、コントラクトの状態を **[確認中]** に変更します。
- その後、契約が確認され、承認または拒否されます。
- 承認済みのコントラクトの場合、契約情報は支払処理用のタブにポストされます。
- 拒否されたコントラクトの場合、チームに詳細な分析が通知されます。 

次の図は、コントラクト管理ソリューションのPower Automate フローを示しています。

![ソリューション全体を示すFlow図。](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a>契約をレビュー用に準備する

SharePoint Syntexドキュメント理解モデルによってコントラクトが識別および分類されると、Power Automate フローは最初に状態を **[確認中]** に変更します。

![状態を更新します。](../media/content-understanding/flow-overview.png)

ファイルをチェックアウトしたら、状態の値を **[確認中]** に変更します。

![レビューの状態。](../media/content-understanding/in-review.png)

次の手順では、コントラクトが確認を待機していることを示すアダプティブ カードを作成し、コントラクト管理チャネルに投稿します。

![契約レビューの投稿。](../media/content-understanding/contract-approval-post.png)


![レビュー用のアダプティブ カードを作成します。](../media/content-understanding/adaptive-card.png)

次のコードは、Power Automate フローのこの手順に使用される JSON です。

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional-context"></a>条件付きコンテキスト

フローでは、次に、契約が  [承認](#if-the-contract-is-approved) または [拒否](#if-the-contract-is-rejected)される条件を作成する必要があります。

![条件 付き。](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a>契約が承認されている場合

契約が承認されると、次のことが発生します。

- [ **契約** ] タブで、コントラクト カードの状態が **[承認済み]** に変わります。

   ![カードの状態が承認されています。](../media/content-understanding/approved-contracts-tab.png)

- フローでは、状態が承認済みに変更 **されます**。

   ![Flow状態が承認されています。](../media/content-understanding/status-approved.png)

- このソリューションでは、支払いを管理できるように、コントラクト データが [ **支払い]** タブに追加されます。 このプロセスを拡張して、フローがサード パーティの財務アプリケーション (Dynamics CRM など) による支払いに対する契約を送信できるようにすることができます。

   ![契約が Pay Out に移行されました。](../media/content-understanding/for-payout.png)

- フローで、承認されたコントラクトを **[支払い]** タブに移動する次の項目を作成します。

   ![[支払い] に移動するアイテムをFlowします。](../media/content-understanding/ready-for-payout.png)

    Teams カードから必要な情報の式を取得するには、次の表に示す値を使用します。
 
    |名前     |Expression |
    |---------|-----------|
    | 承認状態  | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['submitActionId']         |
    | 承認者     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['レスポンダー']['displayName']        |
    | 承認日     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']         |
    | コメント     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']?['acComments']         |
    
    次の例は、Power Automateの数式ボックスを使用して式を記述する方法を示しています。

   ![式の数式を示すPower Automateのスクリーンショット。](../media/content-understanding/expression-formula-power-automate.png)    

- コントラクトが承認されたことを示すアダプティブ カードが作成され、Contract Management チャネルにポストされます。

   ![契約の承認が投稿されました。](../media/content-understanding/adaptive-card-approval.png)

   ![アダプティブ カードの承認。](../media/content-understanding/adaptive-card.png)


   次のコードは、Power Automate フローのこの手順に使用される JSON です。

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']?['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a>コントラクトが拒否された場合

コントラクトが拒否されると、次のことが発生します。

- [ **契約** ] タブで、コントラクト カードの状態が **[拒否済み]** に変わります。

   ![カードの状態が拒否されました。](../media/content-understanding/rejected-contracts-tab.png)

- フローでは、コントラクト ファイルをチェックアウトし、状態を **Rejected** に変更してから、ファイルを再度チェックインします。

   ![Flow状態がコントラクト ファイルで拒否されました。](../media/content-understanding/reject-flow.png)

- フローでは、コントラクトが拒否されたことを示すアダプティブ カードを作成します。

   ![Flow状態は、アダプティブ カードで拒否されたことを示します。](../media/content-understanding/reject-flow-item.png)

次のコードは、Power Automate フローのこの手順に使用される JSON です。

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']?['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- カードはコントラクト管理チャネルに投稿されます。

   ![拒否するアダプティブ カードをFlowします。](../media/content-understanding/rejected.png)
