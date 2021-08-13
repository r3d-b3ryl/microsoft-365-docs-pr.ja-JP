---
title: スキャンの除外をMicrosoft Defender ウイルス対策する
description: ファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーを、ユーザーがスキャンMicrosoft Defender ウイルス対策。 PowerShell を使用して除外を検証します。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: c6daa760dcec7c170cba15619eea380b6a1b882ff5baa7c3fc74c2b88f90ee62
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53854137"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>スキャンの除外を構成およびMicrosoft Defender ウイルス対策する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

特定のファイル、フォルダー、プロセス、およびプロセスで開いたファイルを、特定のスキャンからMicrosoft Defender ウイルス対策できます。 このような除外は、スケジュール[されたスキャン、](scheduled-catch-up-scans-microsoft-defender-antivirus.md)[オンデマンド](run-scan-microsoft-defender-antivirus.md)スキャン、および常時オンのリアルタイム保護と[監視に適用されます](configure-real-time-protection-microsoft-defender-antivirus.md)。 プロセスで開いたファイルの除外は、リアルタイム保護にのみ適用されます。

## <a name="configure-and-validate-exclusions"></a>除外を構成および検証する

除外を構成および検証するには、次の項目を参照してください。

- [ファイル名、拡張子、およびフォルダーの場所に基づいて除外を構成および検証します](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 ファイル拡張子、ファイルMicrosoft Defender ウイルス対策場所に基づいて、ファイルをスキャンから除外できます。

- [プロセスによって開いたファイルの除外を構成および検証します](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。 特定のプロセスで開いたスキャンからファイルを除外できます。

## <a name="recommendations-for-defining-exclusions"></a>除外を定義するための推奨事項

> [!IMPORTANT]
> Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作や一般的な管理ファイル (エンタープライズ管理、データベース管理、その他のエンタープライズ シナリオや状況で使用されるファイルなど) に基づく多くの自動除外が含まれます。  
> 
> 除外を定義すると、ユーザーが提供する保護がMicrosoft Defender ウイルス対策。 除外の実装に関連付けられているリスクは常に評価する必要があります。悪意がないと確信しているファイルのみを除外する必要があります。

除外を定義する場合は、次の点に注意してください。  

- 除外は技術的には保護のギャップです。 除外を定義する場合は、常に軽減策を検討してください。 その他の軽減策は、除外された場所に適切なアクセス制御リスト (ACL)、監査ポリシー、最新のソフトウェアなどによって処理されるのを確認するのと同じほど簡単です。

- 除外を定期的に確認します。 レビュー プロセスの一環として軽減策を再確認し、再適用します。

- 予防的な除外を定義しないようにするのが理想的です。 たとえば、将来問題になる可能性があるからといって、何かを除外しない。 除外は、除外が軽減する可能性のあるパフォーマンスやアプリケーションの互換性に関連する問題など、特定の問題にのみ使用します。

- 除外リストの変更を監査します。 セキュリティ管理者は、特定の除外が追加された理由に関する十分なコンテキストを保持する必要があります。 特定のパスが除外された理由について、特定の理由で回答を提供できる必要があります。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策の除外Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [除外を定義する際に避ける必要のある一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
