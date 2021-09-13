---
title: SKOS ベースの形式を使用して用語セットをインポートする
description: SKOS ベースのフォーマットを使用して用語セットをインポートする方法を学ぶ
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210843"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>SKOS ベースの形式を使用して用語セットをインポートする

SKOS ベースの形式を使用して用語セットをインポートできます。 形式の詳細については、[SharePoint 分類 SKOS フォーマットのリファレンス](skos-format-reference.md)を参照してください。 この機能には、[SharePoint Syntex](index.md) ライセンスが必要です。

インポートファイルは 20,000 語未満に保つことをお勧めします。 ファイルが大きいと、検証とインポートにかかる時間が長くなる場合があります。

1. SharePoint 管理センターで、[**コンテンツサービス**] を展開し、**用語ストア** をクリックします。

2. 用語セットをインポートする用語グループを選択します。

3. コマンドバーで、[**用語セットのインポート**] をクリックします。

4. テンプレートとして使用するサンプルファイルをダウンロードする場合は、**sample-metadata.ttl** をクリックして、SKOS ベースの形式を使用するサンプル ファイルを取得します。

5. インポートする用語セットと、用語を含むインポートファイルを作成します。

6. [**ファイル形式**]で、[**SKOS (*.ttl)**]を選択します。

7. [**参照**] をクリックして、インポートファイルに移動して追加します。

8. [**インポート**] をクリックします。 インポートが完了するまでパネルを閉じないでください。

ファイルのインポートが成功すると、成功メッセージが表示され、用語ストアが更新され、新しく作成された用語セットに移動できます。

## <a name="see-also"></a>関連項目

[管理されたメタデータの概要](/sharepoint/managed-metadata)

[ドキュメント理解の概要](document-understanding-overview.md)

[用語セット (サイトレベル) をインポートする](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
