---
title: Microsoft SharePoint Syntex でのフォーム処理の概要
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
description: MICROSOFT SharePoint Syntexで AI ビルドを使用してフォーム処理モデルを作成する方法について説明します。
ms.openlocfilehash: 7b9ff8b8a1014dfb47aa7061caf31599e497c18a
ms.sourcegitcommit: 37111bc0c5a6cc4690f7144a019bbff11d44858f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65463189"
---
# <a name="form-processing-overview-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex でのフォーム処理の概要

 ![AI ビルダー。](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex は、Microsoft PowerApps [AI Builder](/ai-builder/overview) フォーム処理を使用して、SharePoint ドキュメント ライブラリ内にモデルを作成します。

AI Builder フォーム処理を使用すると、機械学習テクノロジを使用して、フォームや請求書などの構造化ドキュメントまたは半構造化ドキュメントからキーと値のペアとテーブル データを識別して抽出する AI モデルを作成できます。

組織は、多くの場合、メール、FAX、電子メールなど、さまざまなソースから大量の請求書を受け取ります。 これらのドキュメントを処理し、データベースに手動で入力すると、かなりの時間がかかる場合があります。 AI を使用してドキュメントからテキスト、キーと値のペア、およびテーブルを抽出することにより、フォーム処理はこのプロセスを自動化します。 

> [!NOTE]
> フォーム処理シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](./adoption-getstarted.md)」を参照してください。

たとえば、ドキュメント ライブラリにアップロードされたすべての発注書ドキュメントを識別するフォーム処理モデルを作成できます。 各購買発注書から、 *PO 番号*、 *日付*、 *合計コスト* など、重要な特定のデータを抽出して表示できます。

![ドキュメント ライブラリ ビュー。](../media/content-understanding/doc-lib-done.png)</br>  

サンプルファイルを使用してモデルをトレーニングし、フォームから抽出する情報を定義します。 文書のレイアウトは、モデルをトレーニングすることで学習されます。 開始するのに必要なフォーム ドキュメントは5つだけです。 AI Builder は、キーと値のペアについてサンプル ファイルを分析し、検出されなかった可能性のあるファイルを手動で識別することもできます。  AI ビルダーを使用すると、サンプルファイルでモデルの精度をテストできます。

モデルをトレーニングして発行すると、モデルによって[Power Automateフロー](/power-automate/getting-started)が作成されます。 フローは、ファイルが SharePoint ドキュメントライブラリにアップロードされたときに実行され、モデルで識別されたデータを抽出します。 抽出されたデータは、モデルのドキュメント ライブラリ ビューの列に表示されます。

Office 365管理者は、ユーザーがフォーム処理モデルを作成できるようにするために、SharePoint ドキュメント ライブラリの[フォーム処理を](create-a-form-processing-model.md)[有効にする](./set-up-content-understanding.md)必要があります。 セットアップ中、またはセットアップ後に管理設定でサイトを選択できます。

## <a name="file-limitations"></a>ファイルの制限事項

フォーム処理モデルを使用する場合は、[ファイルの使用に関する必要条件と制限事項](/ai-builder/form-processing-model-requirements)にご注意ください。

## <a name="supported-languages"></a>サポートされている言語

フォーム処理では、73 を超える言語のドキュメントがサポートされます。 言語の一覧については、「 [フォーム処理言語のサポート](/power-platform-release-plan/2021wave2/ai-builder/form-processing-new-language-support)」を参照してください。

## <a name="multi-geo-environments"></a>Multi-Geo 環境

[Microsoft 365 Multi-Geo 環境](../enterprise/microsoft-365-multi-geo.md)で SharePoint Syntex をセットアップする場合、中央の場所でフォーム処理を使用するように構成することしかできません。 サテライトの場所でフォーム処理を使用する場合は、Microsoft サポートに連絡してください。

## <a name="custom-environments"></a>カスタム環境

Power Platform の処理に (既定の環境ではなく) カスタム環境を使用する場合は、追加のセットアップ要件があります。 詳細については、「 [カスタム Power Platform 環境](set-up-content-understanding.md#requirements)」を参照してください。


## <a name="see-also"></a>関連項目
  
[Power Automate ドキュメント](/power-automate/)

[フォーム処理モデルを作成する](create-a-form-processing-model.md)

[ドキュメント理解の概要](document-understanding-overview.md)

[トレーニング: AI ビルダーを使用してビジネスの実績を高める](/learn/paths/improve-business-performance-ai-builder/?source=learn)