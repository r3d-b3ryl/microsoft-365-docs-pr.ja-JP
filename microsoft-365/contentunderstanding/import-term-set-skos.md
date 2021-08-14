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
ms.openlocfilehash: edf7afd1eaa8497af6e71d3cc2e2562bb1e349d6c212c59db12a0b435e7f1c15
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53891597"
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
