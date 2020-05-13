---
title: 代理管理の FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: このトピックでは、委任された Microsoft 365 の管理タスクを実行する Microsoft パートナーとリセラーに関する Faq と回答を示します。
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209525"
---
# <a name="delegated-administration-faq"></a>代理管理の FAQ

このトピックでは、他のテナント (企業) の Exchange Online Protection (EOP) を管理する機能など、委任された管理タスクを実行することを望む Microsoft パートナーとリセラーによく寄せられる質問とその回答を示します。

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>リセラーで、お客様のテナントを管理する必要がある。これはどのように動作しますか?

Microsoft のパートナーまたは販売店で、Microsoft advisor にサインアップする場合は、管理センター内でテナントを管理するためのアクセス許可を要求できます。 これは委任された管理と呼ばれ、組織内の管理者であるかのように、Microsoft 365 テナント (EOP 設定を含む) を管理することができます。 委任された管理を実行する手順は次のとおりです。

1. [Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。

2. 委任された管理にサインアップします。 お客様のアカウントの管理を開始する前に、代理管理者として承認する必要があります。 承認を得るには、まず[委任管理の申し出を送信](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)します。 (お客様に後で委任された管理を提供することもできます)。

3. 「[サブスクリプションアドバイザーパートナーを追加、変更、または削除する](https://docs.microsoft.com/office365/admin/misc/add-partner)」の手順に従って、委任された管理者アカウントを作成します。

代理管理を設定する方法の詳細については[、「パートナー: ビジネスを構築し、パートナーサブスクリプションを管理](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319)する」を参照してください。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>お客様は、リセラーではなく、サブテナントの代理管理者を設定する方法を教えてください。

現時点で、代理管理が行えるのはリセラーとパートナーのみです。 しかし、サブ テナント (企業) に適用するのに役立つ Windows PowerShell のサンプル スクリプトが用意されています。 詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>サブ テナント管理者がわたしのポリシーを変更できないようにすることができますか？

現在、Microsoft 365 にはこの機能はありません。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>自分のすべてのサブ テナントを統合したレポートを取得できますか？

この時点では、管理している会社を超えた統合レポートを Microsoft 365 管理センターのレポートで使用することはできません。 ただし、これは[Microsoft Graph](https://docs.microsoft.com/graph/overview)を使用して行うことができます。
