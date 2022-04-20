---
title: あるレビュー セットから別のレビュー セットにデータを追加する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 04/05/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 1 つのレビュー セットからドキュメントを選択し、Microsoft Purview 電子情報開示 (プレミアム) ケースの別のセットでドキュメントを個別に操作する方法について説明します。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: deb0389a4f4bd9bafedd3b2a8dd6c367c6e78fbb
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941173"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>別のレビュー セットからレビュー セットにデータを追加

場合によっては、1 つのレビュー セットからドキュメントを選択し、別のレビュー セットで個別に操作することが必要になる場合があります。 これは、レビューセットのコンテンツを選別して、データのサブセットに対して 分析を実行する場合に、特に役立ちます。

この記事のワークフローに従って、1 つのレビュー セットから別のレビュー セットにコンテンツを追加します。

## <a name="create-a-review-set"></a>レビュー セットを作成する

開始する前に、データを追加するレビュー セットを作成する必要があります。  新しいレビュー セットは、ケースの **[校閲セット** ] タブに追加できます。 詳細については、「 [レビュー セットの作成](managing-review-sets.md#create-a-review-set)」を参照してください。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>手順 1: 別のレビュー セットに追加するコンテンツを特定する

ソース レビュー セットの特定のドキュメントを選択するか、レビュー セット クエリで返されたすべてのアイテムを選択し、レビュー セットから別のレビュー セットにコンテンツを追加できます。 選択したアイテムを追加する場合は、アイテムを選択し、[ **アクション**] を選択して、[ **別のレビュー セットに追加]** を選択します。

![[アクション] メニューの別のレビュー セットに追加します。](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>手順 2: 別のレビュー セットに追加するためのオプションを指定する

[ **別のレビュー セット オプションに追加]** ポップアップ ページで、アイテムを追加するレビュー セットを選択します。 **[すべての検索結果**] または [**選択済みアイテム]** のどちらを追加するかを選択します。  **追加情報** には、アイテムのすべてのメタデータを含めるオプションと、ドキュメントが新しいレビュー セットに追加されたときにソース レビュー セットからタグを含めるかどうかを ( **[ラベル** ] チェック ボックスをオンにして) 含めるかどうかを示します。  

![別のレビュー セットにデータを追加するためのオプション。](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

**[OK]** をクリックすると、新しいジョブ (**別のレビュー セットへのデータの追加** という名前) が作成され、コンテンツが別のレビュー セットに追加されます。 [ **ジョブ]** タブに移動し、このジョブの進行状況を監視できます。 詳細については、「ジョブの [管理](managing-jobs-ediscovery20.md)」を参照してください。
