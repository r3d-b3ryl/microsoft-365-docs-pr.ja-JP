---
title: Microsoft Defender ウイルス対策保護の監視とレポート
description: Configuration Manager またはセキュリティ情報とイベント管理 (SIEM) ツールを使用してレポートを使用し、PowerShell と WMI を使用して Microsoft Defender AV を監視します。
keywords: siem, 監視, レポート, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f0065792f525827ccd1471087b8a707989ef61ef
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691444"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策に関するレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策は、Windows 10、Windows Server 2019、および Windows Server 2016 に組み込されています。 Microsoft Defender Antivirus は、Microsoft Defender for Endpoint の次世代保護の一部です。 次世代の保護は、電子メール、アプリ、クラウド、Web 全体のウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威からデバイスを保護するのに役立ちます。

Microsoft Defender ウイルス対策では、保護の状態とアラートを確認するためのいくつかのオプションがあります。 Microsoft Endpoint Manager を使用して [、Microsoft Defender ウイルス対策を監視](/configmgr/protect/deploy-use/monitor-endpoint-protection) したり、電子メール [通知を作成したりできます](/configmgr/protect/deploy-use/endpoint-configure-alerts)。 または、Microsoft Intune を使用して保護 [を監視できます](/intune/introduction-intune)。  

Microsoft Operations Management [](/windows/deployment/update/update-compliance-get-started) Suite には、保護更新プログラムやリアルタイム保護設定など、Microsoft Defender ウイルス対策の主要な問題を報告する更新コンプライアンス アドインがあります。

サードパーティのセキュリティ情報とイベント管理 (SIEM) サーバーがある場合は、クライアント イベントをWindows Defender [することもできます](/windows/win32/events/windows-events)。 

Windows イベントは、セキュリティ アカウント マネージャー (SAM) イベント[(Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)用に拡張された[](/windows/device-security/auditing/security-auditing-overview)イベント、セキュリティ監査トピックも参照)、およびセキュリティ イベントなど、いくつかのセキュリティ イベント[ソースでWindows Defenderされます](troubleshoot-microsoft-defender-antivirus.md)。 

これらのイベントは、Windows イベント コレクターを使用して一般 [に集約できます](/windows/win32/wec/windows-event-collector)。 多くの場合、SIEM サーバーには Windows イベント用のコネクタが用意され、SIEM サーバー内のすべてのセキュリティ イベントを関連付けできます。 

また、Log [Analytics のマルウェア評価ソリューションを使用してマルウェア イベントを監視することもできます](/azure/log-analytics/log-analytics-malware)。

PowerShell、WMI、または Microsoft Azure を使用して状態を監視または決定するには、(展開、管理、およびレポートオプションの表 [) を参照してください](deploy-manage-report-microsoft-defender-antivirus.md#ref2)。

## <a name="related-articles"></a>関連記事

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 2016 および 2019 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender ウイルス対策の展開](deploy-manage-report-microsoft-defender-antivirus.md)