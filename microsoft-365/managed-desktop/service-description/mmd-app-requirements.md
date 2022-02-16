---
title: アプリの要件
description: 使用する管理ツール
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: 998f9d7e0acef337031721eea9af8df64435733e
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825387"
---
# <a name="app-requirements"></a>アプリの要件

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->

Microsoft Managed Desktop では、デバイスのパフォーマンス、信頼性、およびサービス性を保証するために、特定の方法を使用してデバイスを管理する必要があります。

| 管理領域  | Microsoft Managed Desktop のアプローチ |
| ----- | ----- |
| デバイスの構成またはポリシーの管理 | Microsoft Intune |
| アプリケーションの管理 | Microsoft Intuneとポータル サイト |
| ドライバーの展開 | デバイス、更新プログラム、Intune にWindowsドライバー。 |
| デバイスのセキュリティ | 「デバイス [のセキュリティ」を参照してください](security.md#device-security)。 |
| ID およびアクセス管理 | 「 [Identity and access management」を参照してください](security.md#identity-and-access-management)。 |
| ネットワーク セキュリティ | 「 [ネットワーク セキュリティ」を参照してください](security.md#network-security)。 |
| 情報セキュリティ | 「 [情報セキュリティ」を参照してください](security.md#information-security)。 |
| データ復旧 | OneDrive for Business |
| コア生産性 | Microsoft 365 Apps for enterprise |
| ブラウザー | Microsoft Edge |

Microsoft Managed Desktop は、管理対象デバイスで実行されている他のソフトウェアを監視する場合があります。 ソフトウェアがデバイスの管理、デバイスのセキュリティ、パフォーマンス、または信頼性に悪影響を及ぼす場合は、サービス プランに例外を要求 [する必要があります](customizing.md)。
