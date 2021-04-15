---
title: Microsoft Defender ウイルス対策機能の構成
description: Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell を使用して Microsoft Defender ウイルス対策機能を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、構成マネージャー、Microsoft Endpoint Configuration Manager、SCCM、Intune、MDM、モバイル デバイス管理、GP、グループ ポリシー、PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8503bb5bdd6337ec60390ef1d8e59f6f506fbce2
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765169"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Microsoft Defender ウイルス対策機能の構成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策は、次のツールを使用して構成できます。

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- グループ ポリシー
- PowerShell コマンドレット
- Windows Management Instrumentation (WMI)

次の広範なカテゴリの機能を構成できます。

- クラウドによる保護
- 行動、ヒューリスティック、機械学習ベースの保護を含む、常時オンのリアルタイム保護
- エンド ユーザーが個々のエンドポイントでクライアントとやり取りする方法

次の記事では、Microsoft Defender ウイルス対策を構成するときに重要なタスクを実行する方法について説明します。 各記事には、該当する構成ツール (またはツール) の手順が含まれています。

|記事  |説明  |
|---------|---------|
|[Microsoft クラウド提供の Microsoft Defender ウイルス対策保護を利用する](cloud-protection-microsoft-defender-antivirus.md)     | 高度で高速で堅牢なウイルス対策の検出には、クラウドによる保護を使用します。        |
|[動作、ヒューリスティック、およびリアルタイムの保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)     |動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護を有効にする。         |
|[Microsoft Defender ウイルス対策とのエンド ユーザー操作を構成する](configure-end-user-interaction-microsoft-defender-antivirus.md) | 組織内のエンド ユーザーが Microsoft Defender ウイルス対策とやり取りする方法、表示される通知、および設定を上書きできるかどうかを構成します。 |

> [!TIP]
> また、各ツールの概要 [と](configuration-management-reference-microsoft-defender-antivirus.md) 詳細なヘルプへのリンクについては、「管理および構成ツールのリファレンス トピック」トピックを参照することもできます。