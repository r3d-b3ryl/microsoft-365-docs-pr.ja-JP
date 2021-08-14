---
title: 手順 2.  契約Microsoft Teamsチャネルを作成するには、次の情報を使用します。
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: カスタム ソリューションを使用してMicrosoft Teams管理チャネルを作成する方法について説明Microsoft 365します。
ms.openlocfilehash: 9efd6f49954b6ed9b9dd2339ba720641a2f7fe73e6526809ad5d71d148838337
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53855303"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>手順 2. 契約Microsoft Teamsチャネルを作成するには、次の情報を使用します。

組織が契約管理ソリューションをセットアップする場合は、関係者が契約を確認および管理できる中心的な場所が必要です。 この目的のために、Microsoft Teams[を使用](/microsoftteams/)して、Teamsチャネルを設定し、Teams使用できます。

- **関係者がアクションを必要とするすべての契約を簡単に確認できる場所を作成します。** たとえば、Teams契約管理チャネルに [契約]タブを作成し、承認が必要なすべての契約の便利なタイル ビューをメンバーに表示できます。 また、各 "カード" に重要なデータ (クライアント、契約者、手数料など)が一覧表示されるビュー *を構成することもできます*。

     ![[契約] タブ。](../media/content-understanding/tile-view.png)

- **メンバーが互いに対話し、重要なイベントを表示するための場所を持つ。** たとえば、Teams[投稿] タブを使用して、会話を行い、更新プログラムを取得し、アクション (契約を拒否するメンバーなど) を表示できます。 何かが発生した場合 (承認のために提出された新しい契約など)は、[投稿] タブを使用して、それをアナウンスするだけでなく、その記録を保持することもできます。 また、メンバーが通知を購読すると、更新が行されるたびに通知が届く。

     ![[投稿] タブ。](../media/content-understanding/posts.png)

- **承認された契約をメンバーが支払いのためにいつ提出できるのか知る場所をメンバーに提供します。** このSharePoint、[支払い] リストを作成し、列の種類として [クライアント] 、[契約者] 、および[手数料] の列を含める必要があります。[単一行のテキスト] を選択します。    契約管理チャネルの [支払いTeams] タブを [契約] タブに追加する [**必要** があります](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab)。[**支払い] タブ** には、支払いのために送信する必要があるすべての契約が一覧表示されます。 このソリューションを簡単に拡張して、この情報をサードパーティの金融アプリケーション (Dynamics CRM など) に直接書き込む必要があります。 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>[契約] SharePointにドキュメント ライブラリを添付する

Contracts **Management チャネルで [契約]** タブを作成した後、ドキュメント ライブラリSharePoint [に添付する必要があります](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)。 添付SharePointドキュメント ライブラリは、前のセクションでドキュメントSharePoint Syntexモデルを適用したドキュメント ライブラリです。

ドキュメント ライブラリにSharePointすると、既定のリスト ビューを使用して分類された契約を表示できます。

   ![ライブラリのリスト SharePoint表示します。](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a>[契約] タブのタイル ビューをカスタマイズする

> [!NOTE]
> このセクションでは、Contracts Management Solution Assets[](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json)リポジトリにContractTileFormatting.jsファイルに含まれるコード例[を参照します](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)。

このTeamsタイル ビューで契約を表示することができますが、それをカスタマイズして、契約カードに表示する契約データを表示できます。 たとえば、[ **契約]** タブでは、メンバーが契約カードのクライアント、請負業者、および手数料の金額を確認することが重要です。 これらのフィールドはすべて、ドキュメント ライブラリに適用された SharePoint Syntexモデルを通じて各コントラクトから抽出されました。 また、タイル ヘッダー バーを各ステータスの異なる色に変更して、メンバーが承認プロセス内の契約の場所を簡単に確認できます。 たとえば、承認済みのすべての契約には青色のヘッダー バーが表示されます。

   ![ライブラリのタイル ビュー SharePoint表示します。](../media/content-understanding/tile.png)

使用するカスタム タイル ビューでは、現在のタイル ビューの書式設定に使用する JSON ファイルを変更する必要があります。 カード ビューの作成に使用する JSON ファイルを参照するには、ファイルのContractTileFormatting.js[ します](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 。 次のセクションでは、コントラクト カード内の機能に関するコードの特定のセクションが表示されます。

Teams チャネルのビューの JSON コードを表示または変更する場合は、Teams チャネルでビューのドロップダウン メニューを選択し、[現在のビューの書式設定] を選択します。 

   ![チャネル内の json 形式Teamsスクリーンショット。](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a>カードのサイズと図形

ファイルの [ContractTileFormatting.jsで](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 、次のセクションを参照して、カードのサイズと図形の書式設定方法のコードを確認します。

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

次のコードでは、各タイトル カードの状態を定義できます。 各ステータス値 *(New、In* *review、Approved、**および Rejected)* は、それぞれ異なる色コードを表示します。  [ファイル [ContractTileFormatting.js] で](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) 、状態を定義するセクションを確認します。

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

各契約カードには、契約ごとに抽出された 3 つのフィールド (*クライアント*、契約者、および手数料金額)*が表示されます*。 さらに、ファイルの識別に使用されるデータ モデルによってファイルが分類されたSharePoint Syntex表示する必要があります。

ファイルの [ContractTileFormatting.jsセクション](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) では、これらのそれぞれを定義します。

### <a name="client"></a>クライアント

このセクションでは、カードに "Client" を表示する方法を定義し、特定のコントラクトの値を使用します。

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

### <a name="contractor"></a>請負業者

このセクションでは、"Contractor" がカードに表示される方法を定義し、特定の契約の値を使用します。

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

### <a name="fee-amount"></a>手数料額

このセクションでは、カードに "手数料金額" を表示する方法を定義し、特定の契約の値を使用します。

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

[手順 3.契約Power Automate処理するフローを作成するには、次の情報を使用します。](solution-manage-contracts-step3.md)
