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
description: 管理者は、Microsoft パートナーおよびリセラー向け Microsoft 365 で委任された管理タスクに関するよく寄せられる質問と回答を表示できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065291"
---
# <a name="delegated-administration-faq"></a>代理管理に関する FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


この記事では、Microsoft 365 for Microsoft パートナーおよびリセラー向け委任された管理タスクに関してよく寄せられる質問と回答を提供します。 委任された管理には、他のテナント (企業) の Exchange Online Protection (EOP) 設定を管理する機能が含まれています。

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>リセラーであり、顧客テナントを管理する必要があります。 これはどのように機能しますか?

Microsoft パートナーまたはリセラーで、Microsoft アドバイザーとしてサインアップしている場合は、お客様の Microsoft 365 組織で委任された管理機能を要求できます。 

委任された管理を使用すると、組織内の管理者である場合と同様に、Microsoft 365 (EOP 設定を含む) を管理できます。 委任された管理を構成する手順については、次の一覧で説明します。

1. [Microsoft Office 365 アドバイザー](https://partner.microsoft.com/?cloudbenefits) としてサインアップします。

2. 委任された管理にサインアップします。 顧客のテナントの管理を開始する前に、代理管理者として承認する必要があります。 承認を取得するには、まず代理 [管理のオファーを送信します](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。 また、後で代理管理を顧客に提供することもできます。

3. サブスクリプション アドバイザー パートナーの追加、変更、または削除の手順を使用して、委任された [管理者アカウントを作成します](../../admin/misc/add-partner.md)。

パートナー [にアクセスする: 委任された管理を](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) 設定する方法の詳細については、ビジネスを構築し、パートナー サブスクリプションを管理します。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>リセラーではなく、お客様です。 代理管理者をサブテパンツに設定する方法

委任された管理は、リセラーとパートナーでのみ使用できます。 ただし、サブドメイン (企業) にポリシーを適用するのに役立つ PowerShell スクリプトのサンプルがあります。 詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>管理下の管理者がポリシーを変更するのを防ぐことはできますか?

いいえ。 Microsoft 365 には現在、この機能は含めっていません。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>すべてのサブテナ間で統合レポートを取得できますか?

管理する会社全体の統合レポートは、Microsoft 365 管理センター レポートでは利用できません。 ただし、Microsoft Graph を使用してレポートを [取得できます](/graph/overview)。