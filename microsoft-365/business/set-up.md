---
title: Microsoft 365 Business をセットアップする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business をセットアップする方法について説明します。
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660831"
---
# <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business をセットアップする

開始する前に、「 [Microsoft 365 Business](get-microsoft-365-business.md)を使用してサインアップの詳細を取得する」を参照してください。

セットアップウィザードを使用して[Microsoft 365 Business をセットアップする方法](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1)、およびオンプレミスの Active Directory を使用していない場合について、簡単なビデオを見ることができます。
  

## <a name="overview"></a>概要

セットアップ手順のほとんどはセットアップウィザードで行うことができますが、その他のオプションも表示されます。

1. [ドメインを追加する](#add-your-domain-to-personalize-sign-in)([サインアップ](sign-up.md)中にドメインを購入した場合、この手順は既に完了しています。)
2. ユーザーを追加します。 これは、次の3つの方法のいずれかで行うことができます。
    - [セットアップウィザード](#add-users-in-the-wizard)で。
    - オンプレミスの Active directory を使用している場合は、ディレクトリ同期を使用して、 [AZURE AD Connect を使用してユーザーを追加](#add-users-by-using-azure-ad-connect)します。
    - 後で管理センターで[ユーザーを追加](add-users-m365b.md)することもできます。
3. セキュリティポリシーを設定し、デバイスを構成します。 これは、次の3つの方法のいずれかで行うことができます。
    - [セットアップウィザード](#set-up-policies-in-the-wizard)で。  
    - [管理センター](#modify-or-add-policies-in-the-admin-center)で。
    - [Intune 管理センター](https://docs.microsoft.com/intune/what-is-device-management)で。
4. Windows 10 デバイスをセットアップして管理します。

    WIndows 10 デバイスを Azure AD に参加させると、すべてのポリシーが適用されます。
    - [セットアップウィザード](#set-up-policies-in-the-wizard)で Windows 10 デバイスの構成を設定します。
    - [新しい Windows 10 デバイス](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device)を Azure AD に参加させる。
    - 既存の[Windows 10 デバイス](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro)を Azure AD に参加させる。
1. Office 365 Business をインストールします。
    - [セットアップウィザード](#set-up-policies-in-the-wizard)を使用して、Windows デバイスに Office を自動的にインストールすることができます。
    - 管理センターから Office を自動的に[インストール](auto-install-or-uninstall-office.md)します。
    - ユーザーが Windows およびデバイス用の[Office アプリをインストール](https://docs.microsoft.com/office365/admin/setup/install-applications)できるようにします。
     
1. 追加のセキュリティを設定します。
    - セットアップウィザードは、デバイスをセキュリティで保護するためのポリシーを追加しますが、データ、アカウント、および電子メールのセキュリティ保護に役立つ[追加のセキュリティ](#additional-security-settings)機能を利用することもできます。 

## <a name="add-your-domain-users-and-set-up-policies"></a>ドメイン、ユーザーを追加して、ポリシーをセットアップする

![をhttps://aka.ms/aboutM365preview指すバナー。](media/m365admincenterchanging.png)

Microsoft 365 Business を購入する場合は、所有しているドメインを使用するか、[サインアップ](sign-up.md)中に購入するかを選択できます。

- サインアップ時に新しいドメインを購入した場合、ドメインはすべてセットアップされており、ユーザーを[追加してライセンスを割り当てる](#add-users-and-assign-licenses)ことができます。

### <a name="add-your-domain-to-personalize-sign-in"></a>サインインを個人用に設定するためにドメインを追加する

1. グローバル管理者の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。 

2. [**ドメインの追加**] を選択してウィザードを開始します。

    ![[ドメインの追加] を選択します。](media/addadomainadmincenter.png)
    
3. ウィザードで、使用するドメイン名 (contoso.com など) を入力します。


    ![[サインインのカスタマイズ] ページのスクリーンショット。](media/personalizesignin.png)

    
4. ウィザードの手順に従って、ドメインを所有していることを確認する[Office 365 用の任意の dns ホスティングプロバイダーで dns レコードを作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)します。 ドメインホストがわかっている場合は、「[ホスト固有の指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)」も参照してください。

    ホスティングプロバイダーが GoDaddy の場合、このプロセスは簡単であり、自動的にサインインして Microsoft に代わって認証を行うように求めるメッセージが表示されます。

    ![[GoDaddy のアクセス確認] ページで、[承認] を選択します。](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>ユーザーを追加して、ライセンスを割り当てる

ウィザードでユーザーを追加することはできますが、[後](add-users-m365b.md)で管理センターでユーザーを追加することもできます。 また、ローカルドメインコントローラーがある場合は、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)を使用してユーザーを追加できます。

#### <a name="add-users-in-the-wizard"></a>ウィザードでユーザーを追加する

ウィザードで追加したユーザーには、Microsoft 365 のビジネスライセンスが自動的に割り当てられます。
ローカルドメインコントローラーがあり、Active Directory を使用している場合は、「 [AZURE AD Connect を使用してユーザーを一時にする方法](#add-users-by-using-azure-ad-connect)」を参照してください。

![ウィザードの [新しいユーザーの追加] ページのスクリーンショット](media/addnewuserspage.png)

1. Microsoft 365 Business のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、今すぐこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。

3. ユーザーを追加すると、追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。 それらを印刷、メール、またはダウンロードできます。

4. 移行のメール メッセージをスキップして、[ **メール メッセージの移行**] ページで [ **次へ**] を選びます。 

    別のメールプロバイダーから移行していて、後でデータをコピーする場合は、[メールと連絡先を Office 365 に移行](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)できます。

#### <a name="add-users-by-using-azure-ad-connect"></a>Azure AD Connect を使用してユーザーを追加する

 Active Directory を使用したローカルドメインコントローラーがある場合は、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)を使用して、ユーザーを Microsoft 365 Business と同期させます。 セットアップウィザードを開始する前に、この手順を完了します。 管理センターでダウンロードできます。

- [**ユーザー** \>の**アクティブユーザー**] に移動して、ページの上部にある省略記号を選択し、[**ディレクトリ同期**] を選択して Azure AD Connect をダウンロードします。

    ![[アクティブなユーザー] ページで、[省略 > Directory snchronization] を選択します。](media/setupdirsync.png)

    > [!IMPORTANT]
    > この方法でユーザーを作成する場合でも、管理センターでライセンスを割り当てる必要があります。

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a>ドメインに参加しているアプリとデバイスへのアクセスを続行する

ドメインに参加しているアプリとデバイスへのアクセスを継続する場合は、次の2つの方法で、これを有効にする方法について以下の記事を参照してください。
  
- [Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする](manage-windows-devices.md)
    - この方法をお勧めします。

- [Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする](access-resources.md)

### <a name="connect-your-domain"></a>ドメインを接続する

> [!NOTE]
> . Onmicrosoft ドメインを使用することを選択した場合、または Azure AD Connect を使用してユーザーを設定した場合は、この手順は表示されません。
  
サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。
  
1. セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。 含まれていない場合は、ネームサーバーを[変更して、任意のドメインレジストラーで Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)をセットアップします。 

    - 既存の DNS レコード (既存の web サイトなど) がある場合は、自分の DNS レコードを管理して、既存のサービスが常に接続していることを確認する必要があります。 詳細については、「[ドメインの基礎](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)」を参照してください。

        ![自分の DNS レコードを管理するドメインページに接続します。](media/connectyourdomainpage.png)

2. ウィザードの手順を実行すると、電子メールとその他のサービスが設定されます。

### <a name="set-up-security-policies-and-device-configurations"></a>セキュリティポリシーとデバイス構成を設定する 

これらのポリシーは、ユーザーのセットに異なるポリシーを割り当てる場合は、ライセンスを付与するすべてのユーザー、またはユーザーのグループに適用されます。

#### <a name="set-up-policies-in-the-wizard"></a>ウィザードでポリシーをセットアップする

ウィザードで設定したポリシーは、*すべてのユーザー*と呼ばれる[セキュリティグループ](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)に自動的に適用されます。

1. [**モバイルデバイスの作業ファイルを保護**する] で、[**デバイスが失われたとき、または盗まれたときに作業ファイルを保護する**] オプションが既定で選択されています。 [**ユーザーがモバイルデバイスで Office ファイルにアクセスする方法を管理**する] をオンにすることもできます。これは推奨されています。

    ![[モバイルデバイスの作業ファイルを保護する] ページのスクリーンショット](media/protectworkfilesondevices.png)

     - **デバイスが紛失または盗難になったときに作業ファイルの保護**を拡張すると、[既定値](protect-work-files-on-lost-or-stolen-device.md)が事前に選択されます。

        ![失われたデバイスでファイルを保護するための既定値のスクリーンショット。](media/protectworkfilesondevicesdefault.png)

    - [ユーザーが**モバイルデバイスで Office ファイルにアクセスする方法を管理**する] を選択し、それを展開すると、[既定値](manage-user-access-on-mobile-devices.md)が表示されます。 セットアップ時に既定値を受け入れて、すべてのユーザーに適用される、Android、iOS、Windows 10 のアプリケーション ポリシーを作成することをお勧めします。 セットアップが完了したら、追加のポリシーを作成できます。

        ![モバイルでの Office ファイルの保護設定のスクリーンショット。](media/useraccessonmobile.png)

2. データとデバイスを保護するための最後の手順では、Windows 10 デバイスをセキュリティで保護するためのポリシーを設定できます。 これらの設定は、ユーザーの Windows 10 が組織に接続すると自動的に適用されます。 **セキュリティで保護された Windows 10 デバイス**を拡張して、[既定値](secure-windows-10-devices.md)を表示および変更できます。
3. Windows 10 デバイスで[Office を自動的にインストール](install-office-on-windows-10-during-setup.md)するように選択することもできます。

    ![Windows 10 デバイス構成ページの設定のスクリーンショット。](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a>管理センターでポリシーを変更または追加する

デバイスとアプリの保護ポリシーを表示および変更する方法、およびユーザーデバイスからデータを削除またはリセットする方法に関するトピックへのリンクは、「 [Microsoft 365 Business の管理](manage.md)」を参照してください。

## <a name="deploy-and-manage-windows-10"></a>Windows 10 を展開して管理する
新しいコンピューターのセットアップ時に、または既存のコンピューターのサインインプロファイルを変更することによって、Azure AD に手動で接続するには、「 [Microsoft 365 Business ユーザーの Windows デバイス](set-up-windows-devices.md)をセットアップする」を参照してください。 

### <a name="use-autopilot-to-set-up-new-devices"></a>自動操縦を使用して新しいデバイスをセットアップする

[Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、ユーザーに対して**新しい**windows 10 デバイスを自動的に事前構成することができますが、これを実行できる[パートナー](https://www.microsoft.com/solution-providers/search)を取得する方が簡単な場合があります。 [Microsoft ストア](https://go.microsoft.com/fwlink/?linkid=874598)に移動して、クラウドテクノロジエキスパートに購入した新しいデバイスのセットアップを依頼することもできます。

### <a name="access-on-premises-resources"></a>オンプレミスのリソースにアクセスする

組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。 「[ドメインに参加している Windows 10 デバイスが Microsoft 365 Business で管理される](manage-windows-devices.md)ようにする」の手順に従って、これを設定します。 この方法は推奨されており、この状態のデバイスはハイブリッド Azure AD 参加デバイスと呼ばれます。

オンプレミスのリソース (ファイル共有やプリンターなど) を含むローカルな Active Directory が企業にある場合は、次の手順に従って、Azure AD に参加しているデバイスにこれらのリソースへのアクセス権を付与できます。 [Microsoft 365 Business の Azure AD に参加しているデバイス](access-resources.md)。

## <a name="deploy-office-365-client-apps"></a>Office 365 クライアントアプリを展開する

セットアップ時に Office アプリを自動的にインストールすることを選択した場合、ユーザーが作業の資格情報を使用して Windows デバイスから Azure AD にサインインすると、アプリが Windows 10 デバイスにインストールされます。
モバイル iOS または Android デバイスに Office をインストールするには、「 [Microsoft 365 Business ユーザーのモバイルデバイスをセットアップ](set-up-mobile-devices.md)する」を参照してください。

Office を個別にインストールすることもできます。 手順について[は、「PC または Mac に Office をインストールする](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665)」を参照してください。

## <a name="additional-security-settings"></a>その他のセキュリティ設定

セットアップウィザードのセキュリティとコンプライアンスの設定に加えて、次の追加設定を設定することもできます。
  
- **メールマルウェア対策**
- **Advanced Threat Protection (ATP) の安全な添付ファイル**
- **ATP の安全なリンク**
- **APT フィッシング対策**
- **Exchange Online Archiving**
- **データ損失防止 (DLP)**
- **Azure Information Protection**(プラン 1)
- **Intune ポータルの可用性**

開始するには、「 [advanced security policies をセットアップ](set-up-advanced-security.md)する」を参照してください。

セキュリティに関するベストプラクティスのロードマップについては[、Microsoft 365 Business をセキュリティで保護するための10のトップの方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)も参照してください。