---
title: Microsoft 365 での特権アクセス管理
description: インサイダー リスク機能を構成する方法については、Microsoft 365。
keywords: Microsoft 365、インサイダー リスク、コンプライアンス
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: 60fdb02da960d10b875fcd064c665ecd615ae04c0093f0f90f40ae77e4028f50
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53871616"
---
# <a name="privileged-access-management-in-microsoft-365"></a>Microsoft 365 での特権アクセス管理

一部のユーザーが機密情報や重要なネットワーク構成設定にアクセスすると、Microsoft Exchange Onlineアカウントや内部脅威アクティビティの潜在的な経路になります。 特権アクセス管理は、組織を侵害から保護するのに役立ち、機密データへの永続的なアクセスや重要な構成設定へのアクセスを制限することで、コンプライアンスのベスト プラクティスを満たすのに役立ちます。 管理者が一定のアクセス権を持つ代わりに、管理者特権のアクセス許可を必要とするタスクに対して Just-in-time アクセス ルールが実装されます。 Exchange Online Microsoft 365 の特権アクセス管理を有効にすると、組織は永続的な特権をゼロにし、管理アクセスの永続的な脆弱性に対する防御層を提供できます。

## <a name="configure-privileged-access-management-for-microsoft-365"></a>ユーザーの特権アクセス管理を構成Microsoft 365

組織の特権アクセス管理を構成するには、次の手順を使用します。

![Insider リスク ソリューションの特権アクセス管理手順](../media/ir-solution-pam-steps.png)

1. 特権アクセス[管理の詳細については](privileged-access-management-overview.md)、Microsoft 365
2. 承認者 [のグループを作成する](privileged-access-management-configuration.md#step-1-create-an-approvers-group)
3. 特権 [アクセス管理を有効にする](privileged-access-management-configuration.md#step-2-enable-privileged-access)
4. アクセス ポリシー [の作成](privileged-access-management-configuration.md#step-3-create-an-access-policy)
5. 特権アクセス要求 [の送信および承認](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)

## <a name="more-information-about-privileged-access-management"></a>特権アクセス管理の詳細

- [特権アクセス管理に関するよく寄せられる質問](privileged-access-management-overview.md#frequently-asked-questions)