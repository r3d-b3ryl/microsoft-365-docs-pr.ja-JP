---
title: Microsoft SharePoint Syntex でモデルを複製する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft SharePoint Syntex でモデルを複製する方法と理由について説明します。
ms.openlocfilehash: dc8668ccf407e881bb2114cb679b1ed2049c256e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156440"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex でモデルを複製する

文書理解モデルを複製すると、新しいモデルを作成する必要がある場合に時間や労力を節約できます。また、既存モデルが必要なモデルと非常に似ていることを把握します。

たとえば、「Contracts」という名前の既存モデルでは、作業する必要がある同じファイルが分類されます。 新しいモデルは既存のデータの一部を抽出しますが、一部の追加データを抽出するには更新する必要があります。 新しいモデルを一から作成してトレーニングする代わりに、複製モデル機能を使用して契約モデルのコピーを作成することができます。これにより、サンプル ファイルやエンティティ抽出など、関連するトレーニング アイテムもすべてコピーされます。

モデルを複製すると、名前を変更した後 (たとえば「Contract Renewals (契約書の更新)」に)、モデルを更新できます。 たとえば、必要ない既存の抽出フィールドの一部を削除し、モデルをトレーニングして新しいフィールド (たとえば、「更新日」) を抽出することができます。

## <a name="duplicate-a-model"></a>モデルを複製する

文書理解モデルを複製するには、次の手順を実行します。

1. コンテンツ センターから[**モデル**]を選択して、モデルリストを表示します。

2. **モデル** ページで、複製するモデルを選択します。

3. リボンまたは [**アクションの表示**] ボタン (モデル名の横) を使用して、[**複製する**] を選択します。</br>

    ![[複製] オプションが強調表示された状態で選択されたモデルを示す [モデル] ページのスクリーンショット。](../media/content-understanding/select-model-duplicate-both.png) </br>

4. [**モデルの複製**] パネル上で: 

   a. [**名前**]の下に、複製するモデルの新しい名前を入力します。</br>

    ![[モデルの複製] パネルを示すスクリーンショット。](../media/content-understanding/duplicate-model-panel.png) </br>

   b. [**説明**]下で、新しいモデルの説明を追加します。

   c. (省略可能)[**詳細設定**] で、既存の [コンテンツ タイプ](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)を関連付けるかどうかを選択します。

5. [**複製する**] を選択します。

## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)

[モデルの名前を変更する](rename-a-model.md)

[抽出子を作成する](create-an-extractor.md)

[ドキュメント理解の概要](document-understanding-overview.md)

[説明の種類](explanation-types-overview.md)

[モデルを適用する](apply-a-model.md) 

[SharePoint Syntex アクセシビリティ モード](accessibility-mode.md)