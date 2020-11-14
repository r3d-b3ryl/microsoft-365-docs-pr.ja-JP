---
title: ゲストアカウントの前提条件
description: ゲストアカウントの構成ガイドラインとそれらを調整する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073226"
---
# <a name="prerequisites-for-guest-accounts"></a>ゲストアカウントの前提条件

Microsoft マネージドデスクトップでは、ゲストアカウントへのアクセスのために、Azure AD 組織で次の設定が必要です。 これらの設定は、[ **外部 id/外部コラボレーション** ] の下の [Azure portal](https://portal.azure.com)で調整できます。

-   **管理者および guest 招待元役割のユーザーは、** **[はい]** に設定することができます
-   [ **共同作業の制限** ] で、次のオプションのいずれかを選択します。
    -   [すべての **ドメインに招待を送信できるようにする (最も包括的な)** ] を選択した場合は、その他の構成は必要ありません。
    -   [指定した **ドメインへの招待を拒否** する] を選択した場合は、Microsoft.com が対象のドメインに一覧表示されていないことを確認してください。
    -   指定した **ドメインへの招待を許可する (最も限定的な)** 場合は、Microsoft.com *が* 対象のドメインに一覧表示されていることを確認してください。

これらの設定を操作する制限を設定する場合は、Azure Active Directory **モダン Workplace サービスアカウント** を除外してください。 たとえば、ゲストアカウントが Intune ポータルにアクセスできないようにする条件付きアクセスポリシーがある場合、 **モダン Workplace Service アカウント** グループをこのポリシーから除外します。

