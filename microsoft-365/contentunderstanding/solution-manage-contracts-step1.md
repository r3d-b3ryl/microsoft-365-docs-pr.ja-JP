---
title: 手順 1. Syntex SharePointを使用してコントラクト ファイルを識別し、データを抽出する
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
description: Syntex を使用して、SharePoint ソリューションを使用してコントラクト ファイルを識別し、データを抽出するMicrosoft 365します。
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281211"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>手順 1. Syntex SharePointを使用してコントラクト ファイルを識別し、データを抽出する

組織では、受信した多数のファイルからすべての契約ドキュメントを識別して分類する方法が必要です。 また、特定された各コントラクト ファイル内のいくつかの重要な要素 (クライアント、契約者、手数料金額など)をすばやく *表示できます*。 これを行うには[、Syntex](index.md) SharePointを使用してドキュメント理解モデルを作成し、それをドキュメント ライブラリに適用します。

[ドキュメントの理解](document-understanding-overview.md) では、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。 ドキュメント理解モデルは、必要な情報がテーブルやフォーム (コントラクトなど) に含まれている必要のない非構造化ドキュメントや半構造化ドキュメントから情報を抽出する場合にも最適です。

1. 最初に、モデルを "トレーニング" して、識別しようとしているコンテンツ タイプ (契約) に固有の特性を検索するために使用できる少なくとも 5 つのサンプル ファイルを見つける必要があります。 

2. Syntex SharePoint使用して、新しいドキュメント理解モデルを作成します。 サンプル ファイルを使用して、分類子 [を作成する必要があります](create-a-classifier.md)。 サンプル ファイルを使用して分類子をトレーニングすると、会社の契約に表示される特性に固有の特性を検索できます。 たとえば、サービス契約、契約条件、報酬など、契約内の特定の文字列を検索する "説明 ["](create-a-classifier.md#create-an-explanation)を作成 *します*。 説明をトレーニングして、ドキュメントの特定のセクションでこれらの文字列を探したり、他の文字列の横に位置したりすることもできます。 分類子に必要な情報をトレーニングしたと思う場合は、サンプル ファイルのサンプル セットでモデルをテストして、その効率を確認できます。 テスト後、必要に応じて説明を変更して、より効率的に行えます。 

3. モデルでは、抽出プログラム [を作成して](create-an-extractor.md) 、各コントラクトから特定のデータを抽出できます。 たとえば、契約ごとに、最も懸念される情報は、クライアントが誰か、契約者の名前、および総コストです。

4. モデルを正常に作成したら、そのモデルを[ドキュメント ライブラリSharePoint適用します](apply-a-model.md)。 ドキュメントをドキュメント ライブラリにアップロードすると、ドキュメント理解モデルが実行され、モデルで定義したコントラクト コンテンツ タイプに一致するファイルすべてが識別され、分類されます。 コントラクトとして分類されたファイルはすべて、カスタム ライブラリ ビューに表示されます。 ファイルには、抽出プログラムで定義した各コントラクトの値も表示されます。

   ![ドキュメント ライブラリ内のコントラクト](../media/content-understanding/doc-lib-solution.png)

5. さらに、契約の保持要件がある場合は、モデルを使用して保持ラベルを適用して、指定[](apply-a-retention-label-to-a-model.md)した期間契約が削除されるのを防ぐ方法もあります。

## <a name="next-step"></a>次の手順

[手順 2.契約Microsoft Teamsチャネルを作成するには、次の情報を使用します。](solution-manage-contracts-step2.md)