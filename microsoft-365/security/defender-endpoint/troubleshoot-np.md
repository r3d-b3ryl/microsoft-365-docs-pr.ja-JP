---
title: ネットワーク保護に関する問題のトラブルシューティング
description: Microsoft Defender for Endpointでのネットワーク保護に関する問題のトラブルシューティングを行うリソースとサンプル コード。
keywords: トラブルシューティング, エラー, 修正, Windows Defender 例, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: fbb3a9e038dcd9f342065d538762b41c0673f7e6
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783163"
---
# <a name="troubleshoot-network-protection"></a>ネットワーク保護のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

この記事では、次のような場合に、 [ネットワーク保護](network-protection.md)のトラブルシューティング情報を提供します。

- ネットワーク保護は、安全な Web サイトをブロックします (誤検知)
- ネットワーク保護が疑わしいまたは既知の悪意のある Web サイトをブロックできない (偽陰性)

これらの問題のトラブルシューティングには、次の 4 つの手順があります。

1. 前提条件を確認する
2. 監査モードを使用してルールをテストする
3. 指定したルールの除外を追加する (誤検知の場合)
4. サポート ログを送信する

## <a name="confirm-prerequisites"></a>前提条件を確認する

ネットワーク保護は、次の条件を持つデバイスでのみ機能します。

> [!div class="checklist"]
>
> - エンドポイントは、バージョン 1709 以降のエディションWindows 10 ProまたはEnterprise実行されています。
> - エンドポイントは、唯一のウイルス対策保護アプリとしてMicrosoft Defender ウイルス対策を使用しています。 [Microsoft 以外のウイルス対策ソリューションを使用している場合の動作を確認](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)します。
> - [リアルタイム保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) が有効になっています。
> - [クラウド配信保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) が有効になっている。
> - 監査モードが有効になっていません。 [グループ ポリシー](enable-network-protection.md#group-policy)を使用してルールを **無効** に設定します (値: **0**)。

## <a name="use-audit-mode"></a>監査モードを使用する

監査モードでネットワーク保護を有効にしてから、機能をデモするために作成した Web サイトにアクセスできます。 すべての Web サイト接続はネットワーク保護によって許可されますが、ネットワーク保護が有効になっている場合にブロックされていた接続を示すイベントがログに記録されます。

1. ネットワーク保護を **監査モード** に設定します。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. 問題の原因となっている接続アクティビティを実行します (たとえば、サイトにアクセスしようとしたり、ブロックする IP アドレスに接続しようとしたり、ブロックしたくない場合)。

3. [ネットワーク保護イベント ログを確認](network-protection.md#review-network-protection-events-in-windows-event-viewer) して、機能が **[有効]** に設定されている場合に接続をブロックしたかどうかを確認します。

   ネットワーク保護がブロックする必要がある接続をブロックしていない場合は、この機能を有効にします。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>偽陽性または偽陰性を報告する

デモ サイトと監査モードで機能をテストし、ネットワーク保護が構成済みのシナリオで動作しているが、特定の接続で想定どおりに機能していない場合は、[Windows Defender Security Intelligence Web ベースの送信フォーム](https://www.microsoft.com/wdsi/filesubmission)を使用して、ネットワーク保護の偽陰性または偽陽性を報告します。 E5 サブスクリプションでは、 [関連付けられているアラートへのリンクを指定](alerts-queue.md)することもできます。

[Microsoft Defender for Endpointの「アドレス false positives/negatives」を参照](defender-endpoint-false-positives-negatives.md)してください。

## <a name="add-exclusions"></a>除外を追加する

現在の除外オプションは次のとおりです。

1. カスタム許可インジケーターを設定します。
2. IP 除外の使用: `Add-MpPreference -ExclusionIpAddress 192.168.1.1`
3. プロセス全体を除外します。 詳細については、「[Microsoft Defender ウイルス対策除外](configure-exclusions-microsoft-defender-antivirus.md)」を参照してください。 

## <a name="collect-diagnostic-data-for-file-submissions"></a>ファイル送信の診断データを収集する

ネットワーク保護に関する問題を報告すると、Microsoft サポートチームとエンジニアリング チームが問題のトラブルシューティングに役立つ診断データを収集して送信するように求められます。

1. 管理者特権のコマンド プロンプトを開き、Windows Defender ディレクトリに変更します。

   ```console
   cd c:\program files\windows defender
   ```

2. 次のコマンドを実行して診断ログを生成します。

   ```console
   mpcmdrun -getfiles
   ```

3. 提出フォームにファイルを添付します。 既定では、診断ログは .`C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>ネットワーク保護に関する接続の問題を解決する (E5 のお客様向け)

ネットワーク保護が実行される環境のため、Microsoft ではオペレーティング システム プロキシの設定を確認できません。 場合によっては、ネットワーク保護クライアントがクラウド サービスに到達できないことがあります。 ネットワーク保護に関する接続の問題を解決するには、ネットワーク保護でプロキシ構成が認識されるように、次のいずれかのレジストリ キーを構成します。

```powershell
Set-MpPreference -ProxyServer <proxy IP address: Port>
```

---OR---

```powershell
Set-MpPreference -ProxyPacUrl <Proxy PAC url>
```

レジストリ キーは、PowerShell、Microsoft エンドポイント マネージャー、またはグループ ポリシーを使用して構成できます。 以下に役立つリソースをいくつか示します。

- [レジストリ キーの操作](/powershell/scripting/samples/working-with-registry-keys)
- [Endpoint Protection 向けカスタム クライアント設定の構成](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [グループ ポリシー設定を使用してEndpoint Protectionを管理する](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>関連項目

- [ネットワーク保護](network-protection.md)
- [ネットワーク保護と TCP の 3 方向ハンドシェイク](network-protection.md#network-protection-and-the-tcp-three-way-handshake)
- [ネットワーク保護を評価する](evaluate-network-protection.md)
- [ネットワーク保護を有効にする](enable-network-protection.md)
- [Defender for Endpoint の誤検知/陰性に対処する](defender-endpoint-false-positives-negatives.md)
