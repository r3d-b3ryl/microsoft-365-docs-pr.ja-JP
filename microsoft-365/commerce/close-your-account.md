---
title: アカウントの使用を停止する
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: amberb, vikdesai
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
description: Microsoft でアカウントを閉じると、ライセンス、ユーザー、ユーザー データを含め、アカウントに関連するすべての情報が削除されます。
ms.date: 04/02/2021
ms.openlocfilehash: c036a4cda929d58265a088b15a43772caacb0b94
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102462"
---
# <a name="close-your-account"></a>アカウントの使用を停止する

Microsoft でのアカウントの使用を停止すると、アカウントに関連するすべての情報が削除されます。 この情報には、サブスクリプション、ライセンス、支払方法、ユーザー、ユーザー データが含まれます。

## <a name="before-you-begin"></a>はじめに

このプロセスを開始する前に、保持する必要があるすべてのデータをバックアップしてください。

この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。 詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="step-1-delete-users"></a>手順 1: ユーザーを削除する

1 人のグローバル管理者を除くすべてのユーザーを削除します。 グローバル管理者は、アカウントを閉じる手順を完了します。 このプロセスの最後にディレクトリを削除する前に、他のすべてのユーザーを削除する必要があります。

ユーザーがオンプレミスから同期されている場合は、まず同期をオフにしてから、Azure portalコマンドレットまたはAzure PowerShell コマンドレットを使用してクラウド ディレクトリ内のユーザーを削除します。

ユーザーを削除するには、「 [ユーザー管理管理者: 1 人以上のユーザーを削除](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)する」を参照してください。

[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell コマンドレットを使用して、ユーザーを一括で削除することもできます。

組織で Microsoft Azure Active Directory (Azure AD) と同期する Active Directory を使用している場合は、代わりに Active Directory からユーザー アカウントを削除します。 手順については、「[Azure Active Directoryでユーザーを一括削除する](/azure/active-directory/users-groups-roles/users-bulk-delete)」を参照してください。

## <a name="step-2-cancel-all-active-subscriptions"></a>手順 2: アクティブなすべてのサブスクリプションを取り消す

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [ **製品** ] タブで、アクティブなサブスクリプションを見つけます。 3 つのドット (その他の操作) を選択してから、**[サブスクリプションのキャンセル]** を選択します。
3. **[サブスクリプションのキャンセル]** ウィンドウで、キャンセルする理由を選択します。必要に応じて、フィードバックを提供します。
4. **[保存]** を選択します。
5. 手順 1 ~ 4 を繰り返して、すべてのアクティブなサブスクリプションを取り消します。

## <a name="step-3-delete-all-disabled-subscriptions"></a>手順 3: 無効になっているすべてのサブスクリプションを削除する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [ **製品** ] タブで、無効なサブスクリプションを選択します。
3. [サブスクリプションの詳細] ページの [ **サブスクリプションと支払いの設定** ] セクションで、[ **サブスクリプションの削除**] を選択します。
4. [ **サブスクリプションの削除** ] ウィンドウで、[ **サブスクリプションの削除**] を選択します。
5. [ **サブスクリプションの削除** ] ダイアログ ボックスで、[ **はい**] を選択します。
6. 無効になっているサブスクリプションごとに、すべてのサブスクリプションが削除されるまで手順 3 ~ 5 を繰り返します。

> [!NOTE]
> 無効になっているサブスクリプションをすぐに削除できない場合は、 [サポートにお問い合わせください](../admin/get-help-support.md)。

## <a name="step-4-disable-multi-factor-authentication"></a>手順 4: 多要素認証を無効にする

1. グローバル管理者 アカウントを使用して管理センターにサインインします。 自分の役割を確認するには、「 [組織内の管理者ロールを確認](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)する」を参照してください。
2. **[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブ ユーザー]</a> ページに移動します。
3. [ **多要素認証**] を選択します。
4. 多要素認証ページで、現在使用しているグローバル管理者アカウントを除くすべてのアカウントを無効にします。

[PowerShell を使用して、複数のユーザーの多要素認証を無効に](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)することもできます。


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>手順 5: Azure Active Directoryのディレクトリを削除する

1. グローバル管理者 アカウントを使用して <a href="https://aad.portal.azure.com/" target="_blank">Azure AD 管理センター</a>にサインインします。
2. **Azure Active Directory** を選択します。
3. 削除する組織に切り替えます。
4. [ **テナントの削除]** を選択します。
5. 組織で 1 つ以上のチェックが失敗した場合は、チェックに合格する方法の詳細へのリンクが表示されます。 すべてのチェックに合格したら、[ **削除** ] を選択してプロセスを完了します。

この最後の手順を完了すると、Microsoft を使用しているアカウントは閉じられ、削除されます。

## <a name="related-content"></a>関連コンテンツ 

[Microsoft 365 for Business の請求書または請求明細書を理解する](./billing-and-payments/understand-your-invoice2.md) (記事)\
[サブスクリプションを解約する](./subscriptions/cancel-your-subscription.md) (記事)

