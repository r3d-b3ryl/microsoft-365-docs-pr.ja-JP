---
title: Microsoft Defender for Endpoint で問題が発生したセンサーの修正
description: サービスがデバイスからデータを受信するために、構成が正しく設定されていないか非アクティブとして報告されているデバイス センサーを修正します。
keywords: 誤構成、非アクティブ、センサーの修正、センサーの正常性、センサー データなし、センサー データ、通信障害、通信障害
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: 76b701243b2c458ad623f7e39967bf8d2595bbc5
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53619605"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint で問題が発生したセンサーの修正

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

構成ミスまたは非アクティブとして分類されたデバイスは、さまざまな原因によりフラグが設定される可能性があります。 このセクションでは、デバイスが非アクティブまたは正しく構成されていないと分類された原因について説明します。

## <a name="inactive-devices"></a>非アクティブ デバイス

非アクティブなデバイスは、問題が原因でフラグが設定されているとは限りません。 デバイスで実行される次のアクションにより、デバイスが非アクティブとして分類される可能性があります。

### <a name="device-is-not-in-use"></a>デバイスが使用されていない

何らかの理由でデバイスが 7 日間以上使用されていない場合は、ポータルの [非アクティブ] 状態のままです。

### <a name="device-was-reinstalled-or-renamed"></a>デバイスが再インストールまたは名前の変更された
再インストールまたは名前の変更されたデバイスは、新しいデバイス エンティティを新しいデバイス エンティティMicrosoft Defender セキュリティ センター。 前のデバイス エンティティは、ポータルの "非アクティブ" 状態のままです。 デバイスを再インストールして Defender for Endpoint パッケージを展開した場合は、新しいデバイス名を検索して、デバイスが正常に報告されているのを確認します。

### <a name="device-was-offboarded"></a>デバイスがオフボードされた
デバイスがオフボードされている場合は、デバイスの一覧に表示されます。 7 日後、デバイスの正常性状態は非アクティブに変更されます。

### <a name="device-is-not-sending-signals"></a>デバイスが信号を送信していない
デバイスが、構成が正しく設定されていないデバイス分類に該当する条件を含む何らかの理由で、Microsoft Defender for Endpoint チャネルに 7 日間以上信号を送信していない場合、デバイスは非アクティブと見なされます。 

デバイスが 'Active' 状態にあると思いますか? [サポート チケットを開きます](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)。

## <a name="misconfigured-devices"></a>誤って構成されたデバイス
構成が正しく設定されていないデバイスは、さらに次のように分類できます。
- 通信障害
- センサー データなし

### <a name="impaired-communications"></a>通信障害
この状態は、デバイスとサービス間の通信が制限されている状態を示します。

次の推奨されるアクションは、通信障害のある誤った構成済みデバイスに関連する問題を解決するのに役立ちます。

- [デバイスにインターネット接続が確立されている](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。

- [エンドポイント サービス URL 用 Microsoft Defender へのクライアント接続を確認する](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  プロキシ構成が正常に完了し、WinHTTP が環境内のプロキシ サーバーを介して検出して通信し、プロキシ サーバーが Microsoft Defender for Endpoint サービス URL へのトラフィックを許可することを確認します。

修正アクションを実行してもデバイスの状態が正しく構成されていない場合は、サポート [チケットを開きます](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。

### <a name="no-sensor-data"></a>センサー データなし
"センサー データなし" の状態の誤った構成済みデバイスは、サービスとの通信を持っていますが、部分的なセンサー データのみを報告できます。
これらのアクションに従って、誤って構成されたデバイスに関連する既知の問題を修正し、状態が "センサー データなし" になります。

- [デバイスにインターネット接続が確立されている](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。

- [エンドポイント サービス URL 用 Microsoft Defender へのクライアント接続を確認する](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  プロキシ構成が正常に完了し、WinHTTP が環境内のプロキシ サーバーを介して検出して通信し、プロキシ サーバーが Microsoft Defender for Endpoint サービス URL へのトラフィックを許可することを確認します。

- [診断データ サービスが有効になっているか確認する](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
デバイスが正しく報告されていない場合は、Windows 10 診断データ サービスが自動的に開始するように設定され、エンドポイントで実行されていることを確認する必要があります。

- [ポリシーによってMicrosoft Defender ウイルス対策が無効にされていないか確認する](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
デバイスでサードパーティのマルウェア対策クライアントを実行している場合、Defender for Endpoint エージェントは Microsoft Defender ウイルス対策 早期起動マルウェア対策 (ELAM) ドライバーを有効にする必要があります。

修正アクションを実行してもデバイスの状態が正しく構成されていない場合は、サポート [チケットを開きます](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。

## <a name="see-also"></a>関連項目
- [Microsoft Defender for Endpoint のセンサーの正常性状態を確認する](check-sensor-status.md)
