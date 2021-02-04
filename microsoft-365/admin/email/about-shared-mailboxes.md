---
title: 共有メールボックスについて
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスは、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。 共有メールボックスを作成する前に知る必要がある情報について説明します。
ms.openlocfilehash: f5d46af5abdd528ce3db817dbabce015ed5abade
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094723"
---
# <a name="about-shared-mailboxes"></a>共有メールボックスについて

共有メールボックスは、会社情報やサポート メール アドレス、受付デスク、または複数のユーザーが共有する可能性のあるその他の機能など、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。

グループ メールボックスへのアクセス許可を持つユーザーは、管理者がそのユーザーに対して必要なアクセス許可を付与している場合、メールボックスのメール アドレスとして送信したり、メールボックスのメール アドレスの代わりに送信したりできます。 これは、ユーザーが "Contoso サポート" や "建物 A の受付デスク" からメールを送信できるため、ヘルプとサポートのメールボックスとして特に役立ちます。

共有メールボックス [を作成する前に](create-a-shared-mailbox.md)、次の情報を確認する必要があります。

- **ライセンス:** 共有メールボックスには、ライセンスを割り当てずに最大 50 GB のデータを格納できます。 その後に、より多くのデータを格納するには、メールボックスにライセンスを割り当てる必要があります。 共有メールボックスのライセンスの詳細については [、「Exchange Online の制限」を参照してください](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。 共有メールボックスが記憶域の上限に達した場合、しばらくはメールを受信できますが、新しいメールを送信できなくなります。 その後、メールも受信できなくなります。 そのメールボックスにメールを送信したユーザーには、配信不能エラーが送信されます。

- **ユーザーのアクセス許可:** 共有メールボックスを使用するには、ユーザーにアクセス許可 (メンバーシップ) を付与する必要があります。 組織内のユーザーのみが共有メールボックスを使用できます。

- **外部ユーザー:** 社外のユーザー (Gmail アカウントを持つユーザーなど) に共有メールボックスへのアクセス権を与えすることはできません。 この操作を行う必要がある場合は、代わりに Outlook 用グループを作成することを検討してください。 詳細については、管理センターで [Microsoft 365 グループを作成するを参照してください](../create-groups/create-groups.md)。

- **Outlook と一緒に使用します。** ブラウザーから Outlook on the web を使用して共有メールボックスにアクセスする以外に、Outlook for iOS アプリまたは Outlook for Android アプリを使用することもできます。 詳細については、「共有メールボックス [を Outlook Mobile に追加する」を参照してください](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f)。 もう 1 つのオプションは、共有メールボックスのグループを作成する方法です。 詳細については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。

- **暗号化:** 共有メールボックスから送信された電子メールは暗号化できません。 これは、共有メールボックスに独自のセキュリティ コンテキスト (ユーザー名/パスワード) が設定されていないので、キーを割り当てられていないためです。 複数のユーザーがメンバーであり、暗号化した電子メールを自分のキーで送受信する場合、他のメンバーは電子メールを読み取れ、他のメンバーは電子メールが暗号化された公開キーによっては読めない可能性があります。

- **メールボックスの変換:** ユーザー メールボックスを共有メールボックスに変換できます。 「[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)」を参照してください。

- **管理者ロール:** グローバル管理者または Exchange 管理者の役割を持つユーザーは、共有メールボックスを作成できます。

- **サブスクリプションの要件:** 共有メールボックスを作成するには、電子メール (Exchange Online サービス) を含む Microsoft 365 for Business プランをサブスクライブする必要があります。 Microsoft 365 Apps for business サブスクリプションには電子メールは含まれます。 Microsoft 365 Business Standard には電子メールが含まれます。

- **サインイン:** 共有メールボックスは、関連付けられたユーザー アカウントによる直接サインインを目的としていない。 共有メールボックス アカウントのサインインは常にブロックし、ブロックする必要があります。

- **ユーザーが多すぎます。** 共有メールボックスに同時にアクセスする指定ユーザーが多すぎる場合、このメールボックスへの接続が断続的に失敗する可能性があります。 この場合は、ユーザーの数を減らすか、Microsoft 365 グループやパブリック フォルダーなど、異なるワークロードを使用する方法を検討できます。

- **メッセージの削除:** 残念ながら、ユーザーが共有メールボックス内のメッセージを削除することはできません。 これを回避する唯一の方法は、共有メールボックスの代わりに Microsoft 365 グループを作成する方法です。 Outlook のグループは、共有メールボックスに似たものがあります。 2 つの比較については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。 グループの詳細については、「グループの詳細 [」を参照してください](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。


> [!NOTE]
> 共有メールボックスにアクセスするには、ユーザーは Exchange Online ライセンスを持っている必要がありますが、共有メールボックスには別のライセンスは必要とされません。 どの共有メールボックスにも、対応するユーザー アカウントがあります。 共有メールボックスを作成する際に、パスワードの入力を求められなかったことにご注意ください。 このアカウントにはパスワードが設定されていますが、そのパスワードはシステムで生成され、ユーザーにはわかりません。 アカウントを使用して共有メールボックスにログインしてはならない。 ライセンスがない場合は、共有メールボックスは 50 GB に制限されます。 サイズ制限を 100 GB に増やすには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving アドオンのライセンス付きの Exchange Online プラン 1 のライセンスを共有メールボックスに割り当てる必要があります。 これにより、無制限のアーカイブ記憶域を得るための自動拡張アーカイブを有効にできるようにもなります。 同様に、共有メールボックスに訴訟ホールドをかける場合は、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving アドオン ライセンス付帯のExchange Online Plan 1 ライセンスが共有メールボックスで必要です。 microsoft Defender for Office 365、Advanced eDiscovery、自動アイテム保持ポリシーなどの高度な機能を適用する場合は、それらの機能に対して共有メールボックスのライセンスが必要です。

## <a name="related-articles"></a>関連記事

[共有メールボックスを作成する](create-a-shared-mailbox.md)

[共有メールボックスを構成する](configure-a-shared-mailbox.md)

[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)

[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md)

[共有メールボックスの問題を解決する](resolve-issues-with-shared-mailboxes.md)
