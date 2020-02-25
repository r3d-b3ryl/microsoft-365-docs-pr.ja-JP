---
title: 一般法人向け Office 365 のサブスクリプションとライセンスを理解する
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
description: '一般法人向け Office 365 のサブスクリプションとライセンスについて説明し、ライセンスを割り当てることができるユーザーと、ユーザーにライセンスを割り当てるときの動作を確認します。 '
ms.custom: okr_SMB
ms.openlocfilehash: 1a90e4b80322ad075f2149801aebd02ac07a2aef
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242321"
---
# <a name="understand-subscriptions-and-licenses-in-office-365-for-business"></a>一般法人向け Office 365 のサブスクリプションとライセンスを理解する

この記事では、サブスクリプションとライセンスの関係について説明し、ライセンスを[割り当てることができるユーザー](#find-out-who-can-assign-licenses)と、ユーザー[が Office をインストールできるデバイスの数](#how-many-devices-can-people-install-office-on)についての追加情報を提供します。 [](#understand-what-happens-when-you-assign-a-license-to-someone) また、[ユーザー以外のメールボックスのライセンスを理解](#understand-licenses-for-non-user-mailboxes)し、[ライセンスの管理に関する記事](#articles-about-managing-licenses)へのリンクも含まれています。
  
一般法人向け Office 365 のサブスクリプションを購入する場合は、月単位または年単位のいずれかで支払いを行う一連のアプリケーションとサービスにサインアップします。 サブスクリプションの一部として受信するアプリケーションおよびサービスは、Office 365 Business または Office 365 Business Premium など、購入した製品によって異なります。 [ [Office の購入 365] ページ](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)では、各製品の内容を確認できます。 

サブスクリプションを購入する場合、組織の人数に基づいて、必要なライセンス数を指定します。 購入の完了後、ユーザーのアカウントを作成し、各ユーザーにライセンスを割り当てます。 組織のニーズが変化した場合は、新しいユーザーに対応するためにライセンスを追加したり、他のユーザーが組織を離れたときにライセンスを他のユーザーに再割り当てしたりできます。 

複数のサブスクリプションがある場合、各サブスクリプションを使って異なるユーザーにライセンスを割り当てることができます。 たとえば、すべてのユーザーを Office 365 Business Premium サブスクリプションの一部として、すべての Office 365 アプリケーションとサービスに割り当てることができますが、ユーザーのサブセットは個別の Visio サブスクリプションを使用して Visio Online に割り当てることもできます。 

  
## <a name="find-out-who-can-assign-licenses"></a>ライセンスを割り当てることができるユーザーを見つける

個々の管理者が実行できるライセンスに関する作業は、その役割によって異なります。以下の表は、最も一般的なオプションをまとめたものです。管理者の役割と権限の詳細については、「[Office 365 の管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  
|**管理者の役割**|**ライセンスの割り当て**|**ライセンスの削除**|**追加ライセンスの購入**|**アカウントの削除**|
|:-----|:-----|:-----|:-----|:-----|
|グローバル管理者  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |
|課金管理者  <br/> |いいえ  <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |
|ユーザー管理者  <br/> |はい  <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |
|サービス管理者  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|パスワード管理者  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a>ユーザーにライセンスを割り当てたときに行われることを理解する

以下の表は、ライセンスをユーザーに割り当てたときに自動的に発生することを示しています。
  
|**サブスクリプションにこのサービスがある場合**|**自動的に行われます**|
|:-----|:-----|
|Exchange Online  <br/> |そのユーザーのメールボックスが作成されます。  <br/> |
|SharePoint Online  <br/> |既定の SharePoint Online チーム サイトの編集権限がそのユーザーに割り当てられます。  <br/> |
|Skype for Business Online  <br/> |ライセンスに関連付けられた機能へのアクセス権がユーザーに割り当てられます。  <br/> |
|Office 365 ProPlus  <br/> |ユーザーは、最大 5 台の Mac または PC、5 台のタブレット、および 5 台のスマートフォンに Microsoft Office をダウンロードできます。  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a>ユーザーが Office をインストールできるデバイスは何台ですか?

サブスクリプションに以下の製品のいずれかが含まれている場合、各ユーザーは、最大 5 台の PC または Mac、5 台のタブレット、および 5 台のスマートフォンに Office をインストールできます。
  
- Office 365 Business
    
- Office 365 Business Premium
    
- Office 365 ProPlus
    
- Office 365 Enterprise E3
    
- Office 365 Enterprise E5
    
## <a name="understand-licenses-for-non-user-mailboxes"></a>ユーザー以外のメールボックスのライセンスについて

リソース メールボックス、会議室メールボックス、共有メールボックスにライセンスを割り当てる必要はありません。ただし、記憶域のクォータが 50 ギガバイト (GB) を超えた場合は、ライセンスの割り当てが必要になります。ユーザー以外のメールボックスの詳細については、以下の記事を参照してください。
  
- [共有メールボックスを作成する](../../admin/email/create-a-shared-mailbox.md)
    
- [Exchange Online の共有メールボックス](https://go.microsoft.com/fwlink/p/?linkid=847433) (他のすべての Office 365 プランの場合) 
    
- [会議室メールボックスの作成と管理](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [備品用メールボックスの管理](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a>ライセンス管理に関する記事

- [ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md)
    
- [ユーザーからライセンスを削除する](../../admin/manage/remove-licenses-from-users.md)
    
- [サブスクリプションのライセンスを購入する](buy-licenses.md)
    
- [別のサブスクリプションを購入する](../buy-another-subscription.md)
    
- [アドオンを購入または編集する](../buy-or-edit-an-add-on.md)
    
- [サブスクリプションからライセンスを削除する](remove-licenses-from-subscription.md)
    
- [ライセンスの競合を解決する](../../admin/manage/resolve-license-conflicts.md)
    
- [Yammer ユーザーライセンスを管理する](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
