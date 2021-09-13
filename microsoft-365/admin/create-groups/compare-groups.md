---
title: グループを比較する
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Microsoft 365 グループでは、メンバーは会話用のグループ メールおよび共有ワークスペース、ファイル、カレンダー イベント、ストリーム、Planner を利用できます。
ms.openlocfilehash: 0b622f791de7615e45e49faec47558b0e67067f2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176784"
---
# <a name="compare-groups"></a>グループを比較する

Microsoft 365 管理センターの <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**[グループ]**</a> セクションでは、次の種類のグループを作成および管理できます。 

- **Microsoft 365 グループ** は、社内外のユーザー間での共同作業に使用されます。 これには、SharePoint や Planner などのコラボレーション サービスが含まれます。
- **配布グループ** は、ユーザーのグループにメール通知を送信するのに使用されます。
- **セキュリティ グループ** は、SharePoint サイトなどのリソースへのアクセスを許可するために使用されます。
- **メールが有効なセキュリティ グループ** は、SharePoint などのリソースへのアクセスを許可し、それらのユーザーにメールで通知を送信するために使用されます。
- **共有メールボックス** は、会社情報やサポート メール アドレスなど、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。

一部のグループでは、動的メンバーシップまたはメールが許可されます。

||Microsoft 365 グループ|配布グループ|セキュリティ グループ|メールが有効なセキュリティ グループ|共有メールボックス|
|:----|:----|:----|:----|:----|:----|
|**メールが有効**|はい|はい|いいえ|はい|はい|
|**Azure AD での動的メンバーシップ**|はい|いいえ|はい|いいえ|なし|

これらのグループの種類はすべて、Power Automate で使用できます。

## <a name="microsoft-365-groups"></a>Microsoft 365 グループ

Microsoft 365 グループは、社内外のユーザー間での共同作業に使用されます。 各 Microsoft 365 グループでは、メンバーは会話用のグループ メールおよび共有ワークスペース、ファイル、カレンダー イベント、ストリーム、Planner を利用できます。

[管理者によって有効にされている](manage-guest-access-in-groups.md)限り、組織の外部のユーザーをグループに追加できます。 外部の送信者がグループのメール アドレスにメールを送信できるようにすることもできます。

Microsoft 365 グループは [Azure Active Directory の動的メンバーシップ用に構成でき](/azure/active-directory/users-groups-roles/groups-change-type)、部署、場所、役職などのユーザー属性に基づいてグループ メンバーを自動的に追加または削除できます。

Microsoft 365 グループには、Outlook for iOS や Outlook for Android などのモバイル アプリからアクセスできます。

グループ メンバーは、[管理者によって有効にされている](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)場合、グループのメール アドレスとして送信したり、グループのメール アドレスの代わりに送信したりできます。

Microsoft 365 グループは、他の Microsoft 365 グループ、または配布グループやセキュリティ グループとのネストをサポートしていません。

## <a name="distribution-groups"></a>配布グループ

[配布グループ](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)は、ユーザーのグループに通知を送信するのに使用されます。 管理者によって有効にされている場合、外部メールを受信できます。

配布グループは、"建物 A のユーザー" や "Contoso の全員" など、一連のユーザーに情報をブロードキャストする必要がある状況に最適です。

配布グループは、[Microsoft 365 グループ](../manage/upgrade-distribution-lists.md)にアップグレードできます。

配布グループは、Microsoft Teams のチームに追加できます。

Microsoft 365 グループは、配布グループのメンバーにすることはできません。

## <a name="security-groups"></a>セキュリティ グループ

[セキュリティ グループ](../email/create-edit-or-delete-a-security-group.md)は、SharePoint などの Microsoft 365 リソースへのアクセスを許可するために使用されます。 ユーザーを各リソースに個別に追加するのではなく、グループを管理するだけで済むため、管理が容易になります。

セキュリティ グループには、ユーザーまたはデバイスを含めることができます。デバイス用のセキュリティ グループの作成は、Intune などのモバイル デバイス管理サービスで使用できます。

セキュリティ グループは [Azure Active Directory の動的メンバーシップ用に構成でき](/azure/active-directory/users-groups-roles/groups-change-type)、部署、場所、役職などのユーザー属性、またはオペレーティング システムのバージョンなどのデバイス属性に基づいてグループ メンバーまたはデバイスを自動的に追加または削除できます。

セキュリティ グループをチームに追加できます。

Microsoft 365 グループは、セキュリティ グループのメンバーにすることはできません。

## <a name="mail-enabled-security-groups"></a>メールが有効なセキュリティ グループ

メールが有効なセキュリティ グループは通常のセキュリティ グループと同じように機能しますが、Azure Active Directory で動的に管理できず、デバイスを含めることができません。

グループのすべてのメンバーにメールを送信する機能が含まれます。

メール対応のセキュリティ グループをチームに追加できます。

## <a name="shared-mailboxes"></a>共有メールボックス

[共有メールボックス](../email/create-a-shared-mailbox.md)は、会社情報やサポート メール アドレス、受付デスク、または複数のユーザーが共有する可能性のあるその他の機能など、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。

管理者が有効にしている場合、共有メールボックスは外部メールを受信できます。

共有メールボックスには、コラボレーションに使用できる予定表が含まれています。

グループ メールボックスへのアクセス許可を持つユーザーは、管理者がそのユーザーに対して必要なアクセス許可を付与している場合、メールボックスのメール アドレスとして送信したり、メールボックスのメール アドレスの代わりに送信したりできます。 これは、ユーザーが "Contoso サポート" や "建物 A の受付デスク" からメールを送信できるため、ヘルプとサポートのメールボックスとして特に役立ちます。

現在、共有メールボックスを Microsoft 365 グループに移行することはできません。 

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 グループについて](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Outlook で配布リストを Microsoft 365 グループにアップグレードする](/microsoft-365/admin/manage/upgrade-distribution-lists)

[Outlook で配布リストをグループにアップグレードする理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
