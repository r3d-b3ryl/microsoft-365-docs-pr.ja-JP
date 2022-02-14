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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: スマート タグを使用すると、ケース内のコンテンツを確認するときに機械学習機能をAdvanced eDiscoveryできます。 スマート タグ グループを使用して、弁護士クライアント特権モデルなどの機械学習検出モデルの結果を表示します。
ms.openlocfilehash: 80c946da943e4880dbd82ea6b34d238b80030b4c
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807190"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>スマート タグを設定Advanced eDiscovery

機械学習 (ML) 機能Advanced eDiscovery、レビュー セットでケース ドキュメントを確認する際に、意思決定プロセスをより効率的に行うのに役立ちます。 スマート タグは、レビュー中にドキュメントMLタグ付けする際に、意思決定が記録される場所に、重要な機能を提供する方法です。 スマート タグ グループを作成すると、スマート タグ グループに関連付けられた ML モデルの結果である決定がタグ グループ内のタグと一緒に表示されます。 これにより、特定のドキュメントML確認するときに、検索結果情報を一覧で確認できます。

## <a name="how-to-set-up-a-smart-tag-group"></a>スマート タグ グループを設定する方法

1. レビュー セットで、[レビュー セットの **管理] をクリックし、[** タグの管理] **をクリックします**。

2. [タグ **グループの追加] をクリック** し、[スマート タグ **グループの追加] を選択します**。

3. タグ グループMLするモデルを選択します。
    
   これにより、タグ グループと N 子 *タグが* 作成されます。 *ここで、N* はモデルの出力可能な数です。 たとえば、弁護士クライアント特権 [検出モデルには](attorney-privilege-detection.md) 、次の 2 つの出力があります。 

   - **Positive** – 弁護士クライアント特権コンテンツを含むドキュメントにタグ付けする場合に使用します。
   
   - **負** – 弁護士-クライアント特権コンテンツを含むドキュメントにタグを付け設定します。
    
    このモデルを選択すると、レビュー セットに 2 つの子タグを持つタグ グループ (1 つの子タグが **Positive** 、もう 1 つは **負**) が作成されます。 この例では、各子タグは、弁護士とクライアントの特権検出モデルで使用できる出力の 1 つに対応しています。

4. 必要に応じて、タグ グループと子タグの名前を変更できます。 たとえば、正のタグの名前を **Privileged** に変更し、負のタグ **を [****特権ではありません] に変更できます**。

## <a name="how-to-use-smart-tags"></a>スマート タグの使い方

ドキュメントを確認すると、モデルの結果が適切な子タグの横に表示されます。 たとえば、弁護士クライアント特権検出用のスマート タグ グループを持ち、潜在的に特権のあるドキュメントを確認した場合、その結論の理由が適切なタグの横に表示されます。 タグがドキュメントに自動的に適用されるのではない点に注意することが重要です。 レビューアーは、ドキュメントにタグを付け方を決定します。
