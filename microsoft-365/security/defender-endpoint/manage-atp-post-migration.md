---
title: 移行後の Microsoft Defender for Endpoint の管理
description: Microsoft Defender for Endpoint への切り替えが行われたので、次に、脅威保護機能を管理します。
keywords: 移行後、管理、運用、メンテナンス、使用率、Windows Defender Advanced Threat Protection、atp、edr
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
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: 54302f38f0fd63560ecd1c5545efa4621c6b9bbd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185863"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Microsoft Defender for Endpoint の管理、移行後

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

以前のエンドポイント保護およびウイルス対策ソリューションから Microsoft Defender for Endpoint に移動した後、次に機能と機能を管理します。 Microsoft Intune と[Microsoft Endpoint Configuration](https://docs.microsoft.com/mem/endpoint-manager-overview) [Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)を含む Microsoft [Endpoint](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) Manager を使用して、組織のデバイスとセキュリティ設定を管理することをお勧めします。 ただし、Azure Active Directory ドメイン サービスのグループ ポリシー オブジェクトなど、他のツール/ [メソッドを使用できます](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)。 

次の表に、使用できるさまざまなツール/メソッドの一覧と、詳細へのリンクを示します。 
<br/><br/>

|ツール/メソッド  |説明  |
|---------|---------|
|Microsoft Defender **[セキュリティ センターの脅威](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** と脆弱性管理ダッシュボードの分析情報 ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |脆弱性管理ダッシュボード&脅威は、セキュリティ運用チームが使用して、露出を減らし、組織のセキュリティ体制を改善するために使用できる、アクション可能な情報を提供します。 <br/><br/>「 [脅威&の管理」および「Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [Defender セキュリティ センターの概要」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)。  |
|**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (推奨)    |Microsoft Endpoint Manager のコンポーネントである [Microsoft](https://docs.microsoft.com/mem/endpoint-manager-overview)Intune (Intune) は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) に重点を当てました。 Intune では、携帯電話、タブレット、ラップトップなど、組織のデバイスの使用方法を制御できます。 特定のポリシーを構成して、アプリケーションを制御できます。 <br/><br/>[「Intune を使用した Microsoft Defender for Endpoint の管理」を参照してください](manage-atp-post-migration-intune.md)。         |
|**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager) (以前は System Center Configuration Manager と呼ばれる) は [、Microsoft Endpoint Manager のコンポーネントです](https://docs.microsoft.com/mem/endpoint-manager-overview)。 Configuration Manager は、ユーザー、デバイス、ソフトウェアを管理するための強力なツールです。<br/><br/>「Manage [Microsoft Defender for Endpoint with Configuration Manager」を参照してください](manage-atp-post-migration-configuration-manager.md)。        |
|**[Azure Active Directory ドメイン サービスのグループ ポリシー オブジェクト](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory ドメイン サービスには、](https://docs.microsoft.com/azure/active-directory-domain-services/overview) ユーザーとデバイス用の組み込みのグループ ポリシー オブジェクトが含まれています。 環境で必要に応じて組み込みのグループ ポリシー オブジェクトをカスタマイズし、カスタム グループ ポリシー オブジェクトと組織単位 (OUs) を作成できます。 <br/><br/>「 [グループ ポリシー オブジェクトを使用した Microsoft Defender for Endpoint の管理」を参照してください](manage-atp-post-migration-group-policy-objects.md)。 |
|**[PowerShell、WMI、およびMPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Microsoft Endpoint Manager (Intune と Configuration Manager を含む) を使用して、組織のデバイス上の脅威保護機能を管理することをお勧めします。ただし、PowerShell、WMI、またはデバイス ツールを使用して、個々のデバイス (エンドポイント) の Microsoft Defender ウイルス対策設定など、一部の設定MPCmdRun.exeできます。*<br/><br/>PowerShell を使用して、Microsoft Defender ウイルス対策、エクスプロイト保護、攻撃表面の縮小ルールを管理できます。 「Configure [Microsoft Defender for Endpoint with PowerShell」を参照してください](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)。<br/><br/>Windows 管理インストルメンテーション (WMI) を使用して、Microsoft Defender ウイルス対策と除外を管理できます。 「Configure [Microsoft Defender for Endpoint with WMI」を参照してください](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)。<br/><br/>Microsoft Malware Protection Command-Line ユーティリティ (MPCmdRun.exe) を使用して、Microsoft Defender ウイルス対策と除外を管理し、ネットワークとクラウド間の接続を検証できます。 「Configure [Microsoft Defender for Endpoint with MPCmdRun.exe」 を参照してください ](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)。 |

## <a name="see-also"></a>関連項目

- [エンドポイント向け Microsoft Defender で誤検知/負に対処する](defender-endpoint-false-positives-negatives.md)
