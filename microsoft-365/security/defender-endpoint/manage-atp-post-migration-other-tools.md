---
title: PowerShell、WMI、およびデバイスを使用して Microsoft Defender for Endpoint をMPCmdRun.exe
description: PowerShell、WMI、およびエンドポイントを使用して Microsoft Defender for Endpoint を管理するMPCmdRun.exe
keywords: 移行後、管理、運用、メンテナンス、使用率、PowerShell、WMI、MPCmdRun.exe Microsoft Defender for Endpoint、edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 98b192551a351b58709185022cf311174052592b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934467"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>PowerShell、WMI、およびエンドポイントを使用して Microsoft Defender for Endpoint をMPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Microsoft [Endpoint Manager を使用して](https://docs.microsoft.com/mem) 、デバイス (エンドポイントとも呼ばれます) の組織の脅威保護機能を管理することをお勧めします。 エンドポイント マネージャーには [、Microsoft Intune と](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) Microsoft Endpoint Configuration Manager [が含まれます](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)。 
> - [エンドポイント マネージャーの詳細](https://docs.microsoft.com/mem/endpoint-manager-overview)
> - [Windows 10 デバイス上の Microsoft Defender for Endpoint を Configuration Manager と Intune で共同管理する](manage-atp-post-migration-intune.md)
> - [Intune を使用してエンドポイント用 Microsoft Defender を管理する](manage-atp-post-migration-intune.md) 

[PowerShell、Windows](#configure-microsoft-defender-for-endpoint-with-powershell)[管理](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)インストルメンテーション (WMI)、Microsoft マルウェア保護コマンド ライン ユーティリティ (MPCmdRun.exe) を使用して、デバイス上のいくつかの[Microsoft](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) Defender ウイルス対策設定を管理できます。 たとえば、Microsoft Defender ウイルス対策の設定を管理できます。 また、場合によっては、攻撃表面の縮小ルールをカスタマイズし、保護設定を悪用することもできます。 

> [!IMPORTANT]
> PowerShell、WMI、またはデバイスを使用して構成する脅威保護機能MCPmdRun.exe Intune または Configuration Manager で展開される構成設定によって上書きできます。

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>PowerShell を使用して Microsoft Defender for Endpoint を構成する

PowerShell を使用して、Microsoft Defender ウイルス対策、エクスプロイト保護、攻撃表面の縮小ルールを管理できます。

|Task  |追加情報  |
|---------|---------|
|**Microsoft Defender ウイルス対策の管理** <br/><br/>*マルウェア対策保護の状態を表示し、ウイルス対策スキャンと更新プログラム&設定を構成し、ウイルス対策保護に他の変更を加えます。*    |[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[PowerShell コマンドレットを使用してクラウド配信の保護を有効にする](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**組織のデバイス上の** 脅威を軽減するためのエクスプロイト保護の構成<br/><br/> *最初は監査モードでエクスプロイト [保護を使用することをお](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) 勧めします。その方法で、組織が使用しているアプリに対する悪用防止の影響を確認できます。*     | [エクスプロイト保護をカスタマイズする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[エクスプロイト保護用の PowerShell コマンドレット](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|PowerShell **を使用して攻撃表面の縮小ルール** を構成する <br/><br/>*PowerShell を使用して、攻撃表面の縮小ルールからファイルとフォルダーを除外できます。* |[攻撃表面の縮小ルールをカスタマイズする: PowerShell を使用して、フォルダー内の&する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>また、PowerShell を使用して攻撃表面の縮小ルールを設定する方法については [、António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)のグラフィカル ユーザー インターフェイス ツールを参照してください。 |
|PowerShell **でネットワーク保護** を有効にする <br/><br/>*PowerShell を使用してネットワーク保護を有効にできます。* |[PowerShell を使用してネットワーク保護を有効にする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する <br/><br/>*[フォルダー アクセスの制御](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソイエムウェア保護とも呼ばれます。* |[PowerShell を使用してフォルダー アクセスの制御を有効にする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**組織のデバイスに** 流れ込む、または組織のデバイスから外部に流れる承認されていないネットワーク トラフィックをブロックする Microsoft Defender ファイアウォールを構成する |[Microsoft Defender Firewall with Advanced Security Administration using Windows PowerShell](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Windows を実行している組織の** デバイスの情報を保護するために暗号化と BitLocker を構成する |[BitLocker PowerShell リファレンス ガイド](https://docs.microsoft.com/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Windows 管理インストルメンテーション (WMI) を使用して Microsoft Defender for Endpoint を構成する

WMI は、設定を取得、変更、および更新できるスクリプト インターフェイスです。 詳細については [、「USING WMI」を参照してください](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi)。 

|Task  |追加情報  |
|---------|---------|
|**デバイスでクラウドによる保護** を有効にする    |[Windows 管理命令 (WMI) を使用してクラウドによる保護を有効にする](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|Microsoft Defender ウイルス **対策の設定を取得、** 変更、および更新する     | [WMI を使用して Microsoft Defender ウイルス対策を構成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[利用可能な WMI クラスとサンプル スクリプトの一覧を確認する](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>WMIv2 Provider の参照 [情報Windows Defenderアーカイブされたファイルも参照してください。](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Microsoft マルウェア保護ユーティリティを使用して Microsoft Defender for Endpoint をCommand-Lineする (MPCmdRun.exe)

個々のデバイスで、スキャンの実行、診断トレースの開始、セキュリティ インテリジェンスの更新の確認など、mpcmdrun.exeコマンド ライン ツールを使用できます。 ユーティリティは で確認できます `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 コマンド プロンプトから実行します。

|Task  |追加情報  |
|---------|---------|
|**Microsoft Defender ウイルス対策の管理**  |[Microsoft Defender ウイルス対策の構成とmpcmdrun.exe](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Microsoft Defender セキュリティ センターを構成する

まだ行っていない場合は **、Microsoft Defender Security Center** ( ) を構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報 [https://securitycenter.windows.com](https://securitycenter.windows.com) の表示を行います。 

また、エンド ユーザーが Microsoft Defender セキュリティ センターで表示できる機能と機能を構成できます。

- [Microsoft Defender セキュリティ センターの概要](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [エンドポイント保護: Microsoft Defender セキュリティ センター](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>次の手順

- [脅威と脆弱性の管理の概要を確認する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Microsoft Defender Security Center のセキュリティ操作ダッシュボードにアクセスする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Intune を使用してエンドポイント用 Microsoft Defender を管理する](manage-atp-post-migration-intune.md)
