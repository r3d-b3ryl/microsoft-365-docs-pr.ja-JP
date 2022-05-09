---
title: Linux 上のMicrosoft Defender for Endpointで見つからないイベントまたはアラートの問題のトラブルシューティング
description: Linux 上のMicrosoft Defender for Endpointで見つからないイベントまたはアラートの問題のトラブルシューティングを行います。
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, イベント
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5a17f94e3d26c08c0f6e0ca358778a65189cf6a5
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766018"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 上のMicrosoft Defender for Endpointで見つからないイベントまたはアラートの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

この記事では、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で不足しているイベントやアラートを軽減するための一般的な手順について説明します。

**Microsoft Defender for Endpoint** がデバイスに正しくインストールされると、ポータルで _デバイス ページ_ が生成されます。 記録されたすべてのイベントは、デバイス ページのタイムライン タブまたは高度なハンティング ページで確認できます。 このセクションでは、予想されるイベントの一部または全部が欠落している場合のトラブルシューティングを行います。
たとえば、 _CreatedFile_ イベントがすべて見つからない場合です。

## <a name="missing-network-and-login-events"></a>ネットワーク イベントとログイン イベントが見つからない

Microsoft Defender for Endpointネットワークとログインのアクティビティを追跡するために、linux からフレームワークを利用しました`audit`。

1. 監査フレームワークが機能していることを確認します。

    ```bash
    service auditd status
    ```

    予想される出力:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. 停止済みとしてマークされている場合 `auditd` は、開始します。

    ```bash
    service auditd start
    ```

**SLES システムでは** 、SYSCALL 監査が既定で `auditd` 無効になっている可能性があり、不足しているイベントを考慮できます。

1. SYSCALL 監査が無効になっていないことを検証するには、現在の監査規則を一覧表示します。

    ```bash
    sudo auditctl -l
    ```

    次の行が存在する場合は、削除するか編集して、Microsoft Defender for Endpointが特定の SYSCAL を追跡できるようにします。

    ```output
    -a task, never
    ```

    監査規則は .`/etc/audit/rules.d/audit.rules`

## <a name="missing-file-events"></a>不足しているファイル イベント

ファイル イベントはフレームワークで `fanotify` 収集されます。 一部またはすべてのファイル イベントが見つからない場合は、デバイスで有効になっており、ファイル システムが[サポート](microsoft-defender-endpoint-linux.md#system-requirements)されていることを確認してください`fanotify`。

マシン上のファイルシステムの一覧を次に示します。

```bash
df -Th
```
