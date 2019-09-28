---
title: Microsoft 365 Business をセットアップする
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business をセットアップする方法について説明します。
ms.openlocfilehash: d33839693001f36fbb56541775015f739300b043
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288497"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>セットアップウィザードで Microsoft 365 Business をセットアップする

## <a name="add-your-domain-users-and-set-up-policies"></a>ドメイン、ユーザーを追加し、ポリシーをセットアップする

[![[ラベル] 管理センターが変更されたことを知らせるために、aka.ms/aboutM365preview で詳細を確認できます。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Microsoft 365 Business を購入する場合は、所有しているドメインを使用するか、[サインアップ](sign-up.md)中に購入するかを選択できます。

- サインアップ時に新しいドメインを購入した場合、ドメインはすべてセットアップされており、ユーザーを[追加してライセンスを割り当てる](#add-users-and-assign-licenses)ことができます。

### <a name="add-your-domain-to-personalize-sign-in"></a>サインインを個人用に設定するためにドメインを追加する

1. グローバル管理者の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。 

2. [**ドメインの追加**] または [**ユーザーの追加**] を選択して、ウィザードを開始します。
    > [!IMPORTANT]
    > サインアップ中にドメインを購入した場合は、ここに [**ドメインの追加**] 手順は表示されません。 代わりに、[[ユーザーの追加](#add-users-and-assign-licenses)] に移動します。

    ![[ドメインの追加] を選択します。](media/addadomainadmincenter.png)
    
3. ウィザードで、使用するドメイン名 (contoso.com など) を入力します。


    ![[サインインのカスタマイズ] ページのスクリーンショット。](media/personalizesignin.png)

    
4. ウィザードの手順に従って、ドメインを所有していることを確認する[Office 365 用の任意の dns ホスティングプロバイダーで dns レコードを作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)します。 ドメインホストがわかっている場合は、「[ホスト固有の指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)」も参照してください。

    ホスティングプロバイダーが GoDaddy、または[ドメイン接続](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)を使用して他のホストが有効になっている場合、このプロセスは簡単であり、サインインして Microsoft に代わって認証を行うように自動的に求められます。

    ![[GoDaddy のアクセス確認] ページで、[承認] を選択します。](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>ユーザーを追加して、ライセンスを割り当てる

ウィザードでユーザーを追加することはできますが、[後](add-users-m365b.md)で管理センターでユーザーを追加することもできます。 また、ローカルドメインコントローラーがある場合は、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)を使用してユーザーを追加できます。

#### <a name="add-users-in-the-wizard"></a>ウィザードでユーザーを追加する

ウィザードで追加したユーザーには、Microsoft 365 のビジネスライセンスが自動的に割り当てられます。

![ウィザードの [新しいユーザーの追加] ページのスクリーンショット](media/addnewuserspage.png)

1. Microsoft 365 Business サブスクリプションに既存のユーザーが存在する場合 (たとえば、Azure AD Connect を使用した場合)、すぐにライセンスを割り当てるオプションが表示されます。 続行して、これらのユーザーにもライセンスを追加します。

3. ユーザーを追加すると、追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。 それらを印刷、メール、またはダウンロードできます。

4. 移行のメール メッセージをスキップして、[ **メール メッセージの移行**] ページで [ **次へ**] を選びます。 

    別のメールプロバイダーから移行していて、後でデータをコピーする場合は、[メールと連絡先を Office 365 に移行](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)できます。


### <a name="connect-your-domain"></a>ドメインを接続する

> [!NOTE]
> . Onmicrosoft ドメインを使用することを選択した場合、または Azure AD Connect を使用してユーザーを設定した場合は、この手順は表示されません。
  
サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。
  
1. セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。 含まれていない場合は、ネームサーバーを[変更して、任意のドメインレジストラーで Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)をセットアップします。 

    - 既存の DNS レコード (既存の web サイトなど) があるが、DNS ホストが[ドメイン接続](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)に対して有効になっている場合は、[**レコードの追加**] を選択します。 
    - 他の DNS ホスト (ドメイン接続に対して有効になっていません) に既存の dns レコードがある場合は、自分の DNS レコードを管理して、既存のサービスが常に接続していることを確認してください。 詳細については、「[ドメインの基礎](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)」を参照してください。

        ![自分の DNS レコードを管理するドメインページに接続します。](media/connectyourdomainpage.png)

2. ウィザードの手順を実行すると、電子メールとその他のサービスが設定されます。

### <a name="set-up-security-policies-and-device-configurations"></a>セキュリティポリシーとデバイス構成を設定する 

ウィザードで設定したポリシーは、*すべてのユーザー*と呼ばれる[セキュリティグループ](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)に自動的に適用されます。 管理センターで、ポリシーを割り当てるための追加のグループを作成することもできます。

1. [**モバイルデバイスの作業ファイルを保護**する] で、[**デバイスが失われたとき、または盗まれたときに作業ファイルを保護する**] オプションが既定で選択されています。 [**ユーザーがモバイルデバイスで Office ファイルにアクセスする方法を管理**する] をオンにすることもできます。これは推奨されています。

    ![[モバイルデバイスの作業ファイルを保護する] ページのスクリーンショット](media/protectworkfilesondevices.png)

     - **デバイスが紛失または盗難時**に[既定値](protect-work-files-on-lost-or-stolen-device.md)を表示するように、[作業ファイルの保護] を展開します。

        ![失われたデバイスでファイルを保護するための既定値のスクリーンショット。](media/protectworkfilesondevicesdefault.png)

    - [**ユーザーがモバイルデバイスで Office ファイルにアクセスする方法を管理**する] を選択し、これを展開して[既定値](manage-user-access-on-mobile-devices.md)を表示します。 すべてのユーザーに適用される Android、iOS、Windows 10 のアプリケーションポリシーを作成するには、セットアップ時に既定値を受け入れることをお勧めします。 セットアップが完了したら、追加のポリシーを作成できます。

        ![モバイルでの Office ファイルの保護設定のスクリーンショット。](media/useraccessonmobile.png)

2. データとデバイスを保護するための最後の手順では、Windows 10 デバイスをセキュリティで保護するためのポリシーを設定できます。 これらの設定は、ユーザーの Windows 10 が組織に接続すると自動的に適用されます。 **セキュリティで保護された Windows 10 デバイス**を拡張して、[既定値](secure-windows-10-devices.md)を表示および変更できます。
3. Windows 10 デバイスで[Office を自動的にインストール](install-office-on-windows-10-during-setup.md)するように選択することもできます。

    ![Windows 10 デバイス構成ページの設定のスクリーンショット。](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>Office 365 クライアントアプリを展開する

セットアップ時に Office アプリを自動的にインストールすることを選択した場合、ユーザーが作業の資格情報を使用して Windows デバイスから Azure AD にサインインすると、アプリが Windows 10 デバイスにインストールされます。
モバイル iOS または Android デバイスに Office をインストールするには、「 [Microsoft 365 Business ユーザーのモバイルデバイスをセットアップ](set-up-mobile-devices.md)する」を参照してください。

Office を個別にインストールすることもできます。 手順について[は、「PC または Mac に Office をインストールする](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)」を参照してください。
