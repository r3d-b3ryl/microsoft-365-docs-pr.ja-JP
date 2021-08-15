---
title: Microsoft 365 にドメインを接続する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: ドメインを確認し、Microsoft 365 で DNS レコードを作成する方法を学びます。
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: 52fa6a1bfbf3bdbea51431022ab8ec7f8fe287d9a14afe0d8631df017999fdfe
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53823785"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Microsoft 365 にドメインを接続する

> [!NOTE]
> ドメインを追加しない場合、組織内のユーザーは、メール アドレスに onmicrosoft.com ドメインを使用します。 ユーザーを追加する前にドメインを追加することが重要です。それにより、ユーザーを再度セットアップする必要がなくなります。

探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.yml) を確認してください。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

MX レコードの情報は、管理センターのドメイン セットアップ ウィザードから取得されます。

ホスティング プロバイダーの Web サイトで、新しい MX レコードを追加します。
フィールドが次の値に設定されていることを確認します。

- Record Type: `MX`
- Priority: 使用可能な最高の値を設定します。通常は `0` です。
- Host Name: `@`
- Points to address: 管理センターから値をコピーし、ここに貼り付けます。
- TTL: `3600` (またはプロバイダーの既定値)

レコードを保存して、他の MX レコードを削除します。

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>CNAME レコードを追加して、ユーザーをメールボックスに接続します

CNAME レコードの情報は、管理センターのドメイン セットアップ ウィザードから取得されます。

ホスティング プロバイダーの Web サイトで、以下の CNAME レコードを追加します。 フィールドが次の値に設定されていることを確認します。

- Record Type: `CNAME (Alias)`
- Host: 管理センターからコピーした値をここに貼り付けます。
- Points to address: 管理センターから値をコピーし、ここに貼り付けます。
- TTL: `3600` (またはプロバイダーの既定値)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>迷惑メールの防止に役立つ SPF の TXT レコードを追加する

**開始する前に:** 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、ホスティング プロバイダーの Web サイトの現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが *1 つ* の SPF レコードに含まれるようにします。

ホスティング プロバイダーの Web サイトで、既存の SPF レコードを編集するか、SPF レコードを作成します。
フィールドが次の値に設定されていることを確認します。

- Record Type: `TXT (Text)`
- Host: `@`
- TXT Value: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600` (またはプロバイダーの既定値)

レコードを保存します。

SPF レコードを検証するには、[SPF 検証ツール](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)のいずれかを使用します。

SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング方法があります。それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Microsoft 365 用に構成する必要もあります。

使用を開始する場合は、「[DKIM を使用して、Microsoft 365 のドメインから送信される送信電子メールを検証する](../../security/office-365-security/use-dkim-to-validate-outbound-email.md)」、「[DMARC を使用して Microsoft 365 のメールを検証する](../../security/office-365-security/use-dmarc-to-validate-email.md)」を参照してください。

最後に、管理センターのドメイン セットアップ ウィザードに戻って設定を完了します。
