---
title: ユーザーからライセンスの割り当てを解除する
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- commerce_licensing
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: 製品ライセンスの割り当てを解除する方法は、特定のユーザーから割り当て解除するのか、それとも特定の製品から割り当てを解除するのかによって異なります。
ms.date: 07/12/2022
ms.openlocfilehash: b6459030c376bb891ea32b9cb096d26449dfa0d1
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66748387"
---
# <a name="unassign-microsoft-365-licenses-from-users"></a>一般法人向け Microsoft 365 のユーザーからライセンスの割り当てを解除する

**[アクティブなユーザー]** ページ、または **[ライセンス]** ページ上で、ユーザーからライセンスの割り当てを解除できます。 使用する方法は、特定のユーザーから製品ライセンスの割り当てを解除するのか、または特定の製品からユーザー ライセンスの割り当て解除するのかによって異なります。

> [!NOTE]
>
> - 管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。 [セルフサービス購入サブスクリプションを引き継ぐと](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。
>
> - 一部のサブスクリプションでは、サブスクリプションを購入または更新した後、限られた時間内にのみキャンセルできます。 キャンセル期間が過ぎた場合は、定期的な請求をオフにして、期間の終了時にサブスクリプションをキャンセルします。

## <a name="before-you-begin"></a>開始する前に

- ライセンスの割り当てを解除するには、グローバル、ライセンス、またはユーザー管理者である必要があります。詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。
- [Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)ことができます。
- 他のユーザーがライセンスを使用できるようにするために、ライセンスが割り当てられている[ユーザー アカウントを削除](../add-users/delete-a-user.md)することもできます。ユーザー アカウントを削除すると、そのライセンスはすぐに他のユーザーに割り当てることができます。

## <a name="use-the-licenses-page-to-unassign-licenses"></a>ライセンス ページを使用して、ライセンスの割り当てを解除する

**[ライセンス]** ページでは、一度に最大 20 人のユーザーに対して、ライセンスを割り当てることや、ライセンスの割り当てを解除することができます。 このページには、所有している製品、各製品の使用可能ライセンスの数、および使用可能ライセンスの合計数のうちの割り当て済みライセンスの数が表示されます。

**[ライセンス]** ページには、同じ製品名のすべてのサブスクリプションのライセンスの合計が表示されます。 たとえば、 Microsoft 365 Business Premium の、5 つのライセンスがあるサブスクリプションと、同一製品の、8 つのライセンスがある別のサブスクリプションを所有しているとします。 **[ライセンス]** ページには、すべてのサブスクリプションを合わせて、Microsoft 365 Business Premium のライセンスが 13 個あることが示されます。 これは、**[お使いの製品]** ページに表示される内容とは異なります。そのページでは、同一製品のサブスクリプションを複数所有している場合でもサブスクリプションごとに行が表示されます。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

2. 製品を選択します。

3. ライセンスの割り当てを解除するユーザーのチェック ボックスをオンにします。

4. [**ライセンスの割り当て解除**] を選択します。

5. [**ライセンスの割り当て解除**] ボックスで、[**割り当て解除**] を選択します。

## <a name="use-the-active-users-page-to-unassign-licenses"></a>アクティブなユーザー ページを使用して、ライセンスの割り当てを解除する

[**アクティブなユーザー**] ページを使用してライセンスの割り当てを解除する場合、ユーザーから製品ライセンスの割り当てを解除します。

### <a name="unassign-licenses-from-one-user"></a>1 ユーザーからライセンスの割り当てを解除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

2. ライセンスの割り当てを解除するユーザーの行を選択します。

3. 右側のウィンドウで、[**ライセンスとアプリ**] を選択します。

4. **[ライセンス]** セクションを展開し、割り当ての解除を行うライセンスのボックスを選択を解除して、**[変更の保存]** を選択します。

### <a name="unassign-licenses-from-multiple-users"></a>複数のユーザーからライセンスの割り当てを解除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

2. ライセンスの割り当てを解除するユーザー名の横にある丸ボタンを選択します。

3. 上部にある [**製品ライセンスの管理**] を選択します。

4. **[製品ライセンスの管理]** ウィンドウで、**[すべての割り当てを解除]** > **[変更を保存]** を選択します。

5. ウィンドウの下部で、**[完了]** を選択します。  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>ライセンスを削除すると、ユーザーのデータはどうなりますか?

- ユーザーからライセンスを削除すると、そのアカウントに関連付けられているデータは 30 日間保持されます。 30 日間の猶予期間後、データは削除され、復元できなくなります。 ただし、アイテム保持ポリシーにリンクされ、保持ラベルに一致するコンテンツは検出のために保持されます。
- OneDrive for Business に保存されたファイルは、ユーザーが Microsoft 365 管理センターから削除されるか、Active Directory 同期によって削除されない限り、削除されません。詳細については、「[OneDrive の保持と削除](/onedrive/retention-and-deletion)」を参照してください。
- ライセンスが削除されると、ユーザーのメールボックスは、コンテンツ検索や電子情報開示 (Premium) などの電子情報開示ツールを使用して検索できなくなります。 詳細については、[Microsoft 365 のコンテンツ検索](../../compliance/content-search.md)の「切断された、またはライセンスを解除されたメールボックスを検索する」を参照してください。
- Office 365 Enterprise E3 などの Enterprise サブスクリプションがある場合、Exchange Online では、[非アクティブなメールボックス](../../compliance/inactive-mailboxes-in-office-365.md)を使用して、削除されたユーザー アカウントのメールボックス データを保存できます。詳細については、「[Exchange Online の非アクティブなメールボックスを作成および管理する](../../compliance/create-and-manage-inactive-mailboxes.md)」をご覧ください。
- ライセンスが削除された後にユーザーの Microsoft 365 データへのアクセスをブロックする方法、および後でデータにアクセスする方法については、「[元従業員を削除する](../add-users/remove-former-employee.md)」を参照してください。
- ユーザーのライセンスを削除しても Office アプリがインストールされている場合、Office アプリを使用するときに、[Office でライセンスのない製品とアクティベーション エラー](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)が表示されます。

## <a name="next-steps"></a>次の手順

[未使用のライセンスを他のユーザーに再割り当て](assign-licenses-to-users.md)しない場合は、[サブスクリプションからライセンスを削除](../../commerce/licenses/buy-licenses.md)して、必要以上のライセンスを支払わないようにすることを検討してください。

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションからライセンスを削除する](../../commerce/licenses/buy-licenses.md) (記事)\
[ユーザーにライセンスを割り当てる](assign-licenses-to-users.md)(記事)\
[一般法人向け Microsoft 365 のサブスクリプションとライセンスを理解する](../../commerce/licenses/subscriptions-and-licenses.md) (記事)
