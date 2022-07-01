---
title: Configuration Managerを使用してMicrosoft Defender for Endpointを管理する
description: Configuration Managerを使用してMicrosoft Defender for Endpointを管理する方法について説明します
keywords: 移行後, 管理, 運用, メンテナンス, 使用率, Configuration Manager, Microsoft Defender for Endpoint, edr
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
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 11/29/2021
ms.reviewer: chventou
ms.openlocfilehash: e83306f4af82d8a24745ca5af3d146bb50c41ee7
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66603398"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration ManagerでMicrosoft Defender for Endpointを管理する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


Microsoft Intune (Intune) と [Microsoft Endpoint Configuration Manager](/mem) ([Configuration Manager](/mem/intune/fundamentals/what-is-intune)) を含む [Microsoft エンドポイント マネージャー](/mem/configmgr/core/understand/introduction)を使用することをお勧めします) を使用して、デバイス (エンドポイントとも呼ばれます) に対する組織の脅威保護機能を管理します。

- [エンドポイント マネージャーの詳細を確認する](/mem/endpoint-manager-overview)
- [Configuration ManagerとIntuneを使用して、Windows 10 デバイスとWindows 11 デバイスのMicrosoft Defender for Endpointを共同管理する](manage-mde-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration ManagerでMicrosoft Defender for Endpointを構成する

<br/><br/>

|タスク|追加情報|
|---|---|
|**Configuration Manager コンソール** をまだインストールしていない場合はインストールする <br/><br/> *Configuration Manger コンソールがまだない場合は、これらのリソースを使用してビットを取得してインストールします。*|[インストール メディアを取得する](/mem/configmgr/core/servers/deploy/install/get-install-media) <br/><br/> [Configuration Manager コンソールをインストールする](/mem/configmgr/core/servers/deploy/install/install-consoles)|
|**Configuration Managerを使用してデバイスを** Microsoft Defender for Endpointにオンボードする <br/><br/> *デバイス (またはエンドポイント) がまだMicrosoft Defender for Endpointにオンボードされていない場合は、Configuration Managerを使用して行うことができます。*|[Configuration Managerを使用してMicrosoft Defender for Endpointにオンボードする](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)|
|クライアント コンピューター (エンドポイント) の **マルウェア対策ポリシーと Windows ファイアウォール セキュリティを管理** する <br/><br/> *Microsoft Defender for Endpoint、エクスプロイト保護、アプリケーション制御、マルウェア対策、ファイアウォール設定など、エンドポイント保護機能を構成します。*|[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)|
|組織のデバイスで **マルウェア対策更新プログラムを更新する方法を選択** する <br/><br/> *Configuration Managerの Endpoint Protection を使用すると、組織のデバイスでマルウェア対策定義を最新の状態に保ついくつかの方法から選択できます。*|[Endpoint Protection の定義の更新を構成する](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/> [Configuration Managerを使用して定義の更新を配信する](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr)|
|**ネットワーク保護を有効にして** 、従業員がインターネット上の悪意のあるコンテンツのアプリを使用できないようにする <br/><br/> *テスト環境でネットワーク保護に最初に [監査モード](/microsoft-365/security/defender-endpoint/evaluate-network-protection) を使用して、ロールアウトする前にブロックされるアプリを確認することをお勧めします。*|[Configuration Managerを使用してネットワーク保護を有効にする](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)|
|ランサムウェアから保護するように **フォルダー アクセスの制御を構成** する <br/><br/> *フォルダー アクセスの制御は、アンチランソーイウェア保護とも呼ばれます。*|[エンドポイント保護: フォルダー アクセスの制御](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [Microsoft Endpoint Configuration Manage でフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを構成する

まだ行っていない場合は、アラートを表示し、脅威保護機能を構成し、組織の全体的なセキュリティ体制に関する詳細情報を表示するようにMicrosoft 365 Defender ポータルを構成します。 攻撃が検出されて停止した間に、"初期アクセス アラート" などのアラートがトリガーされ[、Microsoft 365 Defender ポータル](/microsoft-365/security/defender/microsoft-365-defender)に表示された場合を参照してください。 エンド ユーザーがMicrosoft 365 Defender ポータルで表示できる機能の有無と機能を構成することもできます。

- [Microsoft 365 Defenderの概要](/microsoft-365/security/defender-endpoint/use)
- [エンドポイント保護: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次のステップ

- [脅威と脆弱性の管理の概要を取得する](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Microsoft 365 Defender ポータルのセキュリティ操作ダッシュボードにアクセスする](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [IntuneでMicrosoft Defender for Endpointを管理する](manage-mde-post-migration-intune.md)
