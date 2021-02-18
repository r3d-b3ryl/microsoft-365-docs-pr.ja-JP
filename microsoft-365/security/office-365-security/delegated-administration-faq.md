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
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Microsoft パートナーおよびリセラー向け Microsoft 365 の代理管理タスクに関してよく寄せられる質問と回答を表示できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 971572f8bff80da6dd63bed8958112332292feb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288361"
---
# <a name="delegated-administration-faq"></a>代理管理に関する FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


この記事では、Microsoft パートナーおよびリセラー向け Microsoft 365 の代理管理タスクについてよく寄せられる質問と回答を提供します。 代理管理には、他のテナント (企業) の Exchange Online Protection (EOP) 設定を管理する機能が含まれます。

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>リセラーであり、顧客のテナントを管理する必要があります。 これはどのように機能しますか?

Microsoft パートナーまたはリセラーであり、Microsoft アドバイザーとしてサインアップしている場合は、顧客の Microsoft 365 組織で代理管理機能を要求できます。 

代理管理を使用すると、組織内の管理者である場合と同様に、Microsoft 365 (EOP 設定を含む) を管理できます。 代理管理を構成する手順については、次の一覧で説明します。

1. [Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。

2. 代理管理にサインアップします。 顧客のテナントの管理を開始する前に、代理管理者として承認する必要があります。 承認を得るためには、まず代理 [管理のオファーを送信します](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。 後で顧客に代理管理を提供することもできます。

3. 「サブスクリプション アドバイザー パートナーを追加、変更、または削除する」の手順を使用して、代理管理者 [アカウントを作成します](../../admin/misc/add-partner.md)。

パートナー [にアクセス: 代理管理を設定する](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) 方法の詳細については、ビジネスを構築し、パートナー サブスクリプションを管理します。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>リセラーではなく、お客様です。 代理管理者を自分のサブ参加者に設定する方法

代理管理は、リセラーとパートナーにのみ使用できます。 ただし、サブドメイン (企業) にポリシーを適用するのに役立つサンプル PowerShell スクリプトがあります。 詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>サブドメイン管理者によるポリシーの変更を防止できますか?

いいえ。 現在、Microsoft 365 にはこの機能は備えっていません。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>すべてのサブ機能で統合レポートを取得できますか?

管理する企業全体の統合レポートは、Microsoft 365 管理センターのレポートでは利用できません。 ただし [、Microsoft Graph](https://docs.microsoft.com/graph/overview)を使用してレポートを取得できます。
