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
ms.openlocfilehash: e438e9a84b86bd4c3360022c0558480f317144e7
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602915"
---
# <a name="access-the-admin-portal"></a>管理ポータルへのアクセス

サービスへのゲートウェイ[Microsoft マネージド デスクトップが](https://endpoint.microsoft.com/)Microsoft エンドポイント マネージャー。 デバイス管理のためのこのポータルの機能に慣れていない場合は、次のドキュメントMicrosoft エンドポイント マネージャー[してください](/mem/)。

> [!NOTE]
> この[Microsoft エンドポイント マネージャー、](https://endpoint.microsoft.com/)次のブラウザーがサポートされています。
> - Microsoft Edge (最新バージョン)
> - Safari (最新バージョン、Mac のみ)
> - Chrome (最新バージョン)
> - Firefox (最新バージョン)

管理者アカウントは、管理者アカウントの管理機能にアクセスするために特定Microsoft マネージド デスクトップ必要Microsoft エンドポイント マネージャー。 役割ベースのアクセス制御を使用して、組織内のこれらの機能への管理者アクセスを管理できます。 複数Azure Active Directory (Azure AD) 管理者ロールと組み込みの Microsoft マネージド デスクトップ ロールを使用して、Microsoft マネージド デスクトップ 管理ポータル内のさまざまな機能を詳細に制御できます。 ロールの詳細については、「Azure Azure Active Directory組み込み[AD」を参照してください](/azure/active-directory/roles/permissions-reference)。 さまざまな Microsoft 製品ADサービスに適用される Azure AD 管理者ロールとは異なり、組み込みの役割は Microsoft マネージド デスクトップ 固有の役割であり、このサービスの管理者機能へのアクセスのみを保証します。 管理者は、組み込みの役割をユーザーに個別に割り当てるか、Azure AD 管理者ロールと組み合わせて割り当て、既存の管理者アカウントにMicrosoft マネージド デスクトップアクセス許可を追加できます。

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directoryアクセス権を持つMicrosoft マネージド デスクトップロール

|Azure AD ロール  |Microsoft マネージド デスクトップアクセス許可  |
|---------|---------|
|グローバル管理者     | この役割を持つ **管理者には、** 管理者ポータル内のすべての機能に対する読み取りおよびMicrosoft マネージド デスクトップがあります。         |
|グローバル閲覧者     | この役割を持つ管理者には **、管理者** ポータル内のすべての機能に対する読み取りMicrosoft マネージド デスクトップがあります。         |
|Intune サービス管理者     |  この役割を持つ管理者には **、管理者** ポータルのセキュリティに関連しない機能に対する読み取りおよび書き込Microsoft マネージド デスクトップがあります。       |
|サービス サポート管理者     | この役割を持つ管理者には、セキュリティに関連しない機能に対する読み取り専用アクセス許可と、管理者ポータルでサポート要求を管理するための書き込みMicrosoft マネージド デスクトップがあります。         |
|セキュリティ管理者 | この役割を持つ管理者は、管理ポータル内のすべての機能に対する読み取り専用のアクセス許可と、Microsoft マネージド デスクトップのセキュリティ関連機能に対する書き込みアクセス許可を持つ必要があります。 |
|セキュリティ閲覧者 |この役割を持つ管理者には **、管理者** ポータル内のすべての機能に対する読み取りMicrosoft マネージド デスクトップがあります。|

役割の割り当てに関するAzure Active Directory必要な場合は[、「Azure AD組み込みロール」を参照してください](/azure/active-directory/roles/permissions-reference)。

> [!IMPORTANT]
> グローバル管理者の役割にのみ、組織を登録するために必要なアクセス許可Microsoft マネージド デスクトップ。 役割によって、Azure Active Directoryさまざまなユーザー アカウントの権限が付与Microsoft サービス。 ユーザーの登録が完了Microsoft マネージド デスクトップ、他のタスクを実行するために必要な最小の特権を持つロールを常に使用する必要があります。

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>ユーザーが提供する組み込みMicrosoft マネージド デスクトップ


|組み込みの役割  |Microsoft マネージド デスクトップアクセス許可  |
|---------|---------|
|Microsoft マネージド デスクトップサービス管理者  | ユーザーに割り当てられると、管理者は管理者ポータルのセキュリティに関連しない機能に対する読み取りおよび書き込Microsoft マネージド デスクトップします。  |
|Microsoft マネージド デスクトップサービス リーダー | ユーザーに割り当てると、管理者は管理者ポータルのセキュリティに関連しない機能に対する読み取り専用Microsoft マネージド デスクトップします。 |
|Microsoft マネージド デスクトップセキュリティ マネージャー |ユーザーに割り当てると、管理者は管理者ポータルのセキュリティ関連機能に対する読み取りおよび書き込みMicrosoft マネージド デスクトップします。   |

> [!NOTE]
> セキュリティ機能には、セキュリティ関連の通信、セキュリティ連絡先の管理、セキュリティ関連のサポート要求の管理、およびセキュリティ関連レポートへのアクセスが含まれます。 

### <a name="assigning-built-in-roles-to-user"></a>組み込みの役割をユーザーに割り当てる

組み込みの役割を簡単に管理するには、"モダン ワークプレースの役割 _-_ 役割名" という名前のカスタム ロールごとにセキュリティ グループがあります (たとえば、「モダン ワークプレースの役割 - セキュリティ マネージャー」など)。 ユーザーをこれらのセキュリティ グループに割り当てるには、次の手順を実行します。
1. ポータルに移動Microsoft エンドポイント マネージャーします。
2. 左側 **の [グループ** ] を選択します。
3. [モダン **ワークプレースの役割] を** 検索し、割り当てる役割に関連付けられているグループを選択します。 
4. 左側 **の [メンバー** ] を選択し、コマンド バー **の [+ メンバー** の追加] を選択します。
5. 追加するユーザーのメールを入力します。 ゲストの場合は、グループを割り当てる前に招待する必要があります。
6. 下部 **にある [選択** ] を選択します。

> [!NOTE]
> 役割割り当てのセキュリティ グループの入れ子は現在サポートされていません。 

### <a name="assigning-built-in-roles-to-groups"></a>組み込みの役割をグループに割り当てる

1 つ以上の組み込みロールを既存のグループに割り当てる必要がある場合は、次の手順を実行します。

1. に移動[portal.azure.com。](https://portal.azure.com/)
2. アプリケーションを検索して開Enterprise **します**。
3. [アプリケーションの **種類] フィルターを** _[Microsoft アプリケーション] に変更し_ 、[適用] を **選択します**。
4. モダン ワークプレースカスタマー API _を検索して選択します_。
5. 左側 **のウィンドウから [ユーザー** とグループ] を選択し **、[+ ユーザー/グループの追加] を選択します**。
6. [ユーザーとグループ] から必要な **グループを検索します**。
7. [役割の選択] から該当する役割 **を検索** し、その役割を選択します。
8. **[割り当て]** を選択します。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>データの使用を開始するMicrosoft マネージド デスクトップ

1. 管理ポータルにアクセスする (この記事)。
1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
1. [登録後に設定を調整する](conditional-access.md)。
1. [Intune ポータル サイト](company-portal.md)を展開して割り当てます。
1. [ライセンスを割り当てる](assign-licenses.md)。
1. [アプリを展開する](deploy-apps.md)。
1. [デバイスをセットアップする](set-up-devices.md)。
1. [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)のセットアップ。
1. [ユーザー サポート機能を有効にする](enable-support.md)。
1. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
1. [アプリ制御の使用を開始する](get-started-app-control.md)。