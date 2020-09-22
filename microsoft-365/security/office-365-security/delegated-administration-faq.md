---
title: 代理管理の FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 管理者は、microsoft のパートナーと販売店のための Microsoft 365 で、委任された管理タスクについてよく寄せられる質問と回答を確認できます。
ms.openlocfilehash: 6729f276e6afea83568ca59d3bf48c08fcd837d2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203145"
---
# <a name="delegated-administration-faq"></a>代理管理の FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


この記事では、microsoft パートナーおよび販売店で、Microsoft 365 での代理管理タスクについてよく寄せられる質問とその回答について説明します。 代理管理には、他のテナント (企業) の Exchange Online Protection (EOP) 設定を管理する機能が含まれています。

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>リセラーで、お客様のテナントを管理する必要がある。 これはどのように動作しますか?

Microsoft のパートナーまたは販売店の場合は、Microsoft advisor にサインアップすると、お客様の Microsoft 365 組織に委任された _管理_ 機能を要求できます。

委任された管理では、組織内の管理者であるかのように、Microsoft 365 (EOP の設定を含む) を管理できます。 委任された管理を構成する手順については、次の一覧で説明します。

1. [Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。

2. 委任された管理にサインアップします。 お客様のテナントの管理を開始する前に、代理管理者として承認する必要があります。 承認を得るには、まず [委任管理の申し出を送信](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)します。 また、後でお客様に委任された管理を提供することもできます。

3. 「 [サブスクリプションアドバイザーパートナーを追加、変更、または削除する](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)」の手順に従って、委任された管理者アカウントを作成します。

代理管理を設定する方法の詳細については [、「パートナー: ビジネスを構築し、パートナーサブスクリプションを管理](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) する」を参照してください。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>お客様は、販売店ではありません。 委任された管理者を自分のサブテナントに設定するには、どうすればよいですか?

委任された管理は、リセラーとパートナーのみが利用できます。 ただし、サンプルの PowerShell スクリプトを使用すると、サブテナント (企業) にポリシーを適用するのに役立ちます。 詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>自分のサブテナント管理者が自分のポリシーを変更できないようにすることはできますか。

いいえ。 現在、Microsoft 365 にはこの機能はありません。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>すべてのサブテナントでレポートを統合することはできますか?

Microsoft 365 管理センターのレポートでは、管理している会社を超えた統合レポートを作成することはできません。 ただし、 [Microsoft Graph](https://docs.microsoft.com/graph/overview)を使用してレポートを取得することができます。
