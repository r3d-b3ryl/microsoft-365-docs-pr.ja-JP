---
title: グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する
description: グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する方法について説明します。
keywords: 移行後、管理、運用、メンテナンス、使用率、PowerShell、Microsoft Defender for Endpoint、edr
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
ms.date: 09/23/2021
ms.reviewer: chventou
ms.openlocfilehash: 88225337d0c9edbae8185a34bd7d98378007c72a
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240574"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> デバイス (エンドポイント[ともMicrosoft エンドポイント マネージャー)](/mem)に対する組織の脅威保護機能を管理するには、この機能を使用することをお勧めします。 エンドポイント マネージャーには、Microsoft Intuneと[](/mem/intune/fundamentals/what-is-intune)Microsoft Endpoint Configuration Manager[が含Microsoft Endpoint Configuration Manager。](/mem/configmgr/core/understand/introduction) **[詳細については、「エンドポイント マネージャー」 を参照してください](/mem/endpoint-manager-overview)**。

ドメイン サービスのグループ ポリシー オブジェクトをAzure Active Directory、Microsoft Defender for Endpoint のいくつかの設定を管理できます。

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を構成する

> [!NOTE]
> Windows Server 2012 R2 および[2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)の新しい統合 Microsoft Defender for Endpoint ソリューションを使用している場合は、中央ストアで最新の ADMX ファイルを使用して、正しい Microsoft Defender ポリシー オプションにアクセスしていることを確認してください。 「グループ [ポリシー管理](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)用中央ストア管理用テンプレートを作成および管理する方法」を参照し、Windows で使用する最新のファイルをダウンロード **Windows 10。** 

次の表に、グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を構成するために実行できるさまざまなタスクを示します。

<br/><br/>

|タスク|追加情報|
|---|---|
|**ユーザー オブジェクトとコンピューター オブジェクトの設定を管理する** <br/><br/> *組み込みのグループ ポリシー オブジェクトをカスタマイズするか、組織のニーズに合わせてカスタム グループ ポリシー オブジェクトと組織単位を作成します。*|[ドメイン サービス管理ドメインAzure Active Directoryグループ ポリシーの管理](/azure/active-directory-domain-services/manage-group-policy)|
|**構成Microsoft Defender ウイルス対策** <br/><br/> *組織のデバイス&ポリシー設定、除外、修復、スケジュールされたスキャン (エンドポイントとも呼ばれます) などのウイルス対策機能を構成します。*|[グループ ポリシー設定を使用して、グループ ポリシーの構成とMicrosoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/> [グループ ポリシーを使用してクラウド配信の保護を有効にする](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)|
|**組織の攻撃表面の縮小ルールを管理する** <br/><br/> *フォルダー内のファイルを除外するか、&デバイスに表示される通知通知にカスタム テキストを追加して、攻撃表面の縮小ルールをカスタマイズします。*|[グループ ポリシー オブジェクトを使用して攻撃表面の縮小ルールをカスタマイズする](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders)|
|**エクスプロイト保護の設定を管理する** <br/><br/> *エクスプロイト保護設定をカスタマイズし、構成ファイルをインポートしてから、グループ ポリシーを使用してその構成ファイルを展開できます。*|[エクスプロイト保護の設定をカスタマイズする](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [エクスプロイト保護構成のインポート、エクスポート、展開](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml) <br/><br/> [グループ ポリシーを使用して構成を配布する](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)|
|**ネットワーク保護を有効** にして、従業員が悪意のあるコンテンツをインターネット上で使用するアプリを使用するのを防ぐ <br/><br/> *テスト環境で [ネットワーク保護のために](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 監査モードを最初に使用して、展開前にブロックされるアプリを確認することをお勧めします。*|[グループ ポリシーを使用してネットワーク保護を有効にする](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)|
|**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する <br/><br/> *[フォルダー アクセスの制御](/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソイエムウェア保護とも呼ばれます。*|[グループ ポリシーを使用してフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy)|
|**インターネット上Microsoft Defender SmartScreen** 悪意のあるサイトやファイルから保護する方法を構成します。|[グループ Microsoft Defender SmartScreenを使用して、グループ ポリシーとモバイル デバイス管理 (MDM) の設定を構成する](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)|
|**暗号化と BitLocker を構成** して、組織で実行されているデバイスの情報を保護Windows|[BitLocker グループ ポリシーの設定](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings)|
|**資格情報の盗難攻撃から** 保護するために Microsoft Defender Credential Guard を構成する|[グループ ポリシー Windows Defenderして Credential Guard を有効にする](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy)|

## <a name="configure-your-microsoft-365-defender-portal"></a>ポータルをMicrosoft 365 Defenderする

まだ実行していない場合は、Microsoft 365 Defender ポータルを構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報の表示を行います。 「Microsoft 365 Defender」[を参照してください](microsoft-defender-security-center.md)。 エンド ユーザーがポータルで表示できる機能と機能を構成Microsoft 365 Defenderすることもできます。

- [概要 Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [エンドポイント保護: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次の手順

- [脅威と脆弱性の管理の概要を取得する](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [ポータルのセキュリティMicrosoft 365 Defenderダッシュボードにアクセスする](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [Intune を使用してエンドポイント用 Microsoft Defender を管理する](manage-atp-post-migration-intune.md)
