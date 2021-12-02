---
title: 新規ドメインまたは既存のドメインを使用して Microsoft 365 Business Standard を設定する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- BEA160
description: Microsoft 365 Business Standard を購入するときに、所有するドメインを使用するか、サインアップ時に購入するかを選択することができます。
ms.openlocfilehash: 9893084ad351bd6d1195df9f066f3a540af5ded2
ms.sourcegitcommit: cd3f5e3b7fea37fdcd8c811d01afd60ea68301ca
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2021
ms.locfileid: "61254443"
---
# <a name="set-up-microsoft-365-business-standard-with-a-new-or-existing-domain"></a>新規ドメインまたは既存のドメインを使用して Microsoft 365 Business Standard を設定する

Microsoft 365 Business Standard を購入するときに、所有するドメインを追加するか、購入するかを選択することができます。 [Microsoft 365 Business Standard サブスクリプションのサインアップ](../simplified-signup/signup-business-standard.md)をチェックアウトします。

この記事では、既に所有している既存のドメインを追加するか、または新しいドメインを購入する手順について説明します。 サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[[ユーザーを追加してライセンスを割り当てる](#add-users-and-assign-licenses)] に移動することができます。

## <a name="before-you-begin"></a>始める前に

ドメインを追加、変更、または削除するには、グローバル管理者である必要があります。 詳細については、「[管理者の役割について](../add-users/about-admin-roles.md)」を参照してください。

> [!IMPORTANT]
> Microsoft 365 for business にサインアップするユーザー (通常はビジネス所有者) は、自動的に組織の技術管理者になります。 Microsoft 365 のサービスを管理するサポートが必要な場合は、他のユーザーを管理者として追加することができます。 詳細については、「[管理者を追加する](../../business-video/add-admin.md)」をチェックアウトしてください。

## <a name="watch-add-an-existing-domain-to-your-microsoft-365-business-standard-subscription"></a>注目: 既存のドメインを Microsoft 365 Business Standard サブスクリプションに追加します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxApu]

## <a name="steps-add-an-existing-domain-to-your-microsoft-365-business-standard-subscription"></a>手順: 既存のドメインを Microsoft 365 Business Standard サブスクリプションに追加します。

1. Microsoft 365 Business Standard サインアップの **[サインインする方法]** ページで、**新しいビジネス メール アカウントを作成する (詳細設定)** を選択します。

2. [**Office アプリのインストール**] ページでは、オプションで自分のコンピューターにアプリをインストールすることができます。

3. **ドメインの追加** ステップで、使用するドメイン名 (Contoso.com など) を入力します。

    > [!IMPORTANT]
    > サインアップ時にドメインを購入した場合、ここでは **ドメインの追加** ステップは表示されません。[ユーザーの追加](#add-users-and-assign-licenses) に進んでください。

4. 手順に従って[任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)し、ドメインの所有を確認します。 ドメイン ホストがわかっている場合は、「[Microsoft 365 にドメインを追加する](/microsoft-365/admin/setup/add-domain)」も参照してください。

    ご利用のホスティング プロバイダーが GoDaddy または [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) を有効にした別のホストである場合、プロセスは簡単です。サインインし、お客様に代わって Microsoft が認証するよう自動的に求められます。

    ![GoDaddy の [Confirm Access] (アクセスの確認) ページで、[承認] を選択します。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>ユーザーを追加してライセンスを割り当てる

ウィザードでユーザーを追加することもできますが、管理センターで[後からユーザーを追加](../add-users/add-users.md)することもできます。

追加したユーザーには、Microsoft 365 Business Standard ライセンスが自動的に割り当てられます。

1. Microsoft 365 Business Basic のサブスクリプションに既存ユーザーがいる場合、すぐにこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。

2. ユーザーを追加した後、資格証明書をそれらの新規ユーザーに共有するオプションが提供されます。それらをプリントアウトや電子メールで通知、またはダウンロードすることができます。

## <a name="connect-your-domain"></a>ドメインを接続する
  
サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。
  
1. セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。 表示されない場合には、[任意のドメイン レジストラーで Office 365 をセットアップするためにネームサーバーを変更](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)します。

    - 既存の DNS レコード (たとえば、既存の Web サイト) を持っているのに、DNS ホストが [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) に対して有効になっている場合には、[**レコードを追加してもらう**] を選択します。 [**オンライン サービスの選択**] ページで、すべて規定値のまま [**次へ**] を選択し、DNS ホストのページで [**承認**] を選択します。
    - 他の DNS ホストとの間に既存の DNS レコードがある場合 (Domain Connect では有効になっていません)、既存のサービスが接続されたままになっていることを確認するために、自分の DNS レコードを管理したいと思うかもしれません。詳しくは [ドメインの基礎](/office365/admin/get-help-with-domains/dns-basics) を参照してください。

2. ウィザードの手順に従えば、メールやその他のサービスが設定されます。

    サインアップ プロセスが完了すると、管理センターに移動します。ここでは、ウィザードを使用して Office アプリのインストール、ドメインの追加、ユーザーの追加、ライセンスの割り当てを行うことができます。 初期セットアップが完了したら、管理センターの [**セットアップ**] ページを使用して、サブスクリプションに付属するサービスの設定と構成を継続できます。

    セットアップ ウィザードおよび管理センターの **[セットアップ]** ページの詳細については、「[セットアップ ウィザードと [セットアップ] ページの違い](o365-setup-wizard-and-setup-page.md)」を参照してください。

## <a name="watch-set-up-business-email-with-a-new-domain"></a>注目: 新しいドメインを使用してビジネス メールを設定する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyVVA]

## <a name="steps-set-up-business-email-with-a-new-domain"></a>手順: 新しいドメインを使用してビジネス メールを設定する

1. Microsoft 365 Business Standard サインアップの **[サインインする方法]** ページで、**新しいビジネス メール アカウントを作成する (詳細設定)** を選択します。

2. 手順に従って新しいドメインを購入し、使用するドメイン名 (contoso.com など) を入力します。 ドメインの購入が完了したら、[ユーザーとライセンスを追加](../add-users/add-users.md)すると、管理センターで Office アプリをインストールできます。

## <a name="finish-setting-up"></a>セットアップを完了する

以下の手順に従って、Outlook、Teams、OneDrive、および Web サイトを設定します。

### <a name="step-set-up-outlook-for-email"></a>手順: Outlook をメール用にセットアップする

1. Windows の [スタート] メニューで、[Outlook] を検索し、選択します。

    (Mac を使用している場合は、ツールバーから Outlook を開くか、または Finder を使用して Outlook を検索します)。

    Outlook をインストールしたばかりの場合は、[ようこそ] ページで、[**次へ**] を選択します。

2. [**ファイル**] \> [**情報**] \> [**アカウントの追加**] の順に選択します。

3. Microsoft のメール アドレスを入力して、**[接続]** を選択します。

## <a name="watch-set-up-outlook-for-email"></a>注目 : Outlook を電子メール用にセットアップして下さい。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
詳細については、「[メール用に Outlook をセットアップする](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)」を参照してください。
  
### <a name="import-email"></a>メールをインポートする

別のメール アカウントで Outlook を使用していた場合は、以前のメール、予定表、連絡先を新しい Microsoft アカウントにインポートできます。
  
1. **古いメールをエクスポートする**

    Outlook で、[**ファイル**] \> [**開く&amp;エクスポート**] \> [**インポート/エクスポート**] の順に選択します。

    [**ファイルにエクスポート**] を選択し、手順に従って Outlook データ ファイル (.pst) およびすべてのサブフォルダーをエクスポートします。

2. **古いメールをインポートする**

    Outlook で、[**ファイル**] \> [**開く&amp;エクスポート**] \> [**インポート/エクスポート**] を再度選択します。

    今度は、[**他のプログラムまたはファイルからのインポート**] を選択し、古いメールをエクスポートしたときに作成したバックアップ ファイルを手順に従ってインポートします。

## <a name="watch-import-and-redirect-email"></a>注目 : 電子メールをインポートして再配置しましょう。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
詳細については、「[Outlook でメールをインポートする](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)」を参照してください。

また、Exchange 管理センターを使用して、すべてのユーザーのメールをインポートすることもできます。 詳細については、「[複数のメール アカウントを移行する](/Exchange/mailbox-migration/mailbox-migration)」を参照してください。

## <a name="set-up-microsoft-teams-and-onedrive-for-business"></a>Microsoft Teams と OneDrive for business の設定

タスク バーで OneDrive クラウド アイコンを選択し、手順に従って新しい OneDrive for Business フォルダーにファイルを移動します。**[次へ]** を選択して、Microsoft Teams を設定します。

1. Microsoft Teams を開き、プロファイル アイコンを選択して、**[職場または学校アカウントを追加する]** を選択します。 手順に従って、新しいアカウントを Teams に追加します。

## <a name="use-a-public-website"></a>一般向け Web サイトを使用する

Microsoft 365 には、ビジネスに使用するための一般向け Web サイトは含まれていません。 Web サイトをセットアップする場合は、GoDaddy や WIX などの Microsoft パートナーの使用を検討してください。
  
1. 管理センターから、[**リソース**] に移動し、[**一般向け Web サイト**] を選択します。

2. いずれかのオプションの [**詳細情報**] を選択して、Web サイト パートナーにサインアップし、ツールを使用してサイトをセットアップおよびデザインします。

## <a name="watch-create-your-business-website"></a>注目 : ビジネス用のWebサイト を作成しましょう。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="invite-users-to-join-your-subscription-and-organization"></a>サブスクリプションと組織に参加するようにユーザーを招待する

組織を設定したら、他のユーザーを Microsoft 365 ビジネス サブスクリプションに招待できます。 サブスクリプションのすべての機能にアクセスできます。

[ユーザーをサブスクリプションに招待する](../simplified-signup/admin-invite-business-standard.md)

以下の記事の手順に従って組織とサブスクリプションに参加できることをユーザーに知らせてください。

- [メールの招待を受け入れる](../simplified-signup/user-invite-business-standard.md)

- [Outlook、Yahoo、Gmail、またはその他のアカウントを使用して招待メールを受け入れる (ユーザー)](../simplified-signup/user-invite-msa-nodomain-join.md)

## <a name="related-topics"></a>関連トピック

[データを Microsoft 365 Business Standard サブスクリプションに移行する](../simplified-signup/migrate-data-business-standard.md)
