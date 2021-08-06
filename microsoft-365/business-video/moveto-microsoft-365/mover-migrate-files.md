---
title: 'Google ファイルをビジネス向Microsoft 365に移行する '
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Mover を使用して Google ファイルをビジネス向Microsoft 365移行する方法について説明します。
ms.openlocfilehash: 6791655f5ee8a9fc867266d5fe153cde6ec9adaa6148191c4c0eb3aedbfe0141
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53843493"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Google ファイルをビジネス向Microsoft 365に移行する 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

ビジネス向けMicrosoft 365に移動する場合は、ファイルを移行する必要Google ドライブ。 Mover アプリを使用して、個人用ドライブと共有ドライブからファイルを移動できます。 詳細については [、「Mover Cloud Migration」を参照してください](/sharepointmigration/mover-plan-migration)。

> [!NOTE]
> Mover はファイルのコピーを作成し、そのコピーをビジネス向Microsoft 365移動します。 元のファイルは Google ドライブにも保存されます。

## <a name="before-you-start"></a>始める前に

すべてのユーザーが、ビジネス向け Microsoft 365にサインインし、そのユーザーのOneDrive for Business。 これを行うには、[office.com][に移動](https://office.com)し、Microsoft 365資格情報を使用してサインインし、[OneDrive] を選択します。

## <a name="try-it"></a>お試しください!

### <a name="install-mover"></a>Mover のインストール

1. Google Workspace 管理コンソールにサインインするには[、admin.google.com。](https://admin.google.com)

1. [アプリ  >  **] [Google ワークスペース マーケットプレース アプリ]**  >  **[ドメイン インストールリストにアプリを追加する] を選択します**。

1. Mover を検索して選択します。

1. [ドメイン **インストール] を選択し**、[続行] **を選択します**。

1. アクセス許可を確認し、条件に同意するチェック ボックスをオンにし、[許可] を選択し、[ **次** へ] 、[完了] **の順** に **選択します**。

### <a name="create-connectors-and-run-the-migration"></a>コネクタの作成と移行の実行

1. Google Workspace **Marketplace アプリに戻ります**。
1. ブラウザーを更新し **、Mover アプリを選択** します。
1. 下にスクロールして、ユニバーサル ナビゲーション リンクを選択します。
1. [ **新しいコネクタの承認] を** 選択し **、G Suite (Admin) を** 見つけて、[承認] を **選択します**。
1. 必要に応 **じ、[表示名]** を変更し、[承認] を **選択します**。
1. Google 管理者アカウントを選択し、アクセス許可を確認してから、[許可] を **選択します**。

    Mover には、検出されたチーム ドライブとユーザー ドライブの数が表示されます。 

1. [**宛先の選択] で**、[新しい **コネクタの承認]** を選択し、[Office 365]**を探し、[** 承認] を **選択します**。
1. アプリ内の Mover アプリにアクセス許可を付与するにはAzure Active Directory[に移動](https://aka.ms/Office365MoverAuth)aka.ms/Office365MoverAuth。
1. **[Office 365] [権限]** を選択 **し、****会社の管理者の同意を付与します**。
1. アカウントを選択し、アクセス許可を確認し、[同意する] を **選択します**。
1. [プロパティ **] を** 選択し、[ユーザーの **割り当てが必要か]** がオンになっていることを確認します。
1. Mover アプリに戻り、表示 **名を変更** します 。必要に応じ、[ **承認**] を選択し、Microsoft 管理者アカウントを選択します。

    Mover は、オンライン (または SPO) サイトSharePoint検出されたユーザーの数について通知します。
1. [ **移行セットアップの続行] を** 選択し、[ **ユーザーの追加] 、[** ユーザー **の自動検出と追加] の順に選択します**。

    Mover アプリは、Google のソース パスから移行先パスにドライブをマップMicrosoft 365。 

    ドライブが自動的にマップしない場合は、移行先のパスを CSV ファイルに追加します。このパスは、後で共有ドライブを別のドキュメント ライブラリに移行SharePointします。 

1. この場合、移行済みファイルというSharePointサイトが追加され、ドキュメント ページの URL がメモされます。 
1. 次に、ソース パス、宛先パス、およびタグの形式を使用して CSV ファイルを作成しました。 

    詳細については、「aka.ms/movercsv」 [を参照してください](/sharepointmigration/mover-create-migration-csv)。

    宛先パス URL を追加する場合は、共有ドキュメントの後にすべてを削除します。 たとえば、次の完全な URL はエラーを発生します。`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    次のように変更してください。`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. CSV ファイルの準備ができたら、[移行アクション] 、[移行 **に** 追加] **、[アップロード** する **ファイルの選択] を選択します**。
1. CSV ファイルに移動して選択し、[開く] を **選択します**。
1. ファイルを移行するユーザー ドライブを選択し、[ユーザーの移行の開始 **] を選択します**。
1. 移行情報を確認し、移行を開始する時間を選択し、利用規約に同意し、[続行] を **選択します**。

Mover アプリは、移行プロセスが完了すると通知します。