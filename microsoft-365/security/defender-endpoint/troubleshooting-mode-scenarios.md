---
title: Microsoft Defender for Endpointでのモード シナリオのトラブルシューティング (プレビュー)
description: Microsoft Defender for Endpointトラブルシューティング モードを使用して、さまざまなウイルス対策の問題に対処します。
keywords: ウイルス対策, トラブルシューティング, トラブルシューティング モード, 改ざん防止, 互換性
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f5a1734b267f512f19179e20b7ba66d8f38e1d19
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65874114"
---
# <a name="troubleshooting-mode-scenarios-in-microsoft-defender-for-endpoint-preview"></a>Microsoft Defender for Endpointでのモード シナリオのトラブルシューティング (プレビュー)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

> [!IMPORTANT]
> 一部の情報は、リリース済みの製品に関連しており、商用リリースされる前に大幅に変更される可能性があります。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft Defender for Endpointトラブルシューティング モードを使用すると、組織のポリシーによって制御されている場合でも、デバイスから有効にし、さまざまなシナリオをテストすることで、さまざまな Microsoft Defender ウイルス対策機能のトラブルシューティングを行うことができます。 トラブルシューティング モードは既定で無効になっており、デバイス (またはデバイスのグループ) で一定の時間有効にする必要があります。 これは排他的にEnterprise専用の機能であり、Microsoft 365 Defenderアクセスが必要であることに注意してください。

## <a name="scenario-1-unable-to-install-application"></a>シナリオ 1: アプリケーションをインストールできない

アプリケーションをインストールするが、Microsoft Defender ウイルス対策と改ざん防止がオンになっているというエラー メッセージが表示される場合は、次の手順に従って問題のトラブルシューティングを行います。

1. SOC 管理者にトラブルシューティング モードを有効にするよう要求します。 トラブルシューティング モードが開始されると、Windows セキュリティ通知が表示されます。  

2. ローカル管理者のアクセス許可を持つデバイスにConnectします (ターミナル サービスを使用するなど)。  

3. プロセス モニター (ProcMon) を開始します。 [リアルタイム保護に関連するパフォーマンスの問題のトラブルシューティングに関するページで説明されている手順を](troubleshoot-performance-issues.md)参照してください。  

4. **[Windows セキュリティ** > **脅威&ウイルス対策** > **の管理設定** > **改ざん防止** > オフ] に移動 **します**。  

5. 管理者特権の PowerShell コマンド プロンプトを起動し、RTP をオフにします。 

    - RTP の状態を確認するために実行 `get-mppreference` します。
    - 実行 `set–mppreference` して RTP 実行をオフにします。 

6. アプリケーションをインストールしてみてください。

## <a name="scenario-2-high-cpu-usage-due-to-windows-defender-msmpengexe"></a>シナリオ 2: Windows Defenderによる CPU 使用率の高い (MsMpEng.exe)

スケジュールされたスキャン中に、MsMpEng.exeが高い CPU を消費することがあります。

1. **[タスク マネージャー** > **の詳細**] タブに移動し、MsMpEng.exeが CPU 使用率が高い理由であることを確認します。 また、スケジュールされたスキャンが現在進行中かどうかを確認します。

2. CPU スパイク中に約 5 分間 ProcMon を実行し、ProcMon ログで手がかりを確認します。 

3. 根本原因が特定されたら、トラブルシューティング モードをオンにします。 

4. コンピューターにログインし、管理者特権の PowerShell コマンド プロンプトを起動します。 

5. 次のいずれかのコマンドを使用して、ProcMon の結果に基づいてプロセス/ファイル/フォルダー/拡張子の除外を追加します (以下で説明するパス、拡張子、およびプロセスの除外は例のみです)。 

    - Set-mppreference -ExclusionPath (C:\DB\DataFiles など) 
    
    - Set-mppreference –ExclusionExtension (.dbx など) 
    
    - Set-mppreference –ExclusionProcess (C:\DB\Bin\Convertdb.exeなど) 

6. 除外を追加した後、CPU 使用率が低下したかどうかを確認します。 

Windows Defenderのスキャンと更新に対するコマンドレット構成の基本設定Set-MpPreferenceの詳細については、「[Set-MpPreference」を](/powershell/module/defender/set-mppreference)参照してください。 

## <a name="scenario-3-application-taking-longer-to-perform-an-action"></a>シナリオ 3: アクションの実行に時間がかかるアプリケーション

リアルタイム保護Microsoft Defender ウイルス対策有効にすると、アプリケーションで基本的なタスクを実行するのに長い時間がかかります。 リアルタイム保護を無効にし、問題のトラブルシューティングを行うには、次の手順に従います。 

1. デバイスでトラブルシューティング モードを有効にするように SOC 管理者に要求します。 

2. このシナリオで RTP を無効にするには、まず改ざん防止を無効にします。 詳細については、「 [改ざん防止を使用してセキュリティ設定を保護する](prevent-changes-to-security-settings-with-tamper-protection.md)」を参照してください。 

3. 改ざん防止が無効になったら、デバイスにログインします。 

4. 管理者特権の PowerShell コマンド プロンプトを起動します。 

    - Set-mppreference -DisableRealtimeMonitoring $true 

5. RTP を無効にした後、アプリケーションの速度が低下しているかどうかを確認します。 

## <a name="scenario-4-microsoft-office-plugin-blocked-by-attack-surface-reduction"></a>シナリオ 4: 攻撃面の縮小によってブロックされたプラグインMicrosoft Office

Attack Surface Reduction (ASR) では、**すべてのOffice アプリケーションが子プロセスの作成をブロック** モードに設定されているため、プラグインMicrosoft Office正常に動作できません。 

1. トラブルシューティング モードを有効にし、デバイスにログインします。 

2. 管理者特権の PowerShell コマンド プロンプトを起動します。 

    - Set-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EFC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions 無効 

3. ASR 規則を無効にした後、Microsoft Office プラグインが機能することを確認します。

詳細については、 [攻撃面の縮小の概要に関するページを](overview-attack-surface-reduction.md)参照してください。 

## <a name="scenario-5-domain-blocked-by-network-protection"></a>シナリオ 5: Network Protection によってブロックされたドメイン

Network Protection によって Microsoft ドメインがブロックされ、ユーザーがアクセスできなくなります。 

1. トラブルシューティング モードを有効にし、デバイスにログインします。 

2. 管理者特権の PowerShell コマンド プロンプトを起動します。 

    - Set-MpPreference -EnableNetworkProtection が無効になっている 

3. Network Protection を無効にした後、ドメインが許可されているかどうかを確認します。 

詳細については、「 [ネットワーク保護を使用して、不適切なサイトへの接続を防止する」を](network-protection.md)参照してください。 

## <a name="related-topics"></a>関連トピック

- [トラブルシューティング モードを有効にする](enable-troubleshooting-mode.md)
- [改ざん防止機能を使用してセキュリティ設定を保護する](prevent-changes-to-security-settings-with-tamper-protection.md)
- [Set-MpPreference](/powershell/module/defender/set-mppreference)
- [ネットワークを保護する](network-protection.md)
- [攻撃面の減少の概要](overview-attack-surface-reduction.md)
- [望ましくない可能性のあるアプリケーションを検出してブロックする](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [Microsoft Defender for Endpoint の概要を確認する](/microsoft-365/security/defender-endpoint/)
- [ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)