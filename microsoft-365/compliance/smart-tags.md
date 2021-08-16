---
title: スマート タグを設定Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: スマート タグを使用すると、ケース内のコンテンツを確認するときに機械学習機能をAdvanced eDiscoveryできます。 スマート タグ グループを使用して、弁護士クライアント特権モデルなどの機械学習検出モデルの結果を表示します。
ms.openlocfilehash: 4b793b53001a9d03e53d9aadac1bd39d2d6c98d8ab498d91be12d9a6886e185b
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53859781"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>スマート タグを設定Advanced eDiscovery

機械学習 (ML) 機能Advanced eDiscovery、レビュー セットでケース ドキュメントを確認する際に、意思決定プロセスをより効率的に行うのに役立ちます。 スマート タグは、レビュー中にドキュメントMLタグ付けする際に、意思決定が記録される場所に、重要な機能を提供する方法です。 スマート タグ グループを作成すると、スマート タグ グループに関連付けられた ML モデルの結果である決定がタグ グループ内のタグと一緒に表示されます。 これにより、特定のドキュメントML確認するときに、検索結果情報を一覧で確認できます。

## <a name="how-to-set-up-a-smart-tag-group"></a>スマート タグ グループを設定する方法

1. レビュー セットで、[レビュー セットの管理] **をクリックし** 、[タグの管理] **をクリックします**。

2. [タグ **グループの追加] をクリック** し、[スマート タグ **グループの追加] を選択します**。

3. タグ グループMLするモデルを選択します。
    
   これにより、タグ グループと *N 子タグが* 作成されます。 *ここで、N* はモデルの出力可能な数です。 たとえば、弁護士クライアント特権 [検出モデルには](attorney-privilege-detection.md) 、次の 2 つの出力があります。 

   - **Positive** – 弁護士クライアント特権コンテンツを含むドキュメントにタグ付けする場合に使用します。
   
   - **負** – 弁護士-クライアント特権コンテンツを含むドキュメントにタグを付け設定します。
    
    このモデルを選択すると、レビュー セットに 2 つの子タグを持つタグ グループ (1 つの子タグが **正** で、もう 1 つは **負**) が作成されます。 この例では、各子タグは、弁護士とクライアントの特権検出モデルで使用できる出力の 1 つに対応しています。

4. 必要に応じて、タグ グループと子タグの名前を変更できます。 たとえば、正のタグの名前を **[特権**] に、負のタグ **を [****特権ではありません] に変更できます**。 

## <a name="how-to-use-smart-tags"></a>スマート タグの使い方

ドキュメントを確認すると、モデルの結果が適切な子タグの横に表示されます。 たとえば、弁護士クライアント特権検出用のスマート タグ グループを持ち、潜在的に特権のあるドキュメントを確認した場合、その結論の理由が適切なタグの横に表示されます。 タグがドキュメントに自動的に適用されるのではない点に注意することが重要です。 レビューアーは、ドキュメントにタグを付け方を決定します。
