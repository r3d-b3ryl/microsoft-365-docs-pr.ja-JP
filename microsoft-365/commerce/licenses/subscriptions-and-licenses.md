---
title: Microsoft 365 for business のサブスクリプションとライセンスについて
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Microsoft 365 for business のサブスクリプションとライセンスについて説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 6310b3e48c59da3243746cceca2d0516f511b827
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911436"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Microsoft 365 for business のサブスクリプションとライセンスについて

Microsoft 365 for business のサブスクリプションを購入する場合は、月単位または年単位で支払う一連のアプリとサービスにサインアップします。 サブスクリプションの一部として受け取るアプリケーションとサービスは、Microsoft 365 Apps for business や Microsoft 365 Business Standard など、購入した製品によって異なっています。 各製品に付属する内容は [、Microsoft 365 の](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) 中小企業向けページで確認できます。

サブスクリプションを購入する場合、組織の人数に基づいて、必要なライセンス数を指定します。 サブスクリプションを購入した後、組織内のユーザーのアカウントを作成し、各ユーザーにライセンスを割り当てる。 組織のニーズの変化に応じて、新しいユーザーに対応するためにライセンスを追加購入したり、組織を離れるユーザーのライセンスを他のユーザーに再割り当てしたりできます。

複数のサブスクリプションがある場合、各サブスクリプションを使って異なるユーザーにライセンスを割り当てることができます。 たとえば、Microsoft 365 Business Standard サブスクリプションの一部として、すべてのユーザーをすべての Microsoft 365 アプリケーションおよびサービスに割り当てできます。 また、別の Visio サブスクリプションを使用して、ユーザーのサブセットを Visio Online に割り当てできます。

## <a name="how-many-devices-can-people-install-office-on"></a>ユーザーが Office をインストールできるデバイスは何台ですか?

サブスクリプションに次の製品が含まれる場合、各ユーザーは最大 5 台の PC または Mac、5 台のタブレット、および 5 台の電話に Office をインストールできます。

:::row:::
   :::column span="":::
        - Microsoft 365 Apps for business - Microsoft 365 Apps for enterprise - Microsoft 365 Business Standard - Microsoft 365 Business Premium - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>ユーザーにライセンスを割り当てると、何が起こりますか?

以下の表は、ライセンスをユーザーに割り当てたときに自動的に発生することを示しています。
  
|**サブスクリプションにこのサービスがある場合**|**自動的に行われます**|
|:-----|:-----|
|Exchange Online  <br/> |そのユーザーのメールボックスが作成されます。 <br/> このタスクを完了する SLA の詳細については、「 [セットアップ..」を参照してください。Microsoft 365 管理](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)センターのメッセージ 。 |
|SharePoint Online  <br/> |既定の SharePoint Online チーム サイトの編集権限がそのユーザーに割り当てられます。  <br/> |
|Skype for Business Online  <br/> |ユーザーは、ライセンスに関連付けられている機能にアクセスできます。  <br/> |
|エンタープライズ向け Microsoft  365 アプリ  <br/> |このユーザーは、Office最大 5 つの Mac または PC、5 つのタブレット、および 5 つのスマートフォンでアプリをダウンロードできます。  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>ユーザー以外のメールボックスのライセンスについて

リソース メールボックス、会議室メールボックス、共有メールボックスにライセンスを割り当てる必要はありません。ただし、記憶域のクォータが 50 ギガバイト (GB) を超えた場合は、ライセンスの割り当てが必要になります。ユーザー以外のメールボックスの詳細については、以下の記事を参照してください。
  
- [共有メールボックスを作成する](../../admin/email/create-a-shared-mailbox.md)
- [共有メールボックスからライセンスを削除する](../../admin/email/remove-license-from-shared-mailbox.md)
- [他のすべての Microsoft](/exchange/collaboration-exo/shared-mailboxes) 365 プランの Exchange Online の共有メールボックス。
- [会議室メールボックスの作成と管理](/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [備品用メールボックスの管理](/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>ライセンスを割り当てできるユーザー

個々の管理者が実行できるライセンスに関する作業は、その役割によって異なります。以下の表は、最も一般的なオプションをまとめたものです。管理者の役割と権限の詳細については、「[Office 365 の管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  
|**管理者ロール**|**ライセンスを割り当てる**|**ライセンスの割り当てを解除する**|**その他のライセンスを購入する**|**アカウントの削除**|
|:-----|:-----|:-----|:-----|:-----|
|課金管理者  <br/> |いいえ  <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |
|グローバル管理者  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |
|ライセンス管理者 <br/> |はい <br/>|はい <br/> |いいえ <br/> |いいえ <br/> |
|サービス サポート管理者  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー管理者  <br/> |はい  <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |

## <a name="related-content"></a>関連コンテンツ

[ビジネス サブスクリプションのライセンスを購入または削除](buy-licenses.md) する (記事)\
[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md)(記事)\
[ユーザーからライセンスの割り当てを解除する](../../admin/manage/remove-licenses-from-users.md) (記事)\
[共有メールボックスからライセンスを削除する](../../admin/email/remove-license-from-shared-mailbox.md) (記事)