---
title: ユーザーからライセンスの割り当てを解除する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: ユーザーアカウントからライセンスの割り当てを解除する方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015937"
---
# <a name="unassign-licenses-from-users"></a>ユーザーからライセンスの割り当てを解除する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

::: moniker range="o365-worldwide"

[**アクティブなユーザー** ] ページまたは [**ライセンス**] ページで、ユーザーからライセンスを割り当てを解除できます。 使用する方法は、特定のユーザーからの製品ライセンスの割り当てを解除するか、特定の製品からユーザーライセンスの割り当てを解除するかによって異なります。

::: moniker-end

## <a name="before-you-begin"></a>はじめに

- ライセンスの割り当てを解除するには、グローバルなライセンス、ユーザー管理者である必要があります。 詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。
- [Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)ことができます。
- ライセンスを割り当てられた[ユーザーアカウントを削除](../add-users/delete-a-user.md)して、他のユーザーがライセンスを使用できるようにすることもできます。 ユーザーアカウントを削除すると、そのライセンスはすぐに他のユーザーに割り当てることができます。

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>ライセンスの割り当てを解除するには、[ライセンス] ページを使用します。

[**ライセンス**] ページを使用してライセンスを割り当てを解除する場合は、最大20人のユーザーの特定の製品のライセンスの割り当てを解除します。

1. 管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。
2. ライセンスの割り当てを解除する製品を選択します。
3. ライセンスの割り当てを解除するユーザーを選択します。
4. [**ライセンスの割り当て解除**] を選択します。
5. [**ライセンスの割り当て解除**] ボックスで、[**割り当て**の解除] を選択します。

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>ライセンスの割り当てを解除するには、[アクティブなユーザー] ページを使用します。

[**アクティブなユーザー** ] ページを使用してライセンスを割り当てを解除する場合は、ユーザーから製品ライセンスの割り当てを解除します。

### <a name="unassign-licenses-from-one-user"></a>1人のユーザーのライセンスの割り当てを解除する
  
1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ライセンスの割り当てを解除するユーザーの行を選択します。
3. 右側のウィンドウで、[**ライセンスとアプリ**] を選択します。
4. [**ライセンス**] セクションを展開し、割り当てを解除するライセンスのボックスをオフにして、[**変更の保存**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>1人のユーザーのライセンスの割り当てを解除する

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ライセンスの割り当てを解除するユーザーを選択します。
3. 右側の [**製品ライセンス**] 行で、[**編集**] を選択します。
4. [**製品ライセンス**] ウィンドウで、ユーザーの割り当てを解除するライセンスを [**オフ**] の位置に切り替えます。 たとえば、Office 365 Enterprise E3 ライセンスをオフにした場合、そのライセンスとそのユーザーのライセンスの下にあるすべてのサービスは割り当てられません。
5. [**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>1人のユーザーのライセンスの割り当てを解除する

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ライセンスの割り当てを解除するユーザーを選択します。
3. 右側の [**製品ライセンス**] 行で、[**編集**] を選択します。
4. [**製品ライセンス**] ウィンドウで、ユーザーの割り当てを解除するライセンスを [**オフ**] の位置に切り替えます。 たとえば、Office 365 Enterprise E3 ライセンスをオフにした場合、そのライセンスとそのユーザーのライセンスの下にあるすべてのサービスは割り当てられません。
5. [**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>複数のユーザーからのライセンスの割り当てを解除する

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. ライセンスの割り当てを解除するユーザーの名前の横にある円を選択します。
3. 上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。
4. [**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。
5. [既存の製品を**置き換える**] ウィンドウの下部で、[選択した**ユーザーからすべての製品ライセンスを削除**する] チェックボックスをオンにし、[閉じるの**置換**] を選択し \> **Close**ます。

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>複数のユーザーからのライセンスの割り当てを解除する

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. すべてのライセンスの割り当てを解除するユーザーの名前の横にあるチェックボックスをオンにします。
3. [**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
5. [**既存製品の置換**] ウィンドウの下部で、[**選択したユーザーからすべての製品ライセンスを削除**する] チェックボックスをオンにし、[**置換**閉じる] を選択し \> **Close** \> **Close**ます。

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>複数のユーザーからのライセンスの割り当てを解除する
  
1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。
2. すべてのライセンスの割り当てを解除するユーザーの名前の横にあるチェックボックスをオンにします。
3. [**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
5. [**既存製品の置換**] ウィンドウの下部で、[**選択したユーザーからすべての製品ライセンスを削除**する] チェックボックスをオンにし、[**置換**閉じる] を選択し \> **Close** \> **Close**ます。

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>ライセンスを削除すると、ユーザーのデータはどうなりますか。

- ライセンスがユーザーから削除されると、そのアカウントに関連付けられているデータは30日間保持されます。 30日の猶予期間が過ぎると、データは削除され、回復することはできません。
- OneDrive for Business に保存されたファイルは、ユーザーが Microsoft 365 管理センターから削除されているか、Active Directory 同期によって削除されている場合を除き、削除されません。 詳細については、「 [OneDrive の保持と削除](https://docs.microsoft.com/onedrive/retention-and-deletion)」を参照してください。
- ライセンスが削除されると、そのユーザーのメールボックスは、コンテンツ検索や高度な電子情報開示などの電子情報開示ツールを使用して検索できなくなります。 詳細については、「 [Microsoft 365 のコンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)」の「切断されたメールボックスまたはライセンスの解除済みメールボックスの検索」を参照してください。
- Office 365 Enterprise E3 などのエンタープライズサブスクリプションを使用している場合、Exchange Online では、[非アクティブなメールボックス](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)を使用して、削除されたユーザーアカウントのメールボックスデータを保持することができます。 詳細については、「 [Exchange Online の非アクティブなメールボックスの作成と管理](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)」を参照してください。
- ライセンスが削除された後に、ユーザーの Microsoft 365 データへのアクセスをブロックする方法、および後でデータにアクセスする方法については、「元[の従業員を削除](../add-users/remove-former-employee.md)する」を参照してください。
- ユーザーのライセンスを削除しても、まだ Office アプリがインストールされている場合は、office アプリを使用したときに Office のライセンスのない[製品とライセンス認証のエラー](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)が表示されます。

## <a name="next-steps"></a>次の手順

使用されていない[ライセンスを他のユーザーに再割り当て](../../managed-desktop/get-started/assign-licenses.md)する予定がない場合は、[サブスクリプションからライセンスを削除](../../commerce/licenses/buy-licenses.md)して、必要なライセンス数を超えるライセンスを支払っていないことを検討してください。

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md)(記事) \
[ユーザーへのライセンスの割り当て](assign-licenses-to-users.md)(記事) \
[Microsoft 365 for business のサブスクリプションとライセンスについて理解する](../../commerce/licenses/subscriptions-and-licenses.md)(記事)