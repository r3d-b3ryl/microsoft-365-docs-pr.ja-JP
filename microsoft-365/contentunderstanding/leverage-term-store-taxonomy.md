---
title: 抽出器を作成するときに用語ストアの分類を活用する
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: ドキュメントに抽出器を作成するときに用語ストアの分類を活用する Microsoft SharePoint の同期 Tex のモデルを理解する。
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296013"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>抽出器を作成するときに用語ストアの分類を活用する


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

ドキュメント内で抽出器を作成する SharePoint の同期について理解すると、 [Managed Metadata service](https://docs.microsoft.com/sharepoint/managed-metadata#terms) の用語ストア分類を活用して、抽出するデータに適した用語を表示することができます。  

例として、モデルは、ドキュメントライブラリにアップロードされたすべての **契約** ドキュメントを識別して分類します。  さらに、このモデルでは、契約 **サービス** の値を各コントラクトから抽出し、ライブラリビューの列に表示します。 契約のさまざまな契約サービスの値の中には、会社で使用されなくなって名前が変更された古い値がいくつかあります。 たとえば、[ *設計*]、[ *グラフィックス*]、または [ *地形* ] の各契約サービスへのすべての参照は、 *クリエイティブ*と呼ばれるようになりました。 モデルでは、契約ドキュメントから古くなった用語のいずれかを抽出するときに、ライブラリビューに現在の用語クリエイティブを表示することをお勧めします。 次の例では、モデルを学習する際に、1つのサンプルドキュメントに、古い *設計*用語が含まれています。

   ![用語ストア](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>用語セットのシノニム 

用語セットは、SharePoint 管理センターの Managed Metadata service 用語ストアで構成されます。 次の例では、 *契約サービス*の [用語セット](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) が、 *クリエイティブ*を含むいくつかの用語を含むように構成されています。  この用語の詳細には、用語に3つの類義語 (*デザイン*、 *グラフィックス*、および *地形*) があり、類義語を *クリエイティブ*に変換する必要があることが示されています。

   ![用語セット](../media/content-understanding/term-store.png)</br>

これを説明する方法がわからない場合は、Mike <してください。  「Contract Services」列を抽出して表示する抽出器を作成すると、その列はクリエイティブサービスの管理メタデータ用語セットを使用するように "マークされています。" という処理をモデルに指示します。 >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>管理されたメタデータフィールドのドキュメントライブラリサイト列を構成する


   ![管理されたメタデータを作成する](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>関連項目
[管理されたメタデータの概要](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[管理メタデータ列を作成する](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





