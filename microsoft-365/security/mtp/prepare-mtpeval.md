---
title: Microsoft の脅威保護のテスト環境を準備する
description: Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップするときに、ステークホルダーのサインアップ、タイムライン、環境に関する考慮事項、導入の順序を準備する
keywords: Mtp 試用準備、MTP パイロット準備、mtp パイロットプロジェクトを実行するための準備、パイロット MTP プロジェクトの実行、展開、準備、ステークホルダー、タイムライン、環境、エンドポイント、サーバー、管理、導入
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a684f49ab8c70a19a17ff43195197677bccbf95b
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816771"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Microsoft の脅威保護の試用ラボまたはパイロット環境の準備

**適用対象:**
- Microsoft Threat Protection

Microsoft の脅威保護の試用ラボまたはパイロット環境を作成して展開するには、3つのフェーズがあります。

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境の準備" />
      <br/>フェーズ 1: 準備 </a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップする" />
      <br/>フェーズ 2: セットアップ </a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="各 Microsoft 脅威保護の柱とエンドポイントの構成" />
      <br/>フェーズ 3: 構成 & オンボード</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

現在、準備段階になっています。


正常な展開には、準備が重要です。 このセクションでは、Microsoft の脅威保護の展開のための試用ラボまたはパイロット環境を作成するための準備として考慮する必要のある内容について説明します。

## <a name="prerequisites"></a>前提条件
Microsoft の脅威保護をプロビジョニングおよび使用するためのライセンス、ハードウェア要件、ソフトウェア要件、およびその他の構成設定について説明します。 [Microsoft の脅威保護](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide)、 [microsoft Defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)、 [OFFICE 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)、 [Azure atp](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)、 [microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)の最小要件を参照してください。

## <a name="stakeholders-and-sign-off"></a>関係者と承認
次のセクションでは、プロジェクトに関係するすべての関係者を特定し、評価のために、またはパイロットを実行しているかどうかにかかわらず、サインオフ、レビュー、または通知を受ける必要がある可能性があるすべての関係者を識別します。

>[!NOTE]
>組織によっては、このような役割を持つセキュリティ組織の成熟度を持たない場合があります。 このような場合は、レビューと承認の責任について指導者チームと相談してください。

組織に応じて、次の表にステークホルダーを追加します。

-   そのため、このプロジェクトのサインオフ

-   R = このプロジェクトをレビューし、入力を提供します。

-   I = このプロジェクトの通知を受けた

| Name                 | Role                                                                                                                                                                                                          | Action |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 名前と電子メールを入力する | **最高情報セキュリティ責任者 (CISO)** *新しいテクノロジの展開について組織の内部スポンサーとしての役割を果たすエグゼクティブの代表者。*                                                  | だから     |
| 名前と電子メールを入力する | **サイバー防衛運用センター (cdoc) の本社**は、 *この変更がお客様のセキュリティ運用チームのプロセスとどのように連携するかを定義することを担当しています。*       | だから     |
| 名前と電子メールを入力する | **セキュリティアーキテクト**セキュリティ *チームは、この変更が組織内のコアセキュリティアーキテクチャとどのように連携するかを定義することを担当しています。*                         | R      |
| 名前と電子メールを入力する | **Workplace アーキテクト** *IT チームの代表者は、この変更が組織内のコアワークプレースアーキテクチャとどのように連携するかを定義すること*を担当します。                             | R      |
| 名前と電子メールを入力する | **セキュリティアナリスト***この変更によって、検出機能、ユーザーの操作、およびこの変更の全体的な有用性に関する情報を提供できる、cdoc チームからの担当者は、セキュリティ運用の観点から、この変更に関する情報を提供できます。* | I      |

## <a name="prepare-your-azure-active-directory"></a>Azure Active Directory の準備
オンプレミスの Active Directory と Azure Active Directory との間の同期を既に有効にしている場合は、この手順をスキップします。 Azure Active Directory からの既存のベストプラクティスドキュメントを確認します。 次の手順は、パイロット Microsoft の脅威保護プロジェクトを評価または実行するために最適化されています。

1. Azure **AD Connect**> [azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade)ポータルに移動します。 
![Azure Active Directory ポータルページのイメージ](../../media/mtp-eval-1.png) <br> 

2. [ **Microsoft Azure Active Directory Connect**から**ダウンロード**] をクリックして、ドメインコントローラーに転送します。
![Azure Active Directoru Connect ダウンロードページのイメージ](../../media/mtp-eval-2.png) <br>

3. ドメインコントローラーで、Azure Active Directory Connect ウィザードに従います。 ライセンス条項とプライバシーに関する通知を読んで、同意する場合はチェックボックスをオンにします。 [**続行**] をクリックします。
![Azure AD Connect ウェルカムページの画像](../../media/mtp-eval-3.png) <br>

4. [ **エクスプレス設定**] に移動します。
![Express 設定ページのイメージ](../../media/mtp-eval-4.png) <br>

5. グローバル管理者の資格情報を入力します。 [**次へ**] をクリックします。
![グローバル管理者の資格情報を入力する必要がある Azure AD に接続するためのページの画像](../../media/mtp-eval-5.png) <br>

6. Active Directory ドメインサービスのエンタープライズ管理者の資格情報を入力します。 [**次へ**] をクリックします。
![資格情報を入力する必要がある、AD DS への接続ページの画像](../../media/mtp-eval-6.png) <br>

7. [ **インストール** ] をクリックして構成を確認します。
![構成確認ページのイメージ](../../media/mtp-eval-7.png) <br>

8. これで完了です。 Azure Active Directory Connect が正常に構成されました。
![正常に構成された Azure Active Directory Connect ページのイメージ](../../media/mtp-eval-8.png) <br>

これで、 [Active Directory にユーザーとグループを追加](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) し、 [SAM-R ポリシーを構成](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)できるようになります。  


## <a name="configuration-order"></a>構成の順序
次の表は、試用ラボまたはパイロット環境の展開に Microsoft の脅威保護コンポーネントを構成するために Microsoft が推奨する順序を示しています。

| コンポーネント                               | 説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 構成順序のランク |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Office 365 Advanced Threat Protection| Office 365 ATP は、電子メールメッセージ、リンク (Url)、およびコラボレーションツールがもたらす悪意のある脅威から組織を保護します。 <br> [詳細情報](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)                                                                                                                                                                                                                                             | 1                    |
|Azure Advanced Threat Protection|Azure ATP では、Active Directory のシグナルを使用して、高度な脅威、侵害された id、および組織に向けた悪意のある insider 操作を識別、検出、調査します。 <br> [詳細情報](https://docs.microsoft.com/azure-advanced-threat-protection/) を参照してください。| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security は、複数のクラウドで稼働するクラウドアクセスセキュリティブローカー (CASB) です。 これにより、豊富な可視性、データ移動の制御、および高度な分析が提供され、すべてのクラウドサービスにわたる脅威を特定し、戦闘することができます。 <br> [詳細情報](https://docs.microsoft.com/cloud-app-security/) を参照してください。                                                                                                                                                                                                                                                                                                                                                                       |3                    |
|Microsoft Defender Advanced Threat Protection | Microsoft Defender ATP エンドポイント検出および対応機能により、高度な攻撃のほとんどリアルタイムで実用的な検出が実現されます。 セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。 <br> [詳細情報](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>次の手順
![フェーズ 2: セットアップ](../../media/setup.png) <br>[フェーズ 2: セットアップ](setup-mtpeval.md)<br> Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップする

