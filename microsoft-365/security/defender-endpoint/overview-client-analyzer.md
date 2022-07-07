---
title: Microsoft Defender for Endpoint クライアント アナライザーを使用したセンサーの正常性のトラブルシューティング
description: デバイスのセンサーの正常性をトラブルシューティングして、センサー データまたは機能に影響を与える潜在的な構成、環境、接続、またはテレメトリの問題を特定します。
keywords: センサー, センサーの正常性, 不適切な構成, 非アクティブ, センサー データなし, センサー データ, 通信障害, 通信
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
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: cad957dff57da6598e7b7db470998979d2bd0f63
ms.sourcegitcommit: 1734c95ce72d9c8af695cb4b49b1e40d921a1fee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66685594"
---
# <a name="troubleshoot-sensor-health-using-microsoft-defender-for-endpoint-client-analyzer"></a>Microsoft Defender for Endpoint クライアント アナライザーを使用したセンサーの正常性のトラブルシューティング

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint クライアント アナライザー (MDECA) は、Windows、Linux、または macOS を実行している[オンボード デバイス](/microsoft-365/security/defender-endpoint/onboard-configure)でセンサーの正常性または信頼性の問題を診断するときに役立ちます。 たとえば、セキュリティ ポータルで表示される [センサーの正常性状態](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors) (非アクティブ、センサー データなし、または通信障害) に従って異常と思われるコンピューターでアナライザーを実行できます。

明らかなセンサーの正常性の問題に加えて、MDECA は、次のような複雑なシナリオのトラブルシューティングのために、他のトレース、ログ、診断情報を収集できます。

- アプリケーションの互換性 (AppCompat)、パフォーマンス、ネットワーク接続、または
- [エンドポイントデータ損失防止](/microsoft-365/compliance/endpoint-dlp-learn-about)に関連する予期しない動作。

## <a name="privacy-notice"></a>プライバシーに関する声明

- Microsoft Defender for Endpoint クライアント アナライザー ツールは、Microsoft カスタマー サポート サービス (CSS) によって定期的に使用され、Microsoft Defender for Endpointで発生する可能性がある問題のトラブルシューティングに役立つ情報を収集します。

- 収集されたデータには、IP アドレス、PC 名、ユーザー名などの個人識別情報 (PII) や機密データ (ただしこれらに限定されない) が含まれる場合があります。

- データ収集が完了すると、ツールは、サブフォルダーと圧縮された zip ファイル内のコンピューター上のデータをローカルに保存します。

- データは自動的に Microsoft に送信されません。 サポートの問題に関する共同作業中にツールを使用している場合は、セキュリティで保護された File Exchange を使用して Microsoft CSS に圧縮データを送信し、問題の調査を容易にするよう求められる場合があります。

セキュリティで保護されたファイル交換の詳細については、「[Secure File Exchange を使用してファイルをMicrosoft サポートと交換する方法」を](/troubleshoot/azure/general/secure-file-exchange-transfer-files)参照してください。

プライバシーに関する声明の詳細については、 [Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)を参照してください。

## <a name="requirements"></a>要件

- アナライザーを実行する前に、プロキシまたはファイアウォールの構成で[Microsoft Defender for Endpointサービス URL](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) へのアクセスを許可することを確認することをお勧めします。

- アナライザーは、Microsoft Defender for Endpointにオンボードする前に、[サポートされている Windows](minimum-requirements.md#supported-windows-versions)、[Linux](microsoft-defender-endpoint-linux.md#system-requirements)、または [macOS](microsoft-defender-endpoint-mac.md#system-requirements) のエディションで実行できます。

- Windows デバイスの場合、 [Live Response](/microsoft-365/security/defender-endpoint/troubleshoot-collect-support-log) を使用してリモートではなく特定のマシンでアナライザーを直接実行している場合は、SysInternals [PsExec.exe](/sysinternals/downloads/psexec) 実行を (少なくとも一時的に) 許可する必要があります。 アナライザーは、PsExec.exe ツールを呼び出して、クラウド接続チェックをローカル システムとして実行し、SENSE サービスの動作をエミュレートします。

    > [!NOTE]
    > Windows デバイスで、 [PSExec および WMI コマンドから発生する](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands)攻撃表面削減 (ASR) ルールブロック プロセスの作成を使用する場合は、ルールを一時的に無効にするか、 [または ASR 規則に対する除外を構成して](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 、アナライザーが予想どおりにクラウドへの接続チェックを実行できるようにする必要がある場合があります。
