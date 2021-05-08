---
title: Microsoft Defender ウイルス対策機能を構成する
description: Intune、Microsoft Defender ウイルス対策、グループ ポリシー Microsoft Endpoint Configuration Manager PowerShell を使用して、これらの機能を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御者、構成、Microsoft Endpoint Configuration Manager、SCCM、Intune、MDM、モバイル デバイス管理、GP、グループ ポリシー、PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275110"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Microsoft Defender ウイルス対策機能を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

次に示すMicrosoft Defender ウイルス対策ツールを使用して、構成を構成できます。

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- グループ ポリシー
- PowerShell コマンドレット
- Windows Management Instrumentation (WMI)

次の広範なカテゴリの機能を構成できます。

- クラウドによる保護
- 行動、ヒューリスティック、機械学習ベースの保護を含む、常時オンのリアルタイム保護
- エンド ユーザーが個々のエンドポイントでクライアントとやり取りする方法

次の記事では、タスクの構成時に主要なタスクを実行するMicrosoft Defender ウイルス対策。 各記事には、該当する構成ツール (またはツール) の手順が含まれています。

|記事  |説明  |
|---------|---------|
|[Microsoft クラウド提供のセキュリティ保護Microsoft Defender ウイルス対策活用する](cloud-protection-microsoft-defender-antivirus.md)     | 高度で高速で堅牢なウイルス対策の検出には、クラウドによる保護を使用します。        |
|[行動、ヒューリスティック、リアルタイム保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)     |動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護を有効にする。         |
|[ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策](configure-end-user-interaction-microsoft-defender-antivirus.md) | 組織内のエンド ユーザーがユーザーと対話する方法、Microsoft Defender ウイルス対策通知、および設定を上書きできるかどうかを構成します。 |

> [!TIP]
> また、各ツールの概要 [と](configuration-management-reference-microsoft-defender-antivirus.md) 詳細なヘルプへのリンクについては、「管理および構成ツールのリファレンス トピック」トピックを参照することもできます。