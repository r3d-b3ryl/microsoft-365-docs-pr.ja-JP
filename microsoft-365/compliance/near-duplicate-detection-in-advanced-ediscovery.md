---
title: 電子情報開示での重複データの検出に近い
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ほぼ重複データ検出を使用して、電子情報開示 (プレミアム) でケース データを分析するときに、テキストに似たドキュメントをグループ化します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e22444845005f4cf155340e13856722976715d91
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64997606"
---
# <a name="near-duplicate-detection-in-ediscovery-premium"></a>電子情報開示のほぼ重複データ検出 (プレミアム)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

サブセットが同じテンプレートに基づいており、ほとんど同じ定型言語を持つ一連のドキュメントを確認する必要があるとします。ここではいくつかの違いがあります。 校閲者がこのサブセットを特定し、そのうちの 1 つを十分に確認し、残りの部分の違いを確認できる場合は、一意の情報を見逃す必要はありません。一意の情報は見逃せません。一部の時間しかかからず、カバーするすべてのドキュメントを読み取る必要がありました。 準重複の検出グループは、テキスト的に類似したドキュメントをまとめてグループ化し、レビュープロセスをより効率的にします。

## <a name="how-does-it-work"></a>どのような仕組みですか?

準重複の検出が実行されると、システムはテキストを含むすべてのドキュメントを解析します。 次に、すべてのドキュメントを互いに比較して、それらの類似度を設定したしきい値よりも大きいかどうかを判断します。 大きい場合は、ドキュメントはグループ化されます。 すべてのドキュメントが比較およびグループ化されると、各グループのドキュメントが「ピボット」としてマークされます。ドキュメントのレビューでは、最初にピボットをレビューし、同じ準重複セット内の他のドキュメントをレビューして、ピボットとレビュー中のドキュメントの違いに焦点を合わせることができます。
