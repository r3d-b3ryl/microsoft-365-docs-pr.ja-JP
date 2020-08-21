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
description: このトピックでは、委任された Microsoft 365 管理タスクを実行する Microsoft パートナーとリセラーに関する FAQ と回答について説明します。
ms.openlocfilehash: 01781437bbc7e8fe5c035ea23e4392e734e0231f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827089"
---
# <a name="delegated-administration-faq"></a>代理管理の FAQ

このトピックでは、代理管理タスクを実行する必要がある Microsoft パートナーとリセラーに関してよく寄せられる質問と回答について説明します。これには、他のテナント (企業) で Exchange Online Protection (EOP) を管理する機能も含まれます。

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>再販業者で、お客様のテナントを管理する必要があります。この処理のしくみ

Microsoft パートナーまたは販売店で、Microsoft アドバイザーへのサインアップが完了している場合、管理センター内でカスタルトのテナントを管理するアクセス許可を要求できます。 これを代理管理といいます。組織内の管理者と同じ場合のように Microsoft 365 テナント (EOP 設定を含む) を管理することができます。 代理管理を実行するための手順は次のとおりです。

1. [Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。

2. 代理管理用にサインアップします。 カスタマーのアカウント管理を開始する前に、顧客が代理管理者として承認される必要があります。 承認を入手するには、最初に代 [理管理のオファーを送信します](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。 (後でカスタマーに委任管理を提供することもできます)。

3. サブスクリプション アドバイザー パートナーの追加、 [変更、または削除を行う手順を使用して、代理管理者アカウントを作成します](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)。

アクセスを [許可する: 代理管理のセットアップ方法について詳しくは](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) 、ビジネスを構築してパートナーサブスクリプションを管理する。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>再販業者ででない顧客です。どのようにすれば、自分のサブ テナントの代理管理者をセットアップできますか?

現時点で、代理管理が行えるのはリセラーとパートナーのみです。 しかし、サブ テナント (企業) に適用するのに役立つ Windows PowerShell のサンプル スクリプトが用意されています。 詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>サブ テナント管理者がわたしのポリシーを変更できないようにすることができますか？

現在、Microsoft 365 にはその機能が含まれています。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>自分のすべてのサブ テナントを統合したレポートを取得できますか？

現時点では、Microsoft 365 管理センターのレポートで、管理する企業を統合したレポートを利用できません。 ただし、これは Microsoft Graph を使用して [実行できます](https://docs.microsoft.com/graph/overview)。
