---
title: フォーム処理の概要
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex でのフォーム処理について学ぶ
ms.openlocfilehash: 9a979e0f7e45694f1cc7f98bbe2012c773698297
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976485"
---
# <a name="form-processing-overview"></a>フォーム処理の概要

 ![AI ビルダー](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex は、Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) フォーム処理を使用して、SharePoint ドキュメントライブラリ内にモデルを作成します。

AI Builder フォーム処理を使用して、機械学習テクノロジーを使用する AI モデルを作成し、フォームや請求書などの構造化または半構造化文書からキーと値のペアとテーブルデータを識別し、抽出できます。

組織は、メール、ファックス、電子メールなどのさまざまなソースから大量の請求書を受け取ることがよくあります。これらの文書を処理してデータベースに手動で入力するには、かなりの時間がかかる場合があります。 AI を使用してドキュメントからテキスト、キーと値のペア、およびテーブルを抽出することにより、フォーム処理はこのプロセスを自動化します。 

> [!NOTE]
> フォーム処理シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)」を参照してください。

たとえば、ドキュメント ライブラリにアップロードされたすべての発注書ドキュメントを識別するフォーム処理モデルを作成できます。 次に、各発注書から、*PO番号*、*日付*、*総コスト* など、重要な特定のデータを抽出して表示できます。

![ドキュメント ライブラリ ビュー](../media/content-understanding/doc-lib-done.png)</br>  

サンプルファイルを使用してモデルをトレーニングし、フォームから抽出する情報を定義します。 文書のレイアウトは、モデルをトレーニングすることで学習されます。 開始するのに必要なフォーム ドキュメントは5つだけです。 AI Builderは、サンプル ファイルを分析してキーと値のペアを探します。また、検出されなかった可能性のあるファイルを手動で特定することもできます。  AI ビルダーを使用すると、サンプルファイルでモデルの精度をテストできます。

モデルをトレーニングして公開すると、モデルは [Power Automate フロー](https://docs.microsoft.com/power-automate/getting-started)を作成します。 フローは、ファイルが SharePoint ドキュメントライブラリにアップロードされたときに実行され、モデルで識別されたデータを抽出します。 抽出されたデータは、モデルのドキュメント ライブラリ ビューの列に表示されます。

Office 365 管理者 は、ユーザーが SharePoint ドキュメント ライブラリで[フォーム処理モデルを作成](create-a-form-processing-model.md)できるように、SharePoint ドキュメント ライブラリの[フォーム処理を有効にする](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding)必要があります。 セットアップ中、またはセットアップ後に管理設定でサイトを選択できます。



## <a name="see-also"></a>関連項目
  
[Power Automate ドキュメント](https://docs.microsoft.com/power-automate/)

[フォーム処理モデルを作成する](create-a-form-processing-model.md)

[ドキュメント理解の概要](document-understanding-overview.md)

[トレーニング: AI ビルダーを使用してビジネスの実績を高める](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
