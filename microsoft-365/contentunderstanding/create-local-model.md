---
title: Microsoft サービスを使用して、ローカル SharePointサイトにモデルをSharePoint Syntex
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
description: ローカル モデルを使用してローカル モデルをローカル サイトに作成SharePointする方法SharePoint Syntex。
ms.openlocfilehash: f6eab2d081dda379d8eb2c88d762661d374a1db6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319065"
---
# <a name="create-a-model-on-a-local-sharepoint-site-with-microsoft-sharepoint-syntex"></a>Microsoft サービスを使用して、ローカル SharePointサイトにモデルをSharePoint Syntex

SharePoint Syntex、独自のサイトでローカルにモデルを作成してトレーニングSharePointしました。 これらのモデルは、作成されたサイトでのみ使用できます。 

SharePoint サイトでドキュメントの分類と抽出をアクティブ化することにより、SharePoint Syntex では、ドキュメント ライブラリ内のファイルを分類し、新しいファイルから情報を抽出し、抽出された情報に基づいてアクティビティを自動化できます。

ローカル モデルの作成をアクティブ化すると、次のリストとライブラリがサイトに追加されます。

- モデル ドキュメント ライブラリ
- トレーニング ファイルドキュメント ライブラリ
- 説明テンプレートの一覧
- モデル使用状況一覧

この機能は、ドキュメント理解モデルと [事前構築済](apply-a-model.md) みモデルを作成 [する場合にのみ使用できます](prebuilt-models.md)。 

## <a name="create-a-model-on-a-local-site"></a>ローカル サイトにモデルを作成する

1. ドキュメント ライブラリSharePoint分析するファイルを選択し、[分類して抽出] **を選択します**。

    ![[分類と抽出SharePoint強調表示されたドキュメント ライブラリのスクリーンショット。](../media/content-understanding/local-model-classify-and-extract-option.png) 

2. この機能を初めて使用する場合は、サイトSharePoint Syntexアクティブ化します。 次のメッセージが表示されます。

    ![[ドキュメントの分類と抽出情報のアクティブ化] ページのスクリーンショット。](../media/content-understanding/local-model-first-run-activate-message.png) 

3. [アクティブ **化] を** 選択して続行します。 次のメッセージが表示されます。

    ![モデルを作成するオプションを使用して、ドキュメントの分類と抽出がアクティブ化されたメッセージのスクリーンショット。](../media/content-understanding/local-model-activated-message.png) 

4. [モデル **の作成] を選択します**。

5. [モデル **の作成] パネル** で、モデルの名前を入力し、モデルの種類を選択し、[作成] を選択 **します**。

    ![[モデルの作成] パネルのスクリーンショット。](../media/content-understanding/local-model-create-a-model.png) 

6. ドキュメント理解 [モデルのトレーニングに進むか](apply-a-model.md) 、選択 [した](prebuilt-models.md) ファイルを使用して事前構築済みモデルを構成します。

7. 完了すると、[ライブラリに **追加] パネルが** 開きます。

    ![適用されたサイトとライブラリを示す [ライブラリに追加] パネルのスクリーンショット。](../media/content-understanding/local-model-add-to-library-panel.png) 

8. [ライブラリ **に追加] パネル** に、モデルが適用される SharePointサイトの名前とドキュメント ライブラリが表示されます。 別のライブラリにモデルを適用する場合は、[ライブラリに戻る] を選択し、使用するライブラリを選択します。 次に **[追加]** を選択します。

9. モデル ホーム ページの [このサイトでモデルを適用する場所] セクションで、モデルが適用されているライブラリを確認できます。 サイト上の他のライブラリにモデルを適用するには、[モデルの適用] **を選択します**。 

    ![[サイトでモデルを適用する場所] セクションを示すモデル ホーム ページのスクリーンショット。](../media/content-understanding/local-model-home-page.png) 

