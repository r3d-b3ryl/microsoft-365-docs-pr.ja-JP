---
title: Microsoft Defender AV スキャンの除外を設定する
description: Microsoft Defender AV によってスキャンされるファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーを除外できます。 PowerShell を使用して除外を検証します。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691504"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Microsoft Defender ウイルス対策スキャンの除外を構成および検証する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策スキャンから、特定のファイル、フォルダー、プロセス、およびプロセスで開いたファイルを除外できます。 このような除外は、スケジュール[されたスキャン、](scheduled-catch-up-scans-microsoft-defender-antivirus.md)[オンデマンド](run-scan-microsoft-defender-antivirus.md)スキャン、および常時オンのリアルタイム保護と[監視に適用されます](configure-real-time-protection-microsoft-defender-antivirus.md)。 プロセスで開いたファイルの除外は、リアルタイム保護にのみ適用されます。

## <a name="configure-and-validate-exclusions"></a>除外を構成および検証する

除外を構成および検証するには、次の項目を参照してください。

- [ファイル名、拡張子、およびフォルダーの場所に基づいて除外を構成および検証します](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 これにより、ファイル拡張子、ファイル名、または場所に基づいて、Microsoft Defender ウイルス対策スキャンからファイルを除外できます。

- [プロセスによって開いたファイルの除外を構成および検証します](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。 これにより、特定のプロセスで開いたスキャンからファイルを除外できます。

## <a name="recommendations-for-defining-exclusions"></a>除外を定義するための推奨事項

除外を定義すると、Microsoft Defender ウイルス対策によって提供される保護が低下します。 除外の実装に関連付けられているリスクは常に評価する必要があります。悪意がないと確信しているファイルのみを除外する必要があります。

除外を定義する際に注意する必要がある推奨事項の一覧を次に示します。  

- 除外は技術的には保護のギャップです。除外を定義する場合は、常に追加の軽減策を検討してください。 追加の軽減策は、除外された場所に適切なアクセス制御リスト (ACL)、監査ポリシー、最新のソフトウェアなどによって処理されるのを確認するのと同じほど簡単です。

- 除外を定期的に確認します。 レビュー プロセスの一環として軽減策を再確認し、再適用します。

- 予防的な除外を定義しないようにするのが理想的です。 たとえば、将来問題になる可能性があるからといって、何かを除外しない。 除外は、特定の問題 (主にパフォーマンスに関する問題)、または除外が軽減できるアプリケーションの互換性に関する場合にのみ使用します。

- 除外リストの変更を監査します。 セキュリティ管理者は、特定の除外が追加された理由に関する十分なコンテキストを保持する必要があります。 特定のパスが除外された理由について、特定の理由で回答を提供できる必要があります。

## <a name="related-articles"></a>関連記事

- [Windows Server 2016 での Microsoft Defender ウイルス対策の除外](configure-server-exclusions-microsoft-defender-antivirus.md)
- [除外を定義するときに回避する一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)