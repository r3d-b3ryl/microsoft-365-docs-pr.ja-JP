---
title: アイテムが保持または削除されるタイミングを決定するフローチャート
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: フローチャートを使用して、アイテムに複数のアイテム保持ポリシーがある場合、または保持ラベルとアイテム保持ポリシーがある場合の結果を判断する
ms.openlocfilehash: cf35a89faf3ed526c94acf362f1a927eb36420f0
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2022
ms.locfileid: "65286804"
---
# <a name="flowchart-to-determine-when-an-item-will-be-retained-or-permanently-deleted"></a>アイテムが保持または完全に削除されるタイミングを決定するフローチャート

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

次のフローチャートを使用して、アイテムに[保持の原則](retention.md#the-principles-of-retention-or-what-takes-precedence)を適用し、システムがアイテムを保持するか、保持ラベルまたはアイテム保持ポリシーの結果として完全に削除するかを判断します。

このロジック フローは、次のいずれかの条件が適用される場合にアイテムに使用されます。

- 複数のアイテム保持ポリシーが適用されている
- 1 つの保持ラベルと 1 つ以上のアイテム保持ポリシーがある

アイテムが電子情報開示ホールド (または訴訟ホールドまたはインプレース ホールドの古いテクノロジ) の対象になると、アイテム保持ポリシーと保持ラベルの決定フローの前に常に保持されます。

このフローチャートで使用される用語の一部が不明な場合は、「[アイテム保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。


   ![アイテムが保持または完全に削除されるタイミングを決定するフローチャート。](../media/retention-flowchart.svg)

> [!NOTE]
> アイテムの最長保持期間と、アイテム保持ポリシーまたは保持ラベルで指定された最長の期間を区別することが重要です。 アイテムの最短の有効期限とアイテム保持ポリシーで指定した最短の期間についても同様です。
> 
> 詳細については、「[保持の原則](retention.md#the-principles-of-retention-or-what-takes-precedence)」セクションの図の後にある説明を参照してください。
