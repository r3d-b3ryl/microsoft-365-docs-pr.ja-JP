---
title: 電子情報開示での重複データの検出に近い
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: ほぼ重複データ検出を使用して、電子情報開示 (Premium) でケース データを分析するときに、テキストに似たドキュメントをグループ化します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 985374558189b2001c6f11e09581f7cb3ed6d11b
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622571"
---
# <a name="near-duplicate-detection-in-ediscovery-premium"></a>電子情報開示での重複データの検出に近い (Premium)

サブセットが同じテンプレートに基づいており、ほとんど同じ定型言語を持つ一連のドキュメントを確認する必要があるとします。ここではいくつかの違いがあります。 校閲者がこのサブセットを特定し、そのうちの 1 つを十分に確認し、残りの部分の違いを確認できる場合は、一意の情報を見逃す必要はありません。一意の情報は見逃せません。一部の時間しかかからず、カバーするすべてのドキュメントを読み取る必要がありました。 準重複の検出グループは、テキスト的に類似したドキュメントをまとめてグループ化し、レビュープロセスをより効率的にします。

## <a name="how-does-it-work"></a>どのような仕組みですか?

準重複の検出が実行されると、システムはテキストを含むすべてのドキュメントを解析します。 次に、すべてのドキュメントを互いに比較して、それらの類似度を設定したしきい値よりも大きいかどうかを判断します。 大きい場合は、ドキュメントはグループ化されます。 すべてのドキュメントが比較およびグループ化されると、各グループのドキュメントが「ピボット」としてマークされます。ドキュメントのレビューでは、最初にピボットをレビューし、同じ準重複セット内の他のドキュメントをレビューして、ピボットとレビュー中のドキュメントの違いに焦点を合わせることができます。
