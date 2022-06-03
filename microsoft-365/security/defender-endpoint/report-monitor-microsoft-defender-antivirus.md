---
title: Microsoft Defender ウイルス対策保護の監視とレポート
description: Configuration Managerまたはセキュリティ情報とイベント管理 (SIEM) ツールを使用してレポートを使用し、PowerShell と WMI を使用して Microsoft Defender AV を監視します。
keywords: siem、モニター、レポート、Microsoft Defender AV
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 46abb6a11e1752934218a031993b10286d8ab420
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65872250"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策のレポート

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策は、Windows 10、Windows 11、Windows Server 2019、Windows Server 2022、およびWindows Server 2016に組み込まれています。 Microsoft Defender ウイルス対策は、Microsoft Defender for Endpointにおける次世代の保護です。 次世代の保護は、電子メール、アプリ、クラウド、Web 全体のウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威からデバイスを保護するのに役立ちます。

Microsoft Defender ウイルス対策では、保護の状態とアラートを確認するためのいくつかのオプションがあります。 Microsoft エンドポイント マネージャーを使用して[、Microsoft Defender ウイルス対策を監視](/configmgr/protect/deploy-use/monitor-endpoint-protection)したり、[電子メール アラートを作成したりできます](/configmgr/protect/deploy-use/endpoint-configure-alerts)。 または、[Microsoft Intune](/intune/introduction-intune)を使用して保護を監視することもできます。

サード パーティのセキュリティ情報とイベント管理 (SIEM) サーバーがある場合は、[クライアント イベントWindows Defender](/windows/win32/events/windows-events)使用することもできます。

Windows イベントは、Security Account Manager (SAM) イベント ([Windows 10用に強化され](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)、[セキュリティ監査](/windows/security/threat-protection/auditing/security-auditing-overview)のトピックも参照)、[Windows Defender イベント](troubleshoot-microsoft-defender-antivirus.md)など、いくつかのセキュリティ イベント ソースで構成されます。

これらのイベントは、[Windows イベント コレクター](/windows/win32/wec/windows-event-collector)を使用して一元的に集計できます。 多くの場合、SIEM サーバーにはWindows イベント用のコネクタがあり、SIEM サーバー内のすべてのセキュリティ イベントを関連付けることができます。

[Log Analytics のマルウェア評価ソリューションを使用して、マルウェア イベントを監視](/security/benchmark/azure/security-control-logging-monitoring)することもできます。

PowerShell、WMI、またはMicrosoft Azureを使用して状態を監視または決定する方法については、[(デプロイ、管理、およびレポートのオプションの表) を](deploy-manage-report-microsoft-defender-antivirus.md#ref2)参照してください。

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

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策を展開する](deploy-manage-report-microsoft-defender-antivirus.md)
