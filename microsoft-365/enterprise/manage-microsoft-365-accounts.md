---
title: ユーザー Microsoft 365を管理する
ms.author: kvice
author: kelleyvice-msft
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
- admindeeplinkMAC
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: ユーザー アカウントを管理するMicrosoft 365を確認します。
ms.openlocfilehash: 7a21ed12101f3aaa8323c62d2c15ae30860cd041
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221034"
---
# <a name="manage-microsoft-365-user-accounts"></a>ユーザー Microsoft 365を管理する

構成に応Microsoft 365、さまざまな方法でユーザー アカウントを管理できます。 ユーザー アカウントは[、Microsoft 365 管理センター](../admin/add-users/index.yml) [、PowerShell、Active](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)Directory ドメイン サービス (AD DS)、または Azure Active Directory (Azure AD) 管理ポータルで管理できます。 

アカウントを購入すると<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365、Microsoft 365 管理センター</a> PowerShell を使用してアカウントを管理できます。 クラウド ID を管理する場合、組織内のすべてのユーザーには、個別のユーザー アカウント名とパスワードがあります。 オンプレミスインフラストラクチャと統合し、Microsoft 365 とユーザー アカウントを同期する場合は、Azure AD Connect を使用してシングル サインオン (SSO) 機能の ID とパスワードの同期を提供できます。
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>ユーザー アカウントの管理場所と管理方法を計画する

ユーザー アカウントを管理する場所と方法は、ユーザー アカウントに使用する id モデルによってMicrosoft 365。 2 つの全体的なモデルは、クラウド専用とハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

ユーザーを作成および管理するには<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">、Microsoft 365 管理センター。</a> PowerShell または Azure の管理センター AD使用できます。 
    
### <a name="hybrid"></a>ハイブリッド

ユーザー アカウントは DS からMicrosoft 365 ADされます。そのため、ユーザー アカウントを管理するには、オンプレミスの DS ADを使用する必要があります。 
    
## <a name="managing-accounts"></a>アカウントの管理

組織でアカウントを作成および管理する方法を決定する場合は、次の要件を考慮してください。
  
- ディレクトリ同期ソフトウェアは、オンプレミス環境内のサーバーにインストールして、MICROSOFT 365 DS と ADする必要があります。
    
- SSO オプションを含む任意のディレクトリ同期オプションでは、DS 属性がADを満たす必要があります。 ディレクトリで使用する属性と、必要なクリーンアップ (存在する場合) の詳細については、「ディレクトリ同期の準備からディレクトリへの同期の準備」[をMicrosoft 365。](prepare-for-directory-synchronization.md) 
    
- アカウントの作成方法を計画Microsoft 365します。
    
次の表に、さまざまなアカウント管理ツールの一覧を示します。
    
|ツール|Notes|
|:-----|:-----|
|Microsoft 365 管理センター  <br/> |[ユーザーを個別または一括で追加する](../admin/add-users/add-users.md) <br/>  ユーザー アカウントを追加および変更する簡単な Web インターフェイスを提供します。  <br/>  ディレクトリ同期が有効になっている場合は、ユーザーを変更することはできません (場所とライセンスの割り当てを設定できます)。  <br/>  SSO オプションでは使用できません。  <br/> |
|Windows PowerShell  <br/> |[管理Microsoft 365を使用Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  カスタム スクリプトを使用して、一括ユーザーにユーザーをWindows PowerShellできます。  <br/>  アカウントの作成方法に関係なく、場所とライセンスをアカウントに割り当てる場合に使用できます。  <br/> |
|一括インポート  <br/> |[同時に複数のユーザーを追加する](add-several-users-at-the-same-time.md) <br/>  CSV ファイルをインポートして、ユーザーのグループをユーザーグループに追加Microsoft 365。  <br/>  SSO オプションでは使用できません。  <br/> |
|Azure AD  <br/> |サブスクリプションを使用して Azure AD無料版Microsoft 365取得します。 無料版を使用すると、クラウド ユーザーのセルフサービス パスワードのリセット、サインイン ページとアクセス パネル ページのカスタマイズなど、機能を実行できます。 拡張機能を取得するには、基本エディション、Azure AD Premium P1、またはAzure AD Premium P2。 サポート [されている機能のADについては、「Azure](/azure/active-directory/fundamentals/active-directory-whatis) AD エディション」を参照してください。  <br/> |
|ディレクトリ同期  <br/> |[オンプレミス ID と Azure id の統合AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  パスワード同期を使用するかしないディレクトリ同期の場合は、[高速AD Connect Azure AD Connectを使用します](/azure/active-directory/hybrid/how-to-connect-install-express)。  <br/>  複数のフォレストと SSO オプションの場合は[、Azure サーバーの](/azure/active-directory/hybrid/how-to-connect-install-custom)カスタム インストールを使用AD Connect。  <br/>  SSO を有効にするために必要なインフラストラクチャを提供します。  <br/>  ステージ移行やハイブリッド 移行など、多くのハイブリッド シナリオで必要Exchange  <br/>  セキュリティとメールが有効なグループを DS から同期ADします。  <br/> |
|||
   
- Microsoft 365 にユーザー アカウントを追加する方法に関係なく、ライセンスの割り当て、場所の指定など、いくつかのアカウント機能を管理する必要があります。 これらの機能は、サーバーから長期的に管理Microsoft 365 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a> PowerShell を使用してユーザー[アカウントを作成することもできます](./create-user-accounts-with-microsoft-365-powershell.md)。
    
    管理センターを通じてすべてのユーザーを追加および管理する場合は、場所を指定し、ユーザー アカウントの作成と同時にライセンスを割りMicrosoft 365します。 その結果、あまり計画が必要ありません。
    
    > [!IMPORTANT]
    > Microsoft 365 でライセンスを割り当てずに (SharePoint Online に) アカウントを作成すると、アカウント所有者は Microsoft 365 センターを表示できますが、会社のサブスクリプション内のサービスにはアクセスできません。 場所とライセンスを割り当てた後、アカウントは割り当てたサービスまたはサービスにレプリケートされます。 ユーザーは自分のアカウントにサインインし、割り当てたサービスを使用できます。 
  
## <a name="see-also"></a>関連項目

[Microsoft 365 管理センター](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)