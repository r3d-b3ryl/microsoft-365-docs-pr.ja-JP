---
title: Intuneを使用してMicrosoft Defender for Endpointを管理する
description: Intuneを使用してMicrosoft Defender for Endpointを管理する方法について説明します
keywords: 移行後, 管理, 操作, メンテナンス, 使用率, intune, Microsoft Defender for Endpoint, edr
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
ms.openlocfilehash: 290d98f3f4136cfd07b5ea5abc21988ac8d9867a
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464870"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>IntuneでMicrosoft Defender for Endpointを管理する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[Microsoft Intune](/mem) (Intune) を含むMicrosoft エンドポイント マネージャーを使用して、デバイス (エンドポイントとも呼ばれる) に対する組織の脅威保護機能を管理することをお勧めします。 [エンドポイント マネージャーの詳細については、こちらを参照してください](/mem/endpoint-manager-overview)。

この記事では、IntuneでMicrosoft Defender for Endpoint設定を検索する方法と、実行できるさまざまなタスクの一覧を示します。

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>IntuneでMicrosoft Defender for Endpoint設定を見つける

> [!IMPORTANT]
> この記事で説明する設定を構成するには、Intuneでグローバル管理者ロールまたはサービス管理者ロールが割り当てられている必要があります。 詳細については、「**[管理者の種類 (Intune)」](/mem/intune/fundamentals/users-add#types-of-administrators)** を参照してください。

1. Azure portal ([https://portal.azure.com](https://portal.azure.com)) に移動し、サインインします。

2. **[Azure Services**] で [Intune] を選択 **します**。

3. 左側のナビゲーション ウィンドウで [ **デバイスの構成**] を選択し、[ **管理**] で [ **プロファイル**] を選択します。

4. 既存のプロファイルを選択するか、新しいプロファイルを作成します。

> [!TIP]
> お困りの際は、 **[IntuneでのMicrosoft Defender for Endpointの使用に関するIntune](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)** を参照してください。

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>IntuneでMicrosoft Defender for Endpointを構成する

次の表に、Intuneを使用してMicrosoft Defender for Endpointを構成するために実行できるさまざまなタスクを示します。 すべてを一度に構成する必要はありません。タスクを選択し、対応するリソースを読み取って続行します。

<br/><br/>

|タスク|追加情報|
|---|---|
|**Intuneを使用して組織のデバイスを管理** し、デバイスとそのデバイスに保存されているデータを保護する|[Microsoft Intune でデバイスを保護する](/mem/intune/protect/device-protect)|
|モバイル脅威防御ソリューションとして **Microsoft Defender for EndpointとIntuneを統合** する <br/>*(Windows 10またはWindows 11を実行している Android デバイスとデバイスの場合)*|[Intune で条件付きアクセスによる Microsoft Defender for Endpoint のコンプライアンスを強制する](/mem/intune/protect/advanced-threat-protection)|
|**条件付きアクセスを使用して** 、電子メールや会社のリソースに接続できるデバイスとアプリを制御する|[Microsoft Defender for Endpointで条件付きアクセスを構成する](/microsoft-365/security/defender-endpoint/configure-conditional-access)|
|ポリシー構成サービス プロバイダー ([Policy CSP](/windows/client-management/mdm/policy-configuration-service-provider)) を使用して **Microsoft Defender ウイルス対策設定** を構成する|[デバイスの制限: Microsoft Defender ウイルス対策](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) <br/><br/> [ポリシー CSP - Microsoft Defender for Endpoint](/windows/client-management/mdm/policy-csp-defender)|
|**必要に応じて、Microsoft Defender ウイルス対策の除外を指定します** <br/><br/> *一般に、除外を適用する必要はありません。Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作と一般的な管理ファイル (エンタープライズ管理、データベース管理、その他のエンタープライズ シナリオで使用されるものなど) に基づく自動除外が多数含まれています。*|[現在サポートされているバージョンのWindowsを実行しているEnterprise コンピューターのウイルス スキャンに関する推奨事項](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers) <br/><br/> [デバイスの制限: Windows 10 デバイスとWindows 11 デバイスのMicrosoft Defender ウイルス対策除外](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/> [Windows Server 2016または 2019 または 2022 でMicrosoft Defender ウイルス対策除外を構成する](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|攻撃者によって頻繁に悪用されるソフトウェアの動作をターゲットにするように、**攻撃対象の縮小ルールを構成** する <br/><br/> *最初に (少なくとも 1 週間から最大 2 か月間) [監査モード](/microsoft-365/security/defender-endpoint/audit-windows-defender)で攻撃面の縮小ルールを構成します。Power BIを使用して状態を監視し ([テンプレートを取得](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules))、準備ができたらそれらのルールをアクティブ モードに設定できます。*|[Microsoft Defender for Endpointの監査モード](/microsoft-365/security/defender-endpoint/audit-windows-defender) <br/><br/> [エンドポイント保護: 攻撃面の削減](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction) <br/><br/> [攻撃面の縮小ルールの詳細を確認する](/microsoft-365/security/defender-endpoint/attack-surface-reduction) <br/><br/> [Tech Community ブログ投稿: 攻撃表面の縮小ルールをデミスティック化する - パート 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)|
|評判の低い任意のアプリから IP アドレスまたはドメインへの送信接続をブロックするように **ネットワーク フィルターを構成** する  <br/><br/> *ネットワーク フィルター処理は、 [ネットワーク保護](/microsoft-365/security/defender-endpoint/network-protection)とも呼ばれます。* <br/><br/> *Windows 10デバイスとWindows 11 デバイスに最新の [マルウェア対策プラットフォーム更新プログラム](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)がインストールされていることを確認します。*|[エンドポイント保護: ネットワーク フィルター処理](/mem/intune/protect/endpoint-protection-windows-10#network-filtering) <br/><br/> [Windows イベント ビューアーでネットワーク保護イベントを確認する](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer)|
|ランサムウェアから保護するように **フォルダー アクセスの制御を構成** する <br/><br/> *[フォルダー アクセスの制御](/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソーイウェア保護とも呼ばれます。*|[エンドポイント保護: フォルダー アクセスの制御](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [Intuneでフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)|
|**悪用を使用** して他のデバイスを拡散して感染させるマルウェアから組織のデバイスを保護するようにエクスプロイト保護を構成する <br/><br/> *[エクスプロイト保護](/microsoft-365/security/defender-endpoint/exploit-protection) は、Exploit Guard とも呼ばれます。*|[エンドポイント保護: Microsoft Defender Exploit Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/> [Intuneでエクスプロイト保護を有効にする](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune)|
|インターネット上の悪意のあるサイトやファイルから保護するように **Microsoft Defender SmartScreenを構成** します。 <br/><br/> *Microsoft Edgeは、組織のデバイスにインストールする必要があります。Google Chrome および FireFox ブラウザーで保護するには、エクスプロイト保護を構成します。*|[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/> [デバイスの制限: Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen) <br/><br/> [Intuneで SmartScreen を管理するためのポリシー設定](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)|
|組織のデバイスに出入りする未承認のネットワーク トラフィックをブロックするように **Microsoft Defender ファイアウォールを構成** する|[エンドポイント保護: Microsoft Defender ファイアウォール](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [高度なセキュリティを備えた Microsoft Defender ファイアウォール](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)|
|Windowsを実行している組織のデバイスに関する情報を保護するように **暗号化と BitLocker を構成** する|[エンドポイント保護: Windows暗号化](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption) <br/><br/> [Windows 10およびWindows 11 デバイス用の BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview)|
|資格情報盗難攻撃から保護するように **Microsoft Defender Credential Guard を構成する**|Windows 10、Windows 11、Windows Server 2016、Windows Server 2019、Windows Server 2022 については、「[Endpoint Protection: Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard)」を参照してください。 <br/><br/> Windows 7 SP1、Windows Server 2008 R2 SP1、Windows 8.1、Windows Server 2012 R2 については、「[Pass-the-Hash (PtH) 攻撃とその他の資格情報の盗難、バージョン 1 および 2 の軽減](https://www.microsoft.com/download/details.aspx?id=36036)」を参照してください。|
|組織のデバイスでアプリを監査するか信頼するかを選択するように **Microsoft Defender アプリケーション制御を構成** する <br/><br/> *Microsoft Defender アプリケーション制御は、 [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) とも呼ばれます。*|[Microsoft Intuneを使用して Microsoft Defender アプリケーション制御ポリシーを展開する](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune) <br/><br/> [エンドポイント保護: Microsoft Defender アプリケーション制御](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control) <br/><br/> [AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|デバイス **制御と USB 周辺機器のアクセスを構成** して、承認されていない周辺機器の脅威がデバイスを侵害するのを防ぐのに役立ちます|[Microsoft Defender for EndpointとIntuneを使用して USB デバイスやその他のリムーバブル メディアを制御する](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを構成する

まだ行っていない場合は、アラートを表示し、脅威保護機能を構成し、組織の全体的なセキュリティ体制に関する詳細情報を表示するようにMicrosoft 365 Defender ポータルを構成します。 [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)を参照してください。 エンド ユーザーがMicrosoft 365 Defender ポータルで表示できる機能の有無と機能を構成することもできます。

- [Microsoft 365 Defenderの概要](/microsoft-365/security/defender-endpoint/use)
- [エンドポイント保護: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>次の手順

- [脅威と脆弱性の管理の概要を取得する](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Microsoft 365 Defender ポータルのセキュリティ操作ダッシュボードにアクセスする](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
