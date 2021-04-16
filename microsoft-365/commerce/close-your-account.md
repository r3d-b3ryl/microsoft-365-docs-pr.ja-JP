---
title: アカウントの使用を停止する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Microsoft でアカウントを閉じる方法について説明します。
ms.openlocfilehash: 44428654946d31ad249bfd3e7a3609da3e3634a6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860549"
---
# <a name="close-your-account"></a>アカウントの使用を停止する

Microsoft でのアカウントの使用を停止すると、アカウントに関連するすべての情報が削除されます。 この情報には、サブスクリプション、ライセンス、支払方法、ユーザー、ユーザー データが含まれます。

## <a name="before-you-begin"></a>開始する前に

このプロセスを開始する前に、保持する必要があるすべてのデータをバックアップしてください。

この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。 詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="step-1-delete-users"></a>手順 1: ユーザーを削除する

1 人のグローバル管理者を除くすべてのユーザーを削除します。 グローバル管理者は、アカウントを閉じる手順を完了します。 このプロセスの最後にディレクトリを削除する前に、他のすべてのユーザーを削除する必要があります。

ユーザーがオンプレミスから同期されている場合は、まず同期をオフにしてから、Azure portal または Azure PowerShell コマンドレットを使用してクラウド ディレクトリ内のユーザーを削除します。

ユーザーを削除するには、「ユーザー管理管理者 <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">: 1 人または複数のユーザーを削除する」を参照してください</a>。

<a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">Remove-MsolUser PowerShell コマンドレット</a>を使用して、ユーザーを一括で削除することもできます。

組織で Microsoft Azure Active Directory (Azure Active Directory )と同期する Active Directory を使用している場合は、代AD Active Directory からユーザー アカウントを削除します。 手順については <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">、「Azure Active Directory のユーザーを一括削除する」を参照してください</a>。

## <a name="step-2-cancel-all-active-subscriptions"></a>手順 2: すべてのアクティブなサブスクリプションをキャンセルする

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、アクティブなサブスクリプションを探します。 **[その他の操作]** (3 つのドット) を選択してから、**[サブスクリプションのキャンセル]** を選択します。
3. **[サブスクリプションのキャンセル]** ウィンドウで、キャンセルする理由を選択します。 必要に応じて、フィードバックを提供します。
4. **[保存]** を選択します。
5. 手順 1 ~ 4 を繰り返して、アクティブなすべてのサブスクリプションを取り消します。

## <a name="step-3-delete-all-disabled-subscriptions"></a>手順 3: 無効なすべてのサブスクリプションを削除する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、無効なサブスクリプションを選択します。
3. [サブスクリプションの詳細] ページの [ **サブスクリプションと支払** いの設定] セクションで、[サブスクリプションの削除] **を選択します**。
4. [サブスクリプションの **削除] ウィンドウで** 、[サブスクリプションの削除] **を選択します**。
5. [サブスクリプションの **削除] ダイアログ ボックス** で、[はい] を **選択します**。
6. 無効にしたサブスクリプションごとに、すべてのサブスクリプションが削除されるまで手順 3 ~ 5 を繰り返します。

> [!NOTE]
> 無効になっているサブスクリプションを直ちに削除できない場合は、サポート <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">にお問い合わせください</a>

## <a name="step-4-disable-multi-factor-authentication"></a>手順 4: 多要素認証を無効にする

1. グローバル管理者アカウントを使用して管理センターにサインインします。 持っている役割を確認するには、「組織内の [管理者の役割を確認する」を参照してください](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。
2. [ユーザーのアクティブ **なユーザー**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">] ページに移動</a>します。
3. [ **多要素認証] を選択します**。
4. 多要素認証ページで、現在使用しているグローバル管理者アカウントを除くすべてのアカウントを無効にします。

PowerShell を <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">使用して、複数のユーザーの多要素認証を無効にできます</a>。

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>手順 5: Azure Active Directory のディレクトリを削除する

1. グローバル管理者アカウントで <a href="https://aad.portal.azure.com/" target="_blank">Azure AD管理センター</a> にサインインします。
2. [**Azure Active Directory**] を選択します。
3. 削除する組織に切り替えます。
4. [テナント **の削除] を選択します**。
5. 組織で 1 つ以上のチェックに失敗した場合は、チェックに合格する方法の詳細へのリンクが表示されます。 すべてのチェックに合格したら、[削除] **を選択して** プロセスを完了します。

この最後の手順を完了すると、Microsoft のアカウントは閉じ、削除されます。