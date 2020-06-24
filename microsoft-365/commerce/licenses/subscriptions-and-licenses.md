---
title: Microsoft 365 for business のサブスクリプションとライセンスについて
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: 'Microsoft 365 for business のサブスクリプションとライセンスについて説明し、ライセンスを割り当てることができるユーザーと、ユーザーにライセンスを割り当てるときの動作を確認します。 '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: f83b2069bd1b4c86e2198252a54ed2e8e5c55a04
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844682"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Microsoft 365 for business のサブスクリプションとライセンスについて

この記事では、サブスクリプションとライセンスの間の関係を説明し、[ライセンスを割り当てることができるユーザー](#find-out-who-can-assign-licenses)、[ライセンスを割り当てたときに発生すること](#understand-what-happens-when-you-assign-a-license-to-someone)、および[ユーザーが Office をインストールできるデバイスの数](#how-many-devices-can-people-install-office-on)についての追加情報を提供します。 また、[ユーザー以外のメールボックスのライセンスについて](#understand-licenses-for-non-user-mailboxes)へのリンクや、[ライセンス管理に関する記事](#articles-about-managing-licenses)へのリンクも含まれます。
  
Microsoft 365 for business のサブスクリプションを購入する際には、月単位または年単位で支払いを行う一連のアプリケーションとサービスにサインアップします。 サブスクリプションの一部として受信するアプリケーションとサービスは、Microsoft 365 for business または Microsoft 365 Business Standard など、購入した製品によって異なります。 各製品の内容を確認するには、「 [Microsoft 365 を購入](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)する」ページを参照してください。 

[小規模および中規模企業向けに Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)で利用可能なさまざまなライセンスオプションを確認できます。

サブスクリプションを購入する場合、組織の人数に基づいて、必要なライセンス数を指定します。 購入の完了後、ユーザーのアカウントを作成し、各ユーザーにライセンスを割り当てます。 組織のニーズの変化に応じて、新しいユーザーに対応するためにライセンスを追加購入したり、組織を離れるユーザーのライセンスを他のユーザーに再割り当てしたりできます。 

複数のサブスクリプションがある場合、各サブスクリプションを使って異なるユーザーにライセンスを割り当てることができます。 たとえば、すべてのユーザーを microsoft 365 Business Standard サブスクリプションの一部としてすべての Microsoft 365 アプリケーションおよびサービスに割り当てることができますが、ユーザーのサブセットは、個別の Visio サブスクリプションを使用して Visio Online に割り当てることもできます。 

  
## <a name="find-out-who-can-assign-licenses"></a>ライセンスを割り当てることができるユーザーを見つける

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**管理者ロール**|**ライセンスを割り当てる**|**ライセンスの削除**|**追加ライセンスの購入**|**アカウントの削除**|
|:-----|:-----|:-----|:-----|:-----|
|グローバル管理者  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |
|課金管理者  <br/> |いいえ  <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |
|ユーザー管理者  <br/> |はい  <br/> |はい  <br/> |いいえ  <br/> |○  <br/> |
|サービス管理者  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |×  <br/> |
|パスワード管理者  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a>ユーザーにライセンスを割り当てたときに行われることを理解する

以下の表は、ライセンスをユーザーに割り当てたときに自動的に発生することを示しています。
  
|**サブスクリプションにこのサービスがある場合**|**自動的に行われます**|
|:-----|:-----|
|Exchange Online  <br/> |そのユーザーのメールボックスが作成されます。  <br/> このタスクを完了するための SLA については、 [「セットアップ...」を参照してください。Microsoft 365 管理センターのメッセージ](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。 |
|SharePoint Online  <br/> |既定の SharePoint Online チーム サイトの編集権限がそのユーザーに割り当てられます。  <br/> |
|Skype for Business Online  <br/> |ライセンスに関連付けられた機能へのアクセス権がユーザーに割り当てられます。  <br/> |
|Microsoft 365 Apps for enterprise  <br/> |ユーザーは、最大 5 台の Mac または PC、5 台のタブレット、および 5 台のスマートフォンに Microsoft Office をダウンロードできます。  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a>ユーザーが Office をインストールできるデバイスは何台ですか?

サブスクリプションに以下の製品のいずれかが含まれている場合、各ユーザーは、最大 5 台の PC または Mac、5 台のタブレット、および 5 台のスマートフォンに Office をインストールできます。
  
- Microsoft 365 Apps for business
    
- Microsoft 365 Business Standard
    
- Microsoft 365 Apps for enterprise
    
- Office 365 Enterprise E3
    
- Office 365 Enterprise E5
    
## <a name="understand-licenses-for-non-user-mailboxes"></a>ユーザー以外のメールボックスのライセンスについて

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [共有メールボックスを作成する](../../admin/email/create-a-shared-mailbox.md)
    
- 他のすべての Microsoft 365 プランの[Exchange Online の共有メールボックス](https://go.microsoft.com/fwlink/p/?linkid=847433)。 
    
- [会議室メールボックスの作成と管理](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [備品用メールボックスの管理](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a>ライセンスの管理に関する記事

- [ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md)
    
- [ユーザーからライセンスを削除する](../../admin/manage/remove-licenses-from-users.md)
    
- [サブスクリプションのライセンスを購入する](buy-licenses.md)
    
- [別のサブスクリプションを購入する](../buy-another-subscription.md)
    
- [アドオンを購入または編集する](../buy-or-edit-an-add-on.md)
    
- [サブスクリプションからライセンスを削除する](remove-licenses-from-subscription.md)
    
- [ライセンスの競合を解決する](../../admin/manage/resolve-license-conflicts.md)
    
- [Yammer ユーザー ライセンスを管理する](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
