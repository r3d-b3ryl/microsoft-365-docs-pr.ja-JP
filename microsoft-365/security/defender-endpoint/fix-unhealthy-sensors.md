---
title: Microsoft Defender for Endpoint で問題が発生したセンサーの修正
description: サービスがデバイスからデータを受信するように、構成が正しくない、または非アクティブであると報告されているデバイス センサーを修正します。
keywords: 不適切な構成、非アクティブ、センサーの修正、センサーの正常性、センサー データなし、センサー データ、通信障害、通信
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/23/2020
ms.technology: mde
ms.openlocfilehash: cc88fa877c0c284555f1702a5fa3190a06e7e47e
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66490877"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint で問題が発生したセンサーの修正

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-fixsensor-abovefoldlink)

デバイスは、構成が誤っているか、非アクティブとして分類され、さまざまな原因に対してフラグが設定されます。 このセクションでは、デバイスが非アクティブまたは正しく構成されていないと分類される原因について説明します。

## <a name="inactive-devices"></a>非アクティブ デバイス

非アクティブなデバイスは、問題が原因で必ずしもフラグが設定されるとは限りません。 デバイスで実行される次のアクションにより、デバイスが非アクティブとして分類される可能性があります。

- デバイスが使用されていない
- デバイスが再インストールまたは名前変更されました
- デバイスがオフボードされました
- デバイスがシグナルを送信していない


### <a name="device-isnt-in-use"></a>デバイスが使用されていない

7 日間以上使用されていないデバイスは、ポータルで "非アクティブ" 状態を保持します。

### <a name="device-was-reinstalled-or-renamed"></a>デバイスが再インストールまたは名前変更されました
新しいデバイス エンティティは、再インストールまたは名前変更されたデバイスのMicrosoft 365 Defenderで生成されます。 前のデバイス エンティティは、ポータルに "非アクティブ" 状態のままです。 デバイスを再インストールして Defender for Endpoint パッケージを展開した場合は、新しいデバイス名を検索して、デバイスが正常に報告されていることを確認します。

### <a name="device-was-offboarded"></a>デバイスがオフボードされました
デバイスがオフボードであった場合でも、デバイスの一覧に表示されます。 7 日後、デバイスの正常性状態は非アクティブに変わります。

### <a name="device-isnt-sending-signals"></a>デバイスがシグナルを送信していない
デバイスが何らかの理由で 7 日を超えて任意のMicrosoft Defender for Endpoint チャネルに信号を送信していない場合、デバイスは非アクティブと見なすことができます。これには、構成されていないデバイスの分類に該当する条件が含まれます。

デバイスが "アクティブ" 状態になっていると想定していますか? [サポート チケットを開きます](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)。

## <a name="misconfigured-devices"></a>誤って構成されたデバイス
構成が正しくないデバイスは、さらに次のように分類できます。
- 通信に障穣
- センサー データなし

### <a name="impaired-communications"></a>通信に障穣
この状態は、デバイスとサービス間の通信が制限されていることを示します。

次の推奨されるアクションは、通信障害が発生したデバイスの構成ミスに関連する問題を解決するのに役立ちます。

- [デバイスにインターネット接続があることを確認する](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。

- [Microsoft Defender for Endpoint サービス URL へのクライアント接続を確認する](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  プロキシ構成が正常に完了していること、WinHTTP が環境内のプロキシ サーバーを介して検出して通信できること、およびプロキシ サーバーがMicrosoft Defender for Endpoint サービス URL へのトラフィックを許可していることを確認します。

修正アクションを実行し、デバイスの状態がまだ正しく構成されていない場合は、 [サポート チケットを開きます](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。

### <a name="no-sensor-data"></a>センサー データなし
状態が "センサー データなし" の構成が正しくないデバイスでは、サービスとの通信は行われますが、部分的なセンサー データのみを報告できます。

これらのアクションに従って、状態が "センサー データなし" で構成されていないデバイスに関連する既知の問題を修正します。

- [デバイスにインターネット接続があることを確認する](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。

- [Microsoft Defender for Endpoint サービス URL へのクライアント接続を確認する](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  プロキシ構成が正常に完了していること、WinHTTP が環境内のプロキシ サーバーを介して検出して通信できること、およびプロキシ サーバーがMicrosoft Defender for Endpoint サービス URL へのトラフィックを許可していることを確認します。

- [診断データ サービスが有効になっていることを確認する](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
デバイスが正しく報告されていない場合は、Windows 診断データ サービスが自動的に開始するように設定されていることを確認する必要があります。 また、Windows 診断データ サービスがエンドポイントで実行されていることを確認します。

- [ポリシーによって Microsoft Defender ウイルス対策が無効になっていないことを確認する](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
デバイスがサードパーティのマルウェア対策クライアントを実行している場合、Defender for Endpoint エージェントでは、Microsoft Defender ウイルス対策早期起動マルウェア対策 (ELAM) ドライバーが有効になっている必要があります。

修正アクションを実行し、デバイスの状態がまだ正しく構成されていない場合は、 [サポート チケットを開きます](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。

## <a name="see-also"></a>関連項目
- [Microsoft Defender for Endpointでセンサーの正常性状態を確認する](check-sensor-status.md)
- [クライアント アナライザーの概要](overview-client-analyzer.md)
- [クライアント アナライザーのダウンロードと実行](download-client-analyzer.md)
- [Windows でのクライアント アナライザーの実行](run-analyzer-windows.md)
- [macOS または Linux でのクライアント アナライザーの実行](run-analyzer-macos-linux.md)
- [Windows で高度なトラブルシューティングを行うためのデータ収集](data-collection-analyzer.md)

