---
title: 組織からユーザーを削除する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: ユーザー アカウントを削除する方法と、ユーザーの電子メールとコンテンツをOneDriveする方法、および製品ライセンスを保持するかどうかを説明します。
ms.openlocfilehash: 462e9bcec4dac7e9d708618777ea58fb5d182473
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370610"
---
# <a name="delete-a-user-from-your-organization"></a>組織からユーザーを削除する
  
**職場または学校で使用する *自分の* Microsoft 365 ユーザー アカウントを削除する方法をお探しの場合は、職場または大学のテクニカル サポートにこれらの手順の実行を依頼してください。**

## <a name="before-you-begin"></a>はじめに

- ユーザー アカウントを削除できるのは、職場や学校の [Microsoft 365 グローバル管理者](about-admin-roles.md)またはユーザー管理のアクセス許可を持っている管理者のみです。
- 30 日後にユーザーのデータが永久に削除されるまではアカウントを[復元](restore-user.md)できます。
- ユーザーのデータを保持する場合OneDrive別の場所に移動します。 アカウントを削除した後、最大 30 日間データを移動することもできます。 「 [元ユーザーのデータにアクセスしてバックアップを作成する](get-access-to-and-back-up-a-former-user-s-data.md)」を参照してください。 ファイルを移動する必要はありませんSharePointファイルにアクセスできます。
- ユーザーのメールを保持する場合は、アカウントを削除する **前に**、メールを別の場所に移動します。アカウントを既に削除した場合は、30 日以内であれば、復元してメール データを移動し、アカウントを削除できます。「[元ユーザーのデータにアクセスしてバックアップを作成する](get-access-to-and-back-up-a-former-user-s-data.md)」を参照してください。
- Office 365 Enterprise E3 などのエンタープライズ サブスクリプションがある場合、削除したユーザー アカウントのメールボックスを *非アクティブなメールボックス* に変更することで、そのメールボックスのデータを保持できます。 詳細については、「[Exchange Online の非アクティブなメールボックスを管理する](../../compliance/inactive-mailboxes-in-office-365.md)」を参照してください。

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>グローバル管理者: ユーザーを削除し、それらのユーザーのライセンスの支払いを停止し、それらのユーザーのメールと OneDrive のコンテンツの処置方法を選択する

グローバル管理者は、ユーザーを削除した際に、それらのユーザーのメールへのアクセス権を別のユーザーに付与したり、それらのユーザーの OneDrive コンテンツの処置方法を決定したりできます。

### <a name="things-to-consider"></a>考慮事項

作業を開始する前に、ユーザーのメールと OneDrive コンテンツの処置方法、ライセンスを保持するのかそれとも支払いを停止するのかについて検討します。
  
|アイテム | 説明 |
|:-----|:-----|
|製品のライセンス  <br/> |ライセンスをユーザーから削除してライセンスを組織のサブスクリプションから削除すると、ライセンスに対する支払いを停止できます。 このオプションを選択した場合、ライセンスがサブスクリプションから自動的に削除されます。  <br/><br/> パートナー経由またはボリューム ライセンスを通して購入したライセンスは **削除できません**。 年間プランの支払いを行う場合、または請求サイクルの途中にある場合は、契約が完了するまでサブスクリプションからライセンスを削除できます。  <br/> |
|OneDrive のコンテンツ  <br/> |ユーザーがファイルを OneDrive に保存していた場合、これらのファイルへのアクセス権を別のユーザーに付与することができます。  <br/><br/> 保持するファイルは、OneDrive のファイルに対して設定されている保持期間内に移動する必要があります。 **既定の保持期間は 30 日です。** ユーザーを削除した後に保持期間内にファイルを移動しない場合、削除されたユーザーの OneDrive がサイト コレクションのごみ箱に移動され、93 日間保持されます。 この間、ユーザーは、共有コンテンツにアクセスできなくなったOneDrive。 データベースを復元するにはOneDrive PowerShell を使用する必要があります。 詳細については、「[削除されたファイルを復元する」をOneDrive。](/onedrive/restore-deleted-onedrive)<br/><br/> 削除されたアカウントの OneDrive ファイルを保持する日数を増やすには、「[削除されたユーザーの OneDrive の保持期間を設定する](/onedrive/set-retention)」を参照してください。  <br/><br/> **重要!** 削除されたユーザーが個人のコンピューターを使用して SharePoint および OneDrive からファイルをダウンロードしていた場合、ユーザーが自分のコンピューターに保存したファイルを管理者が削除する方法はありません。 OneDrive から同期されたファイルに引き続きアクセスできます。           |
|メール  <br/> | 削除したユーザーのメールへのアクセス権を別のユーザーに付与すると、削除されたユーザーのメールボックスは共有メールボックスに変換されます。 メールボックスの新しい所有者は、メールボックスにアクセスして新しいメールを監視できます。 以下のオプションもあります。  <br/>  <br/>表示名を変更する - [アクティブ ユーザー] リストで共有メールボックスを簡単に識別するために、表示名 **を変更することをお勧** めします。  <br/>  自動応答を有効にする - 丁寧な文面のメッセージが自動応答用に組み込まれています。 組織内のユーザーと組織外のユーザーに対して、さまざまな自動返信を送信できます。  <br/> <br/> エイリアスをクリーンアップする - エイリアスとは、ユーザーの追加のメール アドレスのことです。 組織によっては、エイリアスを使用していません。エイリアスがない場合、何も操作を行う必要はありません。 ユーザーにエイリアスがある場合は、それらのメール アドレスを再利用できるよう、エイリアスを削除することをお勧めします。 それ以外の場合は、削除されたメールボックスの保持期間が過ぎるまで、これらの電子メール アドレスを再利用できません。 既定では、削除したメールボックスは 30 日間回復可能です。 詳細については、「 [Exchange Online のユーザー メールボックスを削除または復元する](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)」を参照してください。 <br/> |
|Active Directory  <br/> |お客様の一般法人で Azure AD と同期している **Active Directory** を使用する場合は、Active Directory からユーザー アカウントを削除する必要があります。 Office 365 からこの操作を行うことはできません。 手順については、「[ユーザー アカウントを削除する](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))」を参照してください。  <br/> |

### <a name="get-started"></a>作業の開始

ユーザーを削除する手順は、ガイドに従って実行できます。以下の方法でガイドを開始できます。

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

2. 削除するユーザーを選択し、[ユーザーの削除] **を選択します**。

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>ユーザー管理の管理者: Office 365 から 1 人または複数のユーザーを削除する

> [!IMPORTANT]
> アカウントを[共有メールボックスに変換した場合](../email/convert-user-mailbox-to-shared-mailbox.md)や、アカウントでメールの転送を設定した場合、ユーザーのアカウントを削除しないでください。これらの機能には、アカウントが必要です。共有メールボックスにはライセンスは必要ありません。アカウントを共有メールボックスに変換した場合は、[ライセンスの支払いを停止](#stop-paying-for-the-license)できます。アカウントでメール転送を設定している場合、ライセンスを削除することはできません。これを行うと、メールの転送が停止し、メールボックスが非アクティブになります。
  
::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。  

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

2. 削除するユーザーの名前を選択し、3 つのドット (その他のアクション) を選択し、[ユーザーの削除]  **を選択します**。

   これによりユーザーのアカウントは削除されますが、**ライセンスの支払いは継続します**。 ライセンスの支払いを停止するには、次の手順を参照してください。  または、ライセンスを別のユーザーに割り当てることができます。 ライセンスが自動的に別のユーザーに割り当てられることはありません。

### <a name="stop-paying-for-the-license"></a>ライセンスの支払いを停止する

ライセンス数を減らす作業は別の手順になり、グローバル管理者または請求管理者のみがこれを行えます。
  
::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。
::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">お使いの製品</a>] ページの順に移動します。
::: moniker-end

2. [製品 **] タブ** で、ライセンスを削除するサブスクリプションを選択します。

3. [サブスクリプションの詳細] ページで、**[ライセンスの削除]** を選択します。

4. [ライセンス **の削除]** ウィンドウの [**新** しい数量] の [ライセンスの合計] ボックスに、このサブスクリプションに必要なライセンスの総数を入力します。 たとえば、100 のライセンスを持ち、5 つのライセンスを削除する場合は、「95」と入力します。

5. **[保存]** を選択します。

将来、新しいユーザーを組織のサブスクリプションに追加する手順を実行すると、ライセンスの購入を求めるメッセージが表示されるため、手間が省けます。

## <a name="delete-many-users-at-the-same-time"></a>多数のユーザーを同時に削除する

[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell コマンドレットを参照してください。

## <a name="fix-issues-with-deleting-a-user"></a>ユーザーの削除に関する問題を解決する

ユーザーを削除するときに発生する最も一般的な問題を以下に示します。
  
- **"ユーザーが削除できません。後でもう一度お試しください。" の行でエラーが発生しました。** アカウントにメール転送が設定されているかどうかをもう一回確認するか、共有メールボックスに変換されています。 これらの両方でエラーが発生します。 メール転送を設定している場合、または共有メールボックスに変換した場合は、アカウントを削除しないでください。

- **ユーザーを削除するための適切なアクセス許可がありません**。 ユーザーを削除できるのは、[Microsoft 365 のグローバル管理者またはユーザー管理の管理者](about-admin-roles.md)のみです。 通常は、学校または職場のテクニカル サポートです。

- **ユーザーを削除しても、その名前がグローバル アドレス帳に表示され続けます** 。 これは、業務で Active Directory を使用している場合に発生します。 Active Directory からユーザー アカウントを削除する必要があります。 手順については、「ユーザー アカウントの [削除」を参照してください。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**自分のコンピューターから Microsoft 365 を削除する場合は、[サブスクリプションのキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)に移動します。**

## <a name="related-content"></a>関連コンテンツ

[ユーザーの復元](restore-user.md) (記事)\
[メールボックスを完全に削除](/exchange/permanently-delete-a-mailbox-exchange-2013-help) する (記事)\
[元従業員を会社から削除Office 365](remove-former-employee.md) (記事)\
[新しい従業員を新しいOffice 365](add-new-employee.md) (記事)\
[ユーザー アカウントを削除する](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)):Azure AD と同期している **Active Directory** を組織で使用している場合は、この手順を使用します。 Office 365 からこの操作を行うことはできません。 (記事)
