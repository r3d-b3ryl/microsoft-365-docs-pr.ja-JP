---
title: テーマ-データ調査
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: データの調査時に、テーマを使用して、一般的なアイデアや概念を検索してドキュメントを整理します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 249d0739e7d83665f3d2a30d544886c43f89e07d
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285523"
---
# <a name="themes-in-data-investigations-preview"></a>データ調査でのテーマ (プレビュー)

ユーザーがドキュメントを合成するときに、ランダムに単語を選択することはありません。これらのユーザーは、いくつかのアイデアや概念を伝えるようにしており、それに応じて単語が選択されます。 Themes モジュールは、同じような主題について議論するドキュメントをクラスター化し、校閲者がドキュメントをより効率的に進めることができるようにします。

## <a name="how-does-themes-work"></a>テーマはどのように機能しますか?

テーマは、ドキュメント全体にわたって表示される共通のテーマを解析するために、作業セット内のテキストが含まれるドキュメントを分析します。 その後、それらのテーマが表示されるドキュメントに割り当てられます。 また、それぞれのテーマの代表的なドキュメントで使用されている単語にラベル付けします。 ドキュメントには複数の件名が含まれることがあるため、多くの場合、ドキュメントには複数のテーマが割り当てられています。 ドキュメントで最も目立つテーマは、その主要なテーマとして指定されます。
