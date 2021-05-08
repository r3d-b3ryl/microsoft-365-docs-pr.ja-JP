---
title: 手順 3. 契約Power Automate処理するフローを作成するには、次の情報を使用します。
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: カスタム ソリューションを使用してPower Automateを作成して契約を処理する方法についてMicrosoft 365します。
ms.openlocfilehash: d9892110d6aebd3eaae6fbc21d453b7eb14d7f7e
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281235"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a><span data-ttu-id="5c121-104">手順 3.</span><span class="sxs-lookup"><span data-stu-id="5c121-104">Step 3.</span></span> <span data-ttu-id="5c121-105">契約Power Automate処理するフローを作成するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c121-105">Use Power Automate to create your flow to process your contracts</span></span>

<span data-ttu-id="5c121-106">契約管理チャネルを作成し、ドキュメント ライブラリにSharePointしました。</span><span class="sxs-lookup"><span data-stu-id="5c121-106">You've created your Contract Management channel and have attached your SharePoint document library.</span></span> <span data-ttu-id="5c121-107">次の手順では、Syntex モデルPower Automate識別して分類するコントラクトを処理するSharePointフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c121-107">The next step is to create a Power Automate flow to process your contracts that your SharePoint Syntex model identifies and classifies.</span></span> <span data-ttu-id="5c121-108">この手順を実行するには、[ドキュメント ライブラリにPower Automateフロー SharePoint作成します](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)。</span><span class="sxs-lookup"><span data-stu-id="5c121-108">You can do this step by [creating a Power Automate flow in your SharePoint document library](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).</span></span>

<span data-ttu-id="5c121-109">契約管理ソリューションでは、次のアクションを実行Power Automateフローを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c121-109">For your contracts management solution, you want to create a Power Automate flow to do the following actions:</span></span>

-  <span data-ttu-id="5c121-110">契約が Syntex モデルによって分類SharePoint、契約の状態を [確認中]**に変更します**。</span><span class="sxs-lookup"><span data-stu-id="5c121-110">After a contract has been classified by your SharePoint Syntex model, change the contract status to **In review**.</span></span>
- <span data-ttu-id="5c121-111">その後、契約が確認され、承認または却下されます。</span><span class="sxs-lookup"><span data-stu-id="5c121-111">The contract is then reviewed and is either approved or rejected.</span></span>
- <span data-ttu-id="5c121-112">承認された契約の場合、契約情報は支払い処理用のタブに投稿されます。</span><span class="sxs-lookup"><span data-stu-id="5c121-112">For approved contracts, the contract information is posted to a tab for payment processing.</span></span>
- <span data-ttu-id="5c121-113">却下された契約の場合、チームは詳細な分析を行う通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="5c121-113">For rejected contracts, the team is notified for further analysis.</span></span> 

<span data-ttu-id="5c121-114">次の図は、契約Power Automateのフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="5c121-114">The following diagram shows the Power Automate flow for the contract management solution.</span></span>

![Flow全体を示す図を示します。](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a><span data-ttu-id="5c121-116">レビューのために契約を準備する</span><span class="sxs-lookup"><span data-stu-id="5c121-116">Prepare your contract for review</span></span>

<span data-ttu-id="5c121-117">契約が Syntex ドキュメント理解モデルSharePoint識別され、分類されると、Power Automate フローは最初に状態を "レビュー中" に変更します。</span><span class="sxs-lookup"><span data-stu-id="5c121-117">When a contract is identified and classified by your SharePoint Syntex document understanding model, the Power Automate flow will first change the status to "In review."</span></span>

![更新の状態。](../media/content-understanding/flow-overview.png)

<span data-ttu-id="5c121-119">ファイルをチェックアウトした後、状態の値を "レビュー中" に変更します。</span><span class="sxs-lookup"><span data-stu-id="5c121-119">After checking out the file, change the status value to "In review."</span></span>

![レビューの状態です。](../media/content-understanding/in-review.png)

<span data-ttu-id="5c121-121">次の手順では、契約がレビューを待ち、それを契約管理チャネルに投稿することを示すアダプティブ カードを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c121-121">The next step is to create an adaptive card stating that the contract is waiting for review and posting it to the Contract Management channel.</span></span>

![契約レビュー投稿。](../media/content-understanding/contract-approval-post.png)


![レビュー用のアダプティブ カードを作成します。](../media/content-understanding/adaptive-card.png)

<span data-ttu-id="5c121-124">次のコードは、この手順で使用される JSON を示Power Automateします。</span><span class="sxs-lookup"><span data-stu-id="5c121-124">The following code is the JSON used for this step in the Power Automate flow.</span></span>

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


## <a name="conditional"></a><span data-ttu-id="5c121-125">条件付き</span><span class="sxs-lookup"><span data-stu-id="5c121-125">Conditional</span></span>

<span data-ttu-id="5c121-126">フローでは、次に、契約が承認または却下される条件を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c121-126">In your flow, next you need to create a condition in which your contract will be either  approved or rejected.</span></span>

![条件付き。](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a><span data-ttu-id="5c121-128">契約が承認された場合</span><span class="sxs-lookup"><span data-stu-id="5c121-128">If the contract is approved</span></span>

<span data-ttu-id="5c121-129">契約が承認されると、次のことが発生します。</span><span class="sxs-lookup"><span data-stu-id="5c121-129">When a contract has been approved, the following things occur:</span></span>

- <span data-ttu-id="5c121-130">[契約 **] タブ** で、契約カードの状態が [承認済み] **に変更されます**。</span><span class="sxs-lookup"><span data-stu-id="5c121-130">On the **Contracts** tab, the status in the contract card will change to **Approved**.</span></span>

   ![カードの状態が承認されました。](../media/content-understanding/approved-contracts-tab.png)

- <span data-ttu-id="5c121-132">フローで、状態が "承認済み" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="5c121-132">In your flow, the status is changed to "Approved."</span></span>

   ![Flowの状態が承認されました。](../media/content-understanding/status-approved.png)

- <span data-ttu-id="5c121-134">このソリューションでは、契約データが [支払い]タブに追加され、支払いを管理できます。</span><span class="sxs-lookup"><span data-stu-id="5c121-134">In this solution, the contract data will be added to the **For Payout** tab so that the payouts can be managed.</span></span> <span data-ttu-id="5c121-135">このプロセスを拡張して、フローがサードパーティの金融アプリケーション (Dynamics CRM など) による支払いのための契約を提出できるよう拡張できます。</span><span class="sxs-lookup"><span data-stu-id="5c121-135">This process can be extended to allow the flow to submit the contracts for payment by a third-party financial application (for example, Dynamics CRM).</span></span>

   ![契約が [支払い] に移動しました。](../media/content-understanding/for-payout.png)

- <span data-ttu-id="5c121-137">フローで、次のアイテムを作成して、承認済み契約を [支払い] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="5c121-137">In the flow, you create the following item to move approved contracts to the **For Payout** tab.</span></span>

   ![Flowに移動するアイテムを選択します。](../media/content-understanding/ready-for-payout.png)

- <span data-ttu-id="5c121-139">契約が承認されたことを示すアダプティブ カードが作成され、契約管理チャネルに投稿されます。</span><span class="sxs-lookup"><span data-stu-id="5c121-139">An adaptive card stating that the contract has been approved is created and posted to the Contract Management channel.</span></span>

   ![契約の承認が投稿されました。](../media/content-understanding/adaptive-card-approval.png)

   ![アダプティブ カードの承認。](../media/content-understanding/adaptive-card.png)


   <span data-ttu-id="5c121-142">次のコードは、この手順で使用される JSON を示Power Automateします。</span><span class="sxs-lookup"><span data-stu-id="5c121-142">The following code is the JSON used for this step in the Power Automate flow.</span></span>

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
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
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

## <a name="if-the-contract-is-rejected"></a><span data-ttu-id="5c121-143">契約が拒否された場合</span><span class="sxs-lookup"><span data-stu-id="5c121-143">If the contract is rejected</span></span>

<span data-ttu-id="5c121-144">契約が拒否された場合、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="5c121-144">When a contract has been rejected, the following things occur:</span></span>

- <span data-ttu-id="5c121-145">[契約 **] タブで** 、契約カードの状態が [拒否済み] に **変更されます**。</span><span class="sxs-lookup"><span data-stu-id="5c121-145">On the **Contracts** tab, the status in the contract card will change to **Rejected**.</span></span>

   ![カードの状態が拒否されました。](../media/content-understanding/rejected-contracts-tab.png)

- <span data-ttu-id="5c121-147">フローで、コントラクト ファイルをチェックアウトし、状態を [拒否] に変更し、ファイルを再びチェックインします。</span><span class="sxs-lookup"><span data-stu-id="5c121-147">In your flow, you check out the contract file, change the status to **Rejected**, and then check the file back in.</span></span>

   ![Flow状態が拒否されました。](../media/content-understanding/reject-flow.png)

- <span data-ttu-id="5c121-149">フローで、契約が拒否されたことを示すアダプティブ カードを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c121-149">In your flow, you create an adaptive card stating that the contract has been rejected.</span></span>

   ![Flow状態が拒否されました。](../media/content-understanding/reject-flow-item.png)

<span data-ttu-id="5c121-151">次のコードは、この手順で使用される JSON を示Power Automateします。</span><span class="sxs-lookup"><span data-stu-id="5c121-151">The following code is the JSON used for this step in the Power Automate flow.</span></span>

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
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
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

- <span data-ttu-id="5c121-152">カードは契約管理チャネルに投稿されます。</span><span class="sxs-lookup"><span data-stu-id="5c121-152">The card is posted in the Contract Management channel.</span></span>

   ![Flowアダプティブ カードを拒否します。](../media/content-understanding/rejected.png)