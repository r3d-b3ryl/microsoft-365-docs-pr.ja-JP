---
title: ユーザーを追加してライセンスを割り当てる
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
- adminvideo
- business_assist
search.appverid:
- MET150
description: 各チーム メンバーは、一般法人向け Microsoft 365 にサインインしてアクセスする前に、ユーザー アカウントが必要になります。ユーザーを追加して、ライセンスを割り当てる方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 90ef6506d10c0f4c106dd18816ccd2f11803a079
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765422"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>ユーザーを追加して同時にライセンスを割り当てる

チームのメンバーそれぞれに、[一般法人向け Microsoft 365](https://www.microsoft.com/microsoft-365/business) にサインインしてアクセスするためのユーザー アカウントが必要です。ユーザー アカウントを追加する最も簡単な方法は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a> で 1 人ずつ追加することです。この作業が完了すると、ユーザーに Microsoft 365 のライセンス、サインイン資格情報、および Microsoft 365 メールボックスが与えられます。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="before-you-begin"></a>開始する前に

ユーザーを追加してライセンスを割り当てるには、グローバル管理者、ライセンス管理者、またはユーザー管理者である必要があります。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="watch-add-users-in-the-dashboard-view"></a>視聴: ダッシュボード ビューでユーザーを追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> 動画で使用されている手順では、ユーザーを追加するための出発点が異なっていますが、残りの手順は以下の手順と同じです。

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a>ダッシュボード ビューで 1 人ずつユーザーを追加する

:::image type="content" source="../../media/classic-admin-center.png" alt-text="スクリーンショット: 管理センターのダッシュボード ビュー":::

::: moniker range="o365-worldwide"

1. <https://admin.microsoft.com> で管理センターに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。

::: moniker-end 

2. [**ユーザー**]  >  [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。
3. [**基本設定**] ウィンドウにユーザーの基本情報を入力し、[**次へ**] を選択します。
    - [**名前**] 姓、名、表示名、ユーザー名を入力します。
    - [**ドメイン**] ユーザーのアカウントのドメインを選択します。たとえば、ユーザー名が Jakob、そのドメインが contoso.com の場合、「jakob@contoso.com」と入力してサインインします。
    - [**パスワードの設定**] ユーザー用のパスワードとして、自動生成されたパスワードを使用するのか独自の強力なパスワードを作成するのかを選択します。
    - ユーザーは、90 日後にパスワードを変更する必要があります。または、[**初回サインイン時にこのユーザーにパスワードの変更を要求する**] を選択することもできます。
    - ユーザーが追加されたときに、パスワードをメールで送信するかどうかを選択します。
4. [**製品ライセンスの割り当て**] ウィンドウで、ユーザーの場所と適切なライセンスを選択します。 利用可能なライセンスがない場合でも、ユーザーを追加し、追加のライセンスを購入できます。 [**アプリ**] を展開し、アプリを選択または選択解除して、ユーザーにライセンスが付与されるアプリを制限します。 **[次へ]** を選択します。
5. [**オプションの設定**] ウィンドウで、このユーザーを管理者にする場合は [**役割**] を展開します。ユーザーに関する追加情報を入力する場合は、[**プロファイル情報**] を展開します。
6. [**次へ**] を選択し、新しいユーザーの設定を確認し、必要に応じて変更を行い、[**追加の完了**] を選択し、**[閉じる]** をクリックします。

## <a name="add-a-user-in-the-admin-simplified-view"></a>管理者簡易ビューでユーザーを追加する

管理センターにこのページが表示されている場合は、**管理者簡易ビュー** が表示されています。 以下の手順に従って、ユーザーを追加します。

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="スクリーンショット: 簡易管理センター ビュー":::

::: moniker range="o365-worldwide"

1. <https://admin.microsoft.com> で管理センターに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。

::: moniker-end 

2. [**別のユーザーのアカウントを作成する**] を選択します。
3. [**ユーザー アカウントの追加**] ページで、サインインに使用する姓名、表示名、ユーザー名を入力します。
4. [**最大 5 つのメール アドレス...**] テキスト ボックスにユーザーのメール アドレスを追加します。 これにより、新しいユーザーは Microsoft 365 サービスにサインインするために必要な情報を確実に取得できます。
5. この情報を保存する場合は、[**ユーザーの追加**] と [**サインイン情報のダウンロード**] を選択します。

## <a name="add-multiple-users-at-the-same-time"></a>複数のユーザーを同時に追加する

複数のユーザーを同時に追加するには、次のいずれかの方法を使用します。

- **ユーザーをまとめて追加するには、スプレッドシートを使用します。** 「[同時に複数のユーザーを追加する](../../enterprise/add-several-users-at-the-same-time.md)」を参照してください。
- **アカウントの追加とライセンスの割り当てを自動化します。** 「[Microsoft 365 PowerShell を使用したユーザー アカウントの作成](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md)」を参照してください。この方法は、Windows PowerShell コマンドレットについて詳しい知識のある場合に選んでください。
- **ActiveDirectory を使用している場合** [Microsoft 365 のディレクトリ同期を設定します](../../enterprise/set-up-directory-synchronization.md)。Azure AD Connect ツールを使用し、Microsoft 365 で Active Directory ユーザー アカウント (およびその他の Active Directory オブジェクト) を複製します。同期では、ユーザー アカウントのみが追加されます。同期されているユーザーがメールとその他の Office アプリを使用するには、そのユーザーにライセンスを割り当てる必要があります。
- **Exchange Server から移行する場合** 「[複数のメール アカウントを Office 365 に移行する方法](/Exchange/mailbox-migration/mailbox-migration)」を参照してください。 カットオーバー、段階的方法、またはハイブリッド Exchange による方法のいずれかを使って、複数のメールボックスを Microsoft 365 に移行するときは、移行の一部としてユーザーが自動的に追加されます。 移行では、ユーザー アカウントのみが追加されます。 ユーザーがメールとその他の Office アプリを使用するには、そのユーザーにライセンスを割り当てる必要があります。 ユーザーにライセンスを割り当てない場合、30 日間の猶予期間が過ぎるとユーザーのメールボックスが無効になります。 Microsoft 365 管理センターで[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)方法を確認してください。

## <a name="next-steps"></a>次の手順

ユーザーを追加すると、Microsoft からメール通知が届きます。 メールには、ユーザーが Microsoft 365 にサインインするための Microsoft 365 のユーザー ID とパスワードが含まれています。 新しいパスワードは、通常のプロセスを使用して通知してください。 新しいユーザーと「[従業員のクイック スタート ガイド](../setup/employee-quick-setup.md)」を共有し、ユーザーが「[PC または Mac に Office アプリをダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 に新しい従業員を追加する](add-new-employee.md) (記事)\
[同時に複数のユーザーを Microsoft 365 に追加する](../../enterprise/add-several-users-at-the-same-time.md) (記事)\
[Microsoft 365 のユーザーを復元する](restore-user.md) (記事)\
[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)(記事)\
[組織からユーザーを削除する](delete-a-user.md) (記事)
