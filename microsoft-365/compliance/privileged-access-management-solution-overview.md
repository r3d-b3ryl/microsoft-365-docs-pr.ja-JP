---
title: Microsoft 365 での特権アクセス管理
description: Microsoft 365 全体でインサイダー リスク機能を構成する方法について説明します。
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
ms.openlocfilehash: a5cd9d62670b35f7093a3d38cf9e499df407de97
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423810"
---
# <a name="privileged-access-management-in-microsoft-365"></a>Microsoft 365 での特権アクセス管理

一部のユーザーが機密情報や重要なネットワーク構成設定にアクセスすると、Microsoft Exchange Onlineアカウントや内部脅威アクティビティの潜在的な経路になります。 特権アクセス管理は、組織を侵害から保護するのに役立ち、機密データへの永続的なアクセスや重要な構成設定へのアクセスを制限することで、コンプライアンスのベスト プラクティスを満たすのに役立ちます。 管理者が一定のアクセス権を持つ代わりに、管理者特権のアクセス許可を必要とするタスクに対して Just-in-time アクセス ルールが実装されます。 Microsoft 365 で Exchange Online の特権アクセス管理を有効にすると、組織はゼロの特権で動作し、管理者アクセスの永続的な脆弱性に対する防御層を提供できます。

## <a name="configure-privileged-access-management-for-microsoft-365"></a>Microsoft 365 の特権アクセス管理を構成する

組織の特権アクセス管理を構成するには、次の手順を使用します。

![Insider リスク ソリューションの特権アクセス管理手順](../media/ir-solution-pam-steps.png)

1. Microsoft 365 [での特権](privileged-access-management-overview.md) アクセス管理の詳細
2. 承認者 [のグループを作成する](privileged-access-management-configuration.md#step-1-create-an-approvers-group)
3. 特権 [アクセス管理を有効にする](privileged-access-management-configuration.md#step-2-enable-privileged-access)
4. アクセス ポリシー [の作成](privileged-access-management-configuration.md#step-3-create-an-access-policy)
5. 特権アクセス要求 [の送信および承認](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)

## <a name="more-information-about-privileged-access-management"></a>特権アクセス管理の詳細

- [特権アクセス管理に関するよく寄せられる質問](privileged-access-management-overview.md#frequently-asked-questions)