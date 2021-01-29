---
title: Microsoft 365 Business Premium のセットアップ
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: ドメインとユーザーの追加、セキュリティ ポリシーの設定など、Microsoft 365 Business Premium のセットアップ手順について説明します。
ms.openlocfilehash: e7ebe179c67077dc71ae4873b0711d0e810c701a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044732"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>セットアップ ウィザードで Microsoft 365 Business Premium をセットアップする

Microsoft 365 Business Premium のセットアップの概要については、このビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>ドメイン、ユーザー、およびポリシーの設定を追加する

When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or purchase one during the [sign-up](sign-up.md).

- サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[[ユーザーを追加してライセンスを割り当てる](#add-users-and-assign-licenses)] に移動することができます。

### <a name="add-your-domain-to-personalize-sign-in"></a>ドメインを追加してサインインをカスタマイズする

1. グローバル管理者の資格情報を使用して、[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。 

2. [**セットアップに移動**] を選択して、ウィザードを開始します。

    ![[セットアップに移動] を選択します。](../media/gotosetupinadmincenter.png)

3. [**Office アプリのインストール**] ページでは、オプションで自分のコンピューターにアプリをインストールすることができます。
    
4. **ドメインの追加** ステップで、使用するドメイン名 (Contoso.com など) を入力します。

    > [!IMPORTANT]
    > サインアップ時にドメインを購入した場合、ここでは **ドメインの追加** ステップは表示されません。 代わりに [[ユーザーの追加](#add-users-and-assign-licenses)] に移動します。

    ![[サインインのカスタマイズ] ページのスクリーンショット。](../media/adddomain.png)

    
4. ウィザードの手順に従って、ドメインを所有している [Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) の DNS ホスティング プロバイダーで DNS レコードを作成します。 ドメイン ホストがわかっている場合は、「[ホスト特有の手順](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)」も参照してください。

    ご利用のホスティング プロバイダーが GoDaddy または [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) を有効にした別のホストである場合、プロセスは簡単です。サインインし、お客様に代わって Microsoft が認証するよう自動的に求められます。

    ![GoDaddy の [Confirm Access] (アクセスの確認) ページで、[承認] を選択します。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>ユーザーを追加してライセンスを割り当てる

ウィザードでユーザーを追加することもできますが、管理センターで[後からユーザーを追加](add-users-m365b.md)することもできます。 さらに、ローカル ドメイン コントローラーを持っている場合には、[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) を使用してユーザーを追加することもできます。

#### <a name="add-users-in-the-wizard"></a>ウィザードでユーザーを追加する

ウィザードで追加したユーザーには、Microsoft 365 Business Premium ライセンスが自動的に割り当てられます。

![ウィザードの [新しいユーザーの追加] ページのスクリーンショット](../media/addnewuserspage.png)

1. Microsoft 365 Business Premium サブスクリプションに既存のユーザーが含まれています (たとえば、Azure AD Connect を使用した場合)、今すぐライセンスを割り当てるオプションが表示されます。 続行して、これらのユーザーにもライセンスを追加します。

2. ユーザーを追加すると、追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。 それらを印刷したり、メールで送信したり、ダウンロードしたりすることができます。

### <a name="connect-your-domain"></a>ドメインを接続する

> [!NOTE]
> .onmicrosoft ドメインの使用を選択した場合、またはユーザーの設定に Azure AD Connect を使用した場合、このステップは表示されません。
  
サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。
  
1. セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。 設定しない場合は、任意のドメイン レジストラーで [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)をセットアップするためにネームサーバーを変更します。 

    - 既存の DNS レコード (たとえば、既存の Web サイト) を持っているのに、DNS ホストが [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) に対して有効になっている場合には、[**レコードを追加してもらう**] を選択します。 [**オンライン サービスの選択**] ページで、すべて規定値のまま [**次へ**] を選択し、DNS ホストのページで [**承認**] を選択します。
    - 他の DNS ホストとの間に既存の DNS レコードがある場合 (Domain Connect では有効になっていません)、既存のサービスが接続されたままになっていることを確認するために、自分の DNS レコードを管理したいと思うかもしれません。 詳細については、「[domain basics (ドメインの基本)](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)」を参照してください。

        ![レコード ページをアクティブ化します。](../media/activaterecords.png)

2. ウィザードの手順に従えば、メールやその他のサービスが設定されます。

### <a name="protect-your-organization"></a>組織を保護する 

ウィザードで設定したポリシーは、[すべてのユーザー] という名前の [セキュリティ グループに自動的](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)*に適用されます*。 管理センターでポリシーを割り当てる追加のグループを作成することもできます。

1. 高度な **サイバー** 脅威からの保護を強化する場合は、Office [365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) が Office アプリのファイルとリンクをスキャンできる既定値を受け入れてお勧めします。

    ![[保護の強化] ページのスクリーンショット。](../media/increasetreatprotection.png)


2. [機密データの漏えいを防止する] ページで、既定の設定を受け入れて Office 365 データ損失防止 (DLP) を有効にし、Office アプリの機密データを追跡し、組織外でこれらを誤って共有しないようにします。

3. [ **モバイル 用 Office** のデータの保護] ページで、モバイル アプリの管理をオンのままにして、設定を展開して確認し、[モバイル アプリ管理ポリシーの作成] **を選択します**。

    ![Screenshot of Protect data in Office for mobile page.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Windows 10 PC をセキュリティで保護する

左側のナビゲーションで [セットアップ] を選択し、[サインインとセキュリティ] で **[Windows 10 コンピューターのセキュリティ保護] を選択します**。 [表示 **] を** 選択して開始します。 詳 [しい手順については、Windows 10 コンピューターの](secure-win-10-pcs.md) セキュリティ保護に関するページをご覧ください。

## <a name="deploy-office-365-client-apps"></a>365 Office アプリを展開する

セットアップ中に Office アプリを自動的にインストールすることを選択した場合、ユーザーが Windows デバイスから Azure AD にサインインすると、アプリは作業資格情報を使用して Windows 10 デバイスにインストールされます。

モバイル iOS Office Android デバイスにインストールするには [、「Microsoft 365 Business Premium](set-up-mobile-devices.md)ユーザー向けモバイル デバイスのセットアップ」を参照してください。

また、個別にOfficeインストールできます。 手順 [についてはOffice PC または Mac にインストールする](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 方法をご覧ください。

## <a name="see-also"></a>関連項目

[一般法人向け Microsoft 365 のトレーニング ビデオ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
