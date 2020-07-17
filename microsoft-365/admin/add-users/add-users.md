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
description: ユーザーを追加して、Microsoft 365 にライセンスを同時に割り当てる方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 016c98fc93bfa1a92274a5b991cf8adbd1131bc9
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015889"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>ユーザーを追加して、ライセンスを同時に割り当てる

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

チームのメンバーは、サインインして[Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395)にアクセスする前に、ユーザーアカウントが必要です。 ユーザー アカウントを追加する最も簡単な方法は、Microsoft 365 管理センターで 1 人ずつ追加する方法です。 この手順を実行すると、ユーザーには Microsoft 365 ライセンス、サインイン資格情報、および Microsoft 365 メールボックスがあります。

## <a name="before-you-begin"></a>はじめに

ユーザーを追加してライセンスを割り当てるには、グローバル、ライセンス、またはユーザーの管理者である必要があります。 詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="watch-add-users-in-the-admin-center"></a>視聴: 管理センターでユーザーを追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> ビデオで使用されている手順はユーザーを追加するための開始点とは異なりますが、残りの手順は次の手順と同じです。

## <a name="add-users-one-at-a-time"></a>一度に1人ずつユーザーを追加する

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。
2. [**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。
3. [基本 **] ウィンドウで**、[基本的なユーザー情報] を入力し、[**次へ**] を選択します。
    - **名前**姓と名、表示名、およびユーザー名を入力します。
    - **ドメイン**ユーザーのアカウントのドメインを選択します。 たとえば、ユーザーの username が Jakob で、ドメインが contoso.com の場合は、jakob@contoso.com を使用してサインインします。
    - **パスワードの設定**自動生成されたパスワードを使用するか、ユーザーに対して独自の強力なパスワードを作成するかを選択します。
    - ユーザーは、90日後にパスワードを変更する必要があります。 または、[**初回サインイン時にこのユーザーにパスワードの変更を要求する**] を選択することもできます。
    - ユーザーが追加されたときに、パスワードを電子メールで送信するかどうかを選択します。
4. [**製品ライセンスの割り当て**] ウィンドウで、ユーザーの場所と適切なライセンスを選択します。 利用可能なライセンスがない場合でも、ユーザーを追加し、追加のライセンスを購入できます。 [**アプリ**] を展開し、アプリを選択または選択解除して、ユーザーがライセンスを持っているアプリを制限します。 [**次へ**] を選択します。
5. [**オプションの設定**] ウィンドウで、[**役割**] を展開してこのユーザーを管理者にします。[**プロファイル情報**] を展開して、ユーザーに関するその他の情報を追加します。
6. [**次へ**] を選択し、新しいユーザーの設定を確認し、必要に応じて変更を加えてから、[**追加**]、[**閉じる**] の順に選択します。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> で管理センターにアクセスします。
2. [**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。
3. [**新しいユーザー**] ウィンドウで、次の情報を入力します。 完了したら、[**追加**] を選択します。
    - [**名前**] 名、姓、表示名、ユーザー名を入力します。
    - **ドメイン**たとえば、ユーザーの username が Jakob で、ドメインが contoso.com の場合は、jakob@contoso.com と入力することによってにサインインします。
    - [**連絡先情報**] 展開して、携帯電話番号、住所などを入力します。
    - **Password**自動生成されたパスワードを使用するか、または展開して、ユーザーに強力なパスワードを指定します。 90日後にパスワードを変更する必要があります。 または、[ **ユーザーが初回サインイン時にパスワードを変更する**] を選ぶこともできます。
    - [**役割**] このユーザーに管理者権限を割り当てる場合に展開します。
    - [**製品ライセンス**] このセクションを展開し、適切なライセンスを選択します。利用可能なライセンスを持っていない場合でも、ユーザーを追加したり、追加のライセンスを購入したりすることができます。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> で管理センターにアクセスします。
2. [**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。
3. [**新しいユーザー**] ウィンドウで、次の情報を入力します。 完了したら、[**追加**] を選択します。
    - [**名前**] 名、姓、表示名、ユーザー名を入力します。
    - **ドメイン**たとえば、ユーザーの username が Jakob で、ドメインが contoso.com の場合は、jakob@contoso.com と入力することによってにサインインします。
    - [**連絡先情報**] 展開して、携帯電話番号、住所などを入力します。
    - **Password**自動生成されたパスワードを使用するか、または展開して、ユーザーに強力なパスワードを指定します。 90日後にパスワードを変更する必要があります。 または、[ **ユーザーが初回サインイン時にパスワードを変更する**] を選ぶこともできます。
    - [**役割**] このユーザーに管理者権限を割り当てる場合に展開します。
    - [**製品ライセンス**] このセクションを展開し、適切なライセンスを選択します。利用可能なライセンスを持っていない場合でも、ユーザーを追加したり、追加のライセンスを購入したりすることができます。

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>一度に複数のユーザーを追加する

複数のユーザーを同時に追加するには、次のいずれかの方法を使用できます。
  
- **ユーザーをまとめて追加するには、スプレッドシートを使用します。** 「[同時に複数のユーザーを追加する](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)」を参照してください。
- **アカウントの追加とライセンスの割り当てを自動化します。** 「[Office 365 PowerShell を使用してユーザー アカウントを作成する](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell)」を参照してください。 この方法は、Windows PowerShell コマンドレットについて詳しい知識のある場合に選んでください。
- **ActiveDirectory を使用する場合** [Office 365 のディレクトリ同期をセットアップ](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)します。 Azure AD Connect ツールを使用して、Microsoft 365 の Active Directory ユーザーアカウント (およびその他の Active Directory オブジェクト) をレプリケートします。 同期では、ユーザー アカウントのみが追加されます。 電子メールやその他の Office アプリを使用するには、その前に、同期されたユーザーにライセンスを割り当てる必要があります。
- **Exchange Server から移行する場合** [複数のメールアカウントを Office 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)を参照してください。 カットオーバー、ステージング、またはハイブリッド Exchange のいずれかの方法を使用して、複数のメールボックスを Microsoft 365 に移行する場合、ユーザーは移行の一部として自動的に追加されます。 移行では、ユーザー アカウントのみが追加されます。 ユーザーが電子メールやその他の Office アプリを使用できるようにするには、その前にライセンスをユーザーに割り当てる必要があります。 ユーザーにライセンスを割り当てない場合、30日の猶予期間後にメールボックスが無効になります。 Microsoft 365 管理センターで[ライセンスをユーザーに割り当てる](../manage/assign-licenses-to-users.md)方法について説明します。

## <a name="next-steps"></a>次の手順

ユーザーを追加すると、Microsoft からの電子メール通知が表示されます。 電子メールには、ユーザーのユーザー ID とパスワードが含まれているため、Microsoft 365 にサインインできます。 新しいパスワードは、通常のプロセスを使用して通知してください。 [Office アプリを PC または Mac にダウンロードしてインストール](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)する方法や、[モバイルデバイスで office アプリや電子メール](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)をセットアップする方法などの設定を行うために、[従業員のクイックスタートガイド](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)を新しいユーザーと共有します。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 (記事) に新しい従業員を追加](add-new-employee.md)します。
[複数のユーザーを同時に Microsoft 365 (記事) に追加する](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)
[Microsoft 365 でユーザーを復元する](restore-user.md)(記事) \
[ユーザーへのライセンスの割り当て](../manage/assign-licenses-to-users.md)(記事) \
[組織からユーザーを削除する](delete-a-user.md)(記事)