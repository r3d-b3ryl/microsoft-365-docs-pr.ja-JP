---
title: ビジネス向けサブスクリプションとライセンスMicrosoft 365理解する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: 受け取るアプリケーションとサービスは、購入Microsoft 365製品によって異Microsoft 365 Apps for business。
ms.date: 07/01/2020
ms.openlocfilehash: 29a56ecfc1cb2f3cbe3afebec552fff29905675b
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756566"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>ビジネス向けサブスクリプションとライセンスMicrosoft 365理解する

ビジネス向け Microsoft 365 サブスクリプションを購入する場合は、月単位または年単位で支払う一連のアプリとサービスにサインアップします。 サブスクリプションの一部として受け取るアプリケーションとサービスは、購入した製品 (サブスクリプションやサービスなど) によってMicrosoft 365 Apps for business Microsoft 365 Business Standard。 各製品に付属する内容は、Microsoft 365中規模のビジネス向けページ[で確認](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)できます。

サブスクリプションを購入する場合、組織の人数に基づいて、必要なライセンス数を指定します。 サブスクリプションを購入した後、組織内のユーザーのアカウントを作成し、各ユーザーにライセンスを割り当てる。 組織のニーズの変化に応じて、新しいユーザーに対応するためにライセンスを追加購入したり、組織を離れるユーザーのライセンスを他のユーザーに再割り当てしたりできます。

複数のサブスクリプションがある場合、各サブスクリプションを使って異なるユーザーにライセンスを割り当てることができます。 たとえば、すべてのユーザーをすべてのユーザーに、Microsoft 365サブスクリプションの一部としてMicrosoft 365 Business Standardできます。 また、ユーザーのサブセットを別のサブスクリプションVisioオンラインに割りVisioできます。

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
|Exchange Online  <br/> |そのユーザーのメールボックスが作成されます。 <br/> このタスクを完了する SLA の詳細については、「[セットアップ..」を参照してください。のメッセージをMicrosoft 365 管理センター。](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center) |
|SharePoint Online  <br/> |既定の SharePoint Online チーム サイトの編集権限がそのユーザーに割り当てられます。  <br/> |
|Skype for Business Online  <br/> |ユーザーは、ライセンスに関連付けられている機能にアクセスできます。  <br/> |
|エンタープライズ向け Microsoft 365 アプリ  <br/> |ユーザーは、最大 5 Officeの Mac または PC、5 つのタブレット、および 5 つのスマートフォンでアプリをダウンロードできます。  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>ユーザー以外のメールボックスのライセンスについて

リソース メールボックス、会議室メールボックス、共有メールボックスにライセンスを割り当てる必要はありません。ただし、記憶域のクォータが 50 ギガバイト (GB) を超えた場合は、ライセンスの割り当てが必要になります。ユーザー以外のメールボックスの詳細については、以下の記事を参照してください。
  
- [共有メールボックスを作成する](../../admin/email/create-a-shared-mailbox.md)
- [共有メールボックスからライセンスを削除する](../../admin/email/remove-license-from-shared-mailbox.md)
- [他のすべてのプランExchange Online](/exchange/collaboration-exo/shared-mailboxes)共有メールボックスMicrosoft 365します。

## <a name="who-can-assign-licenses"></a>Who割り当て可能ですか?

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
