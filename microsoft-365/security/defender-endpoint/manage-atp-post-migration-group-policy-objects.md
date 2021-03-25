---
title: グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する
description: グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する方法について説明します。
keywords: 移行後、管理、運用、メンテナンス、使用率、PowerShell、Windows Defender Advanced Threat Protection、atp、edr
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
ms.openlocfilehash: 6d10bd932d9414f1460076d3fe7ca8dbed8041a6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185659"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Microsoft [Endpoint Manager を使用して](https://docs.microsoft.com/mem) 、デバイス (エンドポイントとも呼ばれます) の組織の脅威保護機能を管理することをお勧めします。 エンドポイント マネージャーには [、Microsoft Intune と](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) Microsoft Endpoint Configuration Manager [が含まれます](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)。 **[エンドポイント マネージャーの詳細については、次のページを参照してください](https://docs.microsoft.com/mem/endpoint-manager-overview)**。 

Azure Active Directory ドメイン サービスのグループ ポリシー オブジェクトを使用して、Microsoft Defender for Endpoint のいくつかの設定を管理できます。

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を構成する

次の表に、グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を構成するために実行できるさまざまなタスクを示します。

|タスク  |追加情報  |
|---------|---------|
|**ユーザー オブジェクトとコンピューター オブジェクトの設定を管理する** <br/><br/>*組み込みのグループ ポリシー オブジェクトをカスタマイズするか、組織のニーズに合わせてカスタム グループ ポリシー オブジェクトと組織単位を作成します。*     |[Azure Active Directory ドメイン サービス管理ドメインでのグループ ポリシーの管理](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|**Microsoft Defender ウイルス対策の構成** <br/><br/>*組織のデバイス&ポリシー設定、除外、修復、スケジュールされたスキャン (エンドポイントとも呼ばれます) などのウイルス対策機能を構成します。*   |[グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を構成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[グループ ポリシーを使用してクラウド配信の保護を有効にする](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**組織の攻撃表面の縮小ルールを管理する** <br/><br/>*フォルダー内のファイルを除外するか、&デバイスに表示される通知通知にカスタム テキストを追加して、攻撃表面の縮小ルールをカスタマイズします。* |[グループ ポリシー オブジェクトを使用して攻撃表面の縮小ルールをカスタマイズする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**エクスプロイト保護の設定を管理する**<br/><br/>*エクスプロイト保護設定をカスタマイズし、構成ファイルをインポートしてから、グループ ポリシーを使用してその構成ファイルを展開できます。*  |[エクスプロイト保護の設定をカスタマイズする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[エクスプロイト保護構成のインポート、エクスポート、および展開](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[グループ ポリシーを使用して構成を配布する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**ネットワーク保護を有効** にして、従業員が悪意のあるコンテンツをインターネット上で使用するアプリを使用するのを防ぐ <br/><br/>*テスト環境で [ネットワーク保護のために](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) 監査モードを最初に使用して、展開前にブロックされるアプリを確認することをお勧めします。* |[グループ ポリシーを使用してネットワーク保護を有効にする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する <br/><br/>*[フォルダー アクセスの制御](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソイエムウェア保護とも呼ばれます。*  |[グループ ポリシーを使用してフォルダー アクセスの制御を有効にする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**インターネット上の悪意のあるサイト** やファイルから保護するために Microsoft Defender SmartScreen を構成します。  |[グループ ポリシーを使用して Microsoft Defender SmartScreen グループ ポリシーとモバイル デバイス管理 (MDM) 設定を構成する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Windows を実行している組織の** デバイスの情報を保護するために暗号化と BitLocker を構成する |[BitLocker グループ ポリシーの設定](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**資格情報の盗難攻撃から** 保護するために Microsoft Defender Credential Guard を構成する |[グループ ポリシー Windows Defenderして Credential Guard を有効にする](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Microsoft Defender セキュリティ センターを構成する

まだ行っていない場合は **、Microsoft Defender Security Center** ( ) を構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報 [https://securitycenter.windows.com](https://securitycenter.windows.com) の表示を行います。 

また、エンド ユーザーが Microsoft Defender セキュリティ センターで表示できる機能と機能を構成できます。

- [Microsoft Defender セキュリティ センターの概要](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [エンドポイント保護: Microsoft Defender セキュリティ センター](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次の手順

- [脅威と脆弱性の管理の概要を確認する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Microsoft Defender Security Center のセキュリティ操作ダッシュボードにアクセスする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Intune を使用してエンドポイント用 Microsoft Defender を管理する](manage-atp-post-migration-intune.md)
