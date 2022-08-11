---
title: Microsoft 365 for Business のサブスクリプションとライセンスについて
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: 受け取るアプリケーションとサービスは、Microsoft 365 Apps for businessなど、購入した Microsoft 365 製品によって異なります。
ms.date: 05/12/2022
ms.openlocfilehash: 2d5b35bd4696e25aa1372dea0ac1bdd0371f0ef5
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "67281314"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Microsoft 365 for Business のサブスクリプションとライセンスについて

Microsoft 365 for Business のサブスクリプションを購入すると、定期的に支払うアプリとサービスのセットにサインアップします。 サブスクリプションの一部として受け取るアプリケーションとサービスは、Microsoft 365 Apps for businessやMicrosoft 365 Business Standardなど、購入した製品によって異なります。 各製品に付属する内容は、 [Microsoft 365 の中小企業向け](https://www.microsoft.com/microsoft-365/business/compare-all-microsoft-365-business-products) ページで確認できます。

サブスクリプションを購入する場合、組織の人数に基づいて、必要なライセンス数を指定します。 サブスクリプションを購入した後、組織内のユーザーのアカウントを作成し、各ユーザーにライセンスを割り当てます。 組織のニーズの変化に応じて、新しいユーザーに対応するためにライセンスを追加購入したり、組織を離れるユーザーのライセンスを他のユーザーに再割り当てしたりできます。

複数のサブスクリプションがある場合、各サブスクリプションを使って異なるユーザーにライセンスを割り当てることができます。 たとえば、Microsoft 365 Business Standard サブスクリプションの一部として、すべてのユーザーをすべての Microsoft 365 アプリケーションとサービスに割り当てることができます。 別の Visio サブスクリプションを使用して、ユーザーのサブセットを Visio Online に割り当てることもできます。

## <a name="how-many-devices-can-people-install-office-on"></a>ユーザーが Office をインストールできるデバイスは何台ですか?

サブスクリプションに次のいずれかの製品が含まれている場合、各ユーザーは最大 5 台の PC または Mac、5 台のタブレット、5 台の携帯電話に Office をインストールできます。

:::row:::
   :::column span="":::
        - Microsoft 365 Apps for business - Microsoft 365 Apps for enterprise - Microsoft 365 Business Standard - Microsoft 365 Business Premium -Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>他のユーザーにライセンスを割り当てるとどうなりますか?

以下の表は、ライセンスをユーザーに割り当てたときに自動的に発生することを示しています。
  
|サブスクリプションにこのサービスがある場合|自動的に行われます|
|---|---|
|Exchange Online|そのユーザーのメールボックスが作成されます。 <br/> このタスクを完了するための SLA については、「[セットアップ..」を参照してください。Microsoft 365 管理センター内のメッセージ](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。|
|SharePoint Online|既定の SharePoint Online チーム サイトの編集権限がそのユーザーに割り当てられます。|
|Microsoft Teams|ユーザーは、ライセンスに関連付けられている機能にアクセスできます。|
|Microsoft 365 Apps for enterpriseとMicrosoft 365 Apps for business|最大 5 台の Mac または PC、5 台のタブレット、5 台のスマートフォンで Office アプリをダウンロードできます。|

## <a name="understand-licenses-for-non-user-mailboxes"></a>ユーザー以外のメールボックスのライセンスについて

リソース メールボックス、会議室メールボックス、共有メールボックスにライセンスを割り当てる必要はありません。ただし、記憶域のクォータが 50 ギガバイト (GB) を超えた場合は、ライセンスの割り当てが必要になります。ユーザー以外のメールボックスの詳細については、以下の記事を参照してください。
  
- [共有メールボックスを作成する](../../admin/email/create-a-shared-mailbox.md)
- [共有メールボックスからライセンスを削除する](../../admin/email/remove-license-from-shared-mailbox.md)
- 他のすべての Microsoft 365 プラン[のExchange Onlineの共有メールボックス](/exchange/collaboration-exo/shared-mailboxes)。

## <a name="who-can-assign-licenses"></a>ライセンスを割り当てることができるユーザー

個々の管理者が実行できるライセンスに関する作業は、その役割によって異なります。以下の表は、最も一般的なオプションをまとめたものです。管理者の役割と権限の詳細については、「[Office 365 の管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  
|管理者ロール|ライセンスを割り当てる|ライセンスの割り当てを解除する|追加ライセンスを購入する|アカウントの削除|
|---|:---:|:---:|:---:|:---:|
|課金管理者|いいえ|不要|はい|不要|
|グローバル管理者|はい|はい|はい|はい|
|ライセンス管理者|はい|はい|不要|不要|
|サービス サポート管理者|不要|不要|不要|不要|
|ユーザー管理者|はい|はい|不要|はい|

## <a name="related-content"></a>関連コンテンツ

[ビジネス サブスクリプションのライセンスを購入または削除](buy-licenses.md) する (記事)\
[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md)(記事)\
[ユーザーからライセンスの割り当てを解除する](../../admin/manage/remove-licenses-from-users.md) (記事)\
[共有メールボックスからライセンスを削除する](../../admin/email/remove-license-from-shared-mailbox.md) (記事)
