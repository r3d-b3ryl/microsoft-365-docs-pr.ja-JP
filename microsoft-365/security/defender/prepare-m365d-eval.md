---
title: 試用版ラボ環境Microsoft 365 Defender準備する
description: 試用版ラボまたはパイロット環境をセットアップする際に、関係者のサインオフ、タイムライン、環境に関する考慮事項、導入Microsoft 365 Defender準備する
keywords: Microsoft 365 Defender準備、Microsoft 365 Defender パイロット準備、Microsoft 365 Defender パイロット プロジェクトの実行準備、パイロット Microsoft 365 Defender プロジェクトの実行、展開、準備、関係者、タイムライン、環境、エンドポイント、サーバー、管理、導入
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7ebb7074b0e06eda96d21142044bd8b9997e094b
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458441"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>テスト ラボMicrosoft 365 Defenderパイロット環境を準備する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

試用版ラボMicrosoft 365 Defenderを作成して展開するには、次の 3 段階のプロセスを実行します。

|![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)<br/>フェーズ 1: 準備 |[![フェーズ 2: 設定](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[フェーズ 2: 設定](setup-m365deval.md) |[![フェーズ 3: オンボード](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[フェーズ 3: オンボード](config-m365d-eval.md) | [![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[パイロット プレイブックに戻る](m365d-pilot.md) |
|--|--|--|--|
|*お前はここにいる!* | || |

現在準備段階です。


展開が成功するには、準備が重要です。 このセクションでは、テスト ラボまたはパイロット環境を開発する際に検討する必要がある点Microsoft 365 Defenderします。

## <a name="prerequisites"></a>前提条件
ライセンス、ハードウェアとソフトウェアの Microsoft 365 Defender要件、その他の構成設定について説明します。 「Microsoft Defender for [](/microsoft-365/security/defender/prerequisites)Endpoint 」、Microsoft 365 Defender Microsoft [Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) [、Microsoft](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) [Defender](/azure-advanced-threat-protection/atp-prerequisites)for Office 365 Id、Microsoft Cloud App Security の最小要件を[参照してください](/azure-advanced-threat-protection/atp-prerequisites)。

## <a name="stakeholders-and-sign-off"></a>関係者とサインオフ
プロジェクトに関与し、評価またはパイロット プロジェクトの実行に関して、サインオフ、レビュー、または情報の提供が必要な関係者を特定します。

>[!NOTE]
>そのような役割を持つセキュリティ組織の成熟度を持つ組織が一部である可能性があります。 このような場合は、リーダーシップ チームに確認と承認の責任について相談してください。

組織に応じて、以下の表に関係者を追加します。

-   SO = このプロジェクトのサインオフ

-   R = このプロジェクトを確認し、入力を提供する

-   I = このプロジェクトの通知

| 氏名                 | 役割                                                                                                                                                                                                          | 操作 |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 名前とメールを入力する | **最高情報セキュリティ責任者 (CISO)** 新しいテクノロジ展開の組織の内部でスポンサーを務め、役員 *の代表者。*                                                  | だから     |
| 名前とメールを入力する | **サイバー防御運用センター (CDOC)** の代表は *、CDOC* チームの担当者で、この変更が顧客のセキュリティ運用チームのプロセスとどのように一致するのか定義します。       | だから     |
| 名前とメールを入力する | **セキュリティ アーキ***テクト* この変更が組織内の主要なセキュリティ アーキテクチャとどのように一致するのか定義するセキュリティ チームの担当者。                         | R      |
| 名前とメールを入力する | **Workplace Architect** *この変更が* 組織内のコアワークプレース アーキテクチャとどのように対応されるかを定義する IT チームの担当者。                             | R      |
| 名前とメールを入力する | **セキュリティ アナリスト***セキュリティ運用の* 観点から、この変更の検出機能、ユーザー エクスペリエンス、および全体的な有用性に関するフィードバックを提供できる CDOC チームの担当者。 | I      |

## <a name="prepare-your-azure-active-directory"></a>アカウントを準備Azure Active Directory
Active Directory とオンプレミスの同期を既に有効にしている場合は、このAzure Active Directoryスキップします。 既存のベスト プラクティスに関するドキュメントを、Azure Active Directory。 次の手順は、プロジェクトのパイロット テストを評価または実行Microsoft 365 Defenderされています。

1. Azure のポータル [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade)に>**移動AD Connect。** 
![ポータル ページAzure Active Directoryイメージ](../../media/mtp-eval-1.png) <br> 

2. [**ドメイン コントローラーから****ダウンロードMicrosoft Azure Active Directory Connect** をクリックし、ドメイン コントローラーに転送します。
![ダウンロード ページの Azure Active Directoru Connectイメージ](../../media/mtp-eval-2.png) <br>

3. ドメイン コントローラーで、ウィザードのAzure Active Directory Connectします。 ライセンス条項とプライバシーに関する通知を読み、同意する場合はチェック ボックスをオンにします。 [**続行**] をクリックします。
![Azure のウェルカム ページAD Connectイメージ](../../media/mtp-eval-3.png) <br>

4. [Express **設定] に移動します**。
![Express 設定 ページのイメージ](../../media/mtp-eval-4.png) <br>

5. グローバル管理者の資格情報を入力します。 **[次へ]** をクリックします。
![グローバル管理者ConnectをADする必要がある Azure ADページのイメージ](../../media/mtp-eval-5.png) <br>

6. Active Directory Domain Services エンタープライズ管理者の資格情報を入力します。 **[次へ]** をクリックします。
![資格情報をConnectするAD DS ページのイメージ](../../media/mtp-eval-6.png) <br>

7. [インストール **] を** クリックして構成を確認します。
![構成確認ページのイメージ](../../media/mtp-eval-7.png) <br>

8. おめでとうございます、正常に構成されたAzure Active Directory Connect。
![正常に構成されたページAzure Active Directory Connect画像](../../media/mtp-eval-8.png) <br>

Active Directory に[ユーザーとグループを追加し](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate)[、SAM-R ポリシーを構成できます](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。  


## <a name="configuration-order"></a>構成順序
次の表は、Microsoft が試用版ラボまたはパイロット環境の展開Microsoft 365 Defenderコンポーネントを構成するために推奨する順序を示しています。

| コンポーネント                               | 説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 構成順序のランク |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender for Office 365|Microsoft Defender for Office 365 は、電子メール メッセージ、リンク (URL) や共同作業ツールによって生じる悪意のある脅威から組織を保護します。 <br> [詳細情報](/microsoft-365/security/office-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender for Identity は、Active Directory シグナルを使用して、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダーアクションを特定、検出、および調査します。 <br> [詳細情報](/azure-advanced-threat-protection/) を参照してください。| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security (MCAS) は、Cloud Access Security Broker (CASB) です。 これにより、豊富な可視性、データ移動の制御、高度な分析が提供され、すべてのクラウド サービスでサイバー脅威を特定して対処できます。 <br> [詳細情報](/cloud-app-security/) を参照してください。                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender for Endpoint | Microsoft Defender for Endpoint のエンドポイント検出および対応機能により、高度な攻撃のほとんどリアルタイムで実用的な検出が実現されます。 セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。 <br> [詳細情報](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>次の手順
|![フェーズ 2: セットアップ](../../media/setup.png) <br>[フェーズ 2: セットアップ](setup-m365deval.md) | 試用版ラボまたはMicrosoft 365 Defender環境をセットアップする
|:-------|:-----|
