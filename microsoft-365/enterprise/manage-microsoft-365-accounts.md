---
title: Microsoft 365 ユーザー アカウントを管理する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.prod: office-online-server
ms.localizationpriority: medium
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
description: Microsoft 365ユーザー アカウントを管理する方法について説明します。
ms.openlocfilehash: dbd1c0a3c1c6fdb10d157299552e83a77f495e3c
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098342"
---
# <a name="manage-microsoft-365-user-accounts"></a>Microsoft 365 ユーザー アカウントを管理する

Microsoft 365ユーザー アカウントは、構成に応じていくつかの方法で管理できます。 ユーザー アカウントは、[Microsoft 365 管理センター](/admin)、[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)、Active Directory Domain Services (AD DS)、またはAzure Active Directory (Azure AD) 管理ポータルで管理できます。 

Microsoft 365を購入するとすぐに、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>と PowerShell を使用してアカウントを管理できます。 クラウド ID を管理する場合、組織内のすべてのユーザーに個別のユーザー アカウント名とパスワードが設定されます。 オンプレミス インフラストラクチャと統合し、ユーザー アカウントをMicrosoft 365と同期させる場合は、Azure AD Connectを使用して、シングル サインオン (SSO) 機能の ID とパスワードの同期を提供できます。
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>ユーザー アカウントを管理する場所と方法を計画する

ユーザー アカウントをどこでどのように管理できるかは、Microsoft 365に使用する ID モデルによって異なります。 2 つの全体的なモデルは、クラウド専用とハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

Microsoft 365 管理センターでユーザーを作成および管理<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">します</a>。 PowerShell またはAzure AD管理センターを使用することもできます。 
    
### <a name="hybrid"></a>ハイブリッド

ユーザー アカウントは AD DS のMicrosoft 365と同期されるため、オンプレミスの AD DS ツールを使用してユーザー アカウントを管理する必要があります。 
    
## <a name="managing-accounts"></a>アカウントの管理

組織でアカウントを作成および管理する方法を決定する場合は、次の要件を考慮してください。
  
- Microsoft 365と AD DS の間で ID を接続するには、オンプレミス環境内のサーバーにディレクトリ同期ソフトウェアをインストールする必要があります。
    
- SSO オプションを含むすべてのディレクトリ同期オプションでは、AD DS 属性が標準を満たしている必要があります。 ディレクトリで使用される属性と、必要なクリーンアップ (存在する場合) の詳細については、「[Microsoft 365へのディレクトリ同期の準備](prepare-for-directory-synchronization.md)」を参照してください。 
    
- Microsoft 365 アカウントを作成する方法を計画します。
    
次の表に、さまざまなアカウント管理ツールを示します。
    
|ツール|備考|
|:-----|:-----|
|Microsoft 365 管理センター  <br/> |[ユーザーを個別または一括で追加する](../admin/add-users/add-users.md) <br/>  ユーザー アカウントを追加および変更するための簡単な Web インターフェイスを提供します。  <br/>  ディレクトリ同期が有効になっている場合は、ユーザーを変更するために使用できません (場所とライセンスの割り当てを設定できます)。  <br/>  SSO オプションでは使用できません。  <br/> |
|Windows PowerShell  <br/> |[Windows PowerShellを使用してMicrosoft 365を管理する](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  Windows PowerShell スクリプトを使用して、ユーザーを一括ユーザーに追加できます。  <br/>  アカウントの作成方法に関係なく、場所とライセンスをアカウントに割り当てるために使用できます。  <br/> |
|一括インポート  <br/> |[同時に複数のユーザーを追加する](add-several-users-at-the-same-time.md) <br/>  CSV ファイルをインポートして、ユーザーのグループをMicrosoft 365に追加できます。  <br/>  SSO オプションでは使用できません。  <br/> |
|Azure AD  <br/> |Microsoft 365 サブスクリプションでAzure ADの無料版を入手できます。 無料版を使用して、クラウド ユーザーのセルフサービス パスワード リセット、サインイン ページとアクセス パネル ページのカスタマイズなどの機能を実行できます。 強化された機能を利用するには、基本エディション、Azure AD Premium P1、またはAzure AD Premium P2にアップグレードします。 サポートされている機能の一覧については、[Azure AD エディション](/azure/active-directory/fundamentals/active-directory-whatis)を参照してください。  <br/> |
|ディレクトリ同期  <br/> |[オンプレミス ID とAzure ADの統合](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  パスワード同期の有無にかかわらずディレクトリ同期を行う場合は、[高速設定でAzure AD Connectを使用します](/azure/active-directory/hybrid/how-to-connect-install-express)。  <br/>  複数のフォレストと SSO オプションの場合は、[Azure AD Connectのカスタム インストール](/azure/active-directory/hybrid/how-to-connect-install-custom)を使用します。  <br/>  SSO を有効にするために必要なインフラストラクチャを提供します。  <br/>  段階的な移行やハイブリッド Exchangeなど、多くのハイブリッド シナリオに必要です  <br/>  AD DS からセキュリティとメールが有効なグループを同期します。  <br/> |
|||
   
- ユーザー アカウントをMicrosoft 365に追加する方法に関係なく、ライセンスの割り当て、場所の指定など、いくつかのアカウント機能を管理する必要があります。 これらの機能は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>から長期的に管理することも、[PowerShell でユーザー アカウントを作成](./create-user-accounts-with-microsoft-365-powershell.md)することもできます。
    
    管理センターですべてのユーザーを追加および管理することを選択した場合は、場所を指定し、Microsoft 365 アカウントの作成と同時にライセンスを割り当てます。 その結果、あまり計画は必要ありません。
    
    > [!IMPORTANT]
    > ライセンスを割り当てずにMicrosoft 365でアカウントを作成する (たとえば、SharePoint Online) とは、アカウント所有者がMicrosoft 365 センターを表示できますが、会社のサブスクリプション内のサービスにはアクセスできないことを意味します。 場所とライセンスを割り当てると、アカウントは割り当てたサービスにレプリケートされます。 ユーザーは自分のアカウントにサインインし、割り当てたサービスを使用できます。 
  
## <a name="see-also"></a>関連項目

[Microsoft 365 管理センター](/admin)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)