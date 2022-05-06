---
title: グループ ポリシー オブジェクトを使用してMicrosoft Defender for Endpointを管理する
description: グループ ポリシー オブジェクトを使用してMicrosoft Defender for Endpointを管理する方法について説明します
keywords: 移行後, 管理, 運用, メンテナンス, 使用率, PowerShell, Microsoft Defender for Endpoint, edr
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
ms.topic: article
ms.date: 11/29/2021
ms.reviewer: chventou
ms.openlocfilehash: 2155c72d7008bf3669a1908b3fd866877eb36a7c
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464616"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>グループ ポリシー オブジェクトを使用したMicrosoft Defender for Endpointの管理

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> [Microsoft エンドポイント マネージャー](/mem)を使用して、デバイス (エンドポイントとも呼ばれる) に対する組織の脅威保護機能を管理することをお勧めします。 エンドポイント マネージャーには[、Microsoft Intune](/mem/intune/fundamentals/what-is-intune)と[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)が含まれます。 **[エンドポイント マネージャーの詳細については、こちらを参照してください](/mem/endpoint-manager-overview)**。

Azure Active Directory Domain Services の グループ ポリシー オブジェクトを使用して、Microsoft Defender for Endpointの一部の設定を管理できます。

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>グループ ポリシー オブジェクトを使用してMicrosoft Defender for Endpointを構成する

> [!NOTE]
> [Windows Server 2012 R2 と 2016 の新しい統合Microsoft Defender for Endpoint ソリューション](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)を使用している場合は、中央ストアで最新の ADMX ファイルを使用して、正しいMicrosoft Defender for Endpoint ポリシー オプションにアクセスしていることを確認してください。 [Windowsで グループ ポリシー 管理用のセントラル ストアを作成および管理する方法と、Windows 10](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)**で使用する** 最新のファイルをダウンロードする方法を参照してください。 

次の表に、グループ ポリシー オブジェクトを使用してMicrosoft Defender for Endpointを構成するために実行できるさまざまなタスクを示します。

<br/><br/>

|タスク|追加情報|
|---|---|
|**ユーザー オブジェクトとコンピューター オブジェクトの設定を管理する** <br/><br/> *組み込みのグループ ポリシー オブジェクトをカスタマイズするか、組織のニーズに合わせてカスタム グループ ポリシー オブジェクトと組織単位を作成します。*|[Azure Active Directory Domain Services マネージド ドメインでグループ ポリシーを管理する](/azure/active-directory-domain-services/manage-group-policy)|
|**Microsoft Defender ウイルス対策を構成する** <br/><br/> *ポリシー設定、除外、修復、組織のデバイス (エンドポイントとも呼ばれる) でのスケジュールされたスキャンなど、ウイルス対策機能&機能を構成します。*|[グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を管理する](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/> [グループ ポリシーを使用してクラウド配信保護を有効にする](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)|
|**組織の攻撃面削減ルールを管理する** <br/><br/> *ファイル&フォルダーを除外するか、ユーザーのデバイスに表示される通知アラートにカスタム テキストを追加して、攻撃対象の縮小ルールをカスタマイズします。*|[グループ ポリシー オブジェクトを使用して攻撃面の縮小ルールをカスタマイズする](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders)|
|**エクスプロイト保護の設定を管理する** <br/><br/> *エクスプロイト保護設定をカスタマイズし、構成ファイルをインポートしてから、グループ ポリシーを使用してその構成ファイルをデプロイできます。*|[エクスプロイト保護設定をカスタマイズする](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [エクスプロイト保護構成のインポート、エクスポート、展開](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml) <br/><br/> [グループ ポリシーを使用して構成を配布する](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)|
|**ネットワーク保護を有効にして** 、従業員がインターネット上の悪意のあるコンテンツのアプリを使用できないようにする <br/><br/> *テスト環境でネットワーク保護に最初に [監査モード](/microsoft-365/security/defender-endpoint/evaluate-network-protection) を使用して、ロールアウトする前にブロックされるアプリを確認することをお勧めします。*|[グループ ポリシーを使用してネットワーク保護を有効にする](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)|
|ランサムウェアから保護するように **フォルダー アクセスの制御を構成** する <br/><br/> *[フォルダー アクセスの制御](/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソーイウェア保護とも呼ばれます。*|[グループ ポリシーを使用してフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy)|
|インターネット上の悪意のあるサイトやファイルから保護するように **Microsoft Defender SmartScreenを構成** します。|[グループ ポリシーを使用してMicrosoft Defender SmartScreen グループ ポリシーとモバイル デバイス管理 (MDM) の設定を構成する](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)|
|Windowsを実行している組織のデバイスに関する情報を保護するように **暗号化と BitLocker を構成** する|[BitLocker グループ ポリシー設定](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings)|
|資格情報盗難攻撃から保護するように **Microsoft Defender Credential Guard を構成する**|[グループ ポリシーを使用してWindows Defender Credential Guard を有効にする](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを構成する

まだ行っていない場合は、アラートを表示し、脅威保護機能を構成し、組織の全体的なセキュリティ体制に関する詳細情報を表示するようにMicrosoft 365 Defender ポータルを構成します。 [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)を参照してください。 エンド ユーザーがMicrosoft 365 Defender ポータルで表示できる機能の有無と機能を構成することもできます。

- [Microsoft 365 Defenderの概要](/microsoft-365/security/defender-endpoint/use)
- [エンドポイント保護: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次の手順

- [脅威と脆弱性の管理の概要を取得する](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Microsoft 365 Defender ポータルのセキュリティ操作ダッシュボードにアクセスする](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [IntuneでMicrosoft Defender for Endpointを管理する](manage-mde-post-migration-intune.md)
