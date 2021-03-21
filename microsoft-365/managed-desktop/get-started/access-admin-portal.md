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
ms.openlocfilehash: 7293c8ced43332f84ced56908ea5203ba867e600
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925906"
---
# <a name="access-the-admin-portal"></a>管理ポータルへのアクセス

Microsoft Managed Desktop サービスへのゲートウェイは [、Microsoft Endpoint Manager です](https://endpoint.microsoft.com/)。 デバイス管理のためのこのポータルの機能に慣れていない場合は [、Microsoft Endpoint Manager のドキュメントを参照してください](/mem/)。

> [!NOTE]
> [Microsoft Endpoint Manager では、](https://endpoint.microsoft.com/)次のブラウザーがサポートされています。
> - Microsoft Edge (最新バージョン)
> - Microsoft Internet Explorer 11
> - Safari (最新バージョン、Mac のみ)
> - Chrome (最新バージョン)
> - Firefox (最新バージョン)

Microsoft Endpoint Manager の Microsoft Managed Desktop 管理機能にアクセスするには、管理アカウントに特定のアクセス許可が必要です。 役割ベースのアクセス制御を使用して、組織内のこれらの機能への管理者アクセスを管理できます。 いくつかの Azure Active Directory (Azure AD) 管理者ロールと組み込みの Microsoft Managed Desktop ロールを使用して、Microsoft 管理デスクトップ管理ポータル内のさまざまな機能に対してより詳細な制御を提供できます。 Azure Active Directory の役割の詳細については、「Azure Active Directory の [管理者ロールのアクセス許可」を参照してください](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 さまざまな Microsoft ADサービスに適用される Azure AD 管理者ロールとは異なり、組み込みの役割は Microsoft Managed Desktop に固有の役割であり、このサービスの管理者機能へのアクセスのみを保証します。 管理者は、組み込みの役割をユーザーに個別に割り当てるか、Azure AD 管理者ロールと組み合わせて割り当て、既存の管理者アカウントに Microsoft Managed Desktop アクセス許可を追加できます。

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Microsoft Managed Desktop アクセスを使用した Azure Active Directory の役割

|Azure ADロール  |Microsoft Managed Desktop のアクセス許可  |
|---------|---------|
|グローバル管理者     | この役割を持つ管理者は **、Microsoft** Managed Desktop Admin ポータルのすべての機能に対する読み取りおよび書き込みアクセス許可を持つ必要があります。         |
|グローバル閲覧者     | この役割を持つ **管理者は** 、Microsoft Managed Desktop Admin ポータルのすべての機能に対する読み取り専用アクセス許可を持つ必要があります。         |
|Intune サービス管理者     |  この役割を持つ管理者は **、Microsoft** Managed Desktop Admin ポータルのセキュリティに関連しない機能に対する読み取りおよび書き込みアクセス許可を持つ必要があります。       |
|サービス サポート管理者     | この役割を持つ管理者は、Microsoft Managed Desktop Admin ポータルでサポート要求を管理するためのセキュリティおよび書き込みアクセス許可に関連しない機能に対する読み取り専用のアクセス許可を持つ。         |
|セキュリティ管理者 | この役割を持つ管理者には、管理ポータルの Microsoft Managed  Desktop のすべての機能に対する読み取り専用アクセス許可と、セキュリティ関連機能の書き込みアクセス許可が付与されます。 |
|セキュリティ閲覧者 |この役割を持つ **管理者は** 、Microsoft Managed Desktop Admin ポータルのすべての機能に対する読み取り専用アクセス許可を持つ必要があります。|

Azure Active Directory ロールの割り当てに関するヘルプが必要な場合は、「Azure Active Directory の管理者 [ロールのアクセス許可」を参照してください](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

> [!IMPORTANT]
> Microsoft Managed Desktop に組織を登録するために必要なアクセス許可を持つのは、グローバル管理者の役割のみです。 Azure Active Directory の役割は、さまざまな Microsoft サービスでユーザー アカウントの特権を与える点に注意してください。 Microsoft Managed Desktop への登録が完了した後は、他のタスクを実行するために必要な最小の特権を持つロールを常に使用する必要があります。

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop によって提供される組み込みの役割


|組み込みの役割  |Microsoft Managed Desktop のアクセス許可  |
|---------|---------|
|Microsoft Managed Desktop Service Administrator  | ユーザーに割り当てられた場合、この役割により、管理者は Microsoft Managed Desktop Admin ポータルのセキュリティに関連しない機能に対する読み取りおよび書き込みアクセス許可を付与します。  |
|Microsoft Managed Desktop Service Reader | ユーザーに割り当てられた場合、この役割は、Microsoft Managed Desktop Admin ポータルのセキュリティに関連しない機能に対する読み取り専用アクセス許可を管理者に付与します。 |
|Microsoft Managed Desktop Security Manager |ユーザーに割り当てられた場合、この役割により、管理者は Microsoft Managed Desktop Admin ポータルのセキュリティ関連機能に対する読み取りおよび書き込み権限のみを付与します。   |

> [!NOTE]
> セキュリティ機能には、セキュリティ関連の通信、セキュリティ連絡先の管理、セキュリティ関連のサポート要求の管理、およびセキュリティ関連レポートへのアクセスが含まれます。 

### <a name="assigning-built-in-roles-to-user"></a>組み込みの役割をユーザーに割り当てる

組み込みの役割を簡単に管理するには、"モダン ワークプレースの役割 _-_ 役割名" という名前のカスタム ロールごとにセキュリティ グループがあります (たとえば、「モダン ワークプレースの役割 - セキュリティ マネージャー」など)。 ユーザーをこれらのセキュリティ グループに割り当てるには、次の手順を実行します。
1.  Microsoft Endpoint Manager ポータルに移動します。
2.  左側 **の [グループ** ] を選択します。
3.  [モダン **ワークプレースの役割] を** 検索し、割り当てる役割に関連付けられているグループを選択します。 
4.  左側 **の [メンバー** ] を選択し、コマンド バー **の [+ メンバー** の追加] を選択します。
5.  追加するユーザーのメールを入力します。 ゲストの場合は、グループを割り当てる前に招待する必要があります。
6.  下部 **にある [選択** ] を選択します。

> [!NOTE]
> 役割割り当てのセキュリティ グループの入れ子は現在サポートされていません。 

### <a name="assigning-built-in-roles-to-groups"></a>組み込みの役割をグループに割り当てる

1 つ以上の組み込みロールを既存のグループに割り当てる必要がある場合は、次の手順を実行します。
1. に移動[portal.azure.com。](https://portal.azure.com/)
2. エンタープライズ アプリケーションを **検索して開きます**。
3. [アプリケーションの **種類] フィルターを** _[Microsoft アプリケーション] に変更し_ 、[適用] を **選択します**。
4. モダン ワークプレースカスタマー API _を検索して選択します_。
5. 左側 **のウィンドウから [ユーザー** とグループ] を選択し **、[+ ユーザー/グループの追加] を選択します**。
6. [ユーザーとグループ] から必要な **グループを検索します**。
7. [役割の選択] から該当する役割 **を検索** し、その役割を選択します。
8. [割り当 **て] を選択します**。
