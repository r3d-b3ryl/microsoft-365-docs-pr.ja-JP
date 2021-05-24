---
title: ユーザーからライセンスの割り当てを解除する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: 製品ライセンスの割り当てを解除する方法は、特定のユーザーからのライセンスの割り当てを解除するか、特定の製品からライセンスを割り当て解除するかによって異なります。
ms.date: 07/01/2020
ms.openlocfilehash: f7624432590a5731b57c45c25e7e7dc458a5b8f5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623591"
---
# <a name="unassign-licenses-from-users"></a>ユーザーからライセンスの割り当てを解除する

ユーザーからのライセンスの割り当てを解除するには、[アクティブなユーザー] ページまたは [ライセンス] ページ **を使用** します。 使用する方法は、特定のユーザーからの製品ライセンスの割り当てを解除するか、特定の製品からのユーザー ライセンスの割り当てを解除するかによって異なります。

> [!NOTE]
> 管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。 [セルフサービス購入サブスクリプションを引き継ぐと](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。

## <a name="before-you-begin"></a>始める前に

- ライセンスの割り当てを解除するには、グローバル、ライセンス、ユーザー管理者である必要があります。 詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。
- [Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)ことができます。
- ライセンスが [割り当てられたユーザー](../add-users/delete-a-user.md) アカウントを削除して、ライセンスを他のユーザーが利用できるようすることもできます。 ユーザー アカウントを削除すると、そのユーザーのライセンスをすぐに他のユーザーに割り当てできます。

## <a name="use-the-licenses-page-to-unassign-licenses"></a>[ライセンス] ページを使用してライセンスの割り当てを解除する

[ライセンス] ページ **を使用して** ライセンスの割り当てを解除すると、最大 20 人のユーザーの特定の製品のライセンスの割り当てを解除します。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-germany"

 1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

2. ライセンスの割り当てを解除する製品を選択します。
3. ライセンスの割り当てを解除するユーザーを選択します。
4. [ライセンス **の割り当て解除] を選択します**。
5. [ライセンスの **割り当て解除] ボックス** で、[割り当 **て解除] を選択します**。

## <a name="use-the-active-users-page-to-unassign-licenses"></a>[アクティブ ユーザー] ページを使用してライセンスの割り当てを解除する

[アクティブ ユーザー] **ページを使用して** ライセンスの割り当てを解除すると、ユーザーからの製品ライセンスの割り当てを解除します。

### <a name="unassign-licenses-from-one-user"></a>1 人のユーザーからのライセンスの割り当てを解除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

 1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

::: moniker-end

2. ライセンスの割り当てを解除するユーザーの行を選択します。
3. 右側のウィンドウで、[**ライセンスとアプリ**] を選択します。
4. [ライセンス **] セクションを展開** し、割り当てを解除するライセンスのボックスをオフにして、[変更の保存] **を選択します**。

### <a name="unassign-licenses-from-multiple-users"></a>複数のユーザーからのライセンスの割り当てを解除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

 1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

::: moniker-end

2. ライセンスの割り当てを解除するユーザーの名前の横にある円を選択します。
3. 上部で 3 つのドット (その他のアクション) を選択し、[**製品ライセンスの管理**] を選択します。
4. [**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。
5. [既存の製品の **置き** 換え] ウィンドウの下部で、[選択したユーザーからすべての製品ライセンスを削除する]チェック ボックスをオンにし、[閉じる] を選択 \> **します**。

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>ライセンスを削除すると、ユーザーのデータは何が起こりますか?

- ライセンスがユーザーから削除されると、Exchange関連付けられているオンライン データが 30 日間保持されます。 30 日間の猶予期間の後、データは削除され、回復できません。
- ユーザーが OneDrive for Business Microsoft 365管理センターから削除されたか、Active Directory 同期によって削除されない限り、OneDrive for Businessに保存されたファイルは削除されません。 詳細については、「保持と[削除OneDriveを参照してください](/onedrive/retention-and-deletion)。
- ライセンスが削除されると、ユーザーのメールボックスは、コンテンツ検索や電子情報開示ツールなどの電子情報開示ツールを使用してAdvanced eDiscovery。 詳細については、「コンテンツ検索」の「切断されたメールボックスまたはライセンス解除されたメールボックスを検索する」[を参照Microsoft 365。](../../compliance/content-search.md)
- Office 365 Enterprise E3 のような Enterprise サブスクリプションがある場合、Exchange Online を使用すると、非アクティブなメールボックスを使用して、削除されたユーザー アカウントのメールボックス データを[保持できます](../../compliance/inactive-mailboxes-in-office-365.md)。 詳細については、「アクティブでないメールボックスを作成して管理する」を参照[Exchange Online。](../../compliance/create-and-manage-inactive-mailboxes.md)
- ライセンスが削除された後でユーザーの Microsoft 365 データへのアクセスをブロックする方法、および後でデータにアクセスする方法については、「元従業員を削除する」を[参照してください](../add-users/remove-former-employee.md)。
- ユーザーのライセンスを削除し、Office アプリがまだインストールされている場合は、Office でライセンス[](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)認証されていない製品とライセンス認証エラーが表示され、Office アプリを使用します。

## <a name="next-steps"></a>次の手順

未使用のライセンスを他のユーザー[](../../managed-desktop/get-started/assign-licenses.md)に再割り当てしない場合は、[](../../commerce/licenses/buy-licenses.md)必要以上に多くのライセンスを支払わない状態でサブスクリプションからライセンスを削除してください。

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションからライセンスを削除](../../commerce/licenses/buy-licenses.md) する (記事)\
[ユーザーにライセンスを割り当てる](assign-licenses-to-users.md)(記事)\
[ビジネス向けサブスクリプションとライセンスMicrosoft 365理解](../../commerce/licenses/subscriptions-and-licenses.md)する (記事)
