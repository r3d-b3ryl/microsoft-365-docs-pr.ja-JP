---
title: Microsoft SharePoint Syntexを使用してローカル SharePoint サイトにモデルを作成する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: SharePoint Syntexを使用してローカル SharePoint サイトにローカル モデルを作成する方法について説明します。
ms.openlocfilehash: bcd3f1f086af3982cb4a3ecc5fe754cf82f09a70
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535384"
---
# <a name="create-a-model-on-a-local-sharepoint-site-with-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntexを使用してローカル SharePoint サイトにモデルを作成する

SharePoint Syntexでは、独自のSharePoint サイトでモデルをローカルに作成してトレーニングするオプションが提供されるようになりました。 これらのモデルは、作成されたサイトでのみ使用できます。 

SharePoint サイトでドキュメントの分類と抽出をアクティブ化することで、SharePoint Syntexはドキュメント ライブラリ内のファイルを分類し、新しいファイルから情報を抽出し、抽出された情報に基づいてアクティビティを自動化できます。

ローカル モデルの作成をアクティブ化すると、サイトに次のリストとライブラリが追加されます。

- Models ドキュメント ライブラリ
- トレーニング ファイルドキュメント ライブラリ
- 説明テンプレートの一覧
- モデルの使用状況の一覧

この機能は、 [ドキュメント理解モデル](apply-a-model.md) と [事前構築済みモデル](prebuilt-models.md)を作成する場合にのみ使用できます。 

## <a name="create-a-model-on-a-local-site"></a>ローカル サイトでモデルを作成する

1. SharePointドキュメント ライブラリから、分析するファイルを選択し、[**分類と抽出**] を選択します。

    ![[分類と抽出] オプションが強調表示されたSharePointドキュメント ライブラリのスクリーンショット。](../media/content-understanding/local-model-classify-and-extract-option.png) 

2. この機能を初めて使用するときは、サイトでSharePoint Syntexをアクティブ化します。 次のメッセージが表示されます。

    ![[ドキュメントの分類と抽出情報のアクティブ化] ページのスクリーンショット。](../media/content-understanding/local-model-first-run-activate-message.png) 

    > [!NOTE]
    > 管理タスクを実行し、サイトのコンテンツを管理するには、Web サイトの管理アクセス許可が必要です。 これはサイト所有者になります。 機能がアクティブ化されると、リストの管理アクセス許可を持つすべてのユーザーがモデルを作成および管理できるようになります。

3. [ **アクティブ化] を** 選択して続行します。 次のメッセージが表示されます。

    ![モデルを作成するオプションを使用して、ドキュメントの分類と抽出がアクティブ化されたメッセージのスクリーンショット。](../media/content-understanding/local-model-activated-message.png) 

4. [ **モデルの作成] を選択します**。

5. [モデルの作成] パネル **で、モデル** の名前を入力し、モデルの種類を選択して、[ **作成**] を選択します。

    ![[モデルの作成] パネルのスクリーンショット。](../media/content-understanding/local-model-create-a-model.png) 

6. [ドキュメント理解モデルをトレーニング](apply-a-model.md)するか、選択したファイルを使用して[事前構築済みモデルを構成](prebuilt-models.md)します。

7. 完了すると、[ **ライブラリに追加]** パネルが開きます。

    ![適用されたサイトとライブラリを示す [ライブラリに追加] パネルのスクリーンショット。](../media/content-understanding/local-model-add-to-library-panel.png) 

8. [**ライブラリに追加]** パネルに、SharePoint サイトの名前と、モデルが適用されるドキュメント ライブラリが表示されます。 モデルを別のライブラリに適用する場合は、[ **ライブラリに戻る**] を選択し、使用するライブラリを選択します。 次に **[追加]** を選択します。

9. モデルのホーム ページの [ **このサイトでモデルを適用する場所** ] セクションで、モデルが適用されているライブラリを確認できます。 サイト上の他のライブラリにモデルを適用するには、[ **モデルの適用**] を選択します。 

    ![[サイト上でモデルが適用される場所] セクションを示すモデル ホーム ページのスクリーンショット。](../media/content-understanding/local-model-home-page.png) 

