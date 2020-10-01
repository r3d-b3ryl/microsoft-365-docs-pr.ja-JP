---
title: Microsoft 365 ユーザーアカウントの管理
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
description: Microsoft 365 のユーザーアカウントを管理する方法について説明します。
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327761"
---
# <a name="manage-microsoft-365-user-accounts"></a>Microsoft 365 ユーザーアカウントの管理

Microsoft 365 ユーザーアカウントは、構成に応じて、いくつかの異なる方法で管理できます。 ユーザーアカウントは、 [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)、 [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)、Active DIRECTORY ドメインサービス (AD DS)、または Azure ACTIVE directory (azure AD) 管理ポータルで管理できます。 

Microsoft 365 を購入するとすぐに、Microsoft 365 管理センターと PowerShell を使用してアカウントを管理できるようになります。 クラウド id を管理する場合、組織内のすべてのユーザーが個別のユーザーアカウント名とパスワードを持っています。 オンプレミスのインフラストラクチャと統合して、ユーザーアカウントを Microsoft 365 と同期させる場合は、Azure AD Connect を使用して、シングルサインオン (SSO) 機能の id とパスワードの同期を行うことができます。
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>ユーザーアカウントを管理する場所と方法を計画します。

ユーザーアカウントを管理する場所と方法は、Microsoft 365 で使用する id モデルによって異なります。 これらのモデル全体は、クラウド専用でハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

Microsoft 365 管理センターでユーザーを作成して管理します。 PowerShell または Azure AD 管理センターを使用することもできます。 
    
### <a name="hybrid"></a>ハイブリッド

ユーザーアカウントは、AD DS から Microsoft 365 と同期されるので、オンプレミスの AD DS ツールを使用してユーザーアカウントを管理する必要があります。 
    
## <a name="managing-accounts"></a>アカウントの管理

組織がアカウントを作成および管理する方法を決定するときは、次の要件を考慮してください。
  
- Microsoft 365 と AD DS 間で id を接続するには、ディレクトリ同期ソフトウェアを社内環境内のサーバーにインストールする必要があります。
    
- SSO オプションを含むディレクトリ同期オプションでは、AD DS 属性が標準に適合している必要があります。 ディレクトリで使用される属性の詳細と、必要に応じてクリーンアップを行う方法については、「 [Microsoft 365 へのディレクトリ同期の準備](prepare-for-directory-synchronization.md)」を参照してください。 
    
- Microsoft 365 アカウントを作成する方法を計画します。
    
次の表に、さまざまなアカウント管理ツールを示します。
    
|ツール|Notes|
|:-----|:-----|
|Microsoft 365 管理センター  <br/> |[ユーザーを個別にまたは一括して追加する](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  ユーザーアカウントを追加および変更するための簡単な web インターフェイスを提供します。  <br/>  ディレクトリ同期が有効になっている場合、ユーザーの変更には使用できません (場所およびライセンスの割り当てを設定できます)。  <br/>  SSO オプションを使用することはできません。  <br/> |
|Windows PowerShell  <br/> |[Windows PowerShell を使用して Microsoft 365 を管理する](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Windows PowerShell スクリプトを使用して、ユーザーを一括ユーザーで追加できるようにします。  <br/>  アカウントの作成方法に関係なく、アカウントに場所とライセンスを割り当てるために使用できます。  <br/> |
|一括インポート  <br/> |[同時に複数のユーザーを追加する](add-several-users-at-the-same-time.md) <br/>  CSV ファイルをインポートして、ユーザーのグループを Microsoft 365 に追加できるようにします。  <br/>  SSO オプションを使用することはできません。  <br/> |
|Azure AD  <br/> |Microsoft 365 のサブスクリプションを使用して、Azure AD の無料版を入手できます。 クラウドユーザーのセルフサービスによるパスワードのリセットなどの機能を実行したり、無料版を使用してサインインページとアクセスパネルページをカスタマイズしたりすることができます。 拡張機能を利用するには、basic edition、Azure AD Premium P1、または Azure AD Premium P2 にアップグレードできます。 サポートされている機能の一覧については、「 [AZURE AD エディション](https://go.microsoft.com/fwlink/p/?LinkId=698465) 」を参照してください。  <br/> |
|ディレクトリ同期  <br/> |[オンプレミス id と Azure AD の統合](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  パスワード同期の有無にかかわらずディレクトリ同期を行うには、 [AZURE AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkID=698537)を使用します。  <br/>  複数のフォレストおよび SSO オプションでは、 [AZURE AD Connect のカスタムインストール](https://go.microsoft.com/fwlink/p/?LinkId=698430)を使用します。  <br/>  SSO を有効にするために必要なインフラストラクチャを提供します。  <br/>  段階的な移行やハイブリッド Exchange などの多くのハイブリッドシナリオに必要  <br/>  セキュリティおよびメールが有効なグループを AD DS から同期します。  <br/> |
|||
   
- ユーザーアカウントを Microsoft 365 に追加する方法に関係なく、ライセンスの割り当て、場所の指定など、いくつかのアカウント機能を管理する必要があります。 これらの機能は、Microsoft 365 管理センターから長期間において管理することも、 [PowerShell を使用してユーザーアカウントを作成](https://go.microsoft.com/fwlink/p/?LinkId=717083)することもできます。
    
    管理センターを使用してすべてのユーザーの追加と管理を選択する場合は、Microsoft 365 アカウントを作成するときと同時に、場所を指定してライセンスを割り当てます。 そのため、計画はあまり必要ありません。
    
    > [!IMPORTANT]
    > Microsoft 365 で、ライセンスを割り当てずに (たとえば SharePoint Online に) アカウントを作成することは、アカウント所有者が Microsoft 365 center を表示できるが、会社のサブスクリプション内のサービスにアクセスできないことを意味します。 場所とライセンスを割り当てた後、割り当てたサービスにアカウントがレプリケートされます。 ユーザーは、自分のアカウントにサインインして、自分に割り当てられているサービスを使用することができます。 
  
## <a name="see-also"></a>関連項目

[Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
