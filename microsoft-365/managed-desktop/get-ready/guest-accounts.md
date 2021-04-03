---
title: ゲスト アカウントの前提条件
description: ゲスト アカウントの構成ガイドラインと調整方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574609"
---
# <a name="prerequisites-for-guest-accounts"></a>ゲスト アカウントの前提条件

Microsoft Managed Desktop では、ゲスト アカウント アクセス用に Azure AD設定が必要です。 これらの設定は [、Azure portal](https://portal.azure.com) の [外部 **ID/ 外部コラボレーション] で調整できます**。

-   **ゲスト 招待者ロールの管理者とユーザーは、[はい** ] に設定して招待 **できます**
-   [ **コラボレーションの制限] で**、次のオプションを選択します。
    -   [任意の **ドメインへの招待の** 送信を許可する ( 最も包括的な) ] を選択した場合、他の構成は必要ありません。
    -   [指定した **ドメインへの** 招待を拒否する] を選択した場合は、Microsoft.com ドメインに一覧が表示されません。
    -   [指定した **ドメインへの** 招待のみを許可する ] (最も制限の厳しい) を *選択した場合* は、Microsoft.com がターゲット ドメインに表示されます。

これらの設定を操作する制限を設定する場合は、必ず Azure Active Directory Modern **Workplace Service アカウントを除外してください**。 たとえば、ゲスト アカウントによる Intune ポータルへのアクセスを妨げる条件付きアクセス ポリシーがある場合は、このポリシーからモダン **Workplace サービス** アカウント グループを除外します。

## <a name="steps-to-get-ready"></a>準備の手順

1. [Microsoft Managed Desktop の前提条件を確認します](prerequisites.md)。
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md) (この記事)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する](authentication.md)
7. [Microsoft マネージド デスクトップのアプリ](apps.md)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md)