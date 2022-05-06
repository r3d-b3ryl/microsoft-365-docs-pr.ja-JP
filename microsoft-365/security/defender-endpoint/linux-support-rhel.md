---
title: Linux RHEL6 でのMicrosoft Defender for Endpointに関する問題のトラブルシューティング
ms.reviewer: ''
description: Linux でのMicrosoft Defender for Endpointに関するクラウド接続の問題のトラブルシューティング
keywords: microsoft, defender, Microsoft Defender for Endpoint, Linux, クラウド, 接続, 通信
search.appverid: met150
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
ms.technology: mde
ms.openlocfilehash: 43a60d12883dc639c4ee5b831d305010cef58533
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61163640"
---
# <a name="troubleshoot-issues-for-microsoft-defender-for-endpoint-on-linux-rhel6"></a>Linux RHEL6 でのMicrosoft Defender for Endpointに関する問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、Red Hat Linux 6 (RHEL 6) 以降で Microsoft Defender for Linux で発生する可能性がある問題のトラブルシューティング方法に関するガイダンスを提供します。 

パッケージ (mdatp_XXX.XX.XX.XX.x86_64.rpm) がインストールされたら、指定されたアクションを実行してインストールが成功したことを確認します。 


## <a name="check-the-service-health"></a>サービスの正常性を確認する

次のコマンドを使用して、サービスの正常性を確認します。

```bash
mdatp health 
```

## <a name="verify-that-the-service-is-running"></a>サービスが実行されていることを確認する

次のコマンドを使用して、サービスが実行されていることを確認します。

```bash
service mdatp status 
```

期待される出力: `mdatp start/running, process 4517`

## <a name="verify-the-distribution-and-kernel-version"></a>ディストリビューションとカーネルのバージョンを確認する
ディストリビューションとカーネルのバージョンは、サポートされている一覧に含める必要があります。

配布バージョンを取得するには、次のコマンドを使用します。

```bash
cat /etc/redhat-release (or /etc/system-release) 
```

次のコマンドを使用して、カーネル バージョンを取得します。

```bash
uname -r
```
## <a name="check-if-mdatp-audisp-process-is-running"></a>mdatp audisp プロセスが実行されているかどうかを確認する 
予想される出力は、プロセスが実行されていることです。

次のコマンドを使用して確認します。

```bash
pidof mdatp_audisp_plugin 
```

## <a name="check-talpa-modules"></a>TALPA モジュールを確認する
9 つのモジュールが読み込まれている必要があります。 

次のコマンドを使用して確認します。

```bash
lsmod | grep talpa
```

期待される出力: 有効

```bash
talpa_pedconnector       878  0 

talpa_pedevice          5189  2 talpa_pedconnector 

talpa_vfshook          32300  1 

talpa_vcdevice          4947  1 

talpa_syscall           9127  0 

talpa_core             90699  4 talpa_vfshook,talpa_vcdevice,talpa_syscall 

talpa_linux            29424  5 talpa_vfshook,talpa_vcdevice,talpa_syscall,talpa_core 

talpa_syscallhookprobe      882  0 

talpa_syscallhook      14987  2 talpa_vfshook,talpa_syscallhookprobe 
```


```bash
lsmod | grep talpa | wc -l 
```

予想される出力: 9

## <a name="check-talpa-status"></a>TALPA の状態を確認する

```bash
cat /proc/sys/talpa/interceptors/VFSHookInterceptor/status 
```

デバッグ ログ ファイル ("mdatp 診断作成" バンドルとは別) 

```bash
/var/log/audit/audit.log 

/var/log/messages 

semanage fcontext -l > selinux.log 
```
 

パフォーマンスとメモリ 

```bash
top -p <wdavdaemon pid>      

pmap -x <wdavdaemon pid> 
```

を使用して`pidof wdavdaemon`見つけることができます。`<wdavdaemon pid>`

