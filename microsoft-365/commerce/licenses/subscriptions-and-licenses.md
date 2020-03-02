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
description: '一般法人向け Office 365 のサブスクリプションとライセンスについて学習し、ライセンスを割り当てることができるユーザー、およびライセンスを割り当てたときに発生することを把握します。 '
ms.custom: okr_SMB
ms.openlocfilehash: 1a90e4b80322ad075f2149801aebd02ac07a2aef
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242321"
---
# <a name="understand-subscriptions-and-licenses-in-office-365-for-business"></a>一般法人向け Office 365 のサブスクリプションとライセンスを理解する

この記事では、サブスクリプションとライセンスの間の関係を説明し、[ライセンスを割り当てることができるユーザー](#find-out-who-can-assign-licenses)、[ライセンスを割り当てたときに発生すること](#understand-what-happens-when-you-assign-a-license-to-someone)、および[ユーザーが Office をインストールできるデバイスの数](#how-many-devices-can-people-install-office-on)についての追加情報を提供します。 また、[ユーザー以外のメールボックスのライセンスについて](#understand-licenses-for-non-user-mailboxes)へのリンクや、[ライセンス管理に関する記事](#articles-about-managing-licenses)へのリンクも含まれます。
  
一般法人向け Office 365 のサブスクリプションを購入すると、月間または年間単位で支払うアプリケーションおよびサービスにサインアップします。 サブスクリプションの一部として受け取るアプリケーションおよびサービスは、Office 365 Business や Office 365 Business Premium など、購入した製品によって異なります。 [Office 365 の購入ページ](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)で、各製品に付属しているものを確認できます。 

サブスクリプションを購入する場合、組織の人数に基づいて、必要なライセンス数を指定します。 購入の完了後、ユーザーのアカウントを作成し、各ユーザーにライセンスを割り当てます。 組織のニーズの変化に応じて、新しいユーザーに対応するためにライセンスを追加購入したり、組織を離れるユーザーのライセンスを他のユーザーに再割り当てしたりできます。 

複数のサブスクリプションがある場合、各サブスクリプションを使って異なるユーザーにライセンスを割り当てることができます。 たとえば、すべてのユーザーを Office 365 Business Premium サブスクリプションの一部としてすべての Office 365 アプリケーションとサービスに割り当てることができますが、ユーザーのサブセットを別の Visio サブスクリプションを通じて Visio Online に割り当てることもできます。 

  
## <a name="find-out-who-can-assign-licenses"></a>ライセンスを割り当てることができるユーザーを見つける

個々の管理者が実行できるライセンスに関する作業は、その役割によって異なります。以下の表は、最も一般的なオプションをまとめたものです。管理者の役割と権限の詳細については、「[Office 365 の管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  
|管理者ロール|ライセンスを割り当てる|ライセンスの削除|追加ライセンスの購入|**アカウントの削除**|
|:-----|:-----|:-----|:-----|:-----|
|グローバル管理者  <br/> |○  <br/> |はい  <br/> |はい  <br/> |○  <br/> |
|課金管理者  <br/> |×  <br/> |いいえ  <br/> |はい  <br/> |×  <br/> |
|ユーザー管理者  <br/> |○  <br/> |はい  <br/> |いいえ  <br/> |○  <br/> |
|サービス管理者  <br/> |×  <br/> |いいえ  <br/> |いいえ  <br/> |×  <br/> |
|パスワード管理者  <br/> |×  <br/> |いいえ  <br/> |いいえ  <br/> |なし  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a>ユーザーにライセンスを割り当てたときに行われることを理解する

以下の表は、ライセンスをユーザーに割り当てたときに自動的に発生することを示しています。
  
|サブスクリプションにこのサービスがある場合|自動的に行われます|
|:-----|:-----|
|Exchange Online  <br/> |そのユーザーのメールボックスが作成されます。  <br/> |
|SharePoint Online  <br/> |既定の  チーム サイトの編集権限がそのユーザーに割り当てられます。  <br/> |
|Skype for Business Online  <br/> |ライセンスに関連付けられた機能へのアクセス権がユーザーに割り当てられます。  <br/> |
|Office 365 ProPlus  <br/> |ユーザーは、最大 5 台の Mac または PC、5 台のタブレット、および 5 台のスマートフォンに  をダウンロードできます。  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a>ユーザーが Office をインストールできるデバイスは何台ですか?

サブスクリプションに以下の製品のいずれかが含まれている場合、各ユーザーは、最大 5 台の PC または Mac、5 台のタブレット、および 5 台のスマートフォンに  をインストールできます。
  
- Office 365 Business
    
- Office 365 Business Premium
    
- Office 365 ProPlus
    
- Office 365 Enterprise E3
    
- Office 365 Enterprise E5
    
## <a name="understand-licenses-for-non-user-mailboxes"></a>ユーザー以外のメールボックスのライセンスについて

リソース メールボックス、会議室メールボックス、共有メールボックスにライセンスを割り当てる必要はありません。ただし、記憶域のクォータが 50 ギガバイト (GB) を超えた場合は、ライセンスの割り当てが必要になります。ユーザー以外のメールボックスの詳細については、以下の記事を参照してください。
  
- [共有メールボックスを作成する](../../admin/email/create-a-shared-mailbox.md)
    
- [
            ](https://go.microsoft.com/fwlink/p/?linkid=847433)Exchange Online の共有メールボックス (他のすべての  プランの場合) 
    
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
