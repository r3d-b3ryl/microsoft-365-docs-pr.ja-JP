---
title: Microsoft SharePoint Syntex で抽出子の名前を変更する
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
description: Microsoft SharePoint Syntex で抽出子の名前を変更する方法および理由について説明します。
ms.openlocfilehash: 0b5c52e00b287b6f4b41e7c8c3070261bccfda96
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195451"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex で抽出子の名前を変更する

抽出されたデータ フィールドを別の名前で参照する場合、ある時点で抽出子の名前を変更する必要がある場合があります。 たとえば、組織が契約文書を変更し、文書内で 「顧客」を「クライアント」と呼ぶことにする場合などです。 モデル内で [顧客] フィールドを抽出する場合、[クライアント] に名前を変更することができます。

更新されたモデルを SharePoint ドキュメント ライブラリと同期すると、ドキュメント ライブラリ ビューに新しい [クライアント] 列が表示されます。 ビューでは過去のアクティビティの [顧客] 列が保持されますが、モデルによって処理されるすべての新しいドキュメントの新しい [クライアント] 列が更新されます。 

> [!IMPORTANT]
>  更新したモデルを以前に適用したドキュメント ライブラリと同期して新しい列名を表示してください。 

## <a name="rename-an-extractor"></a>抽出子の名前を変更する

エンティティ抽出の名前を変更するには、次の手順を実行します。

1. コンテンツ センターから[**モデル**]を選択して、モデルリストを表示します。

2. [**モデル**] ページの [**名前**] 列で、抽出子の名前を変更するモデルを選択します。

3. [**エンティティ抽出**] で、名前を変更する抽出子の名前を選択し、[**名前の変更**] を選択します。</br>

    ![[名前の変更] オプションが強調表示された状態で選択された抽出子を示す [エンティティ抽出] セクションのスクリーンショット。](../media/content-understanding/entity-extractor-rename.png) </br>

4. [**エンティティ抽出の名前の変更**] パネル上で: 

   a. [**新しい名前**] で抽出子の新しい名前を入力します。</br>

    ![[エンティティ抽出] パネルを示すスクリーンショット。](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   b. (省略可能)[**詳細設定**] で、既存のサイト列を関連付けるかどうかを選択します。

5. [**名前の変更**] を選択します。

## <a name="see-also"></a>関連項目
[エクストラクターを作成する](create-an-extractor.md)

[分類子を作成する](create-a-classifier.md)

[モデルの名前を変更する](rename-a-model.md)

[説明の種類](explanation-types-overview.md)

[エクストラクターの作成時に用語ストアの分類を活用する](leverage-term-store-taxonomy.md)

[ドキュメント理解の概要](document-understanding-overview.md)

[モデルを適用する](apply-a-model.md) 
