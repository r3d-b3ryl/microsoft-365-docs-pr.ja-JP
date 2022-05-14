---
title: Microsoft Defender ウイルス対策 スキャンの除外を設定する
description: ファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーは、Microsoft Defender ウイルス対策によってスキャンされないように除外できます。 PowerShell を使用して除外を検証します。
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
ms.collection: m365-security-compliance
ms.openlocfilehash: 2b796d2a3a8cdace765c3c0219466a42d9608763
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65419882"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Microsoft Defender ウイルス対策 スキャンの除外を構成して検証する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策 スキャンから、特定のファイル、フォルダー、プロセス、およびプロセスで開かれたファイルを除外できます。 このような除外は、 [スケジュールされたスキャン](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [オンデマンド スキャン](run-scan-microsoft-defender-antivirus.md)、 [および常時オンのリアルタイムの保護と監視](configure-real-time-protection-microsoft-defender-antivirus.md)に適用されます。 プロセスで開かれたファイルの除外は、リアルタイム保護にのみ適用されます。

## <a name="configure-and-validate-exclusions"></a>除外を構成および検証する

除外を構成して検証するには、次を参照してください。

- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成して検証します](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 ファイル拡張子、ファイル名、または場所に基づいて、Microsoft Defender ウイルス対策 スキャンからファイルを除外できます。

- [プロセスによって開かれたファイルの除外を構成して検証します](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。 特定のプロセスによって開かれたスキャンからファイルを除外できます。

## <a name="recommendations-for-defining-exclusions"></a>除外を定義するためのおすすめ

> [!IMPORTANT]
> Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作や一般的な管理ファイル (エンタープライズ管理、データベース管理、その他のエンタープライズ シナリオや状況で使用されるものなど) に基づく多くの自動除外が含まれます。
>
> 除外を定義すると、Microsoft Defender ウイルス対策によって提供される保護が低下します。 除外の実装に関連するリスクは常に評価する必要があります。また、悪意のないと確信しているファイルのみを除外する必要があります。

除外を定義する場合は、次の点に注意してください。

- 除外は技術的には保護のギャップです。 除外を定義するときは、すべてのオプションを検討してください。 その他のオプションは、除外された場所に適切なアクセス制御リスト (ACL) があることを確認するか、最初に監査モードにポリシーを設定するのと同じくらい簡単です。

- 除外を定期的に確認します。 レビュー プロセスの一環として、軽減策を再確認して再適用します。

- プロアクティブ化するために除外を定義することは避けるのが理想的です。 たとえば、将来問題になる可能性があるからといって、何かを除外しないでください。 除外は、パフォーマンスやアプリケーションの互換性に関連する問題など、除外によって軽減される可能性がある特定の問題に対してのみ使用します。

- 除外リストの変更を確認して監査します。 セキュリティ チームは、後で混乱を避けるために、特定の除外が追加された理由に関するコンテキストを保持する必要があります。 セキュリティ チームは、除外が存在する理由に関する質問に対する具体的な回答を提供できる必要があります。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Windows Server 2016で除外をMicrosoft Defender ウイルス対策する](configure-server-exclusions-microsoft-defender-antivirus.md)
- [除外を定義する際に避ける必要のある一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
