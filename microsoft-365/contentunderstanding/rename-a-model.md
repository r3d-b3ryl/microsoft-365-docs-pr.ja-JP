---
title: Microsoft SharePoint Syntex の文書理解モデルの名前を変更する
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
localization_priority: Priority
description: Microsoft SharePoint Syntex でモデルの名前を変更する方法と理由について説明します。
ms.openlocfilehash: c20d0b0903850e2ff0f0ec68990710001bf64350ae4ab6c123cc12f9125e234d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53871008"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex の文書理解モデルの名前を変更する

ある時点で、文書理解モデルの名前を変更する必要がある場合があります。 一般的な例として、モデルの最初の下書きを作成するときに、最終的な名前について深く考えていない場合があります (たとえば、「AlexWilburModel1」 という名前を付けてしまうかもしれません)。 モデルの最終処理が近くなり使用の調整に入るると、より適切な名前は「Contract Renewals (契約更新)」であると気付き、名前を変更しようとする場合があります。  

別の例として、プロセスやドキュメントの種類を別の名前で参照するよう決定する場合があります。 たとえば、モデルを作成し、それを適用する準備が整うと、すべての「Contract (契約)」が正式に「Agreement (契約)」と呼ばれるよう命じる場合があります。 必要に応じて、モデルの名前を「Contract Renewals (契約の更新)」 から「Agreement Renewals (契約の更新)」に変更することができます。

> [!IMPORTANT]
> ドキュメント ライブラリに適用されていない文書理解モデルの名前のみを変更できます。 

モデルの名前を変更すると、モデルに関連づけられる[コンテンツ タイプ](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)の名前が変更されます。

## <a name="rename-a-model"></a>モデルの名前を変更する

文書理解モデルの名前を変更するには、次の手順を実行します。

1. コンテンツ センターから[**モデル**]を選択して、モデルリストを表示します。

2. **モデル** ページで、名前を変更するモデルを選択します。

3. リボンまたは [**アクションの表示**] ボタン (モデル名の横) を使用して、[**名前の変更**] を選択します。 </br>

    ![[名前の変更] オプションが強調表示された状態で選択されたモデルを示す [モデル] ページのスクリーンショット。](../media/content-understanding/select-model-rename-both.png) </br>

4. [**モデルの名前を変更する**] パネル上で: 

   a. [**新しい名前**]の下に、名前を変更するモデルの新しい名前を入力します。</br>

    ![[名前の変更] パネルを示すスクリーンショット。](../media/content-understanding/rename-model-panel.png) </br>

   b. (省略可能)[**詳細設定**] で、既存の [コンテンツ タイプ](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)を関連付けるかどうかを選択します。 [**既存のコンテンツ タイプを使用する**] を選択すると、選択されたコンテンツ タイプに合わせてモデルの名前が変更されます。

5. [**名前の変更**] を選択します。

## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)

[抽出子を作成する](create-an-extractor.md)

[抽出子の名前を変更する](rename-an-extractor.md)

[ドキュメント理解の概要](document-understanding-overview.md)

[説明の種類](explanation-types-overview.md)

[モデルを適用する](apply-a-model.md) 
