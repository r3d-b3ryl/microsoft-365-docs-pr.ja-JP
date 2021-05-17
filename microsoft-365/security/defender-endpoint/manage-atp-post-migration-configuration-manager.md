---
title: Configuration Manager を使用して Microsoft Defender for Endpoint を管理する
description: Configuration Manager を使用して Microsoft Defender for Endpoint を管理する方法について説明します。
keywords: 移行後、管理、運用、メンテナンス、使用率、Configuration Manager、Microsoft Defender for Endpoint、edr
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
ms.openlocfilehash: 0cd52388feb987b4231d911cd3c3fd10babba017
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933207"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration Manager を使用して Microsoft Defender for Endpoint を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Microsoft エンドポイント マネージャー (Intune) と Microsoft Intune [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem) [(Configuration](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) Manager) を含む[Microsoft エンドポイント マネージャー](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)を使用して、デバイス (エンドポイントとも呼ばれます) の組織の脅威保護機能を管理することをお勧めします。 
- [詳細については、エンドポイント マネージャー](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [Configuration Manager と Intune を使用して、Windows 10の Microsoft Defender for Endpoint を共同管理する](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration Manager を使用して Microsoft Defender for Endpoint を構成する

|タスク  |追加情報  |
|---------|---------|
|**Configuration Manager コンソールをまだ** インストールしていない場合はインストールする<br/><br/>*Configuration Manger コンソールをまだ持ってない場合は、これらのリソースを使用してビットを取得してインストールします。* |[インストール メディアの取得](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Configuration Manager コンソールのインストール](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Configuration Manager を使用してデバイスを** Microsoft Defender for Endpoint にオンボードする <br/><br/> *デバイス (またはエンドポイント) が Microsoft Defender for Endpoint にまだオンボードされていない場合は、Configuration Manager を使用して実行できます。*   |[Configuration Manager を使用して Microsoft Defender for Endpoint にオンボードする](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**マルウェア対策ポリシーを管理し、クライアント Windowsファイアウォール** セキュリティ (エンドポイント) を管理する<br/><br/>*エンドポイント保護機能 (Microsoft Defender for Endpoint、Exploit Protection、アプリケーション制御、マルウェア対策、ファイアウォール設定など) を構成します。*  |[Configuration Manager: Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**組織のデバイスでマルウェア対策更新プログラムを更新** する方法を選択する <br/><br/>*Configuration Manager Endpoint Protectionを使用すると、組織のデバイスでマルウェア対策定義を最新の状態に保つために、いくつかの方法から選択できます。* |[定義の更新プログラムを構成Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Configuration Manager を使用して定義の更新プログラムを配信する](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**ネットワーク保護を有効** にして、従業員が悪意のあるコンテンツをインターネット上で使用するアプリを使用するのを防ぐ <br/><br/>*テスト環境で [ネットワーク保護のために](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) 監査モードを最初に使用して、展開前にブロックされるアプリを確認することをお勧めします。* |[Configuration Manager でネットワーク保護を有効にする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する <br/><br/>*フォルダー アクセスの制御は、アンチランソイエムウェア保護とも呼ばれます。*   |[エンドポイント保護: フォルダー アクセスの制御](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Microsoft Endpoint Configuration Manage でフォルダー アクセスの制御を有効にする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>サーバーを構成Microsoft Defender セキュリティ センター

まだ行っていない場合は **、Microsoft Defender セキュリティ センター** ( ) を構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報 [https://securitycenter.windows.com](https://securitycenter.windows.com) の表示を行います。 

また、エンド ユーザーに表示される機能と機能を構成Microsoft Defender セキュリティ センター。

- [アプリケーションのMicrosoft Defender セキュリティ センター](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [エンドポイント保護: Microsoft Defender セキュリティ センター](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次の手順

- [アプリケーションの概要を脅威と脆弱性の管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [セキュリティ操作ダッシュボードMicrosoft Defender セキュリティ センターアクセスする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Intune を使用してエンドポイント用 Microsoft Defender を管理する](manage-atp-post-migration-intune.md)
