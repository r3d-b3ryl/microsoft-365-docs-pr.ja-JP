---
title: アカウントの使用を停止する
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- AdminTemplateSet
search.appverid: MET150
description: Microsoft でアカウントを閉じると、アカウントに関連する情報 (ライセンス、ユーザー、ユーザー データなど) が削除されます。
ms.date: 04/02/2021
ms.openlocfilehash: b1ac828d047d2c2b9f39185a66ccc77976b8324b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317291"
---
# <a name="close-your-account"></a>アカウントの使用を停止する

Microsoft でのアカウントの使用を停止すると、アカウントに関連するすべての情報が削除されます。 この情報には、サブスクリプション、ライセンス、支払方法、ユーザー、ユーザー データが含まれます。

## <a name="before-you-begin"></a>始める前に

このプロセスを開始する前に、保持する必要があるすべてのデータをバックアップしてください。

この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md)」をご覧ください。

## <a name="step-1-delete-users"></a>手順 1: ユーザーを削除する

1 人のグローバル管理者を除くすべてのユーザーを削除します。 グローバル管理者は、アカウントを閉じる手順を完了します。 このプロセスの最後にディレクトリを削除する前に、他のすべてのユーザーを削除する必要があります。

ユーザーがオンプレミスから同期されている場合は、まず同期をオフにしてから、Azure portal または Azure PowerShell コマンドレットを使用してクラウド ディレクトリ内のユーザーを削除します。

ユーザーを削除するには、「ユーザー管理管理者 [: 1 人または複数のユーザーを削除する」を参照してください](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)。

[Remove-MsolUser PowerShell コマンドレット](/powershell/module/msonline/remove-msoluser)を使用して、ユーザーを一括で削除することもできます。

組織で Active Directory を使用して、Microsoft Azure Active Directory (Azure AD) と同期する場合は、代わりに Active Directory からユーザー アカウントを削除します。 手順については、「ユーザーを一括[削除する」を参照Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete)。

## <a name="step-2-cancel-all-active-subscriptions"></a>手順 2: すべてのアクティブなサブスクリプションをキャンセルする

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、アクティブなサブスクリプションを探します。 3 つのドット (その他の操作) を選択してから、**[サブスクリプションのキャンセル]** を選択します。
3. **[サブスクリプションのキャンセル]** ウィンドウで、キャンセルする理由を選択します。必要に応じて、フィードバックを提供します。
4. **[保存]** を選択します。
5. 手順 1 ~ 4 を繰り返して、アクティブなすべてのサブスクリプションを取り消します。

## <a name="step-3-delete-all-disabled-subscriptions"></a>手順 3: 無効なすべてのサブスクリプションを削除する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、無効なサブスクリプションを選択します。
3. [サブスクリプションの詳細] ページの [サブスクリプションと支払いの設定] セクション **で** 、[サブスクリプションの削除] **を選択します**。
4. [サブスクリプションの **削除] ウィンドウで** 、[サブスクリプションの削除] **を選択します**。
5. [サブスクリプションの **削除] ダイアログ ボックス** で、[はい] を **選択します**。
6. 無効にしたサブスクリプションごとに、すべてのサブスクリプションが削除されるまで手順 3 ~ 5 を繰り返します。

> [!NOTE]
> 無効になっているサブスクリプションを直ちに削除できない場合は、サポート [にお問い合わせください](../admin/get-help-support.md)。

## <a name="step-4-disable-multi-factor-authentication"></a>手順 4: 多要素認証を無効にする

1. グローバル管理者アカウントを使用して管理センターにサインインします。 持っている役割を確認するには、「組織内の [管理者の役割を確認する」を参照してください](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。
2. **[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブ ユーザー]</a> ページに移動します。
3. [ **多要素認証] を選択します**。
4. 多要素認証ページで、現在使用しているグローバル管理者アカウントを除くすべてのアカウントを無効にします。

PowerShell を [使用して、複数のユーザーの多要素認証を無効にできます](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)。


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>手順 5: ディレクトリを削除Azure Active Directory

1. グローバル管理者アカウントを<a href="https://aad.portal.azure.com/" target="_blank">使用Azure AD管理センター</a>にサインインします。
2. **Azure Active Directory** を選択します。
3. 削除する組織に切り替えます。
4. [テナント **の削除] を選択します**。
5. 組織で 1 つ以上のチェックに失敗した場合は、チェックに合格する方法の詳細へのリンクが表示されます。 すべてのチェックに合格したら、[ **削除] を選択して** プロセスを完了します。

この最後の手順を完了すると、Microsoft のアカウントは閉じ、削除されます。

## <a name="related-content"></a>関連コンテンツ 

[ビジネス向け請求書または請求書Microsoft 365を](./billing-and-payments/understand-your-invoice2.md)理解する (記事)\
[サブスクリプションをキャンセルする](./subscriptions/cancel-your-subscription.md) (記事)

