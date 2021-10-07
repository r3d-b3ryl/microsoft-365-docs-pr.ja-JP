---
title: 重複検出に近い - 電子情報開示
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
description: データのケース データを分析する場合は、ほぼ重複した検出を使用して、テキスト的に類似したドキュメントをグループ化Advanced eDiscovery。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cbd01bd38f45a397a82a8db3774997349f4eec88
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193209"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>データの重複検出に近いAdvanced eDiscovery

サブセットが同じテンプレートに基づいており、ほとんど同じ定型言語を持つ一連のドキュメントを検討します。ここではいくつかの違いがあります。 レビュー者がこのサブセットを特定し、そのうちの 1 つを徹底的に確認し、残りの部分の違いを確認できる場合、一意の情報を見逃す必要はありません。一方で、すべてのドキュメントを読み取る時間はほんの一部です。 準重複の検出グループは、テキスト的に類似したドキュメントをまとめてグループ化し、レビュープロセスをより効率的にします。

## <a name="how-does-it-work"></a>どのような仕組みなのか。

準重複の検出が実行されると、システムはテキストを含むすべてのドキュメントを解析します。 次に、すべてのドキュメントを互いに比較して、それらの類似度を設定したしきい値よりも大きいかどうかを判断します。 大きい場合は、ドキュメントはグループ化されます。 すべてのドキュメントが比較およびグループ化されると、各グループのドキュメントが「ピボット」としてマークされます。ドキュメントのレビューでは、最初にピボットをレビューし、同じ準重複セット内の他のドキュメントをレビューして、ピボットとレビュー中のドキュメントの違いに焦点を合わせることができます。
