---
title: Microsoft Azureでディレクトリ同期Microsoft 365展開する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
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
description: Azure の仮想マシンに Azure AD Connectをデプロイして、オンプレミスのディレクトリと Azure AD テナントの間でアカウントを同期する方法について説明します。
ms.openlocfilehash: e04a3a4e681ab50b767670cfd419d29cd95556e7
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753388"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a>Microsoft Azureでディレクトリ同期Microsoft 365展開する

Azure Active Directory (Azure AD) Connect (以前はディレクトリ同期ツール、ディレクトリ同期ツール、またはDirSync.exe ツールと呼ばられていました) は、ドメインに参加しているサーバーにインストールして、オンプレミスの Active Directory Domain Services (AD DS) ユーザーを Azure AD テナントに同期するアプリケーションです。サブスクリプションMicrosoft 365。 Microsoft 365は、ディレクトリ サービスに Azure AD を使用します。 Microsoft 365 サブスクリプションには、Azure AD テナントが含まれています。 このテナントは他の SaaS アプリケーションと Azure のアプリを含む、他のクラウドのワークロードで組織の ID を管理するためにも使用されます。

Azure AD Connectはオンプレミス サーバーにインストールできますが、次の理由から Azure の仮想マシンにインストールすることもできます。
  
- クラウド ベースのサーバーをより迅速にプロビジョニングして構成でき、ユーザーがすぐにサービスを利用できるようになります。
- Azure では、より少ない労力でより良いサイト可用性が得られます。
- 組織内のオンプレミス サーバーの数を削減できます。

このソリューションには、オンプレミス ネットワークと Azure Virtual Network 間の接続が必要です。詳しくは、「[オンプレミス ネットワークを Microsoft Azure 仮想ネットワークに接続する](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)」をご覧ください。 
  
> [!NOTE]
> この記事では、1 つのフォレスト内の単一ドメインの同期について説明します。 Azure AD Connectは、Active Directory フォレスト内のすべての AD DS ドメインをMicrosoft 365と同期します。 Microsoft 365と同期する Active Directory フォレストが複数ある場合は、「[マルチフォレスト ディレクトリ同期と単一のSign-Onシナリオ](/azure/active-directory/hybrid/whatis-hybrid-identity)」を参照してください。 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a>Azure でのディレクトリ同期Microsoft 365デプロイの概要

次の図は、オンプレミスの AD DS フォレストをMicrosoft 365 サブスクリプションに同期する Azure の仮想マシン (ディレクトリ同期サーバー) で実行されている Azure AD Connectを示しています。
  
![Azure AD Connect、オンプレミス アカウントをトラフィック フローを使用してMicrosoft 365 サブスクリプションの Azure AD テナントに同期する Azure の仮想マシン上のツールです。](../media/CP-DirSyncOverview.png)
  
この図には、サイト間 VPN または ExpressRoute 接続で接続されている 2 つのネットワークがあります。 AD DS ドメイン コントローラーが配置されているオンプレミス ネットワークと、Azure AD Connectを実行している仮想マシンであるディレクトリ同期サーバーを備えた [Azure](https://www.microsoft.com/download/details.aspx?id=47594) 仮想ネットワークがあります。 ディレクトリ同期サーバーから発信される主なトラフィック フローは 2 つあります。
  
-  Azure AD Connect は、アカウントとパスワードの変更に関してオンプレミス ネットワーク上のドメイン コントローラーにクエリを実行します。
-  Azure AD Connectは、アカウントとパスワードに対する変更を、Microsoft 365 サブスクリプションの Azure AD インスタンスに送信します。 ディレクトリ同期サーバーはオンプレミス ネットワークの拡張部分にあるため、これらの変更はオンプレミス ネットワークのプロキシ サーバーを介して送信されます。
    
> [!NOTE]
> このソリューションでは、1 つの Active Directory フォレスト内の単一 Active Directory ドメインの同期について説明します。 Azure AD Connectは、Active Directory フォレスト内のすべての Active Directory ドメインをMicrosoft 365と同期します。 Microsoft 365と同期する Active Directory フォレストが複数ある場合は、「[マルチフォレスト ディレクトリ同期と単一のSign-Onシナリオ](/azure/active-directory/hybrid/whatis-hybrid-identity)」を参照してください。 
  
このソリューションをデプロイする場合には、次の 2 つの主要な手順があります。
  
1. Azure Virtual Network を作成し、オンプレミスネットワークに対するサイト間 VPN 接続を確立します。詳しくは、「[オンプレミス ネットワークを Microsoft Azure 仮想ネットワークに接続する](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)」をご覧ください。
    
2. Azure のドメインに参加している仮想マシンに [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)をインストールし、オンプレミスの AD DS をMicrosoft 365に同期します。 これには以下の手順を実行します。
    
    Azure AD Connect を実行するため、Azure Virtual Machine を作成します。
    
    [Azure AD Connect ](https://www.microsoft.com/download/details.aspx?id=47594) をインストールし、設定します。
    
    Azure AD Connectを構成するには、Azure AD 管理者アカウントと AD DS エンタープライズ管理者アカウントの資格情報 (ユーザー名とパスワード) が必要です。 Azure AD Connectは、オンプレミスの AD DS フォレストをMicrosoft 365に同期するために、直ちに継続的に実行されます。
    
このソリューションを運用環境にデプロイする前に、「 [シミュレートされたエンタープライズベース構成」](simulated-ent-base-configuration-microsoft-365-enterprise.md) の手順を使用して、概念実証、デモンストレーション、または実験用にこの構成を設定できます。
  
> [!IMPORTANT]
> Azure AD Connect の設定が完了しても、AD DS エンタープライズ管理者アカウントの資格情報は保存されません。 
  
> [!NOTE]
> このソリューションでは、単一の AD DS フォレストをMicrosoft 365に同期する方法について説明します。 この記事で取り上げられているトポロジは、このソリューションを実装する 1 つの方法に過ぎません。 組織のトポロジは、固有のネットワーク要件とセキュリティに関する考慮事項によって異なる可能性があります。 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a>Azure でMicrosoft 365用のディレクトリ同期サーバーをホストする計画
<a name="PlanningVirtual"> </a>

### <a name="prerequisites"></a>前提条件

開始する前に、このソリューションの以下の前提条件を確認してください。
  
- 「[Azure 仮想ネットワークの計画](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network)」に記されている関連する計画内容を確認します。
    
- Azure Virtual Network を構成するためのすべての「[前提条件](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites)」を満たしていることを確かめます。
    
- Active Directory 統合機能を含むMicrosoft 365 サブスクリプションを用意します。 Microsoft 365サブスクリプションの詳細については、[Microsoft 365サブスクリプション ページ](https://products.office.com/compare-all-microsoft-office-products?tab=2)を参照してください。
    
- オンプレミスの AD DS フォレストをMicrosoft 365と同期するために、Azure AD Connectを実行する 1 つの Azure Virtual Machine をプロビジョニングします。
    
    AD DS エンタープライズ管理者アカウントと Azure AD 管理者アカウントの資格情報 (名前とパスワード) が必要です。
    
### <a name="solution-architecture-design-assumptions"></a>ソリューション アーキテクチャ設計の前提条件

次の一覧では、このソリューションで採用された設計方針について説明します。
  
- このソリューションでは、サイト間 VPN 接続を伴う 1 つの Azure Virtual Network を使用します。Azure Virtual Network は 1 つのサブネットをホストし、このサブネットには Azure AD Connect を実行する 1 つのディレクトリ同期サーバーが含まれます。 
    
- オンプレミス ネットワークには、ドメイン コントローラーと DNS サーバーが存在します。
    
- Azure AD Connectでは、シングル サインオンの代わりにパスワード ハッシュ同期が実行されます。 Active Directory フェデレーション サービス (AD FS) (AD FS) インフラストラクチャをデプロイする必要はありません。 パスワード ハッシュ同期とシングル サインオン オプションの詳細については、「[Azure Active Directory ハイブリッド ID ソリューションに適した認証方法の選択」を](/azure/active-directory/hybrid/choose-ad-authn)参照してください。
    
このソリューションを環境にデプロイする際に考慮する可能性がある設計上の選択肢は他にもあります。 これらには次のコマンドレットがあります。
  
- 既存の Azure Virtual Network 内に既存の DNS サーバーがある場合、オンプレミス ネットワークの DNS サーバーではなく、それらをディレクトリ同期サーバーで使用して名前解決を行うかどうかを決定します。
    
- 既存の Azure Virtual Network にドメイン コントローラーがある場合、Active Directory サイトとサービスを構成するという方法がより有効な選択肢となるかどうかを判別します。ディレクトリ同期サーバーはアカウントとパスワードの変更内容を調べるために、オンプレミス ネットワークのドメイン コントローラーではなく、Azure Virtual Network 内のドメイン コントローラーをクエリできます。
    
## <a name="deployment-roadmap"></a>展開のロードマップ

Azure の仮想マシンへの Azure AD Connect の展開には、3つのフェーズがあります。
  
- フェーズ 1:Azure 仮想ネットワークを作成および構成する
    
- フェーズ 2:Azure 仮想マシンを作成および構成する
    
- フェーズ 3: Azure AD Connect をインストールして構成する
    
デプロイ後、Microsoft 365の新しいユーザー アカウントの場所とライセンスも割り当てる必要があります。


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a>フェーズ 1: Azure Virtual Network を作成および構成する

Azure 仮想ネットワークを作成および構成するには、「[オンプレミス ネットワークを Microsoft Azure 仮想ネットワークに接続する](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)」の展開ロードマップにある「[フェーズ 1: オンプレミス ネットワークの準備](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network)」および「[フェーズ 2: Azure でのクロスプレミスの仮想ネットワークの作成](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure)」を完了してください。
  
以下が最終的な構成です。
  
![Azure でホストされているMicrosoft 365のディレクトリ同期サーバーのフェーズ 1。](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
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
  
![Azure でホストされているMicrosoft 365のディレクトリ同期サーバーのフェーズ 2。](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
この図に、クロスプレミス Azure 仮想ネットワーク内のディレクトリ同期サーバーとしての仮想マシンを示します。
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a>フェーズ 3: Azure AD Connect をインストールして構成する

次の手順を実行します。
  
1. ローカル管理者権限を持つ AD DS ドメイン アカウントを使用して、リモート デスクトップ接続でディレクトリ同期サーバーに接続します。「[仮想マシンへの接続とサインオン](/azure/virtual-machines/windows/connect-logon)」を参照してください。
    
2. ディレクトリ同期サーバーから、[Microsoft 365のディレクトリ同期のセットアップに関する記事を](set-up-directory-synchronization.md)開き、パスワード ハッシュ同期を使用したディレクトリ同期の指示に従います。
    
> [!CAUTION]
> セットアップによって、ローカル ユーザー組織単位 (OU) 内に **AAD_xxxxxxxxxxxx** というアカウントが作成されます。このアカウントは移動も削除も行わないでください。移動や削除を行うと、同期が失敗します。
  
以下が最終的な構成です。
  
![Azure でホストされているMicrosoft 365のディレクトリ同期サーバーのフェーズ 3。](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
この図に、クロスプレミス Azure 仮想ネットワーク内の Azure AD Connect を使ったディレクトリ同期サーバーを示します。
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a>Microsoft 365のユーザーに場所とライセンスを割り当てる

Azure AD Connectは、オンプレミスの AD DS からMicrosoft 365 サブスクリプションにアカウントを追加しますが、ユーザーがMicrosoft 365にサインインしてそのサービスを使用するには、アカウントを場所とライセンスで構成する必要があります。 次の手順で、適切なユーザーアカウントに場所を追加し、ライセンス認証を行います。
  
1. [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインし、[**管理**] をクリックします。
    
2. 左側のナビゲーションで、[ **ユーザー** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**アクティブ ユーザー**</a>] をクリックします。
3. ユーザーアカウントのリストで、アクティブにするユーザー名の隣にあるチェック ボックスをオンにします。
    
4. ユーザーのページで、**[製品ライセンス]** の **[編集]** をクリックします。
    
5. **[製品ライセンス]** ページの **[場所]** でユーザーの場所を選択し、ユーザーの適切なライセンスを有効にします。
    
6. 完了したら、**[保存]** をクリックし、2 回 **[閉じる]** をクリックします。
    
7. 別のユーザーについては、手順 3 に戻ります。
    
## <a name="see-also"></a>関連項目

[Microsoft 365 ソリューションおよびアーキテクチャ センター](../solutions/index.yml)
  
[オンプレミス ネットワークを Microsoft Azure 仮想ネットワークに接続する](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[Azure AD Connect をダウンロードする](https://www.microsoft.com/download/details.aspx?id=47594)
  
[Microsoft 365のディレクトリ同期を設定する](set-up-directory-synchronization.md)
