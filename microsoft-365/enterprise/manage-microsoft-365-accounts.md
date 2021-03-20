---
title: Microsoft 365 ユーザー アカウントの管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 ユーザー アカウントを管理する方法について説明します。
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909564"
---
# <a name="manage-microsoft-365-user-accounts"></a>Microsoft 365 ユーザー アカウントの管理

構成に応じて、さまざまな方法で Microsoft 365 ユーザー アカウントを管理できます。 ユーザー アカウントは [、Microsoft 365](../admin/add-users/index.yml)管理センター [、PowerShell、Active](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)Directory ドメイン サービス (AD DS)、または Azure Active Directory (Azure AD) 管理ポータルで管理できます。 

Microsoft 365 を購入するとすぐに、Microsoft 365 管理センターと PowerShell を使用してアカウントを管理できます。 クラウド ID を管理する場合、組織内のすべてのユーザーには、個別のユーザー アカウント名とパスワードがあります。 オンプレミスインフラストラクチャと統合し、ユーザー アカウントを Microsoft 365 と同期する場合は、Azure AD Connect を使用して、シングル サインオン (SSO) 機能の ID とパスワードの同期を提供できます。
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>ユーザー アカウントの管理場所と管理方法を計画する

ユーザー アカウントを管理する場所と方法は、Microsoft 365 で使用する ID モデルによって異なります。 2 つの全体的なモデルは、クラウド専用とハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

Microsoft 365 管理センターでユーザーを作成および管理します。 PowerShell または Azure の管理センター AD使用できます。 
    
### <a name="hybrid"></a>ハイブリッド

ユーザー アカウントは DS から Microsoft 365 と同期AD、ユーザー アカウントを管理するには、オンプレミスの DS ADを使用する必要があります。 
    
## <a name="managing-accounts"></a>アカウントの管理

組織でアカウントを作成および管理する方法を決定する場合は、次の要件を考慮してください。
  
- ディレクトリ同期ソフトウェアをオンプレミス環境内のサーバーにインストールして、Microsoft 365 と DS 間の id をAD必要があります。
    
- SSO オプションを含む任意のディレクトリ同期オプションでは、DS 属性がADを満たす必要があります。 ディレクトリで使用する属性と、必要なクリーンアップの詳細については、「ディレクトリ同期の準備から [Microsoft 365](prepare-for-directory-synchronization.md)への準備」を参照してください。 
    
- Microsoft 365 アカウントの作成方法を計画します。
    
次の表に、さまざまなアカウント管理ツールの一覧を示します。
    
|ツール|メモ|
|:-----|:-----|
|Microsoft 365 管理センター  <br/> |[ユーザーを個別または一括で追加する](../admin/add-users/add-users.md) <br/>  ユーザー アカウントを追加および変更する簡単な Web インターフェイスを提供します。  <br/>  ディレクトリ同期が有効になっている場合は、ユーザーを変更することはできません (場所とライセンスの割り当てを設定できます)。  <br/>  SSO オプションでは使用できません。  <br/> |
|Windows PowerShell  <br/> |[Microsoft 365 を管理するには、Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  カスタム スクリプトを使用して、一括ユーザーにユーザーをWindows PowerShellできます。  <br/>  アカウントの作成方法に関係なく、場所とライセンスをアカウントに割り当てる場合に使用できます。  <br/> |
|一括インポート  <br/> |[同時に複数のユーザーを追加する](add-several-users-at-the-same-time.md) <br/>  CSV ファイルをインポートして、Microsoft 365 にユーザーのグループを追加できます。  <br/>  SSO オプションでは使用できません。  <br/> |
|Azure AD  <br/> |Microsoft 365 サブスクリプションで Azure AD無料版を取得します。 無料版を使用すると、クラウド ユーザーのセルフサービス パスワードのリセット、サインイン ページとアクセス パネル ページのカスタマイズなど、機能を実行できます。 強化された機能を取得するには、基本エディション、Azure AD Premium P1、または Azure ADプレミアム P2 にアップグレードできます。 サポート [されている機能のADについては、「Azure](/azure/active-directory/fundamentals/active-directory-whatis) AD エディション」を参照してください。  <br/> |
|ディレクトリ同期  <br/> |[オンプレミス ID と Azure id の統合AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  パスワード同期を使用するかしないディレクトリ同期の場合は [、Azure AD高速設定を使用して接続します](/azure/active-directory/hybrid/how-to-connect-install-express)。  <br/>  複数のフォレストと SSO オプションの場合は [、Azure のカスタム インストールを使用して](/azure/active-directory/hybrid/how-to-connect-install-custom)接続ADします。  <br/>  SSO を有効にするために必要なインフラストラクチャを提供します。  <br/>  ステージ移行やハイブリッド Exchange などの多くのハイブリッド シナリオに必要  <br/>  セキュリティとメールが有効なグループを DS から同期ADします。  <br/> |
|||
   
- Microsoft 365 にユーザー アカウントを追加する方法に関係なく、ライセンスの割り当て、場所の指定など、いくつかのアカウント機能を管理する必要があります。 これらの機能は、Microsoft 365 管理センターから長期的に管理するか、PowerShell を使用してユーザー アカウント [を作成することもできます](./create-user-accounts-with-microsoft-365-powershell.md)。
    
    管理センターを通じてすべてのユーザーを追加および管理する場合は、場所を指定し、Microsoft 365 アカウントの作成と同時にライセンスを割り当てる必要があります。 その結果、あまり計画が必要ありません。
    
    > [!IMPORTANT]
    > たとえば、SharePoint Online にライセンスを割り当てずに Microsoft 365 でアカウントを作成すると、アカウント所有者は Microsoft 365 センターを表示できますが、会社のサブスクリプション内のサービスにはアクセスできません。 場所とライセンスを割り当てた後、アカウントは割り当てたサービスまたはサービスにレプリケートされます。 ユーザーは自分のアカウントにサインインし、割り当てたサービスを使用できます。 
  
## <a name="see-also"></a>関連項目

[Microsoft 365 管理センター](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)