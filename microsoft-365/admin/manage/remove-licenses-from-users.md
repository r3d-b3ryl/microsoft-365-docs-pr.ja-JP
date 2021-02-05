---
title: ユーザーからライセンスの割り当てを解除する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
description: ユーザー アカウントからライセンスの割り当てを解除する方法について学習します。
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114479"
---
# <a name="unassign-licenses-from-users"></a>ユーザーからライセンスの割り当てを解除する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

::: moniker range="o365-worldwide"

ライセンスは、[アクティブなユーザー] ページまたは[ライセンス] ページでユーザーから割り当 **てを解除** できます。 使用する方法は、特定のユーザーからの製品ライセンスの割り当てを解除するか、特定の製品のライセンスの割り当てを解除するかによって異なります。

::: moniker-end

## <a name="before-you-begin"></a>開始する前に

- ライセンスの割り当てを解除するには、グローバル、ライセンス、ユーザー管理者である必要があります。 詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。
- [Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell)ことができます。
- ライセンスが割 [り当てられた](../add-users/delete-a-user.md) ユーザー アカウントを削除して、ライセンスを他のユーザーが利用できるようすることもできます。 ユーザー アカウントを削除すると、そのユーザーのライセンスがすぐに他のユーザーに割り当て可能になります。

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>[ライセンス] ページを使用してライセンスの割り当てを解除する

[ライセンス] ページ **を使用** してライセンスの割り当てを解除すると、最大 20 人のユーザーの特定の製品のライセンスの割り当てを解除できます。

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。
2. ライセンスの割り当てを解除する製品を選択します。
3. ライセンスの割り当てを解除するユーザーを選択します。
4. [ライセンス **の割り当て解除] を選択します**。
5. [ライセンス **の割り当て解除] ボックスで** 、[割り当て **解除] を選択します**。

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>[アクティブなユーザー] ページを使用してライセンスの割り当てを解除する

[アクティブなユーザー] **ページを使用** してライセンスの割り当てを解除すると、ユーザーから製品ライセンスの割り当てを解除します。

### <a name="unassign-licenses-from-one-user"></a>1 人のユーザーからライセンスの割り当てを解除する
  
1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. ライセンスの割り当てを解除するユーザーの行を選択します。
3. 右側のウィンドウで、[**ライセンスとアプリ**] を選択します。
4. [ライセンス **] セクションを** 展開し、割り当てを解除するライセンスのボックスをオフにして、[変更の保存] **を選択します**。

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>1 人のユーザーからライセンスの割り当てを解除する

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. ライセンスの割り当てを解除するユーザーを選択します。
3. 右側の [製品ライセンス] 行 **で** 、[編集] を選択 **します**。
4. [製品 **ライセンス] ウィンドウ** で、ユーザーの割り当てを解除するライセンスのトグルを [オフ] の位置に切り替えます。 たとえば、Office 365 Enterprise E3 ライセンスをオフにした場合、そのユーザーのライセンスと、そのライセンスのすべてのサービスが割り当て解除されます。
5. [**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>1 人のユーザーからライセンスの割り当てを解除する

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. ライセンスの割り当てを解除するユーザーを選択します。
3. 右側の [製品ライセンス] 行 **で** 、[編集] を選択 **します**。
4. [製品 **ライセンス] ウィンドウ** で、ユーザーの割り当てを解除するライセンスのトグルを [オフ] の位置に切り替えます。 たとえば、Office 365 Enterprise E3 ライセンスをオフにした場合、そのユーザーのライセンスと、そのライセンスのすべてのサービスが割り当て解除されます。
5. [**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>複数のユーザーからのライセンスの割り当てを解除する

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. ライセンスの割り当てを解除するユーザーの名前の横にある円を選択します。
3. 上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。
4. [**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。
5. [既存の製品の置換 **]** ウィンドウの下部で、[選択したユーザーからすべての製品ライセンスを削除する] チェック ボックスをオンにし、[閉じる] を **選択** \> **します**。

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>複数のユーザーからのライセンスの割り当てを解除する

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. すべてのライセンスの割り当てを解除するユーザーの名前の横にあるボックスを選択します。
3. [**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
5. [既存の製品の置換 **]** ウィンドウの下部で、[選択したユーザーからすべての製品ライセンスを削除する] チェックボックスをオンにして、[閉じる置換] を \> **選択** \> **します**。

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>複数のユーザーからのライセンスの割り当てを解除する
  
1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。
2. すべてのライセンスの割り当てを解除するユーザーの名前の横にあるボックスを選択します。
3. [**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
5. [既存の製品の置換 **]** ウィンドウの下部で、[選択したユーザーからすべての製品ライセンスを削除する] チェックボックスをオンにして、[閉じる置換] を \> **選択** \> **します**。

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>ライセンスを削除すると、ユーザーのデータは何が起こりますか?

- ユーザーからライセンスが削除されると、そのアカウントに関連付けられているデータは 30 日間保持されます。 30 日間の猶予期間の後、データは削除され、回復できません。
- ユーザーが Microsoft 365 管理センターから削除されたか、Active Directory 同期によって削除されない限り、OneDrive for Business に保存されたファイルは削除されません。 詳細については [、「OneDrive の保持と削除」を参照してください](https://docs.microsoft.com/onedrive/retention-and-deletion)。
- ライセンスが削除されると、ユーザーのメールボックスは、コンテンツ検索や Advanced eDiscovery などの電子情報開示ツールを使用して検索できなくなりました。 詳細については [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)のコンテンツ検索の「切断されたメールボックスまたはライセンス解除されたメールボックスの検索」を参照してください。
- Office 365 Enterprise E3 のような Enterprise サブスクリプションがある場合、Exchange Online では、非アクティブなメールボックスを使用して、削除されたユーザー アカウントのメールボックス データを [保持できます](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)。 詳細については、「Exchange Online で非アクティブ [なメールボックスを作成および管理する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)。
- ライセンスが削除された後にユーザーの Microsoft 365 データへのアクセスをブロックする方法、および後でデータにアクセスする方法については、「元従業員を削除する」を参照 [してください](../add-users/remove-former-employee.md)。
- ユーザーのライセンスを削除し、引き続き Office アプリがインストールされている場合、ユーザーが Office アプリを使用すると、ライセンスのない製品とライセンス認証のエラーが [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) で表示されます。

## <a name="next-steps"></a>次の手順

未使用のライセンスを他のユーザー[](../../managed-desktop/get-started/assign-licenses.md)に再割り当てしない場合は、[](../../commerce/licenses/buy-licenses.md)サブスクリプションからライセンスを削除して、必要以上のライセンスの支払いを行わないか検討してください。

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md) (記事)\
[ユーザーにライセンスを割り当てる](assign-licenses-to-users.md)(記事)\
[一ビジネス向け Microsoft 365 のサブスクリプションとライセンス](../../commerce/licenses/subscriptions-and-licenses.md) について (記事)