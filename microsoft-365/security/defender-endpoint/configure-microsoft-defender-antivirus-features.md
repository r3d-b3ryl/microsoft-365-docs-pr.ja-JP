---
title: Microsoft Defender ウイルス対策機能を構成する
description: Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell を使用して Microsoft Defender ウイルス対策機能を構成できます。
keywords: Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, Defender, 構成, 構成, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, モバイル デバイス管理, GP, グループ ポリシー, PowerShell
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: c0950ead64f39dced48bbdea0e242bdc1d8fe3b6
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479534"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Microsoft Defender ウイルス対策機能を構成する


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策は、次のようなさまざまなツールを使用して構成できます。

- Microsoft エンドポイント マネージャー (Microsoft Intuneと Microsoft Endpoint Configuration Managerを含む)
- グループ ポリシー
- PowerShell コマンドレット
- Windows Management Instrumentation (WMI)
- [テナントのアタッチ](/mem/configmgr/tenant-attach/)

次の広範な機能カテゴリを構成できます。

- クラウド配信の保護。 [クラウド配信保護と Microsoft Defender ウイルス対策を](cloud-protection-microsoft-defender-antivirus.md)参照してください

- 行動、ヒューリスティック、機械学習ベースの保護を含む、常時オンのリアルタイム保護。 [動作、ヒューリスティック、およびリアルタイム保護の構成に関する](configure-protection-features-microsoft-defender-antivirus.md)ページを参照してください。

- エンド ユーザーが個々のエンドポイントでクライアントと対話する方法。 以下のリソースを参照してください。
  - [ユーザーが Microsoft Defender ウイルス対策ユーザー インターフェイスを表示または操作できないようにする](prevent-end-user-interaction-microsoft-defender-antivirus.md)
  - [ユーザーが Microsoft Defender ウイルス対策ポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)

> [!TIP]
> [管理ツールと構成ツールのリファレンス トピックを確認](configuration-management-reference-microsoft-defender-antivirus.md)します。
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
