---
title: Microsoft 365 Business Standard のセットアップ
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
search.appverid:
- MET150
- MOE150
- BEA160
description: Microsoft 365 Business Standard を購入するときに、所有するドメインを使用するか、サインアップ時に購入するかを選択することができます。
ms.openlocfilehash: f9dc7c45256e87a1482cb7d39cdba65b07c7502ad15f6a0ba300325f96d053e2
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53821477"
---
# <a name="set-up-microsoft-business-standard"></a>Microsoft Business Standard をセットアップする



## <a name="add-your-domain-to-personalize-sign-in"></a>ドメインを追加してサインインをカスタマイズする

Microsoft 365 Business Standard を購入するときに、所有するドメインを使用するか、サインアップ時に購入するかを選択することができます。

- サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[[ユーザーを追加してライセンスを割り当てる](#add-users-and-assign-licenses)] に移動することができます。

1. グローバル管理者の資格情報を使用して、[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。 

2. [**セットアップに移動**] を選択して、ウィザードを開始します。

3. [**Office アプリのインストール**] ページでは、オプションで自分のコンピューターにアプリをインストールすることができます。
    
4. **ドメインの追加** ステップで、使用するドメイン名 (Contoso.com など) を入力します。

    > [!IMPORTANT]
    > サインアップ時にドメインを購入した場合、ここでは **ドメインの追加** ステップは表示されません。[ユーザーの追加](#add-users-and-assign-licenses) に進んでください。

    
4. ウィザードの手順に従って[任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)し、ドメインの所有を確認します。 ドメイン ホストがわかっている場合は、「[Microsoft 365 にドメインを追加する](/microsoft-365/admin/setup/add-domain)」も参照してください。

    ご利用のホスティング プロバイダーが GoDaddy または [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) を有効にした別のホストである場合、プロセスは簡単です。サインインし、お客様に代わって Microsoft が認証するよう自動的に求められます。

    ![GoDaddy の [Confirm Access] (アクセスの確認) ページで、[承認] を選択します。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>ユーザーを追加してライセンスを割り当てる

ウィザードでユーザーを追加することもできますが、管理センターで[後からユーザーを追加](../add-users/add-users.md)することもできます。 さらに、ローカル ドメイン コントローラーを持っている場合には、[Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) を使用してユーザーを追加することもできます。

## <a name="add-users-in-the-wizard"></a>ウィザードでユーザーを追加する

ウィザードで追加したユーザーには、Microsoft 365 Business Standard ライセンスが自動的に割り当てられます。

1. Microsoft 365 Business Basic のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、すぐにこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。

2. ユーザーを追加した後、資格証明書をそれらの新規ユーザーに共有するオプションが提供されます。それらをプリントアウトや電子メールで通知、またはダウンロードすることができます。

## <a name="connect-your-domain"></a>ドメインを接続する

> [!NOTE]
> .onmicrosoft ドメインの使用を選択した場合、またはユーザーの設定に Azure AD Connect を使用した場合、このステップは表示されません。
  
サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。
  
1. セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。 表示されない場合には、[任意のドメイン レジストラーで Office 365 をセットアップするためにネームサーバーを変更](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)します。 

    - 既存の DNS レコード (たとえば、既存の Web サイト) を持っているのに、DNS ホストが [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) に対して有効になっている場合には、[**レコードを追加してもらう**] を選択します。 [**オンライン サービスの選択**] ページで、すべて規定値のまま [**次へ**] を選択し、DNS ホストのページで [**承認**] を選択します。
    - 他の DNS ホストとの間に既存の DNS レコードがある場合 (Domain Connect では有効になっていません)、既存のサービスが接続されたままになっていることを確認するために、自分の DNS レコードを管理したいと思うかもしれません。詳しくは [ドメインの基礎](/office365/admin/get-help-with-domains/dns-basics) を参照してください。

2. ウィザードの手順に従えば、メールやその他のサービスが設定されます。

    サインアップ プロセスが完了すると、管理センターに移動します。ここでは、ウィザードを使用して Office アプリのインストール、ドメインの追加、ユーザーの追加、ライセンスの割り当てを行うことができます。 初期セットアップが完了したら、管理センターの [**セットアップ**] ページを使用して、サブスクリプションに付属するサービスの設定と構成を継続できます。

    セットアップ ウィザードおよび管理センターの **[セットアップ]** ページの詳細については、「[セットアップ ウィザードと [セットアップ] ページの違い](o365-setup-wizard-and-setup-page.md)」を参照してください。

## <a name="finish-setting-up"></a>セットアップを完了する

### <a name="set-up-outlook-for-email"></a>Outlook をメール用にセットアップする

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
  
### <a name="use-a-public-website"></a>一般向け Web サイトを使用する

Microsoft 365 には、ビジネスに使用するための一般向け Web サイトは含まれていません。 Web サイトをセットアップする場合は、GoDaddy や WIX などの Microsoft パートナーの使用を検討してください。
  
1. 管理センターから、[**リソース**] に移動し、[**一般向け Web サイト**] を選択します。

2. いずれかのオプションの [**詳細情報**] を選択して、Web サイト パートナーにサインアップし、ツールを使用してサイトをセットアップおよびデザインします。

## <a name="watch-create-your-business-website"></a>注目 : ビジネス用のWebサイト を作成しましょう。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a>関連コンテンツ

[Web サイトを作成](../../business-video/create-web-site.md) (ビデオ)\
[一般法人向け Microsoft 365](../../business-video/index.yml) (リンク ページ)
