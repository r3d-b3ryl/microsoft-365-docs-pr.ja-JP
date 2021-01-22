---
title: Microsoft 365 Defender 試用版ラボ環境を準備する
description: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップするときに、関係者のサインオフ、タイムライン、環境に関する考慮事項、導入順序を準備する
keywords: MTP 試用版の準備, MTP パイロット準備, MTP パイロット プロジェクトの実行の準備, パイロット MTP プロジェクトの実行, 展開, 準備, 関係者, タイムライン, 環境, エンドポイント, サーバー, 管理, 導入
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 35f1d3f0b5cefb0f14508571511449fc2c7d58a9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930152"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender 試用版ラボまたはパイロット環境を準備する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成して展開するには、次の 3 段階のプロセスがあります。

|![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)<br/>フェーズ 1: 準備 |[![フェーズ 2: セットアップ](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[フェーズ 2: セットアップ](setup-mtpeval.md) |[![フェーズ 3: オンボーディング](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[フェーズ 3: オンボーディング](config-mtpeval.md) | [![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[パイロット プレイブックに戻る](mtp-pilot.md) |
|--|--|--|--|
|*ここにいます。* | || |

現在準備段階です。


展開が成功するには、準備が重要です。 このセクションでは、Microsoft 365 Defender 展開用の試験ラボまたはパイロット環境を作成する準備をする際に考慮する必要がある点について説明します。

## <a name="prerequisites"></a>前提条件
Microsoft 365 Defender をプロビジョニングして使用するライセンス、ハードウェアおよびソフトウェアの要件、その他の構成設定について説明します。 [Microsoft 365 Defender、](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)エンドポイント用[Microsoft Defender、Office](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)用 Microsoft [Defender、Id](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)用 Microsoft [Defender、Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)の最小要件をご覧ください。

## <a name="stakeholders-and-sign-off"></a>関係者とサインオフ
評価またはパイロット プロジェクトの実行に関して、プロジェクトに関与し、サインオフ、レビュー、通知を受け取る必要がある関係者を特定します。

>[!NOTE]
>すべての組織が、このような役割を持つセキュリティ組織の成熟度を持っている可能性があります。 その場合は、レビューと承認の責任についてリーダー チームに問い合わせください。

組織に応じて、次の表に関係者を追加します。

-   SO = このプロジェクトのサインオフ

-   R = このプロジェクトを確認し、入力を提供する

-   I = このプロジェクトの情報

| 名前                 | Role                                                                                                                                                                                                          | アクション |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 名前とメールを入力する | **最高情報セキュリティ責任者 (CISO)** 新しいテクノロジ展開の組織内でスポンサーを務め、経営幹部 *。*                                                  | だから     |
| 名前とメールを入力する | サイバー防御オペレーション センター **(CDOC)** の長 *。CDOC* チームの担当者で、この変更が顧客セキュリティ運用チームのプロセスとどのように一致するのかの定義を担当します。       | だから     |
| 名前とメールを入力する | **セキュリティ アー***キテクト* この変更が組織内のコア セキュリティ アーキテクチャとどのように一致するのかの定義を担当するセキュリティ チームの担当者。                         | R      |
| 名前とメールを入力する | **ワークプレース***アーキテクト:この* 変更が組織のコア ワークプレース アーキテクチャとどのように一致するのかの定義を担当する IT チームの担当者。                             | R      |
| 名前とメールを入力する | **セキュリティ アナリスト** CDOC チームの担当者で、セキュリティ運用の観点から、この変更の検出機能、ユーザー エクスペリエンス、および全体的な有用性に関するフィードバックを *提供できます。* | I      |

## <a name="prepare-your-azure-active-directory"></a>Azure Active Directory を準備する
Active Directory とオンプレミスの Azure Active Directory 間の同期が既に有効になっている場合は、この手順をスキップします。 Azure Active Directory の既存のベスト プラクティスに関するドキュメントを確認します。 次の手順は、パイロット Microsoft 365 Defender プロジェクトを評価または実行するために最適化されています。

1. [Azure Active Directory ポータルに](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade)移動し、Azure > Connect **ADします**。 
![Azure Active Directory ポータル ページの画像](../../media/mtp-eval-1.png) <br> 

2. **[Microsoft Azure Active Directory Connect からダウンロード] をクリック** し、ドメイン コントローラーに転送します。 
![Azure Active Directoru Connect ダウンロード ページの画像](../../media/mtp-eval-2.png) <br>

3. ドメイン コントローラーで、Azure Active Directory Connect ウィザードに従います。 ライセンス条項とプライバシーに関する通知を読み、同意する場合はチェック ボックスをオンにします。 [**続行**] をクリックします。
![Azure AD Connect のウェルカム ページの画像](../../media/mtp-eval-3.png) <br>

4. [高速設定 **] に移動します**。
![[高速設定] ページの画像](../../media/mtp-eval-4.png) <br>

5. グローバル管理者の資格情報を入力します。 [**次へ**] をクリックします。
![グローバル管理者の資格情報ADする Azure への接続ページの画像](../../media/mtp-eval-5.png) <br>

6. Active Directory ドメイン サービスのエンタープライズ管理者の資格情報を入力します。 [**次へ**] をクリックします。
![資格情報を入力AD DS への接続の画像](../../media/mtp-eval-6.png) <br>

7. [ **インストール] を** クリックして構成を確認します。
![構成確認ページの画像](../../media/mtp-eval-7.png) <br>

8. これで完了です。Azure Active Directory Connect が正常に構成されました。
![正常に構成された Azure Active Directory Connect ページの画像](../../media/mtp-eval-8.png) <br>

Active Directory に[ユーザーとグループを追加し](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate)[、SAM-R ポリシーを構成できます](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。  


## <a name="configuration-order"></a>構成順序
次の表は、Microsoft が試用版ラボまたはパイロット環境の展開用に Microsoft 365 Defender コンポーネントを構成するために推奨する順序を示しています。

| コンポーネント                               | 説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 構成順序のランク |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender for Office 365|Microsoft Defender for Office 365 は、電子メール メッセージ、リンク (URL) や共同作業ツールによって生じる悪意のある脅威から組織を保護します。 <br> [詳細情報](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                    |
|Microsoft Defender for Identity|Microsoft Defender for Identity は、Active Directory シグナルを使用して、高度な脅威、侵害された ID、組織に向けられた悪意のあるインサイダーアクションを特定、検出、および調査します。 <br> [詳細情報を参照してください](https://docs.microsoft.com/azure-advanced-threat-protection/)。| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security は、複数のクラウドで動作するクラウド アクセス セキュリティ ブローカー (CASB) です。 すべてのクラウド サービスでサイバー脅威を特定して対処するための、豊富な可視性、データ移動の制御、および高度な分析を提供します。 <br> [詳細情報を参照してください](https://docs.microsoft.com/cloud-app-security/)。                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender for Endpoint | Microsoft Defender for Endpoint エンドポイントの検出および対応機能は、ほぼリアルタイムで操作可能な高度な攻撃検出を提供します。 セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。 <br> [詳細情報](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>次の手順
|![フェーズ 2: セットアップ](../../media/setup.png) <br>[フェーズ 2: セットアップ](setup-mtpeval.md) | Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップする
|:-------|:-----|

