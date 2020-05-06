---
title: ほぼ重複した検出-電子情報開示
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
description: 詳細な電子情報開示のケースデータを分析する際に、類似したドキュメントをグループ化するには、近い重複検出を使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4c24e1b67af68dc5fccd900fc390a63e8da3c389
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036442"
---
# <a name="near-duplicate-detection"></a>準重複の検出

サブセットが同じテンプレートを基にしていて、ほとんど同じ定型表現を持っており、ここではいくつかの違いがある、ドキュメントのセットをレビューすることを検討してください。 レビュー担当者がこのサブセットを特定し、そのうちの1つを徹底的に確認して、残りの相違点を確認した場合は、すべてのドキュメントカバーの読み取りにかかる時間が限られているため、固有の情報が失われることはありません。 ほぼ重複した検出グループでは、よく似たドキュメントが一緒に表示され、レビュープロセスの効率を高めることができます。

## <a name="how-does-it-work"></a>どのような仕組みなのか。

近い重複検出が実行されると、システムによってすべてのドキュメントがテキストで解析されます。 次に、すべてのドキュメントを比較して、類似性が設定されたしきい値より大きいかどうかを判断します。 その場合、ドキュメントはグループ化されています。 すべてのドキュメントを比較してグループ化すると、各グループのドキュメントが "pivot" としてマークされます。ドキュメントを確認するには、ピボットを最初に確認して、同じ付近にある重複セット内の他のドキュメントを確認して、ピボットとレビュー中のドキュメントの違いに焦点を合わせます。
