---
title: Configuration Manager を使用して Microsoft Defender for Endpoint を管理する
description: Configuration Manager を使用して Microsoft Defender for Endpoint を管理する方法について説明します。
keywords: 移行後、管理、運用、メンテナンス、使用率、Configuration Manager、Microsoft Defender for Endpoint、edr
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
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 11/29/2021
ms.reviewer: chventou
ms.openlocfilehash: 40bac47a4c22e3a8706ed4b38b479fff5d500410
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62465230"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration Manager を使用して Microsoft Defender for Endpoint を管理する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


デバイス [(Microsoft エンドポイント マネージャーの](/mem)脅威保護機能を管理するには、[Microsoft Intune (Intune](/mem/intune/fundamentals/what-is-intune)) と [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) を含むデバイスを使用することをお勧めします。エンドポイントと呼ばれます)。

- [詳細については、エンドポイント マネージャー](/mem/endpoint-manager-overview)
- [Configuration Manager と Intune を使用して 11 Windows 10デバイスWindows Microsoft Defender for Endpoint を共同管理する](manage-mde-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration Manager を使用して Microsoft Defender for Endpoint を構成する

<br/><br/>

|タスク|追加情報|
|---|---|
|**Configuration Manager コンソールをまだ** インストールしていない場合はインストールする <br/><br/> *Configuration Manger コンソールをまだ持ってない場合は、これらのリソースを使用してビットを取得してインストールします。*|[インストール メディアの取得](/mem/configmgr/core/servers/deploy/install/get-install-media) <br/><br/> [Configuration Manager コンソールのインストール](/mem/configmgr/core/servers/deploy/install/install-consoles)|
|**Configuration Manager を使用してデバイスを** Microsoft Defender for Endpoint にオンボードする <br/><br/> *デバイス (またはエンドポイント) が Microsoft Defender for Endpoint にまだオンボードされていない場合は、Configuration Manager を使用して実行できます。*|[Configuration Manager を使用して Microsoft Defender for Endpoint にオンボードする](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)|
|**マルウェア対策ポリシーを管理し、クライアント Windowsファイアウォール** セキュリティを管理する (エンドポイント) <br/><br/> *エンドポイント保護機能 (Microsoft Defender for Endpoint、Exploit Protection、アプリケーション制御、マルウェア対策、ファイアウォール設定など) を構成します。*|[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)|
|**組織のデバイスでマルウェア対策更新プログラムを更新** する方法を選択する <br/><br/> *Configuration Manager Endpoint Protectionを使用すると、組織のデバイスでマルウェア対策定義を最新の状態に保つために、いくつかの方法から選択できます。*|[Endpoint Protection の定義の更新を構成する](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/> [Configuration Manager を使用して定義の更新プログラムを配信する](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr)|
|**ネットワーク保護を有効** にして、従業員が悪意のあるコンテンツをインターネット上で使用するアプリを使用するのを防ぐ <br/><br/> *テスト環境で [ネットワーク保護のために](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 監査モードを最初に使用して、展開前にブロックされるアプリを確認することをお勧めします。*|[Configuration Manager でネットワーク保護を有効にする](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)|
|**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する <br/><br/> *フォルダー アクセスの制御は、アンチランソイエムウェア保護とも呼ばれます。*|[エンドポイント保護: フォルダー アクセスの制御](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [Microsoft Endpoint Configuration Manage でフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager)|

## <a name="configure-your-microsoft-365-defender-portal"></a>ポータルをMicrosoft 365 Defenderする

まだ実行していない場合は、Microsoft 365 Defender ポータルを構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報の表示を行います。 「攻撃が検出および停止されている間に、"初期アクセスアラート" などのアラートがトリガーされ、Microsoft 365 Defender[されました](/microsoft-365/security/defender/microsoft-365-defender)。 エンド ユーザーがポータルで表示できる機能と機能を構成Microsoft 365 Defenderすることもできます。

- [概要 Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [エンドポイント保護: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次の手順

- [脅威と脆弱性の管理の概要を取得する](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [ポータルのセキュリティMicrosoft 365 Defenderダッシュボードにアクセスする](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [Intune を使用してエンドポイント用 Microsoft Defender を管理する](manage-mde-post-migration-intune.md)
