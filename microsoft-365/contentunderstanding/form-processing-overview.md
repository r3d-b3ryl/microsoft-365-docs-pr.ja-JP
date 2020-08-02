---
title: フォーム処理の概要 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: プロジェクト Cortex でのフォーム処理について説明します。
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540060"
---
# <a name="form-processing-overview-preview"></a>フォーム処理の概要 (プレビュー)
> [!Note]
> この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。

プロジェクト Cortex は、Microsoft PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)フォーム処理を使用して、SharePoint ドキュメントライブラリ内にモデルを作成します。
AI ビルダーフォーム処理を使用すると、機械学習技術を使用して、フォームや請求書などの構造化または半構造化されたドキュメントからキーと値のペアやテーブルデータを特定および抽出する AI モデルを作成できます。

多くの企業では、メール、fax、電子メール、ユーザーなど、さまざまなソースから請求書を受信しています。 これらのドキュメントを処理してデータベースに手動で入力するには、かなりの時間がかかることがあります。 AI を使用して、ドキュメントからテキスト、キーと値のペア、およびテーブルを抽出することにより、フォーム処理によってこのプロセスが自動化されます。 

たとえば、ドキュメントライブラリにアップロードされたすべての発注書ドキュメントを識別するフォーム処理モデルを作成できます。 また、各発注書から、 *PO 番号*、*日付*、*総コスト*など、自分にとって重要な特定のデータを抽出して表示することができます。

サンプルファイルを使用して、モデルを学習し、フォームから抽出する情報を定義します。 ドキュメントのレイアウトは、モデルをトレーニングすることによって得られます。 開始するには5つのフォームドキュメントのみが必要です。 AI ビルは、キーと値のペアのサンプルファイルを分析し、検出されなかった可能性があるものを手動で識別することもできます。  AI ビルダーを使用すると、サンプルファイルのモデルの精度をテストできます。

モデルをトレーニングおよび発行した後、それを使用して、ファイルが SharePoint ドキュメントライブラリにアップロードされたときに実行され、モデルで識別されたデータを抽出する[電力自動化フロー](https://docs.microsoft.com/power-automate/getting-started)を作成します。 抽出したデータは、モデルのドキュメントライブラリビューの列に表示されます。

Office 365 管理者は、SharePoint ドキュメントライブラリの[フォーム処理を有効](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding)にして、ユーザーが[フォーム処理モデルを作成](create-a-form-processing-model.md)できるようにする必要があります。



## <a name="see-also"></a>関連項目
  
[電力の自動化に関するドキュメント](https://docs.microsoft.com/power-automate/)</br>
[フォーム処理モデルを作成する](create-a-form-processing-model.md)</br>
[ドキュメント理解の概要](document-understanding-overview.md)</br>
[トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




