---
title: PowerShell、WMI、およびMPCmdRun.exeを使用してMicrosoft Defender for Endpointを管理する
description: PowerShell、WMI、およびMPCmdRun.exeを使用してMicrosoft Defender for Endpointを管理する方法について説明します
keywords: 移行後, 管理, 操作, メンテナンス, 使用率, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender for Endpoint, edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.reviewer: chventou
ms.openlocfilehash: 4003f2a41674ec6dbaa875235ccc12412d23ddba
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327181"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>PowerShell、WMI、およびMPCmdRun.exeを使用してMicrosoft Defender for Endpointを管理する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> [Microsoft エンドポイント マネージャー](/mem)を使用して、デバイス (エンドポイントとも呼ばれる) に対する組織の脅威保護機能を管理することをお勧めします。 エンドポイント マネージャーには[、Microsoft Intune](/mem/intune/fundamentals/what-is-intune)と [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)が含まれます。
> - [エンドポイント マネージャーの詳細を確認する](/mem/endpoint-manager-overview)
> - [Configuration ManagerとIntuneを使用して、Windows 10 デバイスとWindows 11 デバイスのMicrosoft Defender for Endpointを共同管理する](manage-mde-post-migration-intune.md)
> - [IntuneでMicrosoft Defender for Endpointを管理する](manage-mde-post-migration-intune.md)

[PowerShell](#configure-microsoft-defender-for-endpoint-with-powershell)、[Windows Management Instrumentation](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI)、Microsoft [Malware Protection コマンド ライン ユーティリティ](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe) を使用して、デバイスで Microsoft Defender ウイルス対策の一部の設定を管理できます。 たとえば、Microsoft Defender ウイルス対策の一部の設定を管理できます。 また、場合によっては、攻撃面の縮小ルールと悪用保護設定をカスタマイズできます。

> [!IMPORTANT]
> PowerShell、WMI、またはMCPmdRun.exeを使用して構成した脅威保護機能は、IntuneまたはConfiguration Managerで展開される構成設定で上書きできます。

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>PowerShell を使用してMicrosoft Defender for Endpointを構成する

PowerShell を使用して、Microsoft Defender ウイルス対策、エクスプロイト保護、および攻撃面の縮小ルールを管理できます。

|タスク|追加情報|
|---|---|
|**Microsoft Defender ウイルス対策を管理する** <br/><br/> マルウェア対策保護の状態の表示、ウイルス対策スキャン&更新の基本設定の構成、ウイルス対策保護に対するその他の変更を行います。|[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および管理する](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus) <br/><br/> [PowerShell コマンドレットを使用してクラウド配信保護を有効にする](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)|
|組織のデバイス上の脅威を軽減するための **エクスプロイト保護を構成する** <br/><br/> *最初は [、監査モード](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) でエクスプロイト保護を使用することをお勧めします。これにより、悪用保護が組織で使用しているアプリにどのような影響を与えるかを確認できます。*|[エクスプロイト保護をカスタマイズする](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [エクスプロイト保護用の PowerShell コマンドレット](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)|
|PowerShell **を使用して攻撃対象の縮小ルールを構成する** <br/><br/> *PowerShell を使用して、攻撃対象の縮小ルールからファイルとフォルダーを除外できます。*|[攻撃対象の縮小ルールをカスタマイズする: PowerShell を使用してファイル&フォルダーを除外する](/microsoft-365/security/defender-endpoint/enable-attack-surface-reduction) <br/><br/> また、PowerShell を使用して [攻撃面の縮小ルールを設定するための、AntónioVasconcelo のグラフィカル ユーザー インターフェイス ツール](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)も参照してください。|
|PowerShell **で Network Protection を有効にする** <br/><br/> *PowerShell を使用してネットワーク保護を有効にすることができます。*|[PowerShell で Network Protection を有効にする](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell)|
|ランサムウェアから保護するように **フォルダー アクセスの制御を構成** する <br/><br/> *[フォルダー アクセスの制御](/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソーイウェア保護とも呼ばれます。*|[PowerShell でフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell)|
|組織のデバイスに出入りする未承認のネットワーク トラフィックをブロックするように **Microsoft Defender ファイアウォールを構成** する|[Windows PowerShellを使用した高度なセキュリティ管理を備えた Microsoft Defender ファイアウォール](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell)|
|Windows を実行している組織のデバイスの情報を保護するように **暗号化と BitLocker を構成する**|[BitLocker PowerShell リファレンス ガイド](/powershell/module/bitlocker/)|

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Windows Management Instrumentation (WMI) を使用してMicrosoft Defender for Endpointを構成する

WMI は、設定を取得、変更、更新できるスクリプト インターフェイスです。 詳細については、「WMI の [使用](/windows/win32/wmisdk/using-wmi)」を参照してください。<br/><br/>

|タスク|追加情報|
|---|---|
|デバイス **でクラウド配信保護を有効にする**|[Windows 管理命令 (WMI) を使用してクラウド配信保護を有効にする](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)|
|Microsoft Defender ウイルス対策 **の設定を取得、変更、更新** する|[WMI を使用して Microsoft Defender ウイルス対策を構成および管理する](/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus <br/><br/> [使用可能な WMI クラスとスクリプトの例の一覧を確認する](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/> アーカイブされた[Windows Defender WMIv2 プロバイダーの参照情報](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)も参照してください|

## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Microsoft Malware Protection Command-Line ユーティリティを使用してMicrosoft Defender for Endpointを構成する (MPCmdRun.exe)

個々のデバイスで、mpcmdrun.exe コマンド ライン ツールを使用して、スキャンの実行、診断トレースの開始、セキュリティ インテリジェンスの更新の確認などを行うことができます。 ユーティリティは `%ProgramFiles%\Windows Defender\MpCmdRun.exe` で確認できます。 コマンド プロンプトから実行します。

詳細については、「 [mpcmdrun.exeを使用した Microsoft Defender ウイルス対策の構成と管理 ](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)」を参照してください。

## <a name="configure-your-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを構成する

まだ行っていない場合は、アラートを表示し、脅威保護機能を構成し、組織の全体的なセキュリティ体制に関する詳細情報を表示するようにMicrosoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータル</a>を構成します。

エンド ユーザーがMicrosoft Defender セキュリティ センターで表示できる機能の有無と機能を構成することもできます。

- [Microsoft Defender セキュリティ センターの概要](/microsoft-365/security/defender-endpoint/use)
- [エンドポイント保護: Microsoft Defender セキュリティ センター](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次の手順

- [Defender 脆弱性管理の概要を確認する](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Microsoft Defender セキュリティ センターセキュリティ操作ダッシュボードにアクセスする](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [IntuneでMicrosoft Defender for Endpointを管理する](manage-mde-post-migration-intune.md)
