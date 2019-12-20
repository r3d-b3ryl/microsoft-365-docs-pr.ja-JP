---
title: アカウントの削除
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Microsoft を使用してアカウントを終了する方法について説明します。
ms.openlocfilehash: 905b3d1dfef44a6b1f78c5afe5f7673aec6b8894
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809336"
---
# <a name="close-your-account"></a>アカウントの削除

Microsoft を使用してアカウントを閉じると、アカウントに関連するすべての情報が削除されます。 この情報には、サブスクリプション、ライセンス、支払い方法、ユーザー、ユーザーデータが含まれます。 このプロセスを開始する前に、保持する必要のあるデータを必ずバックアップしてください。

## <a name="step-1-delete-users"></a>手順 1: ユーザーを削除する

アカウントを閉じる手順を完了した1人のグローバル管理者を除くすべてのユーザーを削除します。 このプロセスの終了時にディレクトリを削除するには、その前に他のすべてのユーザーを削除する必要があります。

ユーザーがオンプレミスから同期されている場合は、まず sync をオフにしてから、Azure portal または Azure PowerShell コマンドレットを使用してクラウドディレクトリ内のユーザーを削除します。

ユーザーを削除するには、「 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: 1 人</a>以上のユーザーを削除する」を参照してください。

<a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell コマンドレットを使用して、ユーザーを一括で削除することもできます。

組織が Azure AD と同期する Active Directory を使用している場合は、代わりに Active Directory からユーザーアカウントを削除します。 手順については、「 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Azure Active Directory でユーザーを一括削除</a>する」を参照してください。

## <a name="step-2-cancel-all-active-subscriptions"></a>手順 2: すべてのアクティブなサブスクリプションをキャンセルする

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] のページに移動します。

2. 購読リストが**表**形式の場合は、右側の [**カード**] を選択します。

3. アクティブなサブスクリプションを検索し、[**設定 & の操作**] セクションで、[**サブスクリプションのキャンセル**] を選択します。

4. 画面の指示に従って、プロセスを完了します。

5. 手順 1 ~ 4 を繰り返して、すべてのアクティブなサブスクリプションを取り消します。

## <a name="step-3-delete-all-disabled-subscriptions"></a>手順 3: 無効になっているすべてのサブスクリプションを削除する

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] のページに移動します。

2. 購読リストが**表**形式の場合は、右側の [**カード**] を選択します。

3. [**サブスクリプションの状態**] の横で、[**無効**] を選択します。

4. 無効になっているサブスクリプションを検索し、[**設定 & の操作**] セクションで、[**削除**] を選択します。

5. [**サブスクリプションの削除**] ダイアログボックスで、[**影響について理解**しています] チェックボックスをオンにして、[**サブスクリプションの削除**] を選択します。

6. 無効化された各サブスクリプションについて、すべてのサブスクリプションが削除されるまで、ステップ4と5を繰り返します。

## <a name="step-4-disable-multi-factor-authentication"></a>手順 4: 多要素認証を無効にする

1. 管理センターで、[**ユーザー** > の<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a> ] ページに移動します。

2. [**多要素認証**] を選択します。

3. [多要素認証] ページで、現在使用中のグローバル管理者アカウント以外のすべてのアカウントを無効にします。

<a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">PowerShell を使用して、複数のユーザーに対して多要素認証を無効に</a>することもできます。

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>手順 5: Azure Active Directory のディレクトリを削除する

1. グローバル管理者アカウントを使用して、 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 管理センター</a>にサインインします。

2. **Azure Active Directory** を選択します。

3. 削除するディレクトリに切り替えます。

4. [**ディレクトリの削除**] を選択します。

5. ディレクトリが1つ以上のチェックに失敗した場合は、チェックを通過する方法に関する詳細情報へのリンクが表示されます。 すべてのチェックに合格したら、[**削除**] を選択してプロセスを完了します。

この最後の手順を完了すると、Microsoft とのアカウントが閉じられ、削除されます。