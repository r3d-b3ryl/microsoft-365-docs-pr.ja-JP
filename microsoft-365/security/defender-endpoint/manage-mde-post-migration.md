---
title: 初期セットアップまたは移行後のMicrosoft Defender for Endpointの管理
description: Microsoft Defender for Endpointに切り替えたので、次の手順は脅威保護機能を管理することです。
keywords: 移行後, 管理, 運用, メンテナンス, 使用率, Microsoft Defender for Endpoint, edr
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
ms.topic: conceptual
ms.date: 07/01/2022
ms.reviewer: chventou
ms.openlocfilehash: 3158f75d98d1536f54f9c5387c1515fe64be1c25
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67324037"
---
# <a name="manage-microsoft-defender-for-endpoint-after-initial-setup-or-migration"></a>初期セットアップまたは移行後のMicrosoft Defender for Endpointの管理

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpointを設定して構成したら、次の手順では機能と機能を管理します。 組織[の](/mem/endpoint-manager-overview)デバイスとセキュリティ設定を管理するには、[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)と [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)を含む Microsoft エンドポイント マネージャーを使用することをお勧めします。 ただし、[Azure Active Directory Domain Servicesの グループ ポリシー オブジェクト](/azure/active-directory-domain-services/manage-group-policy)など、他のツールやメソッドを使用することもできます。

次の表に、使用できるさまざまなツール/方法と、詳細を確認するためのリンクを示します。

|ツール/メソッド|説明|
|---|---|
|Microsoft 365 Defender ポータルで **[ダッシュボードの分析情報](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** を [Microsoft Defender 脆弱性の管理](https://security.microsoft.com/)する|Defender の脆弱性管理ダッシュボードには、セキュリティ運用チームが公開を減らし、組織のセキュリティ体制を改善するために使用できる実用的な情報が提供されます。 <br/><br/> [Defender の脆弱性の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)と[Microsoft 365 Defenderの概要に関するページ](/microsoft-365/security/defender-endpoint/use)を参照してください。|
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (推奨)|microsoft エンドポイント マネージャーのコンポーネントであるMicrosoft Intune ([Intune](/mem/endpoint-manager-overview)) は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) に重点を置いています。 Intuneを使用すると、携帯電話、タブレット、ノート PC など、組織のデバイスの使用方法を制御できます。 また、特定のポリシーを構成してアプリケーションを制御することもできます。 <br/><br/> [Intuneを使用したMicrosoft Defender for Endpointの管理に関するページを参照](manage-mde-post-migration-intune.md)してください。|
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**|Microsoft エンドポイント マネージャー (Configuration Manager) は、以前は System Center Configuration Manager と呼ば[エンドポイント マネージャーのコンポーネント](/mem/endpoint-manager-overview)です。 Configuration Managerは、ユーザー、デバイス、ソフトウェアを管理するための強力なツールです。 <br/><br/> Configuration Manager[を使用したMicrosoft Defender for Endpointの管理に関するページを参照](manage-mde-post-migration-configuration-manager.md)してください。|
|**[Azure Active Directory Domain Servicesのグループ ポリシー オブジェクト](/azure/active-directory-domain-services/manage-group-policy)**|[Azure Active Directory Domain Services](/azure/active-directory-domain-services/overview)には、ユーザーとデバイス用の組み込みのグループ ポリシー オブジェクトが含まれています。 環境に必要に応じて、組み込みのグループ ポリシー オブジェクトをカスタマイズしたり、カスタム グループ ポリシー オブジェクトや組織単位 (OU) を作成したりできます。 <br/><br/> グループ ポリシー [オブジェクトを使用したMicrosoft Defender for Endpointの管理に関するページを参照してください](manage-mde-post-migration-group-policy-objects.md)。|
|**[PowerShell、WMI、MPCmdRun.exe](manage-mde-post-migration-other-tools.md)**|*Microsoft エンドポイント マネージャー (IntuneとConfiguration Managerを含む) を使用して、組織のデバイス上の脅威保護機能を管理することをお勧めします。ただし、PowerShell、WMI、またはMPCmdRun.exe ツールを使用して、個々のデバイス (エンドポイント) の Microsoft Defender ウイルス対策設定など、一部の設定を構成できます。* <br/><br/> PowerShell を使用して、Microsoft Defender ウイルス対策、エクスプロイト保護、および攻撃面の縮小ルールを管理できます。 [PowerShell を使用したMicrosoft Defender for Endpointの構成に関するページを参照](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)してください。 <br/><br/> Windows Management Instrumentation (WMI) を使用して、Microsoft Defender ウイルス対策と除外を管理できます。 [WMI を使用したMicrosoft Defender for Endpointの構成に関するページを](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)参照してください。 <br/><br/> Microsoft Malware Protection Command-Line ユーティリティ (MPCmdRun.exe) を使用して、Microsoft Defender ウイルス対策と除外を管理したり、ネットワークとクラウド間の接続を検証したりできます。 [MPCmdRun.exeを使用したMicrosoft Defender for Endpointの構成に関するページを参照](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)してください。|


## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)
