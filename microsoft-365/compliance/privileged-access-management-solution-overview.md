---
title: Microsoft 365 での特権アクセス管理
description: Microsoft 365 で insider のリスク機能を構成する方法について説明します。
keywords: Microsoft 365、内部者のリスク、コンプライアンス
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
ms.openlocfilehash: 7fecfd7088f65effd6addddc51c1236c7b2af191
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613871"
---
# <a name="privileged-access-management-in-microsoft-365"></a>Microsoft 365 での特権アクセス管理

Microsoft Exchange Online の機密情報または重要なネットワーク構成の設定にユーザーがアクセスできるようにすることは、侵害されたアカウントまたは内部の脅威のアクティビティに対して潜在的な経路です。 特権アクセス管理は、機密データへのアクセスを制限したり、重要な構成設定にアクセスしたりすることによって、違反から組織を保護し、コンプライアンスのベストプラクティスに準拠するために役に立ちます。 管理者が継続的にアクセスするのではなく、管理者特権を必要とするタスクに対してジャストインタイムのアクセスルールが実装されています。 Microsoft 365 で Exchange Online の特権アクセス管理を有効にすることで、組織はゼロに立った権限で運用し、継続的な管理アクセスの脆弱性に対する防御層を提供することができます。

## <a name="configure-privileged-access-management-for-microsoft-365"></a>Microsoft 365 の特権アクセス管理を構成する

組織の特権アクセス管理を構成するには、次の手順を使用します。

![Insider リスクソリューションの特権アクセス管理の手順](../media/ir-solution-pam-steps.png)

1. Microsoft 365 での [特権アクセス管理](privileged-access-management-overview.md) について説明します。
2. [承認者のグループ](privileged-access-management-configuration.md#step-1-create-an-approvers-group)を作成する
3. [特権アクセス管理](privileged-access-management-configuration.md#step-2-enable-privileged-access)を有効にする
4. [アクセスポリシー](privileged-access-management-configuration.md#step-3-create-an-access-policy)を作成する
5. [特権アクセス要求](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)を送信/承認する

## <a name="more-information-about-privileged-access-management"></a>特権アクセス管理の詳細情報

- [特権アクセス管理についてよく寄せられる質問](privileged-access-management-overview.md#frequently-asked-questions)