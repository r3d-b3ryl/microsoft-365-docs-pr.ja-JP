---
title: Linux RHEL6 の Microsoft Defender for Endpoint の問題のトラブルシューティング
ms.reviewer: ''
description: Microsoft Defender for Endpoint on Linux のクラウド接続の問題のトラブルシューティング
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, Linux, cloud, connectivity, communication
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
ms.openlocfilehash: 0abb5615b0c1a51b06ec47eeb0c0e0718ebb7f9b
ms.sourcegitcommit: 43adb0d91af234c34e22d450a9c1d26aa745c2ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2021
ms.locfileid: "60479018"
---
# <a name="troubleshoot-issues-for-microsoft-defender-for-endpoint-on-linux-rhel6"></a>Linux RHEL6 の Microsoft Defender for Endpoint の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、Red Hat Linux 6 (RHEL 6) 以上の Microsoft Defender for Linux で発生する可能性のある問題をトラブルシューティングする方法について説明します。 

パッケージ (mdatp_XXX.XX.XX.XX.x86_64.rpm) がインストールされた後、提供されたアクションを実行して、インストールが成功したと確認します。 


## <a name="check-the-service-health"></a>サービスの正常性を確認する

次のコマンドを使用して、サービスの正常性を確認します。

```bash
mdatp health 
```

## <a name="verify-that-the-service-is-running"></a>サービスが実行されているのを確認する

次のコマンドを使用して、サービスが実行されている状態を確認します。

```bash
service mdatp status 
```

期待される出力: `mdatp start/running, process 4517`

## <a name="verify-the-distribution-and-kernel-version"></a>配布とカーネルのバージョンを確認する
配布バージョンとカーネル バージョンは、サポートされている一覧にある必要があります。

配布バージョンを取得するには、次のコマンドを使用します。

```bash
cat /etc/redhat-release (or /etc/system-release) 
```

カーネル バージョンを取得するには、次のコマンドを使用します。

```bash
uname -r
```
## <a name="check-if-mdatp-audisp-process-is-running"></a>mdatp audisp プロセスが実行されている場合の確認 
予想される出力は、プロセスが実行されている状態です。

次のコマンドを使用して確認します。

```bash
pidof mdatp_audisp_plugin 
```

## <a name="check-talpa-modules"></a>TALPA モジュールの確認
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

ログ ファイルのデバッグ ('mdatp 診断作成' バンドルとは別) 

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

を `<wdavdaemon pid>` 使用して見つかる `pidof wdavdaemon` 場所です。

