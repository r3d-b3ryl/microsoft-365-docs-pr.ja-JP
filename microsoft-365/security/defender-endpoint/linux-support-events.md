---
title: Linux 上の Microsoft Defender for Endpoint の不足しているイベントまたはアラートの問題のトラブルシューティング
description: Linux 上の Microsoft Defender for Endpoint のイベントやアラートの問題が見つからない場合のトラブルシューティングを行います。
keywords: microsoft、defender、Microsoft Defender for Endpoint、Linux、イベント
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e53f959e75551fdd5b065514a1c990663a667201
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194143"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 上の Microsoft Defender for Endpoint の不足しているイベントまたはアラートの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)

この記事では、ポータルで不足しているイベントやアラートを軽減するための一般的なMicrosoft 365 Defender[します](https://security.microsoft.com/)。

**Microsoft Defender for Endpoint** がデバイスに正しくインストールされると、ポータルにデバイス ページが生成されます。  記録されたイベントはすべて、デバイス ページの [タイムライン] タブ、または高度な検索ページで確認できます。 このセクションでは、一部またはすべての予期されるイベントが見つからない場合のトラブルシューティングを行います。
たとえば、すべての _CreatedFile_ イベントが見つからない場合です。

## <a name="missing-network-and-login-events"></a>ネットワークイベントとログイン イベントが見つからない

Microsoft Defender for Endpoint では、ネットワーク `audit` とログインアクティビティを追跡するために Linux からフレームワークを利用しました。

1. 監査フレームワークが機能している必要があります。

    ```bash
    service auditd status
    ```

    予期される出力:

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

2. 停止 `auditd` 済みとしてマークされている場合は、開始します。

    ```bash
    service auditd start
    ```

**SLES システムでは** 、SYSCALL 監査は既定で無効になっている可能性があります。イベントが見つからない `auditd` 場合は考慮できます。

1. SYSCALL 監査が無効でなかっているのを検証するには、現在の監査ルールを一覧表示します。

    ```bash
    sudo auditctl -l
    ```

    次の行が存在する場合は、削除するか編集して、Microsoft Defender for Endpoint が特定の SYSCALL を追跡できます。

    ```output
    -a task, never
    ```

    監査ルールは 、 に位置します `/etc/audit/rules.d/audit.rules` 。

## <a name="missing-file-events"></a>ファイル イベントが見つからない

ファイル イベントはフレームワークで収集 `fanotify` されます。 一部またはすべてのファイル イベントが見つからない場合は、デバイスで有効になっているか、ファイル システムが `fanotify` サポートされている必要 [があります](microsoft-defender-endpoint-linux.md#system-requirements)。

コンピューター上のファイルシステムを次のコマンドで一覧表示します。

```bash
df -Th
```
