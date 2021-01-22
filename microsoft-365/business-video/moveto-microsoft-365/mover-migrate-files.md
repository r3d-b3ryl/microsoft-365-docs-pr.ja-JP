---
title: 'Google ファイルを Microsoft 365 for business に移行する '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Mover を使用して Google ファイルを Microsoft 365 for business に移行する方法について説明します。
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928200"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Google ファイルを Microsoft 365 for business に移行する 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

ビジネス向け Microsoft 365 に移行する場合は、Google ドライブからファイルを移行する必要があります。 Mover アプリを使って、個人用ドライブと共有ドライブからファイルを移動できます。 詳細については [、「Mover クラウド移行」を参照してください。](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover は、ファイルのコピーを作成し、コピーを Microsoft 365 for business に移動します。 元のファイルは Google ドライブにも保持されます。

## <a name="before-you-start"></a>始める前に

すべてのユーザーが Microsoft 365 for business にサインインし、OneDrive for Business をセットアップしている必要があります。 これを行うには、[Office.com][](https://office.com)に移動し、ビジネス向け Microsft 365 の資格情報でサインインし、[OneDrive] を選択します。

## <a name="try-it"></a>演習

### <a name="install-mover"></a>Mover をインストールする

1. Google Workspace 管理コンソールにサインインするには、次の[admin.google.com。](https://admin.google.com)

1. Choose **Apps,** **Google Workspace Marketplace apps,** Then Add app to Domain Install **list**.

1. Mover を検索して選択します。

1. Choose **Domain Install,** then **Continue**.

1. アクセス許可を確認し、条件に同意するチェック ボックスをオンにして、[許可] を選択し、[次へ]、次に **[完了**] の順に選択 **します**。

### <a name="create-connectors-and-run-the-migration"></a>コネクタを作成して移行を実行する

1. Google **Workspace Marketplace アプリに戻ります**。
1. ブラウザーを更新し **、Mover アプリを選択** します。
1. 下にスクロールして、ユニバーサル ナビゲーション リンクを選択します。
1. [ **新しいコネクタの承認] を** 選択し **、[G Suite (管理者)**] を見つけて 、[承認] を **選択します**。
1. 必要に応 **じ、表示名** を変更し、[承認] を **選択します**。
1. Google 管理者アカウントを選択し、アクセス許可を確認して、[許可] を選択 **します**。

    Mover には、検出されたチーム ドライブとユーザー ドライブの数が表示されます。 

1. [ **宛先の選択] で**、[ **新しいコネクタ** の承認] を選択し **、[Office 365]** を見つけて、[承認] を **選択します**。
1. Azure Active Directory の Mover アプリにアクセス許可を付与するには、次の操作[aka.ms/Office365MoverAuth。](https://aka.ms/Office365MoverAuth)
1. Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.
1. アカウントを選択し、アクセス許可を確認して、[承諾] を選択 **します**。
1. [プロパティ **] を** 選択し、[ユーザーの割 **り当てが必要か]** がオンになっていることを確認します。
1. Mover アプリに戻り、表示名を変更します (必要な場合は、[**承認**] を選択し、Microsoft 管理者アカウントを選択します)。

    Mover は、SharePoint Online (または SPO) サイトの数と検出されたユーザーについて通知します。
1. Choose **Continue Migration Setup,** select **Add Users,** then **Automatically Discover and Add Users**.

    Mover アプリは、Google のソース パスから Microsoft 365 の宛先パスにドライブをマップします。 

    ドライブが自動的にマップしない場合は、そのドライブの保存先パスを CSV ファイルに追加します。これは後で共有ドライブを SharePoint ドキュメント ライブラリに移行するために使用します。 

1. この例では、Migrated ファイルという SharePoint サイトを追加し、ドキュメント ページの URL をメモしています。 
1. 次に、ソース パス、宛先パス、タグの形式を使用して CSV ファイルを作成しました。 

    詳細については、以下を[aka.ms/movercsv。](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)

    宛先パス URL を追加する場合は、共有ドキュメントの後のすべてを削除します。たとえば、次の完全な URL は機能しません。 `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    次のように変更してください。`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. CSV ファイルの準備ができたら、[移行操作] 、[移行 **に追加]**、アップロード **するファイルの選択を選択します**。
1. CSV ファイルに移動して選択し、[開く] を選択 **します**。
1. ファイルを移行するユーザー ドライブを選択し、[ユーザーの移行の開始] **を選択します**。
1. 移行情報を確認し、移行を開始する時間を選択し、使用条件に同意して、[続行] を選択 **します**。

移行プロセスが完了すると、Mover アプリから通知が表示されます。