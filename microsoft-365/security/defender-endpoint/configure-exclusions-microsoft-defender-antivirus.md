---
title: スキャンの除外をMicrosoft Defender ウイルス対策する
description: ファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーを、ユーザーがスキャンMicrosoft Defender ウイルス対策。 PowerShell を使用して除外を検証します。
keywords: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 5a26951535b6e2197d8ada45b2108e62f15fda03
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62245149"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>スキャンの除外を構成およびMicrosoft Defender ウイルス対策する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


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

- 除外は技術的には保護のギャップです。 除外を定義する場合は、すべてのオプションを検討してください。 その他のオプションは、除外された場所に適切なアクセス制御リスト (ACL) を設定するか、最初はポリシーを監査モードに設定するのと同じほど簡単です。

- 除外を定期的に確認します。 レビュー プロセスの一環として軽減策を再確認し、再適用します。

- 予防的に取り組む際に除外を定義しないようにするのが理想的です。 たとえば、将来問題になる可能性があるからといって、何かを除外しない。 除外は、除外が軽減する可能性のあるパフォーマンスやアプリケーションの互換性に関連する問題など、特定の問題にのみ使用します。

- 除外リストに対する変更を確認および監査します。 セキュリティ チームは、後で混乱を避けるために、特定の除外が追加された理由に関するコンテキストを保持する必要があります。 セキュリティ チームは、除外が存在する理由に関する質問に対する具体的な回答を提供できる必要があります。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策の除外Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [除外を定義する際に避ける必要のある一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
