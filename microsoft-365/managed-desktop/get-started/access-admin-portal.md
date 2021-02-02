---
title: 管理ポータルにアクセスする
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
description: 管理ポータルへのアクセスの制御など、管理ポータルを検索して使用する方法。
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 5b7ba0db52f06f7b3f6fce596015b56c8e46c6c2
ms.sourcegitcommit: 2c4c7ebe9bea52765ece0ed27d3ea77313711b10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "50068955"
---
# <a name="access-the-admin-portal"></a>管理ポータルにアクセスする

Microsoft マネージド デスクトップ サービスへのゲートウェイは [、Microsoft Endpoint Manager です](https://endpoint.microsoft.com/)。 このポータルのデバイス管理の機能について詳しくは、Microsoft Endpoint Manager のドキュメント [をご覧ください](https://docs.microsoft.com/mem/)。

> [!NOTE]
> [Microsoft Endpoint Manager では、](https://endpoint.microsoft.com/)次のブラウザーがサポートされています。
> - Microsoft Edge (最新バージョン)
> - Microsoft Internet Explorer 11
> - Safari (最新バージョン、Mac のみ)
> - Chrome (最新バージョン)
> - Firefox (最新バージョン)

Microsoft Endpoint Manager の Microsoft マネージド デスクトップの管理機能にアクセスするには、管理者アカウントに特定のアクセス許可が必要です。 役割ベースのアクセス制御を使用して、組織内のこれらの機能への管理者アクセスを管理できます。 複数の Azure Active Directory (Azure AD) 管理者ロールと組み込みの Microsoft マネージド デスクトップの役割を使用して、Microsoft マネージド デスクトップ管理ポータル内のさまざまな機能を詳細に制御できます。 Azure Active Directory ロールの詳細については、「Azure Active Directory での管理者 [ロールのアクセス許可」を参照してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 さまざまな Microsoft 製品ADに適用される Azure AD 管理者ロールとは異なり、組み込みのロールは Microsoft マネージド デスクトップに固有であり、このサービスの管理者機能へのアクセスのみを保証します。 管理者は、組み込みのロールをユーザーに個別に割り当てるか、Azure AD 管理者ロールと組み合わせて割り当て、既存の管理者アカウントに Microsoft マネージド デスクトップのアクセス許可を追加できます。

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Microsoft マネージド デスクトップ アクセスを使用した Azure Active Directory ロール

|Azure AD ロール  |Microsoft マネージド デスクトップのアクセス許可  |
|---------|---------|
|グローバル管理者     | この役割を持つ管理者は **、Microsoft** マネージド デスクトップ管理ポータルのすべての機能に対する読み取りおよび書き込みアクセス許可を持っています。         |
|グローバル閲覧者     | この役割を持つ管理者は **、Microsoft** マネージド デスクトップ管理ポータルのすべての機能に対する読み取り専用アクセス許可を持っています。         |
|Intune サービス管理者     |  この役割を持つ管理者は **、Microsoft** マネージド デスクトップ管理ポータルのセキュリティに関連しない機能に対する読み取りおよび書き込みアクセス許可を持っています。       |
|サービス サポート管理者     | この役割を持つ管理者は、Microsoft マネージド デスクトップ管理ポータルでサポート要求を管理するためのセキュリティおよび書き込みアクセス許可に関連しない機能に対する読み取り専用アクセス許可を持っています。         |
|セキュリティ管理者 | この役割を持つ管理者は、管理ポータルの Microsoft マネージドデスクトップのセキュリティ関連機能のすべての機能に対する読み取り専用アクセス許可と書き込みアクセス許可を持っています。 |
|セキュリティ閲覧者 |この役割を持つ管理者は **、Microsoft** マネージド デスクトップ管理ポータルのすべての機能に対する読み取り専用アクセス許可を持っています。|

Azure Active Directory ロールの割り当てに関するヘルプが必要な場合は、「Azure Active Directory での管理者 [ロールのアクセス許可」を参照してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

> [!IMPORTANT]
> 組織を Microsoft マネージド デスクトップに登録するために必要なアクセス許可を持つのは、グローバル管理者の役割のみです。 Azure Active Directory ロールは、さまざまな Microsoft サービスでユーザー アカウントの権限を付与します。 Microsoft マネージド デスクトップへの登録が完了した後は、他のタスクを実行するために必要な最小の特権を持つロールを常に使用する必要があります。

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップによって提供される組み込みの役割


|組み込みの役割  |Microsoft マネージド デスクトップのアクセス許可  |
|---------|---------|
|Microsoft マネージド デスクトップ サービス管理者  | ユーザーに割り当てられると、このロールは、Microsoft Managed Desktop 管理ポータルのセキュリティに関連しない機能に対する読み取りおよび書き込みアクセス許可を管理者に付与します。  |
|Microsoft マネージド デスクトップ サービス リーダー | ユーザーに割り当てられると、このロールは、Microsoft Managed Desktop 管理ポータルのセキュリティに関連しない機能に対する読み取り専用アクセス許可を管理者に付与します。 |
|Microsoft マネージド デスクトップ セキュリティ マネージャー |ユーザーに割り当てられると、このロールは、Microsoft Managed Desktop 管理ポータルのセキュリティ関連機能に対する読み取りおよび書き込みアクセス許可のみを管理者に付与します。   |

> [!NOTE]
> セキュリティ機能には、セキュリティ関連の通信、セキュリティ連絡先の管理、セキュリティ関連のサポート要求の管理、およびセキュリティ関連レポートへのアクセスが含まれます。 

### <a name="assigning-built-in-roles-to-administrators"></a>組み込みの役割を管理者に割り当てる

組み込みの役割を管理するには、"Modern Workplace Roles - _Role Name"_ という名前のカスタム ロールごとにセキュリティ グループがあります (例: "Modern Workplace Roles – Security Manager")。 これらのセキュリティ グループの 1 つにユーザーを割り当てるには、次の手順を実行します。
1.  Microsoft Endpoint Manager ポータルに移動します。
2.  左側 **の [グループ** ] を選択します。
3.  モダン Workplace **Roles を検索** し、割り当てる役割に関連付けられているグループを選択します。 
4.  左側 **の [メンバー** ] を選択し、コマンド バーで **[ +** メンバーの追加] を選択します。
5.  追加するユーザーのメールを入力します。 ゲストである場合は、グループを割り当てる前に招待する必要があります。
6.  下部 **にある [選択** ] を選択します。

> [!NOTE]
> 役割割り当てのセキュリティ グループの入れ子は現在サポートされていません。 
