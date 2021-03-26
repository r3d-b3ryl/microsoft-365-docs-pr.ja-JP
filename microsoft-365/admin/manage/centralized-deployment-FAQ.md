---
title: 一元展開に関する FAQ
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 管理センターからの集中展開に関するよくある質問に対する回答を確認します。
ms.openlocfilehash: 06e3b7973a209cdf40446c5a9511713d779373b8
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221837"
---
# <a name="centralized-deployment-faq"></a>一元展開に関する FAQ

Office 365 管理者が Office アドイン (Word、Excel、PowerPoint、および Outlook) を組織内のユーザーおよびグループに展開する場合は、この記事で説明した集中展開を使用するためのすべての要件を満たしている場合に、集中展開が推奨されます。   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>組織が集中展開用に設定されているかどうかは、どのように確認できますか?  

アドインの一元的な展開では、ユーザーが Microsoft 365 Apps for enterprise を使用している (組織のログイン資格情報を使用して Office にサインインしている) 必要があります。Exchange Online メールボックスを持つ必要があります。 サブスクリプション ディレクトリは、Azure Active Directory に存在するか、Azure Active Directory にフェデレーションされている必要があります。  
 
集中展開は、オンライン メールボックスでのみサポートされます。 オンプレミスの Exchange メールボックスへの展開はサポートされていません。

集中展開互換性[チェッカーを使用して](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   、サブスクリプションが適格かどうかを判断できます。 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>集中展開を使用してアドインのユーザー割り当てをターゲットに設定する方法  

集中展開は、テナント内の個々のユーザー、グループ、およびすべてのユーザーへの割り当てをサポートします。 集中展開は、上位レベルのグループまたは親グループのないグループのユーザーには使用できますが、ネストされたグループまたは親グループを持つグループのユーザーには使用できません。 一元展開は、365 グループ、配布リスト、およびセキュリティ グループOffice含む、ほとんどの Azure Active Directory グループの一部です。  

管理を容易にするために、個々のユーザー割り当てではなくグループ割り当てを使用する方が良いです。
 
詳細については、「ユーザーと [グループの割り当て」を参照してください](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)。  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>アドインがすべてのユーザーに表示されるのにどれくらいの時間が必要ですか?  

アドインがすべてのユーザーに表示するには、最大 24 時間かかる場合があります。 アドインの更新、オンまたはオフからの変更、アドインの削除に同じ時間がかかる場合があります。 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>管理者として、組織のアドインへのユーザー アクセスを管理する方法

ユーザー、グループ、または組織全体にアドインを簡単に展開するには、管理者が集中展開を使用することをお勧めします。

ユーザー アクセスの管理の詳細については、以下を参照してください。
 - [すべてのクライアントでアドイン ストアをオフにしてアドインOfficeを防止する (Outlook を除く)](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Outlook 用のアドインをインストールおよび管理できる管理者とユーザーを指定する](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>一元展開では、管理者は Outlook アドインの展開方法を柔軟に選択できますか?  

はい。 一元展開では、管理者は、アドインの展開中に Outlook アドインの 3 つの展開方法のいずれかを柔軟に選択できます。

**固定 (既定)**  アドインは割り当てられたユーザーに自動的に展開され、削除できません。  
 
**使用可能** ユーザーは、[ホーム] を選択して Outlook にアドインをインストール>管理者が管理>アドインを **取得します**。
 
**省略可能** アドインは割り当てられたユーザーに自動的に展開されますが、削除を選択できます。  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>管理者は、LINE-of-Business (LOB) アドインを更新できますか?  

はい。 管理者は、管理者が展開した LOB アドインのメタデータ変更をサポートするために、新しいマニフェスト ファイルをアップロードできます。アドインは、次にアプリケーションを起動Office更新します。 Web アプリケーションはいつでも変更できます。  
 
詳細については [、「line-of-business アドイン」を参照してください](./manage-addins-in-the-admin-center.md)。  

## <a name="can-admins-turn-off-add-ins"></a>管理者はアドインをオフにできますか?  

はい。 管理者は、Microsoft 管理センターからすべてのユーザーに展開するアドインをオンまたはオフにできます。

詳細については、「アドインの [状態」を参照してください](./manage-addins-in-the-admin-center.md#add-in-states)。  

##  <a name="can-admins-delete-or-remove-add-ins"></a>管理者はアドインを削除または削除できますか?

はい。 管理者は、Microsoft 管理センターからすべてのユーザーに展開したアドインを削除できます。

詳細については、「Delete [an add-in」を参照してください](./manage-addins-in-the-admin-center.md#delete-an-add-in)。 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>管理者は、集中展開を使用して、Officeストアから有料アドインを展開できますか? 

いいえ。 現時点では、集中展開を使用して、Officeストアから有料アドインを展開できます。  
 
マニフェスト ファイルまたは URL を要求するには、有料アドインの ISV 開発者に手を差し伸べることです。 テナント管理者は、集中展開を使用して、アドインを LOB アドインとして展開できます。
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>組織のアドインを管理するために必要な管理者の役割は何ですか?  

グローバル管理者は、アドイン管理ライフサイクルへの完全なアクセス権を持つ推奨される役割です。 他の管理者の役割では、アドイン展開ライフサイクルへのアクセスが制限されています。 Microsoft 365 for business サブスクリプションを購入したユーザーは、グローバル管理者です。 
 
サブスクリプションには、組織内の他のユーザーに割り当て可能な一連の管理者ロールが付属しています。 各管理者ロールは、一般的なビジネス機能にマップされ、組織内のユーザーが Microsoft 365 管理センターで特定のタスクを実行するためのアクセス許可を付与します。  
 
詳細については、「管理者ロールの割り [当て」を参照してください](../add-users/assign-admin-roles.md?view=o365-worldwide)。 