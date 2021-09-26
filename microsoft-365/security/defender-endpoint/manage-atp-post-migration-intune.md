---
title: Intune を使用して Microsoft Defender for Endpoint を管理する
description: Intune を使用して Microsoft Defender for Endpoint を管理する方法について説明します。
keywords: 移行後、管理、運用、メンテナンス、使用率、Intune、Microsoft Defender for Endpoint、edr
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
ms.date: 09/23/2021
ms.reviewer: chventou
ms.openlocfilehash: 8ec9b00a0484a4d58868d3bf7bd53038dc949575
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59776958"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Intune を使用してエンドポイント用 Microsoft Defender を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイス (エンドポイント[ともMicrosoft エンドポイント マネージャー)](/mem)に対する組織の脅威保護機能を管理するには、Microsoft Intune (Intune) を含むセキュリティ 保護機能を使用することをお勧めします。 [詳細については、「エンドポイント マネージャー」 を参照してください](/mem/endpoint-manager-overview)。

この記事では、Intune で Microsoft Defender for Endpoint の設定を検索する方法について説明し、実行できるさまざまなタスクの一覧を示します。

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Intune で Microsoft Defender for Endpoint の設定を検索する

> [!IMPORTANT]
> この記事で説明する設定を構成するには、Intune でグローバル管理者またはサービス管理者の役割が割り当てられている必要があります。 詳細については、「管理者の **[種類 (Intune)」を参照してください](/mem/intune/fundamentals/users-add#types-of-administrators)**。

1. Azure portal ( ) に移動 [https://portal.azure.com](https://portal.azure.com) し、サインインします。

2. [Azure **Services] で****、[Intune] を選択します**。

3. 左側のナビゲーション ウィンドウで、[デバイス構成] を選択し、[管理] で [**プロファイル**]**を選択します**。

4. 既存のプロファイルを選択するか、新しいプロファイルを作成します。

> [!TIP]
> お困りの際は、 「Intune **[での Microsoft Defender for Endpoint の使用」を参照してください](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**。

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Intune を使用してエンドポイント用 Microsoft Defender を構成する

次の表に、Intune を使用して Microsoft Defender for Endpoint を構成するために実行できるさまざまなタスクを示します。 すべてを一度に構成する必要は一度に行う必要があります。タスクを選択し、対応するリソースを読み取り、続行します。

<br/><br/>

|タスク|追加情報|
|---|---|
|**Intune を使用して組織のデバイスを管理** して、それらのデバイスとデバイスに保存されているデータを保護する|[Microsoft Intune でデバイスを保護する](/mem/intune/protect/device-protect)|
|**Microsoft Defender for Endpoint と Intune をモバイル** 脅威防御ソリューションとして統合する <br/>*(Android デバイスおよびデバイスが Windows 10以降の場合)*|[Intune で条件付きアクセスを使用して Microsoft Defender for Endpoint のコンプライアンスを適用する](/mem/intune/protect/advanced-threat-protection)|
|**条件付きアクセスを** 使用して、電子メールや会社のリソースに接続できるデバイスとアプリを制御する|[Microsoft Defender for Endpoint で条件付きアクセスを構成する](/microsoft-365/security/defender-endpoint/configure-conditional-access)|
|**ポリシー Microsoft Defender ウイルス対策サービス** プロバイダー (ポリシー CSP) を使用して、ポリシー設定 [を構成します](/windows/client-management/mdm/policy-configuration-service-provider)。|[デバイスの制限: Microsoft Defender ウイルス対策](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) <br/><br/> [ポリシー CSP - Microsoft Defender for Endpoint](/windows/client-management/mdm/policy-csp-defender)|
|**必要に応じて、ユーザーの除外を指定Microsoft Defender ウイルス対策** <br/><br/> *一般に、除外を適用する必要はない必要があります。Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作や一般的な管理ファイル (エンタープライズ管理、データベース管理、その他のエンタープライズ シナリオで使用されるファイルなど) に基づく多数の自動除外が含まれます。*|[現在サポートされているバージョンの Enterpriseを実行しているコンピューターのウイルス スキャンの推奨事項Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers) <br/><br/> [デバイスの制限: Microsoft Defender ウイルス対策デバイスのWindows 10除外](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/> [2019 Microsoft Defender ウイルス対策または 2019 のWindows Server 2016除外を構成する](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**攻撃者によって悪用されるソフトウェア** の動作をターゲットに攻撃表面の縮小ルールを構成する <br/><br/> *最初に監査モードで攻撃表面の縮小ルールを [構成](/microsoft-365/security/defender-endpoint/audit-windows-defender)します (少なくとも 1 週間、最大 2 か月間)。準備ができたら、Power BI [(テンプレート](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)を取得) を使用して状態を監視し、それらのルールをアクティブ モードに設定できます。*|[エンドポイント用 Microsoft Defender の監査モード](/microsoft-365/security/defender-endpoint/audit-windows-defender) <br/><br/> [エンドポイント保護: 攻撃表面の縮小](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction) <br/><br/> [攻撃表面の縮小ルールの詳細](/microsoft-365/security/defender-endpoint/attack-surface-reduction) <br/><br/> [Tech Communityブログ投稿: Demystifying 攻撃表面の縮小ルール - パート 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)|
|**評判の低い任意** のアプリから IP アドレスまたはドメインへの送信接続をブロックするネットワーク フィルターを構成する  <br/><br/> *ネットワーク フィルターは、ネットワーク保護とも [呼ばれます](/microsoft-365/security/defender-endpoint/network-protection)。* <br/><br/> *最新のマルウェアWindows 10更新 [プログラムが](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)インストールされていることを確認します。*|[エンドポイント保護: ネットワーク フィルター](/mem/intune/protect/endpoint-protection-windows-10#network-filtering) <br/><br/> [イベント ビューアーでネットワーク保護イベントWindows確認する](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer)|
|**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する <br/><br/> *[フォルダー アクセスの制御](/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソイエムウェア保護とも呼ばれます。*|[エンドポイント保護: フォルダー アクセスの制御](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [Intune でフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)|
|**悪用を使用して他** のデバイスを拡散および感染するマルウェアから組織のデバイスを保護するエクスプロイト保護を構成する <br/><br/> *[エクスプロイ](/microsoft-365/security/defender-endpoint/exploit-protection) ト保護は Exploit Guard とも呼ばれます。*|[エンドポイント保護: Microsoft Defender Exploit Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/> [Intune でエクスプロイト保護を有効にする](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune)|
|**インターネット上Microsoft Defender SmartScreen** 悪意のあるサイトやファイルから保護する方法を構成します。 <br/><br/> *Microsoft Edgeデバイスにインストールする必要があります。Google Chrome ブラウザーと FireFox ブラウザーで保護を行う場合は、エクスプロイト保護を構成します。*|[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/> [デバイスの制限: Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen) <br/><br/> [Intune で SmartScreen を管理するためのポリシー設定](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)|
|**組織のデバイスに** 流れ込む、または組織のデバイスから外部に流れる承認されていないネットワーク トラフィックをブロックする Microsoft Defender ファイアウォールを構成する|[エンドポイント保護: Microsoft Defender ファイアウォール](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [高度なセキュリティを備え、Microsoft Defender ファイアウォール](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)|
|**暗号化と BitLocker を構成** して、組織で実行されているデバイスの情報を保護Windows|[エンドポイント保護: Windows暗号化](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption) <br/><br/> [BitLocker for Windows 10 デバイス](/windows/security/information-protection/bitlocker/bitlocker-overview)|
|**資格情報の盗難攻撃から** 保護するために Microsoft Defender Credential Guard を構成する|サーバー 2019 Windows 10、Windows Server 2016、Windowsについては、「Endpoint [protection: Microsoft Defender Credential Guard」を参照してください。](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/> Windows 7 SP1、Windows Server 2008 R2 SP1、Windows 8.1、および Windows Server 2012 R2 については[、「Pass-the-Hash (PtH) Attacks and Other Credential Theft、Versions 1 および 2」](https://www.microsoft.com/download/details.aspx?id=36036)を参照してください。|
|**組織のデバイスでアプリ** を監査または信頼するかどうかを選択する Microsoft Defender アプリケーションコントロールを構成する <br/><br/> *Microsoft Defender アプリケーションコントロールは [AppLocker とも呼ばれます](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)。*|[Microsoft Defender アプリケーション制御ポリシーを展開するには、次のMicrosoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune) <br/><br/> [エンドポイント保護: Microsoft Defender アプリケーション制御](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control) <br/><br/> [AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|**デバイス制御と USB 周辺機器へのアクセスを** 構成して、承認されていない周辺機器の脅威がデバイスを侵害するのを防ぐ|[Microsoft Defender for Endpoint と Intune を使用して USB デバイスや他のリムーバブル メディアを制御する](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)|

## <a name="configure-your-microsoft-365-defender-portal"></a>ポータルをMicrosoft 365 Defenderする

まだ実行していない場合は、Microsoft 365 Defender ポータルを構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報の表示を行います。 「Microsoft 365 Defender」[を参照してください](microsoft-defender-security-center.md)。 エンド ユーザーがポータルで表示できる機能と機能を構成Microsoft 365 Defenderすることもできます。

- [概要 Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [エンドポイント保護: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次のステップ

- [脅威と脆弱性の管理の概要を取得する](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [ポータルのセキュリティMicrosoft 365 Defenderダッシュボードにアクセスする](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
