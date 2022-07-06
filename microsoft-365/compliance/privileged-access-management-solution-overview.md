---
title: 特権アクセス管理
description: Microsoft Purview 全体でインサイダー リスク機能を構成する方法について説明します。
keywords: Microsoft 365、インサイダー リスク、コンプライアンス
ms.localizationpriority: medium
ms.service: O365-seccomp
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
ms.openlocfilehash: 67857a2ad2ac57543ce20dd8eab544cf7dcfef42
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66639866"
---
# <a name="privileged-access-management"></a>特権アクセス管理

Microsoft Exchange Onlineの機密情報や重要なネットワーク構成設定に一部のユーザーが永続的にアクセスすることは、侵害されたアカウントや内部脅威アクティビティの潜在的な経路です。 Microsoft Purview Privileged Access Management は、組織を侵害から保護し、機密データへの永続的なアクセスや重要な構成設定へのアクセスを制限することで、コンプライアンスのベスト プラクティスを満たすのに役立ちます。 管理者が一定のアクセス権を持つ代わりに、管理者特権でアクセス許可を必要とするタスクに対して Just-In-Time アクセス 規則が実装されます。 Microsoft 365 でExchange Onlineの特権アクセス管理を有効にすると、組織は永続的な特権をゼロで運用し、永続的な管理アクセスの脆弱性に対する防御層を提供できます。

## <a name="configure-privileged-access-management"></a>特権アクセス管理を設定する

組織の特権アクセス管理を構成するには、次の手順に従います。

![Insider リスク ソリューションの特権アクセス管理手順。](../media/ir-solution-pam-steps.png)

1. [特権アクセス管理](privileged-access-management.md)の詳細
2. [承認者のグループを](privileged-access-management-configuration.md#step-1-create-an-approvers-group)作成する
3. [特権アクセス管理を](privileged-access-management-configuration.md#step-2-enable-privileged-access)有効にする
4. [アクセス ポリシー](privileged-access-management-configuration.md#step-3-create-an-access-policy)を作成する
5. [特権アクセス要求の](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)送信/承認

## <a name="more-information-about-privileged-access-management"></a>特権アクセス管理の詳細

- [特権アクセス管理に関してよく寄せられる質問](privileged-access-management.md#frequently-asked-questions)
