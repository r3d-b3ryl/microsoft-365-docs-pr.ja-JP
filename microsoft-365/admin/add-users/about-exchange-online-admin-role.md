---
title: Exchange管理者ロールについて
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: Exchange管理者は、組織の電子メールとメールボックスを管理し、たとえば、ユーザーのメールボックス内の削除済みアイテムを回復します。
ms.openlocfilehash: 375e2d6a1bf08ab310da28233deaf5dbbbae9be7
ms.sourcegitcommit: 7ab324551afac4fd82abc015247371ebfe6ccac2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65842259"
---
# <a name="about-the-exchange-administrator-role"></a>Exchange管理者ロールについて

Microsoft 365を管理するために、Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">管理センター</a>から組織のメールとメールボックスを管理するためのアクセス許可をユーザーに[割り当てることができます](assign-admin-roles.md)。 これを行うには、Exchange管理者ロールに割り当てます。
  
> [!TIP]
> Exchange管理者ロールにユーザーを割り当てる場合は、サービス サポート管理者ロールに割り当てることをお勧めします。 これにより、ユーザーは Microsoft 365 管理センター での重要な情報 (Exchange Online サービスの正常性など) の確認や、通知内容の変更および通知のリリースを行うことができます。

ユーザーがExchange管理者ロールに割り当てられたときに実行できる主なタスクの一部を次に示します。
  
- [ユーザーのメールボックスで削除済みアイテムを復元する - 管理者ヘルプ](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [組織内のメールボックスのアーカイブポリシーと削除ポリシーを設定します](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)。

- メールボックスの機能をセットアップします。たとえば、メールボックス共有ポリシーを設定すると、ユーザーが予定表や連絡先の情報を組織外の人とどのように共有できるかを指定できます。

- 他のユーザーのメールボックスに対して "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" と "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" デリゲートを設定します。 たとえば、経営幹部は、メールの送信を代理でアシスタントに行ってもらう場合があります。

- [共有メールボックスを作成](../email/create-a-shared-mailbox.md) して、ユーザーのグループが共通の電子メール アドレスからメールを監視および送信できるようにします。

- 組織[の電子メールスパム対策保護](../../security/office-365-security/anti-spam-protection.md)とマルウェア フィルター。

- Microsoft 365 グループを管理する

## <a name="exchange-online-role-groups"></a>Exchange Online の役割グループ

大規模な組織では、Exchange 管理者がユーザーを Exchange の役割グループに割り当てることがあります。役割グループに追加されたユーザーは、そのグループのメンバーだけに許可されている、特定のビジネス機能を実行できるようになります。
  
 たとえば、証拠開示管理という役割グループに割り当てられたユーザーは、メールボックスの検索を実行して条件に一致するデータを得ることができます。詳細については、「 [Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」と「[役割グループの管理](/exchange/manage-role-groups-exchange-2013-help)」を参照してください。
  
## <a name="learn-about-other-admin-roles"></a>その他の管理者ロールについて学習する

- [Microsoft 365 管理者ロールについて](about-admin-roles.md)

- [SharePoint Online 管理者の役割について](/sharepoint/sharepoint-admin-role)

- [Skype for Business 管理者の役割について](/skypeforbusiness/skype-for-business-online)

- [管理者ロールMicrosoft Teams使用する](/MicrosoftTeams/using-admin-roles)
