---
title: Microsoft SharePoint の同期 Tex でコンテンツセンターを作成する
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: コンテンツセンターを作成する方法について説明します。
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295434"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint の同期 Tex でコンテンツセンターを作成する

この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

ドキュメントを作成および管理するには、まずコンテンツセンターが必要です。 コンテンツセンターはモデル作成インターフェイスで、ドキュメントライブラリに発行されたどのモデルが適用されているかに関する情報も含まれています。</br>

   ![ドキュメントライブラリを選択する](../media/content-understanding/content-center-page.png)</br>

[セットアップ](set-up-content-understanding.md)時に最初のコンテンツセンターを作成します。 ただし、SharePoint 管理者は必要に応じて追加のセンターを作成することもできます。 すべてのモデルのアクティビティをロールアップする必要がある環境では、1つのコンテンツセンターが適している場合がありますが、組織内の複数の部門に対して追加のセンターが必要になる場合があります。これには、それぞれのモデルのニーズや要件が異なる場合があります。

> [!NOTE]
> SharePoint 管理者は、サイトテンプレートを使用して [他の sharepoint サイトを作成するの](https://docs.microsoft.com/sharepoint/create-site-collection) と同じように、コンテンツセンターサイトを作成できます。

新しいコンテンツセンターを作成するには、次のようにします。

1. Microsoft 365 管理センターから、SharePoint 管理センターに移動します。
2. SharePoint 管理センターの [ **サイト**] で、[ **アクティブなサイト**] を選択します。
3. [ **アクティブなサイト** ] ページで、[ **作成**] をクリックし、[ **その他のオプション**] を選択します。
4. [ **テンプレートの選択** ] メニューで、[ **コンテンツセンター**] を選択します。
5. 新しいサイトの場合は、 **サイト名**、 **プライマリ管理者**、および **言語**を指定します。</br>

> [!NOTE] 
> 必要に応じて、コンテンツセンターサイトを選択して、使用可能な任意の言語で表示することができます。 英語のファイルには、現在のモデルのみを作成できます。</br>

6. [ **完了**] を選択します。

### <a name="give-access-to-additional-users"></a>他のユーザーへのアクセスを許可する
 
サイトを作成した後、追加のユーザーに、標準の [SharePoint サイトアクセス許可モデル](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)を使用してサイトへのアクセス権を与えることができます。

## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[コンテンツセンター](create-a-content-center.md) 
 を作成する[ドキュメント理解の概要](document-understanding-overview.md)</br>
[フォーム処理モデルを作成する](create-a-form-processing-model.md)</br>
[モデルを適用する](apply-a-model.md)    
