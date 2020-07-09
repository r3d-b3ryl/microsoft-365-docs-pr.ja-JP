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
description: Microsoft 365 管理センターからの一元展開についてよく寄せられる質問に対する回答を確認してください。
ms.openlocfilehash: 2d9a3c6f2cfe9418cc83cbd0f29537e5533c4257
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083564"
---
# <a name="centralized-deployment-faq"></a>一元展開に関する FAQ

一元展開は、Office 365 管理者が Office アドイン (Word、Excel、PowerPoint、および Outlook) を組織内のユーザーとグループに展開する場合に推奨される方法です。これは、この記事で説明されているように、一元展開を使用するためのすべての要件を組織が満たしている場合です。   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>組織で一元展開が設定されているかどうかを確認する方法  

アドインを一元展開するには、ユーザーが Microsoft 365 Apps for enterprise (組織のログイン資格情報を使用して Office にサインインしている) を使用しており、Exchange Online メールボックスを持っている必要があります。 サブスクリプションディレクトリは、Azure Active Directory に存在するか、フェデレーションされている必要があります。  
 
一元展開は、オンラインメールボックスでのみサポートされます。 オンプレミスの Exchange メールボックスへの展開はサポートされていません。
 
[一元展開の互換性チェック](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   を使用して、サブスクリプションが対象になるかどうかを判断できます。 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>一元展開を使用してアドインユーザーの割り当てをどのように対象にしていますか。  

一元展開では、テナント内の個々のユーザー、グループ、および全員への割り当てがサポートされます。 階層型展開は、最上位のグループまたは親グループのないグループのユーザーに使用できますが、親グループを持つグループまたはグループのユーザーには使用できません。 一元展開は、Office 365 グループ、配布リスト、セキュリティグループなど、ほとんどの Azure Active Directory グループの一部でもあります。  

管理を容易にするには、個別のユーザー割り当てではなく、グループの割り当てを使用することをお勧めします。
 
詳細については、「[ユーザーとグループの割り当て](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)」を参照してください。  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>アドインがすべてのユーザーに対して表示されるまでにどのくらいの時間がかかりますか?  

すべてのユーザーに対してアドインが表示されるまでに最大24時間かかる場合があります。 これには、アドインの更新に対して同じ時間、オン/オフの切り替え、またはアドインの削除による変更を行うことができます。 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>管理者として、組織のアドインへのユーザーアクセスを管理するにはどうすればよいですか?

ユーザー、グループ、または組織全体にアドインを簡単に展開するには、管理者が一元展開を使用することをお勧めします。

ユーザーアクセスの管理の詳細については、「」を参照してください。 </br>[すべてのクライアント (Outlook を除く) に対して Office ストアをオフにして、アドインのダウンロードを禁止する](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) </br>[Outlook 用のアドインをインストールおよび管理できる管理者とユーザーを指定](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN)します。

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>一元展開によって、管理者は Outlook アドインの展開方法を柔軟に選択できるようになりますか。  

はい。 一元展開を使用すると、管理者はアドインの展開時に Outlook アドインの3つの展開方法のうちの1つを柔軟に選択できます。

**Fixed (既定値)**  アドインは、割り当てられたユーザーに自動的に展開され、削除することはできません。  
 
**利用可能**ユーザーは、[ホーム] を選択してアドインを Outlook にインストールし、管理者によって管理されたアドイン > > します。   
 
**省略可能**アドインは、割り当てられたユーザーに自動的に展開されますが、削除することもできます。  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>管理者は基幹業務 (LOB) アドインを更新できますか?  

はい。 管理者が展開した LOB アドインのメタデータ変更をサポートするために、管理者は新しいマニフェストファイルをアップロードできます。アドインは、次に Office アプリケーションが起動したときに更新されます。 Web アプリケーションはいつでも変更できます。  
 
詳細については、「[基幹業務アドイン](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins)」を参照してください。  

## <a name="can-admins-turn-off-add-ins"></a>管理者がアドインをオフにできるか  

はい。 管理者は、Microsoft 管理センターからすべてのユーザーに対して展開するアドインをオンまたはオフにすることができます。

詳細については、「[アドインの状態](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states)」を参照してください。  

##  <a name="can-admins-delete-or-remove-add-ins"></a>管理者がアドインを削除または削除できるかどうか。

はい。 管理者は、Microsoft 管理センターからすべてのユーザー向けに展開したアドインを削除できます。

詳細については、「[アドインを削除する](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in)」を参照してください。 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>管理者は一元展開を使用して、Office ストアから有料のアドインを展開できますか。 

いいえ。 現時点では、一元展開を使用して、Office ストアから有料のアドインを展開することはできません。  
 
マニフェストファイルまたは URL を要求するには、有料アドインの ISV 開発者に確認することをお勧めします。 テナント管理者は、一元展開を使用して、アドインを LOB アドインとして展開できます。
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>組織のアドインを管理するには、どの管理者の役割を使用する必要がありますか。  

アドインを管理するには、グローバル管理者の役割を持っている必要があります。Microsoft 365 for business サブスクリプションを購入したユーザーである場合は、グローバル管理者になります。 
 
サブスクリプションには、組織内の他のユーザーに割り当てることができる一連の管理者ロールが付属しています。 各管理役割は、一般的なビジネス機能にマップされ、組織内のユーザーに Microsoft 365 管理センターで特定のタスクを実行するためのアクセス許可を付与します。  
 
詳細については、「[管理者ロールを割り当てる](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)」を参照してください。  