---
title: SKOS ベースの形式を使用して用語セットをインポートする
description: SKOS ベースの形式を使用して用語セットをインポートする方法について説明します。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296078"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>SKOS ベースの形式を使用して用語セットをインポートする

SKOS ベースの形式を使用して用語セットをインポートすることができます。 形式の詳細については、「 [SharePoint 分類 SKOS 形式リファレンス](skos-format-reference.md)」を参照してください。

インポートファイルの保存期間は2万未満にすることをお勧めします。 ファイルが大きいほど、検証とインポートにかかる時間が長くなる可能性があります。

1. SharePoint 管理センターで、 **Content services**を展開し、[ **用語ストア**] をクリックします。

2. 用語セットをインポートする用語グループを選択します。

3. コマンドバーで、[ **用語セットのインポート**] をクリックします。
 
4.  テンプレートとして使用するサンプルファイルをダウンロードする場合は、 **sample-metadata** をクリックして、skos ベースの形式を使用するサンプルファイルを取得します。
 
5.  インポートする用語セット & 用語セットを含むインポートファイルを作成します。

6.  [ **ファイル形式**] で [ **skos (* ttl)**] を選択します。

7.  [ **参照** ] をクリックし、インポートファイルに移動して追加します。

8.  [**インポート**] をクリックします。 インポートが完了するまでパネルを閉じないでください。

ファイルが正常にインポートされると、成功メッセージが表示され、用語ストアが更新され、新しく作成された用語セットに移動できるようになります。

## <a name="see-also"></a>関連項目

[管理されたメタデータの概要](https://docs.microsoft.com/sharepoint/managed-metadata)

[ドキュメント理解の概要](document-understanding-overview.md)

[用語セットのインポート (サイトレベル)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)