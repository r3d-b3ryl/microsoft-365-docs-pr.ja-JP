---
title: ユーザーを追加してライセンスを割り当てる
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: ユーザーを追加して、同時に Microsoft 365 にライセンスを割り当てる方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 5df0db1cb782cc55bcf3e2b599430a98ea88750c
ms.sourcegitcommit: 8252377f63de188d32ed1ccd37540d92cba3cb65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2020
ms.locfileid: "49670997"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>ユーザーを追加して同時にライセンスを割り当てる

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

[一般法人向け Microsoft 365](https://www.microsoft.com/microsoft-365/business) にサインインしてアクセスする前に、チームの各ユーザーにはユーザー アカウントが必要です。 ユーザー アカウントを追加する最も簡単な方法は、Microsoft 365 管理センターで 1 人ずつ追加する方法です。 この手順を実行すると、Microsoft 365 ライセンス、サインイン用の資格情報、および Microsoft 365 メールボックスがユーザーに付与されます。

## <a name="before-you-begin"></a>開始する前に

ユーザーを追加してライセンスを割り当てるには、グローバル管理者、ライセンス管理者、またはユーザー管理者である必要があります。 詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="watch-add-users-in-the-admin-center"></a>視聴: 管理センターでユーザーを追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> 動画で使用されている手順では、ユーザーを追加するための出発点が異なっていますが、残りの手順は以下の手順と同じです。

## <a name="add-users-one-at-a-time"></a>ユーザーを 1 人ずつ追加する

::: moniker range="o365-worldwide"

1. <https://admin.microsoft.com> で管理センターに移動します。
2. [**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。
3. [**基本設定**] ウィンドウにユーザーの基本情報を入力し、[**次へ**] を選択します。
    - [**名前**] 姓、名、表示名、ユーザー名を入力します。
    - [**ドメイン**] ユーザーのアカウントのドメインを選びます。 たとえば、ユーザー名が Jakob、そのドメインが contoso.com の場合、「jakob@contoso.com」と入力してサインインします。
    - [**パスワードの設定**] ユーザー用のパスワードとして、自動生成されたパスワードを使用するのか独自の強力なパスワードを作成するのかを選択します。
    - ユーザーは 90 日後にパスワードを変更する必要があります。 または、[**初回サインイン時にこのユーザーにパスワードの変更を要求する**] を選択することもできます。
    - ユーザーが追加されたときに、パスワードをメールで送信するかどうかを選択します。
4. [**製品ライセンスの割り当て**] ウィンドウで、ユーザーの場所と適切なライセンスを選択します。 利用可能なライセンスがない場合でも、ユーザーを追加し、追加のライセンスを購入できます。 [**アプリ**] を展開し、アプリを選択または選択解除して、ユーザーにライセンスが付与されるアプリを制限します。 [**次へ**] を選択します。
5. [**オプションの設定**] ウィンドウで、このユーザーを管理者にする場合は [**役割**] を展開します。ユーザーに関する追加情報を入力する場合は、[**プロファイル情報**] を展開します。
6. [**次へ**] を選択し、新しいユーザーの設定を確認し、必要に応じて変更を行い、[**追加の完了**] を選択し、**[閉じる]** をクリックします。

::: moniker-end

::: moniker range="o365-germany"

1. <https://portal.office.de/adminportal> で管理センターに移動します。
2. [**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。
3. [**新しいユーザー**] ウィンドウで、次の情報を入力します。 完了したら、[**追加**] を選択します。
    - [**名前**] 名、姓、表示名、ユーザー名を入力します。
    - [**ドメイン**] たとえば、ユーザー名が Jakob、そのドメインが contoso.com の場合、「jakob@contoso.com」と入力してサインインします。
    - [**連絡先情報**] 展開して、携帯電話番号、住所などを入力します。
    - [**パスワード**] 自動生成されたパスワードを使用するか、展開してユーザーに強力なパスワードを指定します。 ユーザーは 90 日後にパスワードを変更する必要があります。 または、[ **ユーザーが初回サインイン時にパスワードを変更する**] を選ぶこともできます。
    - [**役割**] このユーザーに管理者権限を割り当てる場合に展開します。
    - [**製品ライセンス**] このセクションを展開し、適切なライセンスを選択します。利用可能なライセンスを持っていない場合でも、ユーザーを追加したり、追加のライセンスを購入したりすることができます。

::: moniker-end

::: moniker range="o365-21vianet"

1. <https://portal.partner.microsoftonline.cn> で管理センターに移動します。
2. [**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。
3. [**新しいユーザー**] ウィンドウで、次の情報を入力します。 完了したら、[**追加**] を選択します。
    - [**名前**] 名、姓、表示名、ユーザー名を入力します。
    - [**ドメイン**] たとえば、ユーザー名が Jakob、そのドメインが contoso.com の場合、「jakob@contoso.com」と入力してサインインします。
    - [**連絡先情報**] 展開して、携帯電話番号、住所などを入力します。
    - [**パスワード**] 自動生成されたパスワードを使用するか、展開してユーザーに強力なパスワードを指定します。 ユーザーは 90 日後にパスワードを変更する必要があります。 または、[ **ユーザーが初回サインイン時にパスワードを変更する**] を選ぶこともできます。
    - [**役割**] このユーザーに管理者権限を割り当てる場合に展開します。
    - [**製品ライセンス**] このセクションを展開し、適切なライセンスを選択します。利用可能なライセンスを持っていない場合でも、ユーザーを追加したり、追加のライセンスを購入したりすることができます。

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>複数のユーザーを同時に追加する

複数のユーザーを同時に追加するには、次のいずれかの方法を使用します。

- **ユーザーをまとめて追加するには、スプレッドシートを使用します。** 「[同時に複数のユーザーを追加する](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)」を参照してください。
- **アカウントの追加とライセンスの割り当てを自動化します。** 「[Microsoft 365 の PowerShell を使用してユーザー アカウントを作成する](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell)」を参照してください。 この方法は、Windows PowerShell コマンドレットについて詳しい知識のある場合に選んでください。
- **ActiveDirectory を使用する場合** [Microsoft 365 のディレクトリ同期をセットアップ](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)します。 Azure AD Connect ツールを使用し、Microsoft 365 で Active Directory ユーザー アカウント (およびその他の Active Directory オブジェクト) を複製します。 同期では、ユーザー アカウントのみが追加されます。 同期されているユーザーがメールとその他の Office アプリを使用するには、そのユーザーにライセンスを割り当てる必要があります。
- **Exchange Server から移行する場合** 「[複数のメール アカウントを Office 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)」を参照してください。 カットオーバー、段階的方法、またはハイブリッド Exchange による方法のいずれかを使って、複数のメールボックスを Microsoft 365 に移行するときは、移行の一部としてユーザーが自動的に追加されます。 移行では、ユーザー アカウントのみが追加されます。 ユーザーがメールとその他の Office アプリを使用するには、そのユーザーにライセンスを割り当てる必要があります。 ユーザーにライセンスを割り当てない場合、30 日間の猶予期間が過ぎるとユーザーのメールボックスが無効になります。 Microsoft 365 管理センターで[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)方法を確認してください。

## <a name="next-steps"></a>次の手順

ユーザーを追加すると、Microsoft からメール通知が届きます。 メールには、ユーザーが Microsoft 365 にサインインするための Microsoft 365 のユーザー ID とパスワードが含まれています。 新しいパスワードは、通常のプロセスを使用して通知してください。 新しいユーザーと「[従業員のクイック スタート ガイド](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)」を共有し、ユーザーが「[PC または Mac に Office アプリをダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 に新しい従業員を追加する](add-new-employee.md) (記事)\
[同時に複数のユーザーを Microsoft 365 に追加する](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (記事)\
[Microsoft 365 のユーザーを復元する](restore-user.md) (記事)\
[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)(記事)\
[組織からユーザーを削除する](delete-a-user.md) (記事)
