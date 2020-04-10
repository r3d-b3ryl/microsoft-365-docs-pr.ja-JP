---
title: 共有メールボックスについて
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスは、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。 共有メールボックスを作成する前に知っておく必要のある情報について説明します。
ms.openlocfilehash: 8e9e4b1ae0235886a9dbb5b39ad4c0f78c27b53f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210542"
---
# <a name="about-shared-mailboxes"></a>共有メールボックスについて

共有メールボックスは、会社情報やサポート メール アドレス、受付デスク、または複数のユーザーが共有する可能性のあるその他の機能など、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。

グループ メールボックスへのアクセス許可を持つユーザーは、管理者がそのユーザーに対して必要なアクセス許可を付与している場合、メールボックスのメール アドレスとして送信したり、メールボックスのメール アドレスの代わりに送信したりできます。 これは、ユーザーが「Contoso Support」または「受付デスクを構築」から電子メールを送信できるため、ヘルプとサポートメールボックスに特に役立ちます。

[共有メールボックスを作成](create-a-shared-mailbox.md)する前に、次の点を理解しておく必要があります。

- **ライセンス:** 共有メールボックスには、ライセンスを割り当てなくても最大 50 GB のデータを格納できます。 その後に、より多くのデータを格納するには、メールボックスにライセンスを割り当てる必要があります。 共有メールボックスのライセンスの詳細については、「 [Exchange Online の制限](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)」を参照してください。 共有メールボックスが記憶域の上限に達した場合、しばらくはメールを受信できますが、新しいメールを送信できなくなります。 その後、メールも受信できなくなります。 そのメールボックスにメールを送信したユーザーには、配信不能エラーが送信されます。

- **ユーザー権限:** ユーザーに共有メールボックスを使用する権限 (メンバーシップ) を付与する必要があります。 組織内のユーザーのみが共有メールボックスを使用できます。

- **外部ユーザー:** 会社外のユーザー (Gmail アカウントを持つユーザーなど) に共有メールボックスへのアクセス権を付与することはできません。 この操作を行う必要がある場合は、代わりに Outlook 用グループを作成することを検討してください。 詳細については、「[管理センターで Office 365 グループを作成する](../create-groups/create-groups.md)」を参照してください。

-  **Outlook で使用:** ブラウザーから web 上の Outlook を使用して共有メールボックスにアクセスするだけでなく、Outlook for iOS アプリまたは Outlook for Android アプリを使用することもできます。 詳細については、「<a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">共有メールボックスを Outlook mobile に追加</a>する」を参照してください。 別の方法として、共有メールボックスのグループを作成することもできます。 詳細については、「[グループを比較](../create-groups/compare-groups.md)する」を参照してください。  

- **暗号化:** 共有メールボックスから送信された電子メールを暗号化することはできません。 これは、共有メールボックスには独自のセキュリティコンテキスト (username/password) が含まれていないため、キーを割り当てることができないためです。 複数のユーザーがメンバーであり、自分のキーで暗号化された電子メールを送信または受信した場合、他のメンバーが電子メールの暗号化に使用された公開キーによっては電子メールを読むことができますが、そうでない場合があります。

- **メールボックスの変換:** ユーザーメールボックスを共有メールボックスに変換することができます。 「[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)」を参照してください。

- **管理者の役割:** グローバル管理者または Exchange 管理者の役割を持つユーザーは、共有メールボックスを作成できます。

- **サブスクリプションの要件:** 共有メールボックスを作成するには、電子メールを含む Office 365 for business プラン (Exchange Online サービス) を購読する必要があります。 Office 365 Business サブスクリプションには、電子メールは含まれていません。Office 365 Business Premium

- **サインイン:** 共有メールボックスは、関連付けられたユーザーアカウントによる直接サインインを目的としたものではありません。 常に共有メールボックスアカウントのサインインをブロックし、ブロックしたままにしておきます。

- **ユーザーが多すぎます:** 共有メールボックスに同時にアクセスする指定ユーザーの数が多すぎると、断続的にこのメールボックスへの接続に失敗する可能性があります。 この場合は、ユーザーの数を減らすか、Office 365 グループまたはパブリックフォルダーなどの異なるワークロードを使用することを検討してください。

- **メッセージの削除:** 残念ながら、ユーザーが共有メールボックス内のメッセージを削除するのを防ぐことはできません。 これを回避する唯一の方法は、共有メールボックスの代わりに、Office 365 グループを作成することです。 Outlook のグループは、共有メールボックスに似ています。 両者の比較については、「[グループの比較](../create-groups/compare-groups.md)」を参照してください。 グループの詳細については、「[グループに関する詳細](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)情報」を参照してください。

## <a name="related-articles"></a>関連記事

[共有メールボックスを作成する](create-a-shared-mailbox.md)

[共有メールボックスを構成する](configure-a-shared-mailbox.md)

[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)

[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md)

[共有メールボックスの問題を解決する](resolve-issues-with-shared-mailboxes.md)
