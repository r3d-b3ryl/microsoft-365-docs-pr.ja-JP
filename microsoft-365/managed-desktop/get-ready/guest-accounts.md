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
ms.openlocfilehash: 2c1878dc9095fc4c4cfbd307154097cc6ff572f1
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623998"
---
# <a name="prerequisites-for-guest-accounts"></a>ゲスト アカウントの前提条件

## <a name="external-collaboration-settings"></a>外部コラボレーションの設定

Microsoft マネージド デスクトップアカウントアクセスには、Azure ADの設定が必要です。 これらの設定は [、Azure portal](https://portal.azure.com) の [外部 **ID/ 外部コラボレーション設定] で調整できます**。

-   [ **ゲスト招待の制限] を** [メンバー ユーザー] に設定し、特定の管理者ロールに割り当てられたユーザーは、メンバーのアクセス許可を持つゲストを含むゲスト ユーザー **を招待できます。**
-   [ **コラボレーションの制限] で**、次のオプションを選択します。
    -   [任意の **ドメインへの招待の** 送信を許可する ( 最も包括的な) ] を選択した場合、他の構成は必要ありません。
    -   [指定した **ドメインへの** 招待を拒否する] を選択した場合は、Microsoft.com ドメインに一覧が表示されません。
    -   [指定した **ドメインへの** 招待のみを許可する ] (最も制限の厳しい) を *選択した場合* は、Microsoft.com がターゲット ドメインに表示されます。

これらの設定を操作する制限を設定する場合は、必ずモダン Workplace サービス Azure Active Directory **を除外してください**。 たとえば、ゲスト アカウントによる Intune ポータルへのアクセスを妨げる条件付きアクセス ポリシーがある場合は、このポリシーからモダン **Workplace サービス** アカウント グループを除外します。

## <a name="unlicensed-intune-admin"></a>ライセンスのない Intune 管理者

[ **ライセンスのない管理者へのアクセスを許可する** ] 設定を有効にする必要があります。 この設定を有効にしない場合、Azure 組織にサービスを提供するために Azure ADアクセスしようとするときにエラーが発生する可能性があります。 アクセス範囲は、運用スタッフを含むユーザーに割り当てられた役割によって定義されますので、セキュリティへの影響を気にすることなく、この設定を安全に有効にできます。

この設定を有効にするには、次の手順を実行します。

1. 管理センターのMicrosoft エンドポイント マネージャー[移動します](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. [テナント管理 **の役割**  >  **]**  >  **[管理者ライセンス] に移動します**。
3. [ **ライセンスのない管理者へのアクセスを許可する] で、[** はい] を **選択します**。

> [!IMPORTANT]
> [はい] を選択した後は、この設定を元に **戻すことはできません**。

詳細については、「ライセンスのない管理者」[を参照Microsoft Intune。](/mem/intune/fundamentals/unlicensed-admins)
## <a name="steps-to-get-ready"></a>準備の手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. [準備状況の評価ツール](readiness-assessment-tool.md)を使用します。
3. [ゲスト アカウントの前提条件](guest-accounts.md) (この記事)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する](authentication.md)
7. [Microsoft マネージド デスクトップのアプリ](apps.md)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md)
