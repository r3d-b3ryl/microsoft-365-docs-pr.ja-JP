---
title: 移行後の Microsoft Defender for Endpoint の管理
description: Microsoft Defender for Endpoint への切り替えが行われたので、次に、脅威保護機能を管理します。
keywords: 移行後、管理、運用、メンテナンス、使用率、Microsoft Defender for Endpoint、edr
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
ms.topic: conceptual
ms.date: 09/23/2021
ms.reviewer: chventou
ms.openlocfilehash: 1b0dfbb7996cde595fc4d133f1a946e8692d8941
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206901"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Microsoft Defender for Endpoint の管理、移行後

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

以前のエンドポイント保護およびウイルス対策ソリューションから Microsoft Defender for Endpoint に移動した後、次に機能と機能を管理します。 組織のデバイス[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)セキュリティ設定をMicrosoft Intune、Microsoft Endpoint Configuration Manager[](/mem/intune/fundamentals/what-is-intune)を使用することをお勧めします[](/mem/configmgr/core/understand/introduction)。 ただし、ドメイン サービスのグループ ポリシー オブジェクトなど、他のツールAzure Active Directory[使用できます](/azure/active-directory-domain-services/manage-group-policy)。

次の表に、使用できるさまざまなツール/メソッドの一覧と、詳細へのリンクを示します。

<br/><br/>

|ツール/メソッド|説明|
|---|---|
|**[脅威と脆弱性の管理ダッシュボードの分析情報](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** [(Microsoft 365 Defenderポータル](https://security.microsoft.com/))|ダッシュボード& 脆弱性の管理脅威は、セキュリティ運用チームが使用できるアクション可能な情報を提供して、露出を減らし、組織のセキュリティ体制を改善します。 <br/><br/> 「[脅威の& 脆弱性の管理」](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)および「[脅威の概要」をMicrosoft 365 Defender。](/microsoft-365/security/defender-endpoint/use)|
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (推奨)|Microsoft Intune (Intune) は、Microsoft エンドポイント マネージャー[](/mem/endpoint-manager-overview)デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) に重点を当てました。 Intune では、携帯電話、タブレット、ラップトップなど、組織のデバイスの使用方法を制御できます。 特定のポリシーを構成して、アプリケーションを制御できます。 <br/><br/> [「Intune を使用した Microsoft Defender for Endpoint の管理」を参照してください](manage-atp-post-migration-intune.md)。|
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**|Microsoft エンドポイント マネージャー (Configuration Manager) (以前は System Center Configuration Manager と呼ばれる) は、Microsoft エンドポイント マネージャー の[コンポーネントです](/mem/endpoint-manager-overview)。 Configuration Manager は、ユーザー、デバイス、ソフトウェアを管理するための強力なツールです。 <br/><br/> 「Manage [Microsoft Defender for Endpoint with Configuration Manager」を参照してください](manage-atp-post-migration-configuration-manager.md)。|
|**[ドメイン サービスのグループ Azure Active Directory オブジェクト](/azure/active-directory-domain-services/manage-group-policy)**|[Azure Active Directoryドメイン サービスには、](/azure/active-directory-domain-services/overview)ユーザーとデバイス用の組み込みのグループ ポリシー オブジェクトが含まれています。 環境で必要に応じて組み込みのグループ ポリシー オブジェクトをカスタマイズし、カスタム グループ ポリシー オブジェクトと組織単位 (OUs) を作成できます。 <br/><br/> 「 [グループ ポリシー オブジェクトを使用した Microsoft Defender for Endpoint の管理」を参照してください](manage-atp-post-migration-group-policy-objects.md)。|
|**[PowerShell、WMI、MPCmdRun.exe](manage-atp-post-migration-other-tools.md)**|*組織のデバイスMicrosoft エンドポイント マネージャー脅威保護機能を管理するには、Intune と Configuration Manager を含むセキュリティ ポリシー (Intune と Configuration Manager を含む) を使用することをお勧めします。ただし、PowerShell、WMI、または Microsoft Defender ウイルス対策 ツールを使用して、個々のデバイス (エンドポイント) の設定などの一部の設定MPCmdRun.exeできます。* <br/><br/> PowerShell を使用して、攻撃Microsoft Defender ウイルス対策、攻撃表面の縮小ルールを管理できます。 「Configure [Microsoft Defender for Endpoint with PowerShell」を参照してください](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)。 <br/><br/> 管理インストルメンWindows (WMI) を使用して、Microsoft Defender ウイルス対策除外を管理できます。 「Configure [Microsoft Defender for Endpoint with WMI」を参照してください](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)。 <br/><br/> Microsoft Malware Protection Command-Line ユーティリティ (MPCmdRun.exe) を使用して、Microsoft Defender ウイルス対策 と除外を管理し、ネットワークとクラウド間の接続を検証できます。 「Configure [Microsoft Defender for Endpoint with MPCmdRun.exe」 を参照してください ](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)。|


## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)
