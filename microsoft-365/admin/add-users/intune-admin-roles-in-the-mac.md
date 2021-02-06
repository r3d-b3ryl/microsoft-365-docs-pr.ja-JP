---
title: Microsoft 365管理センター の Intune 管理者の役割について
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 管理者ロールはビジネス機能にマップされ、管理センターで特定のタスクを実行するための権限を付与します。 たとえば、サービス管理者が Microsoft のサポート チケットを開きます。
ms.openlocfilehash: 48bb0f3d1a3a239025017fda261945094a3eda79
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126083"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターにおける Intune 管理者の役割

Microsoft 365 または Office 365 サブスクリプションには、Microsoft 365 管理センターを使用して組織内のユーザーに割り当てることができる管理者ロールセットがあります。 各管理者ロールは、一般的なビジネス機能にマップされ、組織内のユーザーに管理センターで特定のタスクを実行する許可を与えます。

Microsoft 365 管理センターを使用すると、Microsoft Intune の役割を管理できます。 ただし、これらの役割は、Intune 管理センターで使用可能な役割のサブセットです。 Microsoft Intune の役割の詳細な説明をお探しですか ? 「[Microsoft Intune の役割ベースのアクセス制御 (RBAC)](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)」を確認してください。

Microsoft 365 管理センターでの役割を割り当てる方法の詳細については、「[管理者ロールを割り当てる](assign-admin-roles.md)」を参照してください。

::: moniker range="o365-worldwide"

Microsoft 365 管理センターで、[**役割**] に移動し、任意の役割を選択して詳細ウィンドウを開きます。 [**アクセス許可**] タブを選択して、実行する許可を持った役割を割り当てられた管理者についての詳細な一覧を表示します。 役割にユーザーを追加するには、**[割り当てられた]** または **[割り当てられた管理者]** タブを選択します。

::: moniker-end

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで利用可能なMicrosoft Intune の役割

|管理者ロール     |誰にこの役割を割り当てるか  |
|---------|---------|
|アプリケーション マネージャー     |   モバイルアプリのアプリケーションライフサイクルを管理し、ポリシーに管理されたアプリとビューのデバイス情報と構成プロファイルを表示するユーザーに、アプリケーション マネージャーの役割を割り当てます。  |
|ヘルプデスク オペレーター     |   ユーザーとデバイスにアプリとポリシーを割り当てるユーザーに、ヘルプデスク オペレーターの役割を割り当てます。 |
|Intune の役割の管理者    |   Intune の管理者を他の管理者に割り当てることができるユーザーに、Intune の役割を割り当てることができます。ユーザーは Intune の役割を管理できます。   |
|ポリシーおよびプロファイル マネージャー     |   ポリシーおよびプロファイル マネージャーの役割をユーザーに割り当て	て、コンプライアンス ポリシーの管理、構成プロファイル、Apple の登録を行います。   |
|読み取り専用の演算子     |   ユーザー、デバイス、登録の詳細、構成の表示のみ可能なユーザーに読み取り専用オペレーターの役割を割り当てます。   |
|学校の管理者     |   Intune for Education で Windows 10 と iOS デバイス、アプリ、および構成を管理するためのフルアクセス権をもつユーザーに学校の管理者の役割を割り当てます。   |

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft パートナーの代理管理

Microsoft パートナーと連携している場合、パートナーに管理者ロールを割り当てることができます。 次に、彼らはあなたの会社のユーザーまたはその会社の管理者ロールを割り当てることができます。 たとえば、彼らがあなたのためにオンライン組織をセットアップし管理している場合、彼らにして欲しいのはこれかもしれません。
  
パートナーは、次の役割を割り当てることができます。
  
- パートナー センターを介した多要素認証の管理を除いた、グローバル管理者と同等の特権を持つ完全な管理。

- ヘルプデスク管理者と同等の特権を持つ制限付き管理。

パートナーがこれらの役割をユーザーに割り当てる前に、パートナーを代理管理者としてアカウントに追加する必要があります。 このプロセスは認定パートナーによって開始されます。 パートナーは管理者に電子メールを送信し、代理管理者となる権限を割り当てるかどうか質問します。手順については、「[パートナー リレーションシップの承認または削除](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)」を参照してください。
  
## <a name="related-articles"></a>関連記事

[Microsoft 365 管理者ロールについて](about-admin-roles.md)

[管理者の役割を割り当てる](assign-admin-roles.md)

[Microsoft 365 管理センターのアクティビティ レポート](../activity-reports/activity-reports.md)