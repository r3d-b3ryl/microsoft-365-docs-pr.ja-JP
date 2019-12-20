---
title: Microsoft Threat Protection でインシデントを管理する
description: 状態の割り当てと更新を行う方法について説明します。
keywords: インシデント、インシデント、警告、関連付けられた警告、割り当て、更新、状態、管理、分類、microsoft、365、m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d6b7c754db3b43e909871a5a60fa1ab155f2d01d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806956"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>Microsoft Threat Protection でインシデントを管理する

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

インシデントの管理は、脅威を封じ込めて対処する上でとても重要です。 Microsoft Threat Protection では、デバイス、ユーザー、およびメールボックスにおけるインシデントを管理できます。 


インシデントを管理するには、**インシデント キュー**からインシデントを選択します。 

インシデントの名前を編集し、インシデントを解決し、インシデントの分類と判定を設定できます。 インシデントを自分に割り当てたり、インシデント タグやコメントを追加したりすることもできます。

調査中にあるインシデントから別のインシデントに警告を移動する場合は、この操作は [Alerts (警告)] タブで行うこともできます。こうすることで、関連するすべての警告が含まれた大規模なインシデントまたは小規模なインシデントを作成できます。

## <a name="edit-incident-name"></a>インシデント名を編集する
既定では、インシデントには数値が割り当てられます。 インシデント名は、組織での命名規則に準拠するよう変更できます。
 
## <a name="assign-incidents"></a>インシデントを割り当てる
インシデントがまだ割り当てられていない場合、[**Assign to me (自分に割り当て)**] を選択してインシデントを自分に割り当てることができます。 これにより、インシデントの所有権だけでなくそのインシデントと関連するすべての警告の所有権が自分に割り当てられます。

## <a name="set-status-and-classification"></a>状態と分類を設定する
### <a name="incident-status"></a>インシデントの状態
インシデントは、調査の進捗に合わせて状態を変更することにより、**Active (アクティブ)** または **Resolved (解決済み)** に分類できます。 こうすることで、チームでのインシデントへの対応方法を整理して管理できます。

たとえば、組織の SOC アナリストは、当日の緊急の **Active (アクティブ)** インシデントを確認して、調査のためにそれらを自分に割り当てることができます。

また、インシデントが修復された場合は、SOC アナリストはインシデントを **Resolved (解決済み)** と設定することができます。 インシデントを解決すると、インシデントに含まれているすべての警告が、まだ開かれているものも含めて自動的に閉じられます。 

### <a name="classification-and-determination"></a>分類と判定
分類を設定しないことも、インシデントが真または偽であると指定することもできます。 こうすることで、チームにはインシデントの傾向が示され、チームの学習につながります。 

## <a name="add-comments"></a>コメントを追加する
警告にはコメントを追加することができ、インシデントに関する過去のイベントを表示して、以前に行われた変更を確認できます。

警告に変更またはコメントが加えられるたびに、[Comments and history (コメントと履歴)] セクションに記録されます。

追加されたコメントは直ちにウィンドウに表示されます。

## <a name="add-incident-tags"></a>インシデント タグを追加する
共通した特徴を持つインシデントのグループにフラグを設定するなどの目的に、カスタム タグをインシデントに追加できます。 こうすることで、特定のタグを含むすべてのインシデントのインシデント キューを後からフィルター処理できます。

