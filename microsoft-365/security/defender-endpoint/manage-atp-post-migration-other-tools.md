---
title: PowerShell、WMI、およびデバイスを使用して Microsoft Defender for Endpoint をMPCmdRun.exe
description: PowerShell、WMI、およびエンドポイントを使用して Microsoft Defender for Endpoint を管理するMPCmdRun.exe
keywords: 移行後、管理、運用、メンテナンス、使用率、PowerShell、WMI、MPCmdRun.exe Microsoft Defender for Endpoint、edr
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
- m365solution-scenario
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.date: 09/23/2020
ms.reviewer: chventou
ms.openlocfilehash: 4109a7754cb277f615ba7dc337606d32fb191d1e
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962749"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>PowerShell、WMI、およびエンドポイントを使用して Microsoft Defender for Endpoint をMPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> デバイス (エンドポイント[ともMicrosoft エンドポイント マネージャー)](/mem)に対する組織の脅威保護機能を管理するには、この機能を使用することをお勧めします。 エンドポイント マネージャーには、Microsoft Intuneと[](/mem/intune/fundamentals/what-is-intune)Microsoft Endpoint Configuration Manager[が含Microsoft Endpoint Configuration Manager。](/mem/configmgr/core/understand/introduction)
>
> - [詳細については、エンドポイント マネージャー](/mem/endpoint-manager-overview)
> - [Configuration Manager と Intune を使用して 11 Windows 10デバイスWindows Microsoft Defender for Endpoint を共同管理する](manage-atp-post-migration-intune.md)
> - [Intune を使用してエンドポイント用 Microsoft Defender を管理する](manage-atp-post-migration-intune.md)

[PowerShell、Microsoft Defender ウイルス対策](#configure-microsoft-defender-for-endpoint-with-powershell)Windows 管理インストルメンテーション[](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI)、および Microsoft[マルウェア](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)保護コマンド ライン ユーティリティ (MPCmdRun.exe) を使用して、デバイスの一部の設定を管理MPCmdRun.exe。 たとえば、一部の設定をMicrosoft Defender ウイルス対策できます。 また、場合によっては、攻撃表面の縮小ルールをカスタマイズし、保護設定を悪用することもできます。

> [!IMPORTANT]
> PowerShell、WMI、またはデバイスを使用して構成する脅威保護機能MCPmdRun.exe Intune または Configuration Manager で展開される構成設定によって上書きできます。

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>PowerShell を使用して Microsoft Defender for Endpoint を構成する

PowerShell を使用して、攻撃Microsoft Defender ウイルス対策、攻撃表面の縮小ルールを管理できます。<br/><br/>

|タスク|追加情報|
|---|---|
|**管理Microsoft Defender ウイルス対策** <br/><br/> マルウェア対策保護の状態を表示し、ウイルス対策スキャンの基本設定&更新プログラムを構成し、ウイルス対策保護に他の変更を加えます。*|[PowerShell コマンドレットを使用して、サーバーの構成とMicrosoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus) <br/><br/> [PowerShell コマンドレットを使用してクラウド配信の保護を有効にする](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)|
|**組織のデバイス上の** 脅威を軽減するためのエクスプロイト保護の構成 <br/><br/> *最初は監査モードでエクスプロイト [保護を使用することをお](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) 勧めします。その方法で、組織が使用しているアプリに対する悪用防止の影響を確認できます。*|[エクスプロイト保護をカスタマイズする](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [エクスプロイト保護用の PowerShell コマンドレット](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)|
|PowerShell **を使用して攻撃表面の縮小ルール** を構成する <br/><br/> *PowerShell を使用して、攻撃表面の縮小ルールからファイルとフォルダーを除外できます。*|[攻撃表面の縮小ルールをカスタマイズする: PowerShell を使用して、フォルダー内の&する](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders) <br/><br/> また、PowerShell を使用して攻撃表面の縮小ルールを設定する方法については [、António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)のグラフィカル ユーザー インターフェイス ツールを参照してください。|
|PowerShell **でネットワーク保護** を有効にする <br/><br/> *PowerShell を使用してネットワーク保護を有効にできます。*|[PowerShell を使用してネットワーク保護を有効にする](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell)|
|**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する <br/><br/> *[フォルダー アクセスの制御](/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソイエムウェア保護とも呼ばれます。*|[PowerShell を使用してフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell)|
|**組織のデバイスに** 流れ込む、または組織のデバイスから外部に流れる承認されていないネットワーク トラフィックをブロックする Microsoft Defender ファイアウォールを構成する|[Microsoft Defender Firewall with Advanced Security Administration using Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell)|
|**暗号化と BitLocker を構成** して、組織で実行されているデバイスの情報を保護Windows|[BitLocker PowerShell リファレンス ガイド](/powershell/module/bitlocker/)|

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Microsoft Defender for Endpoint with Windows管理インストルメンテーション (WMI)

WMI は、設定を取得、変更、および更新できるスクリプト インターフェイスです。 詳細については [、「USING WMI」を参照してください](/windows/win32/wmisdk/using-wmi)。<br/><br/>

|タスク|追加情報|
|---|---|
|**デバイスでクラウドによる保護** を有効にする|[クラウドWindows保護を有効にするには、管理命令 (WMI) を使用します。](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)|
|**ユーザーの設定を取得**、変更、および更新Microsoft Defender ウイルス対策|[WMI を使用して Microsoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)を構成および管理する <br/><br/> [利用可能な WMI クラスとサンプル スクリプトの一覧を確認する](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/> WMIv2 Provider リファレンス[情報Windows Defenderアーカイブ済みファイルも参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)|

## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Microsoft マルウェア保護ユーティリティを使用して Microsoft Defender for Endpoint をCommand-Lineする (MPCmdRun.exe)

個々のデバイスで、スキャンの実行、診断トレースの開始、セキュリティ インテリジェンスの更新の確認など、mpcmdrun.exeコマンド ライン ツールを使用できます。 ユーティリティは で確認できます `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 コマンド プロンプトから実行します。

詳細については、「構成と管理[」を参照Microsoft Defender ウイルス対策をmpcmdrun.exe。 ](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)

## <a name="configure-your-microsoft-365-defender-portal"></a>ポータルをMicrosoft 365 Defenderする

まだ行っていない場合は<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">、Microsoft 365 Defender</a>ポータルを構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報の表示を行います。

また、エンド ユーザーに表示される機能と機能を構成Microsoft Defender セキュリティ センター。

- [アプリケーションのMicrosoft Defender セキュリティ センター](/microsoft-365/security/defender-endpoint/use)

- [エンドポイント保護: Microsoft Defender セキュリティ センター](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次の手順

- [脅威と脆弱性の管理の概要を取得する](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [セキュリティ操作ダッシュボードMicrosoft Defender セキュリティ センターアクセスする](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Intune を使用してエンドポイント用 Microsoft Defender を管理する](manage-atp-post-migration-intune.md)
