---
title: 管理者ロールについて
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: svidican
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 管理者ロールはビジネス機能にマップされ、管理センターで特定のタスクを実行するための権限を付与します。 たとえば、サービス管理者が Microsoft のサポート チケットを開きます。
ms.openlocfilehash: 1f662221a2bcd8bc75c8226b2da726966a096be6
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602095"
---
# <a name="get-started-with-the-roles-page"></a>[ロール] ページで作業を開始する

[役割] ページでは、管理センターでタスクを実行するためのアクセス許可をユーザーに付与できます。 これにより、組織は適切な人物にタスクを分散し、データを安全に保つことができます。

![管理者の役割を示す図](../../media/roles-main-page.png)

> [!TIP]
> 役割の詳細な説明をお探しですか ? 「 [Azure Active Directory」](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)と「管理者の役割[について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。

## <a name="about-the-admin-roles-page"></a>[管理者ロール] ページについて

管理者リストをエクスポートして、役割で検索してフィルター処理することもできます。

![管理者の役割をフィルターまたはインポートする](../../media/admin-role-page-options.png)

|||
|:-----|:-----|
|  <br/> |[**エクスポート管理] リスト**を使用して、組織内のすべての管理者ユーザーの完全な一覧を取得します。 リストは、Excel .csv ファイルに保存されます。   <br/> |
|  <br/> |**検索**を使用して管理者の役割を検索し、その役割に割り当てられているユーザーを表示します。   <br/> |
|  <br/> |表示される管理者の役割の表示を変更するには、**フィルター**を使用します。   <br/> |

## <a name="get-the-most-out-of-the-roles"></a>役割を最大限に活用する

さまざまな管理者の役割と、組織内で役割が実行できるタスクについては、以下の内容を参照してください。

> [!NOTE]
これは、これらの役割が持つすべてのアクセス許可を網羅したリストではありません。 各ロールの詳細については、「**詳細**情報」のリンクをクリックしてください。

### <a name="exchange-admin"></a>Exchange 管理者

ユーザーの電子メールメールボックス、Microsoft 365 グループ、Exchange Online を表示および管理する必要があるユーザーに、Exchange 管理者の役割を割り当てます。 また、Microsoft サポートへのサービス要求を開いて管理することもできます。 [詳細情報](https://docs.microsoft.com/office365/admin/add-users/about-exchange-online-admin-role)

### <a name="global-admin"></a>グローバル管理者

Microsoft online services 間で、ほとんどの管理機能およびデータへのグローバルアクセスを必要とするユーザーにグローバル管理者の役割を割り当てます。 グローバルなアクセスを多くのユーザーに許可することはセキュリティ上のリスクであるため、2 〜 4 人のグローバル管理者を配置することをお勧めします。 グローバル管理者のみが、すべてのユーザーのパスワードをリセットし、ドメインを追加および管理できます。 また、Microsoft サポートへのサービス要求を開いて管理することもできます。 Microsoft online services にサインアップしたユーザーは、自動的にグローバル管理者になります。[詳細情報](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

### <a name="global-reader"></a>グローバルリーダー

グローバル管理者が表示できるすべての管理センターで管理機能と設定を表示する必要があるユーザーに、グローバル読み取り管理者の役割を割り当てます。 グローバル閲覧者の管理者の役割では、設定を編集することはできません。 [詳細情報](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

### <a name="helpdesk-admin"></a>ヘルプデスク管理者

パスワードをリセットするユーザーにヘルプデスク管理者の役割を割り当て、ユーザーがセキュリティ上の問題についてサインアウトすることを強制します。 また、Microsoft サポートへのサービス要求を開いて管理することもできます。 ヘルプデスク管理者は、管理者以外のユーザーとこれらの役割を割り当てられたユーザー (ディレクトリリーダー、ゲスト招待元、ヘルプデスク管理者、メッセージセンターリーダ、およびレポート閲覧者のみ) を支援します。 [詳細情報](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

### <a name="service-admin"></a>サービス管理者

Azure、Microsoft 365、および Office 365 サービスのサービス要求を作成する必要があるユーザーに、サービス管理者の役割を割り当てます。 [詳細情報](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

### <a name="sharepoint-admin"></a>SharePoint 管理者

Microsoft 365 サブスクリプションを購入すると、チームサイトが自動的に作成され、グローバル管理者がサイトコレクションの管理者として設定されます。 Sharepoint 管理センターにアクセスするユーザーに SharePoint 管理者の役割を割り当てます。 SharePoint 管理者の役割を持つユーザーは、サイトコレクションを作成および管理したり、サイトコレクション管理者を指定したり、ユーザープロファイルを管理したりできます。 SharePoint 管理者の役割を持つユーザーは、microsoft 365 グループを管理し、Microsoft サポートを通じてサービス要求を開くこともできます。 [詳細情報](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

### <a name="teams-service-admin"></a>Teams のサービス管理者

Teams & Skype admin center にアクセスして管理するユーザーに Teams の管理者の役割を割り当てます。 Teams 管理者の役割を持つユーザーは、microsoft 365 グループを管理し、Microsoft サポートを通じてサービス要求を開くこともできます。 [詳細情報](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)

### <a name="user-admin"></a>ユーザー管理者

ユーザーのパスワードのリセットを管理し、ユーザーとグループを管理するユーザーに、ユーザー管理者の役割を割り当てます。 また、Microsoft サポートへのサービス要求を開いて管理することもできます。 [詳細情報](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles#roles-available-in-the-microsoft-365-admin-center)

::: moniker range="o365-worldwide"

## <a name="compare-roles"></a>ロールの比較

一度に最大3つの役割のアクセス許可を比較できるので、最も制限のない役割を割り当てることができます。

管理センターで、次のようにします。

- [最大3つのロール] を選択し、[**ロールの比較**] を選択して、各ロールが持つアクセス許可を表示します。

![管理者の役割の比較を示す図](../../media/compare-roles-list.png)

::: moniker-end

## <a name="related-topics"></a>関連トピック

[Microsoft 365 管理者ロールについて](about-admin-roles.md)

[管理者の役割を割り当てる](assign-admin-roles.md)