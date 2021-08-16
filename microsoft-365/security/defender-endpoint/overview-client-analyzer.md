---
title: Microsoft Defender for Endpoint Client Analyzer を使用したセンサーの正常性のトラブルシューティング
description: デバイスのセンサーの正常性をトラブルシューティングし、センサー のデータまたは機能に影響を与える潜在的な構成、環境、接続、または利用統計情報の問題を特定します。
keywords: センサー、センサーの正常性、構成ミス、非アクティブ、センサー データなし、センサー データ、通信障害、通信障害
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 94824039c582706d8042079b492e1b4beae2cddb
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58254835"
---
#  <a name="troubleshoot-sensor-health-using-microsoft-defender-for-endpoint-client-analyzer"></a>Microsoft Defender for Endpoint Client Analyzer を使用したセンサーの正常性のトラブルシューティング

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Microsoft Defender for Endpoint Client Analyzer (MDECA) は、Windows、Linux、または[](/microsoft-365/security/defender-endpoint/onboard-configure)macOS のいずれかを実行しているオンボード デバイスでセンサーの正常性または信頼性の問題を診断するときに役立ちます。 たとえば、セキュリティ ポータルに表示されるセンサーの正常性状態 [(非](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors) アクティブ、センサー データなし、または通信障害) に従って、異常と思われるコンピューターでアナライザーを実行できます。

明らかなセンサーの正常性の問題に加え、MDECA は、次のような複雑なシナリオをトラブルシューティングするための他のトレース、ログ、および診断情報を収集できます。  
アプリケーションの互換性 (AppCompat)、パフォーマンス、ネットワーク接続、またはエンドポイント データ損失防止に関連する予期しない[動作。](/microsoft-365/compliance/endpoint-dlp-learn-about)

## <a name="privacy-notice"></a>プライバシーに関する声明


-   Microsoft Defender for Endpoint Client Analyzer ツールは、Microsoft Defender for Endpoint で発生する可能性のある問題のトラブルシューティングに役立つ情報を収集するために、Microsoft カスタマー サポート サービス (CSS) によって定期的に使用されます。

-   収集されたデータには、IP アドレス、PC 名、ユーザー名など、個人を特定できる情報 (PII) や機密データ (ただしこれらに限定されません) が含まれる場合があります。

-   データ収集が完了すると、ツールはサブフォルダーと圧縮された zip ファイル内のコンピューターにデータをローカルに保存します。

-   データは自動的に Microsoft に送信されません。 サポートの問題で共同作業中にツールを使用している場合は、問題の調査を容易にするために、Secure File Exchange を使用して圧縮データを Microsoft CSS に送信する必要があります。

Secure File Exchangeの詳細については、「Secure File Exchangeを使用して Microsoft サポートとファイルを交換する」[を参照してください](/troubleshoot/azure/general/secure-file-exchange-transfer-files)。  

プライバシーに関する声明の詳細については [、「Microsoft Privacy Statement」を参照してください](https://privacy.microsoft.com/privacystatement)。

## <a name="requirements"></a>要件

-   アナライザーを実行する前に、プロキシまたはファイアウォールの構成で Microsoft Defender for Endpoint サービス URL へのアクセスを許可することを [確認することをお勧めします](/microsoft-365/security/defender-endpoint/configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

-   アナライザーは、Microsoft Defender for Endpoint[](/microsoft-365/security/defender-endpoint/minimum-requirements.md#supported-windows-versions)へのオンボーディングの前に、Windows、Linux、[または macOS](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac.md#system-requirements)のサポートされているエディションで実行できます。 [](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-linux.md#system-requirements)

-   Windowsデバイスの場合、Live [Response](/microsoft-365/security/defender-endpoint/troubleshoot-collect-support-log)を介してリモートではなく、特定のコンピューターでアナライザーを直接実行している場合は、SysInternals [PsExec.exe](/sysinternals/downloads/psexec)の実行を許可する必要があります (少なくとも一時的に)。  
    アナライザーは、クラウド接続PsExec.exeローカル システムとして実行し、SENSE サービスの動作をエミュレートするために、このツールを呼び出します。

    > [!NOTE]
    > Windows デバイスで、攻撃表面縮小 (ASR) ルール[PSExec](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)および WMI コマンドから発生するプロセスの作成をブロックする場合は、ルールを一時的に無効にするか[、ASR](/microsoft-365/security/defender-endpoint/enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules)ルールの除外を構成して、アナライザーが期待した通りクラウドに接続チェックを実行できます。