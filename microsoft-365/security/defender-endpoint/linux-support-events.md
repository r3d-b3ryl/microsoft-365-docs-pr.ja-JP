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
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 上の Microsoft Defender for Endpoint の不足しているイベントまたはアラートの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

この記事では、ポータルで不足しているイベントやアラートを軽減するための一般的な<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderします</a>。

**Microsoft Defender for Endpoint** がデバイスに正しくインストールされると _、ポータルに_ デバイス ページが生成されます。 記録されたイベントはすべて、デバイス ページの [タイムライン] タブ、または高度な検索ページで確認できます。 このセクションでは、一部またはすべての予期されるイベントが見つからない場合のトラブルシューティングを行います。
たとえば、すべての _CreatedFile_ イベントが見つからない場合です。

## <a name="missing-network-and-login-events"></a>ネットワークイベントとログイン イベントが見つからない

Microsoft Defender for Endpoint では `audit` 、ネットワークとログインアクティビティを追跡するために Linux からフレームワークを利用しました。

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

**SLES システムでは** 、SYSCALL `auditd` 監査は既定で無効になっている可能性があります。イベントが見つからない場合は考慮できます。

1. SYSCALL 監査が無効でなかっているのを検証するには、現在の監査ルールを一覧表示します。

    ```bash
    sudo auditctl -l
    ```

    次の行が存在する場合は、削除するか編集して、Microsoft Defender for Endpoint が特定の SYSCALL を追跡できます。

    ```output
    -a task, never
    ```

    監査ルールは 、 に位置します `/etc/audit/rules.d/audit.rules`。

## <a name="missing-file-events"></a>ファイル イベントが見つからない

ファイル イベントはフレームワークで収集 `fanotify` されます。 一部またはすべてのファイル イベント `fanotify` が見つからない場合は、デバイスで有効にし、ファイル システムがサポートされている必要 [があります](microsoft-defender-endpoint-linux.md#system-requirements)。

コンピューター上のファイルシステムを次のコマンドで一覧表示します。

```bash
df -Th
```
