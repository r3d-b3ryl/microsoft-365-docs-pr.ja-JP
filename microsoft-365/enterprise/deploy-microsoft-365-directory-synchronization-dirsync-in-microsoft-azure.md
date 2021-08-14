---
title: ディレクトリMicrosoft 365を展開するMicrosoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Azure の仮想マシンに Azure AD Connectを展開して、オンプレミス ディレクトリと Azure サーバー テナントの間でアカウントを同期するADします。
ms.openlocfilehash: 6f7744ab894346e7468f3b90c211d0f8247ba253b291a4a8eda0b292e7409f04
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53835215"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a>ディレクトリMicrosoft 365を展開するMicrosoft Azure

Azure Active Directory (Azure AD) Connect (以前はディレクトリ同期ツール、ディレクトリ同期ツール、または DirSync.exe ツールと呼ばれる) は、ドメインに参加しているサーバーにインストールして、Microsoft 365 サブスクリプションの Azure AD テナントにオンプレミスの Active Directory ドメイン サービス (AD DS) ユーザーを同期するアプリケーションです。 Microsoft 365ディレクトリ サービスAD Azure ADを使用します。 サブスクリプションにはMicrosoft 365 Azure テナントがADされます。 このテナントは他の SaaS アプリケーションと Azure のアプリを含む、他のクラウドのワークロードで組織の ID を管理するためにも使用されます。

Azure AD Connect はオンプレミス サーバーにインストールできますが、次の理由により、Azure の仮想マシンにもインストールできます。
  
- クラウド ベースのサーバーをより迅速にプロビジョニングして構成でき、ユーザーがすぐにサービスを利用できるようになります。
- Azure では、より少ない労力でより良いサイト可用性が得られます。
- 組織内のオンプレミス サーバーの数を削減できます。

このソリューションには、オンプレミス ネットワークと Azure Virtual Network 間の接続が必要です。詳しくは、「[オンプレミス ネットワークを Microsoft Azure 仮想ネットワークに接続する](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)」をご覧ください。 
  
> [!NOTE]
> この記事では、1 つのフォレスト内の単一ドメインの同期について説明します。 Azure AD Connect Active Directory フォレストAD DS ドメインのすべてのドメインを、そのドメインと同期Microsoft 365。 複数の Active Directory フォレストを複数の Active Directory フォレストと同期するMicrosoft 365、マルチフォレスト ディレクトリ同期と単一のシナリオをSign-On[してください](/azure/active-directory/hybrid/whatis-hybrid-identity)。 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a>Azure でのディレクトリ同期Microsoft 365展開の概要

次の図は、Azure AD Connect (ディレクトリ同期サーバー) の仮想マシン上で実行されている Azure AD DS フォレストを Microsoft 365 サブスクリプションに同期する方法を示しています。
  
![Azure AD Connectクラウド サブスクリプションの Azure AD テナントに同期する Azure の仮想マシン上の Azure Microsoft 365 ツール](../media/CP-DirSyncOverview.png)
  
この図には、サイト間 VPN または ExpressRoute 接続で接続されている 2 つのネットワークがあります。具体的には、AD DS ドメイン コントローラーが配置されているオンプレミス ネットワークと、ディレクトリ同期サーバーとして [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) を実行している仮想マシンが含まれる Azure 仮想ネットワークの 2 つです。ディレクトリ同期サーバーを発信元とする主要なトラフィック フローは 2 つあります。
  
-  Azure AD Connect は、アカウントとパスワードの変更に関してオンプレミス ネットワーク上のドメイン コントローラーにクエリを実行します。
-  Azure AD Connectは、アカウントとパスワードへの変更を、サブスクリプションの Azure ADインスタンスMicrosoft 365します。 ディレクトリ同期サーバーはオンプレミス ネットワークの拡張部分にあるため、これらの変更はオンプレミス ネットワークのプロキシ サーバーを介して送信されます。
    
> [!NOTE]
> このソリューションでは、1 つの Active Directory フォレスト内の単一 Active Directory ドメインの同期について説明します。 Azure AD Connectは、Active Directory フォレスト内のすべての Active Directory ドメインを、そのドメインMicrosoft 365。 複数の Active Directory フォレストを複数の Active Directory フォレストと同期するMicrosoft 365、マルチフォレスト ディレクトリ同期と単一のシナリオをSign-On[してください](/azure/active-directory/hybrid/whatis-hybrid-identity)。 
  
このソリューションをデプロイする場合には、次の 2 つの主要な手順があります。
  
1. Azure Virtual Network を作成し、オンプレミスネットワークに対するサイト間 VPN 接続を確立します。詳しくは、「[オンプレミス ネットワークを Microsoft Azure 仮想ネットワークに接続する](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)」をご覧ください。
    
2. [Azure のドメインAD Connect](https://www.microsoft.com/download/details.aspx?id=47594)仮想マシンに Azure AD Connectをインストールし、オンプレミスの DS を同期ADにMicrosoft 365。 これには以下の手順を実行します。
    
    Azure AD Connect を実行するため、Azure Virtual Machine を作成します。
    
    [Azure AD Connect ](https://www.microsoft.com/download/details.aspx?id=47594) をインストールし、設定します。
    
    Azure AD Connectを構成するには、Azure AD 管理者アカウントの資格情報 (ユーザー名とパスワード) と、AD DS エンタープライズ管理者アカウントが必要です。 Azure AD Connectすぐに継続的に実行され、オンプレミスの DS フォレストと ADを同期Microsoft 365。
    
このソリューションを実稼働環境に展開する前に、「シミュレートされたエンタープライズ[](simulated-ent-base-configuration-microsoft-365-enterprise.md)ベース構成」の手順を使用して、この構成を概念実証、デモンストレーション、または実験用として設定できます。
  
> [!IMPORTANT]
> Azure AD Connect の設定が完了しても、AD DS エンタープライズ管理者アカウントの資格情報は保存されません。 
  
> [!NOTE]
> このソリューションでは、単一の DS フォレストADの同期についてMicrosoft 365。 この記事で取り上げられているトポロジは、このソリューションを実装する 1 つの方法に過ぎません。 組織のトポロジは、固有のネットワーク要件とセキュリティに関する考慮事項によって異なる可能性があります。 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a>Azure でディレクトリ同期サーバーをホストするMicrosoft 365計画する
<a name="PlanningVirtual"> </a>

### <a name="prerequisites"></a>前提条件

開始する前に、このソリューションの以下の前提条件を確認してください。
  
- 「[Azure 仮想ネットワークの計画](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network)」に記されている関連する計画内容を確認します。
    
- Azure Virtual Network を構成するためのすべての「[前提条件](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites)」を満たしていることを確かめます。
    
- Active Directory 統合Microsoft 365含むサブスクリプションを作成します。 サブスクリプションの詳細Microsoft 365、[サブスクリプション] ページMicrosoft 365[覧ください](https://products.office.com/compare-all-microsoft-office-products?tab=2)。
    
- Azure を実行する 1 つの Azure 仮想マシンAD Connectプロビジョニングして、オンプレミスの DS フォレストとADを同期Microsoft 365。
    
    AD DS エンタープライズ管理者アカウントと Azure AD 管理者アカウントの資格情報 (名前とパスワード) が必要です。
    
### <a name="solution-architecture-design-assumptions"></a>ソリューション アーキテクチャ設計の前提条件

次の一覧では、このソリューションで採用された設計方針について説明します。
  
- このソリューションでは、サイト間 VPN 接続を伴う 1 つの Azure Virtual Network を使用します。Azure Virtual Network は 1 つのサブネットをホストし、このサブネットには Azure AD Connect を実行する 1 つのディレクトリ同期サーバーが含まれます。 
    
- オンプレミス ネットワークには、ドメイン コントローラーと DNS サーバーが存在します。
    
- Azure AD Connect は、シングル サインオンではなくパスワード ハッシュ同期を実行します (Active Directory フェデレーション サービス (AD FS) インフラストラクチャを展開する必要はありません)。パスワード ハッシュ同期とシングル サインオンのオプションの詳細については、「[Azure Active Directory ハイブリッド ID ソリューションの適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn)」を参照してください。
    
ご使用の環境でこのソリューションを展開する場合に考慮できるその他の設計に関する選択内容があります。それらには以下が含まれます。
  
- 既存の Azure Virtual Network 内に既存の DNS サーバーがある場合、オンプレミス ネットワークの DNS サーバーではなく、それらをディレクトリ同期サーバーで使用して名前解決を行うかどうかを決定します。
    
- 既存の Azure Virtual Network にドメイン コントローラーがある場合、Active Directory サイトとサービスを構成するという方法がより有効な選択肢となるかどうかを判別します。ディレクトリ同期サーバーはアカウントとパスワードの変更内容を調べるために、オンプレミス ネットワークのドメイン コントローラーではなく、Azure Virtual Network 内のドメイン コントローラーをクエリできます。
    
## <a name="deployment-roadmap"></a>展開のロードマップ

Azure の仮想マシンへの Azure AD Connect の展開には、3つのフェーズがあります。
  
- フェーズ 1:Azure 仮想ネットワークを作成および構成する
    
- フェーズ 2:Azure 仮想マシンを作成および構成する
    
- フェーズ 3: Azure AD Connect をインストールして構成する
    
展開後、新しいユーザー アカウントの場所とライセンスも割り当てる必要Microsoft 365。


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a>フェーズ 1: Azure Virtual Network を作成および構成する

Azure 仮想ネットワークを作成および構成するには、「[オンプレミス ネットワークを Microsoft Azure 仮想ネットワークに接続する](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)」の展開ロードマップにある「[フェーズ 1: オンプレミス ネットワークの準備](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network)」および「[フェーズ 2: Azure でのクロスプレミスの仮想ネットワークの作成](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure)」を完了してください。
  
以下が最終的な構成です。
  
![Azure でホストされているディレクトリ同期サーバー Microsoft 365フェーズ 1](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
この図は、サイト間 VPN や ExpressRoute 接続を介してAzure 仮想ネットワークに接続しているオンプレミスネットワークを示しています。
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a>フェーズ 2:Azure 仮想マシンを作成および構成する

「[Azure ポータルで最初の Windows 仮想マシンを作成する](https://go.microsoft.com/fwlink/p/?LinkId=393098)」の説明に従い、Azure に仮想マシンを作成します。以下の設定を使用します。
  
- **[基本]** ウィンドウで、仮想ネットワークと同じサブスクリプション、場所およびリソース グループを選択します。ユーザー名とパスワードを安全な場所に記録します。後ほど、仮想マシンに接続するときに必要になります。
    
- **[サイズの選択]** ウィンドウで、 **A2 標準** サイズを選択します。
    
- **[設定]** ウィンドウの **[ストレージ]** セクションで、**[標準]** ストレージ タイプを選択します。**[ネットワーク]** セクションで、(ゲートウェイ サブネットではなく) ディレクトリ同期サーバーをホストするための仮想ネットワークの名前とサブネットを選択します。他のすべての設定は、既定値のままにします。
    
内部 DNS をチェックして、ディレクトリ同期サーバーが DNS を正しく使用していることを検証し、仮想マシンに IP アドレスのアドレス (A) レコードが追加されたことを確認します。 
  
「[仮想マシンへの接続とサインオン](/azure/virtual-machines/windows/connect-logon)」の説明を参照してリモートデスクトップ接続でディレクトリ同期サーバーに接続します。サインイン後、仮想マシンをオンプレミス AD DS ドメインに参加させます。
  
Azure AD Connect がインターネット リソースにアクセスできるようにするには、オンプレミス ネットワークのプロキシ サーバーを使用するようディレクトリ同期サーバーを構成する必要があります。実行する追加の構成手順は、ネットワーク管理者に問い合わせてください。
  
以下が最終的な構成です。
  
![Azure でホストされているディレクトリ同期サーバー Microsoft 365フェーズ 2](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
この図に、クロスプレミス Azure 仮想ネットワーク内のディレクトリ同期サーバーとしての仮想マシンを示します。
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a>フェーズ 3: Azure AD Connect をインストールして構成する

次の手順を実行します。
  
1. ローカル管理者権限を持つ AD DS ドメイン アカウントを使用して、リモート デスクトップ接続でディレクトリ同期サーバーに接続します。「[仮想マシンへの接続とサインオン](/azure/virtual-machines/windows/connect-logon)」を参照してください。
    
2. ディレクトリ同期サーバーから、[ディレクトリ同期の[](set-up-directory-synchronization.md)セットアップ] Microsoft 365を開き、パスワード ハッシュ同期を使用したディレクトリ同期の指示に従います。
    
> [!CAUTION]
> セットアップによって、ローカル ユーザー組織単位 (OU) 内に **AAD_xxxxxxxxxxxx** というアカウントが作成されます。このアカウントは移動も削除も行わないでください。移動や削除を行うと、同期が失敗します。
  
以下が最終的な構成です。
  
![Azure でホストされているディレクトリ同期サーバー Microsoft 365フェーズ 3](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
この図に、クロスプレミス Azure 仮想ネットワーク内の Azure AD Connect を使ったディレクトリ同期サーバーを示します。
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a>ユーザーに場所とライセンスを割り当Microsoft 365

Azure AD Connect は、オンプレミスの AD DS から Microsoft 365 サブスクリプションにアカウントを追加しますが、ユーザーが Microsoft 365 にサインインしてサービスを使用するには、アカウントを場所とライセンスで構成する必要があります。 次の手順で、適切なユーザーアカウントに場所を追加し、ライセンス認証を行います。
  
1. [管理者] の順に [Microsoft 365 管理センター](https://admin.microsoft.com)し、[管理者] を **クリックします**。
    
2. 左側のナビゲーションで、 **[ユーザー] > [アクティブなユーザー]** をクリックします。
    
3. ユーザーアカウントのリストで、アクティブにするユーザー名の隣にあるチェック ボックスをオンにします。
    
4. ユーザーのページで、**[製品ライセンス]** の **[編集]** をクリックします。
    
5. **[製品ライセンス]** ページの **[場所]** でユーザーの場所を選択し、ユーザーの適切なライセンスを有効にします。
    
6. 完了したら、**[保存]** をクリックし、2 回 **[閉じる]** をクリックします。
    
7. 別のユーザーについては、手順 3 に戻ります。
    
## <a name="see-also"></a>関連項目

[Microsoft 365 ソリューションおよびアーキテクチャ センター](../solutions/index.yml)
  
[オンプレミス ネットワークを Microsoft Azure 仮想ネットワークに接続する](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[Azure AD Connect をダウンロードする](https://www.microsoft.com/download/details.aspx?id=47594)
  
[ユーザーのディレクトリ同期をMicrosoft 365](set-up-directory-synchronization.md)
