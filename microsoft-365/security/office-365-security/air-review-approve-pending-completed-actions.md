---
title: 自動化された調査と応答で、保留中の修復アクションを確認および承認する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の修復アクションについて説明します。
ms.openlocfilehash: 29a3c2f59ba85c2c5d9965c0c7f262dcba1ecda7
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411988"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a>Office 365 の自動調査の後に、保留中または完了した修復アクションを表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]



![AIR の調査処理 ページ](../../media/air-investigationactionspage.png)

## <a name="approve-or-reject-pending-actions"></a>保留中のアクションを承認 (または拒否) します。

[調査の詳細](air-view-investigation-results.md)を表示している間に、保留中の修復処理を承認または拒否することができます。 自動化された調査が完了するように、この手順をできるだけ早く実行することをお勧めします。

> [!IMPORTANT]
> 修復アクションを承認または拒否するには、適切なアクセス許可が必要です。 [AIR 機能を使用するには、必要なアクセス許可を](office-365-air.md#required-permissions-to-use-air-capabilities)参照してください。

1. [https://protection.office.com](https://protection.office.com) に移動し、サインインします。 これにより、セキュリティ & コンプライアンスセンターに移動できます。

2. [**脅威管理**  >  の**調査**] に移動します。

3. 調査の一覧で、[ **ID** ] 列のアイテムを選択します。 

4. [ **操作** ] タブを選択します。

5. リストからアイテムを選択します。 (これにより、[承認] ボタンと [拒否] ボタンが有効になります)。

6. 選択したアイテムの利用可能な情報を確認し、その操作を承認または拒否します。 
   - **承認** は修復を開始することを許可します。
   - **却下** にはその他のアクションはありません

## <a name="next-steps"></a>次の手順

- [Office 365 の自動調査の詳細と結果](air-view-investigation-results.md)

- [脅威エクスプローラーを使用する](threat-explorer.md)
