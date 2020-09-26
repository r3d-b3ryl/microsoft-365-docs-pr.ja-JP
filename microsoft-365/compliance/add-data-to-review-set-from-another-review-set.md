---
title: 1つのレビューセットから別のレビューセットにデータを追加する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 1つの校閲セットからドキュメントを選択し、それらを別のセットで個別に操作する方法について説明します。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285182"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>別のレビュー セットからレビュー セットにデータを追加

場合によっては、1つの校閲セットからドキュメントを選択して、別のレビューセットで個別に操作する必要があります。 これは、レビューセットのコンテンツを選別して、データのサブセットに対して 分析を実行する場合に、特に役立ちます。

この記事のワークフローに従って、ある校閲セットから別のレビューセットにコンテンツを追加します。

## <a name="create-a-review-set"></a>レビューセットを作成する

開始する前に、データを追加するためのレビューセットを作成する必要があります。  ケースの [ **レビューセット** ] タブに新しいレビューセットを追加できます。 詳細については、「 [レビューセットを作成する](managing-review-sets.md#create-a-review-set)」を参照してください。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>手順 1: 別のレビューセットに追加するコンテンツを識別する

ソース レビュー セットの特定のドキュメントを選択するか、レビュー セット クエリで返されたすべてのアイテムを選択し、レビュー セットから別のレビュー セットにコンテンツを追加できます。 選択したアイテムを追加している場合は、アイテムを選択し、[ **アクション**] を選択してから、[ **別のレビューセットに追加**] を選択します。

![[アクション] メニューの別の校閲セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>手順 2: 別のレビューセットに追加するためのオプションを指定する

[ **別のレビューセットオプションポップアップに追加** ] ページで、アイテムを追加するレビューセットを選択します。 **すべての検索結果**または**選択したアイテム**を追加するかどうかを選択します。  **その他の情報** には、アイテムのすべてのメタデータを含めるオプションと、ドキュメントが新しいレビューセットに追加されたときにソースレビューセットからタグを含める ( **ラベル** チェックボックスをオンにする) 必要があるかどうかが表示されます。  

![別のレビューセットにデータを追加するためのオプション](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

[ **Ok]** をクリックすると、別のレビューセットにコンテンツを追加するための新しいジョブ ( **別のレビューセットへのデータの追加**) が作成されます。 [ **ジョブ** ] タブに移動して、このジョブの進行状況を監視できます。 詳細については、「 [Manage jobs](managing-jobs-ediscovery20.md)」を参照してください。
