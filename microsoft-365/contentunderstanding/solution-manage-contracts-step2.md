---
title: 手順 2.  Microsoft Teamsを使用してコントラクト管理チャネルを作成する
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
description: Microsoft Teamsを使用して、Microsoft 365 ソリューションを使用してコントラクト管理チャネルを作成する方法について説明します。
ms.openlocfilehash: a5a42bedcb6acba4caf8f6f114812c63869ee92e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172121"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>手順 2。 Microsoft Teamsを使用してコントラクト管理チャネルを作成する

組織がコントラクト管理ソリューションを設定する場合は、利害関係者が契約を確認および管理できる一元的な場所が必要です。 この目的のために、[Microsoft Teams](/microsoftteams/)を使用してTeams チャネルを設定し、Teamsの機能を使用して次のことを行うことができます。

- **関係者がアクションを必要とするすべてのコントラクトを簡単に確認できる場所を作成します。** たとえば、Teamsでは、メンバーが承認を必要とするすべての **コントラクト** の有用なタイル ビューを表示できるコントラクト管理チャネルで [コントラクト] タブを作成できます。 また、ビューを構成して、各 "カード" に必要な重要なデータ ( *クライアント*、 *請負業者*、 *料金* など) を一覧表示することもできます。

     ![[コントラクト] タブ。](../media/content-understanding/tile-view.png)

- **メンバーが相互に対話し、重要なイベントを表示する場所を用意します。** たとえば、Teamsでは、[**投稿**] タブを使用して会話を行い、更新を取得し、アクション (メンバーがコントラクトを拒否するなど) を表示できます。 何かが発生した場合 (承認のために送信された新しいコントラクトなど) は、[ **投稿** ] タブを使用して発表するだけでなく、レコードを保持することもできます。 また、メンバーが通知をサブスクライブすると、更新があるたびに通知を受け取ります。

     ![[投稿] タブ。](../media/content-understanding/posts.png)

- **メンバーが承認された契約を確認し、支払いのためにいつ提出できるかを知る場所を設定します。** SharePointでは、**For Payout** リストを作成し、**クライアント**、**請負業者**、**料金の金額** の列を含め、列の種類として **[1 行のテキスト**] を選択する必要があります。 [契約] タブで行う場合と同様に、[支払 **い**] リストを [契約管理] チャネルの [Teams [] タブとして追加 **する**](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab)必要があります。[**支払い]** タブには、支払いに送信する必要があるすべての契約が一覧表示されます。 このソリューションを簡単に拡張して、代わりにこの情報をサードパーティの財務アプリケーション (Dynamics CRM など) に直接書き込むことができます。 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>SharePointドキュメント ライブラリを [コントラクト] タブにアタッチする

Contracts Management チャネルで **[コントラクト**] タブを作成したら、[SharePointドキュメント ライブラリをアタッチする必要があります](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)。 添付するSharePointドキュメント ライブラリは、前のセクションでSharePoint Syntexドキュメント理解モデルを適用したドキュメント ライブラリです。

SharePointドキュメント ライブラリをアタッチすると、既定のリスト ビューを使用して分類されたコントラクトを表示できます。

   ![SharePoint ライブラリのリスト ビュー。](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a>[コントラクト] タブタイル ビューをカスタマイズする

> [!NOTE]
> このセクションでは、[Contracts Management Solution Assets リポジトリ](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)に含まれる [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ファイルに含まれるコード例を参照します。

Teamsではタイル ビューでコントラクトを表示できますが、コントラクト カードに表示するコントラクト データを表示するようにカスタマイズすることもできます。 たとえば、[ **契約** ] タブでは、メンバーが契約カードでクライアント、請負業者、料金の金額を確認することが重要です。 これらのフィールドはすべて、ドキュメント ライブラリに適用されたSharePoint Syntex モデルを通じて各コントラクトから抽出されました。 また、メンバーが承認プロセス内のコントラクトの場所を簡単に確認できるように、タイル ヘッダー バーをステータスごとに異なる色に変更することもできます。 たとえば、承認済みのすべてのコントラクトには青いヘッダー バーが表示されます。

   ![ライブラリのタイル ビュー SharePoint。](../media/content-understanding/tile.png)

使用するカスタム タイル ビューでは、現在のタイル ビューの書式設定に使用される JSON ファイルを変更する必要があります。 [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ファイルを見ると、カード ビューの作成に使用される JSON ファイルを参照できます。 次のセクションでは、コントラクト カード内の機能に関するコードの特定のセクションが表示されます。

Teams チャネルでビューの JSON コードを表示または変更する場合は、Teams チャネルでビューのドロップダウン メニューを選択し、[**現在のビューの書式設定**] を選択します。

   ![Teams チャネルの json 形式のスクリーンショット。](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a>カードのサイズと図形

[ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ファイルで、次のセクションを参照して、カードのサイズと図形の書式設定方法のコードを確認します。

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```

## <a name="contract-status"></a>契約の状態

次のコードでは、各タイトル カードの状態を定義できます。 各状態値 (*新規*、 *レビュー中*、 *承認済み*、 *拒否* 済み) ごとに異なる色コードが表示されることに注意してください。 [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ファイルで、状態を定義するセクションを確認します。

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```

## <a name="extracted-fields"></a>抽出されたフィールド

各契約カードには、契約ごとに抽出された 3 つのフィールド (*クライアント*、 *契約業者*、 *料金金額*) が表示されます。 さらに、ファイルを識別するために使用されるSharePoint Syntex モデルによって分類された時刻/日付を表示することもできます。

[ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) ファイルでは、次のセクションでこれらをそれぞれ定義します。

### <a name="client"></a>クライアント

このセクションでは、カードに "クライアント" を表示する方法を定義し、特定のコントラクトの値を使用します。

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a>建築 業者

このセクションでは、"Contractor" をカードに表示する方法を定義し、特定のコントラクトの値を使用します。

```JSON
                        {
                          "elmType": "div",
                          "txtContent": "Contractor",
                          "style": {
                            "color": "#767676",
                            "font-size": "12px",
                            "margin-bottom": "2px"
                          }
                        },
                        {
                          "elmType": "div",
                          "style": {
                            "margin-bottom": "12px",
                            "font-size": "14px"
                          },
                          "txtContent": "[$Contractor]"
                        },
```

### <a name="fee-amount"></a>料金

このセクションでは、カードに "料金金額" を表示する方法を定義し、特定のコントラクトの値を使用します。

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```

### <a name="classification-date"></a>分類日

このセクションでは、カードに "分類" を表示する方法を定義し、特定のコントラクトの値を使用します。

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a>次の手順

[手順 3.Power Automateを使用して、コントラクトを処理するフローを作成する](solution-manage-contracts-step3.md)
