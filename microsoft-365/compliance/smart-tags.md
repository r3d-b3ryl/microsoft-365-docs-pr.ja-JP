---
title: 電子情報開示 (Premium) でスマート タグを設定する
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
ROBOTS: NOINDEX, NOFOLLOW
description: スマート タグを使用すると、電子情報開示 (Premium) ケースのコンテンツを確認するときに機械学習機能を適用できます。 スマート タグ グループを使用して、弁護士とクライアントの特権モデルなどの機械学習検出モデルの結果を表示します。
ms.openlocfilehash: 30d2d6f30f09fe8fb6772a4fb46c6895b174991f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629081"
---
# <a name="set-up-smart-tags-in-ediscovery-premium"></a>電子情報開示 (Premium) でスマート タグを設定する

Microsoft Purview eDiscovery (Premium) の機械学習 (ML) 機能は、レビュー セット内のケース ドキュメントをレビューするときに意思決定プロセスをより効率的にするのに役立ちます。 スマート タグは、レビュー中にドキュメントにタグを付ける場合に、決定が記録される ML 機能を取得する方法です。 スマート タグ グループを作成すると、スマート タグ グループに関連付けられた ML モデルの結果である決定事項が、タグ グループ内のタグとインラインで表示されます。 これにより、特定のドキュメントを確認するときに、ML の結果情報がインラインで表示されます。

## <a name="how-to-set-up-a-smart-tag-group"></a>スマート タグ グループを設定する方法

1. レビュー セットで、[ **レビュー セットの管理** ] をクリックし、[ **タグの管理**] をクリックします。

2. [ **タグ グループの追加]** をクリックし、[ **スマート タグ グループの追加]** を選択します。

3. タグ グループに関連付ける ML モデルを選択します。
    
   これにより、タグ グループと *N 個* の子タグが作成されます。 *N* はモデルの可能な出力の数です。 たとえば、 [弁護士とクライアントの特権検出モデル](attorney-privilege-detection.md) には、次の 2 つの出力が考えられます。 

   - **陽性** – 弁護士クライアント特権コンテンツを含むドキュメントにタグを付ける場合に使用します。
   
   - **負** の値 – 弁護士とクライアントの特権コンテンツを含まないドキュメントにタグを付けるために使用します。
    
    このモデルを選択した場合、2 つの子タグを持つタグ グループ (1 つの子タグは **Positive** 、もう 1 つは **Negative** という名前) がレビュー セットに作成されます。 この例では、各子タグは、弁護士とクライアントの特権検出モデルから可能な出力の 1 つに対応します。

4. 必要に応じて、タグ グループと子タグの名前を変更できます。 たとえば、 **Positive** タグの名前を **Privileged** に、 **負** のタグを **[権限なし]** に変更できます。

## <a name="how-to-use-smart-tags"></a>スマート タグを使用する方法

ドキュメントを確認すると、適切な子タグの横にモデルの結果が表示されます。 たとえば、弁護士とクライアントの特権検出用のスマート タグ グループがあり、特権を持つ可能性のあるドキュメントを確認すると、その結論の理由が適切なタグの横に表示されます。 タグはドキュメントに自動的に適用されないことに注意してください。 校閲者は、ドキュメントにタグを付ける方法を決定します。
