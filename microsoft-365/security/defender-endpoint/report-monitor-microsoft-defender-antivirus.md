---
title: 保護の監視とMicrosoft Defender ウイルス対策する
description: Configuration Manager またはセキュリティ情報とイベント管理 (SIEM) ツールを使用してレポートを使用し、PowerShell と WMI を使用して Microsoft Defender AV を監視します。
keywords: siem, 監視, レポート, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5aa38bc1209b6ad114892805aef4ee3c462fdf1844775946b86801f2796cb96d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863513"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策のレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策サーバー 2019、Windows 10、Windowsに組み込Windows Server 2016。 Microsoft Defender ウイルス対策は、Microsoft Defender for Endpoint の次世代保護です。 次世代の保護は、電子メール、アプリ、クラウド、Web 全体のウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威からデバイスを保護するのに役立ちます。

このMicrosoft Defender ウイルス対策、保護状態とアラートを確認するためのいくつかのオプションがあります。 メール通知を監視[Microsoft エンドポイント マネージャー、またはMicrosoft Defender ウイルス対策](/configmgr/protect/deploy-use/monitor-endpoint-protection)を[作成するために使用できます](/configmgr/protect/deploy-use/endpoint-configure-alerts)。 または、 を使用して保護を[監視Microsoft Intune。](/intune/introduction-intune)  

Microsoft Operations Management [](/windows/deployment/update/update-compliance-get-started) Suite には、保護更新プログラムやリアルタイム保護設定など、Microsoft Defender ウイルス対策に関する重要な問題を報告する更新コンプライアンス アドインがあります。

サードパーティのセキュリティ情報とイベント管理 (SIEM) サーバーがある場合は、クライアント イベントWindows Defender[使用することもできます](/windows/win32/events/windows-events)。 

Windowsイベントは、セキュリティ アカウント マネージャー (SAM) イベント[(Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)用に拡張されたイベント、セキュリティ監査トピックも[](/windows/device-security/auditing/security-auditing-overview)参照) および Windows Defender イベントなど、いくつかのセキュリティ[イベント ソースで構成されます](troubleshoot-microsoft-defender-antivirus.md)。 

これらのイベントは、イベント コレクターを使用して一[Windowsできます](/windows/win32/wec/windows-event-collector)。 多くの場合、SIEM サーバーには、WINDOWSイベント用のコネクタが用意され、SIEM サーバー内のすべてのセキュリティ イベントを関連付けできます。 

また、Log [Analytics のマルウェア評価ソリューションを使用してマルウェア イベントを監視することもできます](/azure/log-analytics/log-analytics-malware)。

PowerShell、WMI、またはサーバーを使用して状態を監視または決定Microsoft Azure、(展開、管理、およびレポートオプションの表)[を参照してください](deploy-manage-report-microsoft-defender-antivirus.md#ref2)。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 2016 および 2019 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [展開Microsoft Defender ウイルス対策](deploy-manage-report-microsoft-defender-antivirus.md)