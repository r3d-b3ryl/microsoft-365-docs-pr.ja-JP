---
title: 組織内の Power BI
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
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: 組織のユーザー Power BIこのビジネス分析サービスを使用する方法について詳しくは、こちらをご覧ください。
ms.openlocfilehash: 5301d3cd6b10101543741637014455aa2b2a207a
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58566954"
---
# <a name="power-bi-in-your-organization"></a>組織内の Power BI

このページでは、組織のユーザーが Power BI を使う方法と、組織でこのサービスを取得する手順を制御する方法について説明します。

## <a name="what-is-power-bi"></a>Power BI とは

Microsoft Power BI は、直感的な新しい方法でデータの可視化、発見の共有、共同作業を実現します。 詳細については、[Power BI Web サイト](https://powerbi.microsoft.com/en-us/)を参照してください。
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>国内Power BI、業界固有のコンプライアンス要件を満たしているか。

コンプライアンスの詳細についてはPower BI Microsoft Trust Center[を参照してください](https://go.microsoft.com/fwlink/?LinkId=785324)。
  
## <a name="how-do-users-sign-up-for-power-bi"></a>ユーザーが Power BI にサインアップする方法

管理者であるユーザーは、[Power BI Web サイト](https://powerbi.microsoft.com/en-us/)を通じて Power BI にサインアップできます。 また、アプリの [サービスの購入] ページからサインアップMicrosoft 365 管理センター。 管理者が Power BI にサインアップすると、アクセス権が必要なユーザーにユーザー サブスクリプション ライセンスを割り当てることができます。
  
また、組織の個々のユーザーは、[Power BI Web サイト](https://powerbi.microsoft.com/en-us/)を通じて Power BI にサインアップできる場合もあります。 組織のユーザーが Power BI にサインアップする場合、そのユーザーには Power BI ライセンスが自動的に割り当てられます。
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>組織の個々のユーザーがサインアップする方法

組織のユーザーには、以下のように 3 種類のシナリオが考えられます。
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-a-microsoft-365-account"></a>シナリオ 1: 組織に既に既存のMicrosoft 365環境が存在し、ユーザーが既存の Power BIアカウントをMicrosoft 365します。

このシナリオでは、テナント (たとえば、contoso.com) 内で、ユーザーには職場や学校のアカウントが既にあり、まだ Power BI を使っていない場合、マイクロソフトが単にそのアカウントのプランをライセンス認証することになります。ユーザーには、Power BI サービスの使い方が自動的に通知されます。
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-a-microsoft-365-account"></a>シナリオ 2: 組織に既存の Microsoft 365環境が存在し、ユーザーが Power BIアカウントを持Microsoft 365はありません。

このシナリオでは、ユーザーは組織のドメイン (contoso.com など) に電子メール アドレスを持っていますが、Microsoft 365 アカウントを持っていません。 この場合、ユーザーは Power BI にサインアップすることができ、自動的にアカウントが割り当てられます。 この手順で、ユーザーは Power BI サービスにアクセスできるようになります。 たとえば、Nancy という名前の従業員が自分の仕事用メール アドレス (Nancy@contoso.com など) を使用してサインアップした場合、Microsoft は自動的に Contoso Microsoft 365 環境で Nancy をユーザーとして追加し、そのアカウントの Power BI をアクティブにします。
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a>シナリオ 3: 組織にメール ドメインにMicrosoft 365環境はありません。

組織がサービスを利用するために必要な管理Power BI。
  
> [!IMPORTANT]
> 組織にメール ドメインが複数あり、すべてのメール アドレスの拡張子を同じテナントに含める場合は、ユーザーがプライマリ テナントを作成する前に、そのテナントにすべてのメール アドレス ドメインを追加します。 テナントが作成された後で、ユーザーをテナント間で自動的に移動する方法は、サポートされていません。 このプロセスの詳細については、「複数のドメインがある場合、ユーザーが追加されるテナントを制御できますか[?」](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to)および「Add a domain to Office 365 online」[を参照](../setup/add-domain.md)してください。
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>組織側での現在のユーザー ID の管理方法は、どのように変わりますか?

組織に既存の環境が既に存在Microsoft 365、組織内のすべてのユーザーにアカウントMicrosoft 365がある場合、ID 管理は変更されません。
  
組織に既に既存の Microsoft 365 環境がありますが、組織内のすべてのユーザーが Microsoft 365 アカウントを持っている場合は、テナントにユーザーを作成し、ユーザーの仕事または学校の電子メール アドレスに基づいてライセンスを割り当てる必要があります。 これは、特定の時間に管理するユーザー数は、組織内のユーザーが当該サービスにサインアップするに従って増えていくことを表しています。
  
ディレクトリをオンプレミスで管理しており、Active Directory フェデレーション サービス (AD FS) を使っている場合、マイクロソフトはテナントにユーザーを追加しません。テナントに参加しようとするユーザーは、組織の管理者に連絡するように求めるメッセージを受信します。
  
組織にメール ドメインに接続Microsoft 365環境がない場合、ID の管理方法に変更はありません。 ユーザーは、クラウドのみを使用する新しいユーザー ディレクトリに追加され、組織の管理者はテナントの管理者としての役割を引き継いで、ユーザーを管理できるようになります。
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>ユーザー用にマイクロソフトによって作成されたテナントを管理するためのプロセス

Microsoft によってテナントが作成されたら、次の手順に従って、そのテナントが自分の管理対象であることを宣言して管理できます。
  
1. テナントに参加するには、管理するテナントのドメインと同じメール アドレス ドメインを使って [Power BI にサインアップ](https://go.microsoft.com/fwlink/?LinkId=522448)します。たとえば、contoso.com というテナントが作成された場合は、@contoso.com で終わるメール アドレスを使って、テナントに参加する必要があります。

1. ドメインの所有者を検証して管理者コントロールを宣言します。テナントに参加したら、ドメインの所有者を検証して、自分自身を管理者の役割に昇格させることができます。この操作を行うには、以下の手順に従います。

::: moniker range="o365-worldwide"

3. <a href="https://admin.microsoft.com" target="_blank">https://admin.microsoft.com</a> にアクセスします。

::: moniker-end

::: moniker range="o365-germany"

3. <a href="https://portal.office.de" target="_blank">https://portal.office.de</a> に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

3. <a href="https://portal.partner.microsoftonline.cn" target="_blank">https://portal.partner.microsoftonline.cn</a> に移動します。

::: moniker-end

4. 左上にあるアプリ起動ツールのアイコンを選択して、**[管理]** をクリックします。

    ![管理アプリが強調表示されたアプリ 起動ツール。](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. [管理者になる] ページの **手順を** 読み、[はい] を選択 **します。管理者になる必要があります**。

    > [!NOTE]
    >  このオプションが表示されない場合は、既に管理者が配置されています。
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a>複数のドメインがある場合、ユーザーが追加されるテナントを制御できますか?

何の操作も行わない場合、テナントはユーザーのメール ドメインとサブドメインごとに作成されます。
  
メール アドレスの拡張子に関係なく、すべてのユーザーを同じテナントに入れたい場合は、次のようにします。
  
- 目的のテナントをあらかじめ作成しておくか、または既存のテナントを使って、1 つにまとめたい既存のドメインとサブドメインを目的のテナントに追加します。この操作で、それらのドメインおよびサブドメインで終わるメール アドレスを持つすべてのユーザーは、サインアップ時に目的のテナントに自動的に参加するようになります。

> [!IMPORTANT]
> テナントが作成された後にユーザーをテナント間で自動的に移動する仕組みは、サポートされていません。 1 つのテナントにドメインを追加する方法Microsoft 365、「ドメインをドメインに追加する」[をOffice 365。](../setup/add-domain.md)

> [!IMPORTANT]
> テナントの管理に関する詳細とガイダンスについては、「管理とは[」をPower BIしてください](/power-bi/service-admin-administering-power-bi-in-your-organization)。
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a>ユーザーが既存のテナントに参加するのを防ぐ方法

ユーザーが既存のテナントに参加するのを防ぐため、管理者として実行できる手順があります。 ユーザーがテナントに参加するのをブロックすると、ユーザーのサインイン試行は失敗し、組織の管理者に連絡する指示が表示されます。以前にライセンスの自動配布を既に無効にしている場合は、このプロセスを繰り返す必要があります (たとえば、学生、教職員、およびスタッフのOffice 365 Educationなど)。
  
これらの手順では、Windows PowerShell を使う必要があります。 Windows PowerShell を使い始める場合は、「[PowerShell ファースト ステップ ガイド](/powershell/scripting/overview)」を参照してください。
  
次の手順を実行するには、V2 PowerShell モジュールの最新の 64 ビット バージョンをインストールAzure Active Directory[する必要があります](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5)。
  
リンクを選択したら、[**実行**] を選択して、インストーラー パッケージを実行します。
  
**テナントの自動参加を無効にする**: 新規ユーザーが管理対象テナントに参加できないようにするには、次に示す Windows PowerShell コマンドを使います。
  
新規ユーザーに対してテナントの自動参加を無効にする場合:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
新規ユーザーに対してテナントの自動参加を有効にする場合:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> このブロックの設定で、組織の新しいユーザーは Power BI にサインアップできなくなります。 組織内の新しいサインアップを無効にする前に Power BI にサインアップしていたユーザーは、それ以降もライセンスを与えられたままになります。 以前に[サービス](#how-do-i-remove-power-bi-for-users-that-already-signed-up)にサインアップしたユーザーの Power BI へのアクセスを削除する方法については、「既にサインアップしたユーザーの Power BI を削除する方法」を参照してください。
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a>ユーザーに既存のテナントへの参加を許可する方法

To allow users to join your tenant, run the opposite command as described in the question above:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>テナントでブロックが設定されているかどうかを確認する方法を教えてください

次の PowerShell スクリプトを使用します:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>既存のユーザーが Power BI を使い始めることを防ぐ方法

**ライセンスの自動配布を無効にする**: 既存ユーザーに対してライセンスの自動配布を無効にするには、次に示す Windows PowerShell スクリプトを使用します。 以前にライセンスの自動配布を既に無効にしている場合は、このプロセスを繰り返す必要があります (たとえば、学生、教職員、およびスタッフのOffice 365 Educationなど)。
  
既存ユーザーに対してライセンスの自動配布を無効にする場合:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
既存ユーザーに対してライセンスの自動配布を有効にする場合:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> *AllowAdHocSubscriptions* フラグは、ユーザーが Azure Rights Management Service にサインアップする機能など、組織内のいくつかのユーザー機能を制御するために使用されます。 このフラグを変更すると、これらのすべての機能に影響が及びます。
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>既存のユーザーが Power BI にサインアップできるようにする方法

To allow your existing users to sign up for Power BI, run the opposite command as described in the question above:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>既にサインアップしたユーザーの Power BI を削除する方法

ユーザーが Power BI にサインアップしたが、Power BI へのアクセス権を持たなくなった場合は、そのユーザーの Power BI ライセンスを削除できます。
  
::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

::: moniker range="o365-germany"

 1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

2. ライセンスを削除するユーザーを見つけて、そのユーザーの名前を選択します。

3. [ライセンスと **アプリ] タブで****、[Microsoft** のライセンスとアプリ] チェック Power BIをオフにします。

4. [**変更の保存**] を選択します。

## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>新しいユーザーがテナントに参加したことは、どのようにしてわかりますか?

このプログラムの一員として、あなたのテナントに参加したユーザーには、一意のライセンスが割り当てられます。このライセンスは、管理者ダッシュボードの [アクティブ ユーザー] ウィンドウでフィルタリングできます。
  
この新しいビューを作成するには、管理センターで、「カスタム ユーザー ビューを作成する [」の手順に従います](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view)。 [割 **り当てられた製品ライセンス] で****、[Microsoft ライセンス] をPower BI。** 新しいビューが作成されると、このプログラムに登録したテナント内のすべてのユーザーが表示されます。
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>事前に準備しておく必要のあるものが、他にもありますか?

パスワード再設定の依頼が増えることがあります。 このプロセスの詳細については、「[ユーザーのパスワードを再設定する](../add-users/reset-passwords.md)」を参照してください。
  
管理センターの標準プロセスを使用して、テナントからユーザーを削除できます。 ただし、ユーザーが組織のアクティブなメール アドレスをまだ持っている場合、すべてのユーザーの参加がブロックされていない限り、そのユーザーは再び参加することができます。
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a>Microsoft サービスのライセンスが 100 万件Power BIテナントに表示された理由

対象となる組織では、組織内のユーザーが Microsoft Power BI サービスを使用する資格を持ち、これらのライセンスはテナント内の新しいユーザーのPower BI容量を表します。 これらのライセンスの料金は発生しません。 ユーザーが自分で Power BI へのサインアップを許可する場合は、サインアップ プロセスが完了すると、これらの利用可能な無料ライセンスの 1 つが割り当てられます。 これらのライセンスを管理センターからユーザー自身に割り当てすることもできます。
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>料金はかかりますか? ライセンス料は請求されますか?

これらのライセンスは Power BI の無料版で使えます。 機能を拡張したい場合は、Power BI Pro 版を参照してください。
  
## <a name="why-1-million-licenses"></a>ライセンス数が 100 万件なのは、なぜですか?

大多数の組織がユーザーにこの利点を提供するのに十分なライセンスを持つ十分な大きな数を選択しました。
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>100 万件を超えるライセンスが必要な場合は、どうしたらよいですか?

追加のライセンスが必要な場合は、マイクロソフトのアカウント担当者に問い合わせてください。