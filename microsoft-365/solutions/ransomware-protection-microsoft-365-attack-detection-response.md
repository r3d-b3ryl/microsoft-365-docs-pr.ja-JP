---
title: 手順 2.  攻撃検出および対応を展開する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
ms.custom: seo-marvel-jun2020
keywords: ランサムウェア、人が操作するランサムウェア、人間が操作するランサムウェア、HumOR、強要攻撃、ランサムウェア攻撃、暗号化、暗号ウイルス学
description: Microsoft 365 Defender とそのセキュリティ信号ソースを使用して、ランサムウェアの攻撃から Microsoft 365 リソースを保護します。
ms.openlocfilehash: 7380e546733a299e7cf888946d502c43074822f5
ms.sourcegitcommit: 7e7effd8ef4ffe75cdee7bb8517fec8608e4c230
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2021
ms.locfileid: "59444669"
---
# <a name="step-2-deploy-attack-detection-and-response"></a>手順 2.  攻撃検出および対応を展開する

ランサムウェア攻撃の検出と対応のために、これらのツールを有効にし、構成して使用します。

| 機能 | 説明 | どこから始めるか | 検知と対応に活用する方法 |
|:-------|:-----|:-------|:-------|
| [Microsoft 365 Defender](/microsoft-365/security/defender) | シグナルを統合し、機能を単一のソリューションに調整する <br><br> セキュリティ専門家は、脅威の信号をつなぎ合わせ、脅威の全範囲と影響を把握することができます。 <br><br> 攻撃を防止または停止するためのアクションを自動化し、影響を受けたメールボックス、エンドポイント、およびユーザー ID を自己回復させる | [はじめに](/microsoft-365/security/defender/get-started) | [インシデント対応](/microsoft-365/security/defender/incidents-overview) |
| [Microsoft Defender for Identity](/defender-for-identity/what-is) |  Active Directory ドメイン サービス (AD DS) のシグナルを利用するクラウドベースのセキュリティ インターフェイスを通して、組織で高度な脅威やセキュリティ侵害を受けた ID、内部関係者の不正な行動を特定し、検知し、調査します。 | [概要](/defender-for-identity/what-is) | [Microsoft Defender for Identity ポータルとの連携](/defender-for-identity/workspace-portal) |
| [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) | メール メッセージ、リンク (URL)、共同作業ツールによってもたらされる悪意のある脅威から組織を保護します。 <br><br> マルウェア、フィッシング、スプーフィング、その他の攻撃の種類に対する保護  | [概要](/microsoft-365/security/office-365-security/overview) | [脅威の捜索](/microsoft-365/security/office-365-security/threat-hunting-in-threat-explorer) |
| [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint) | エンドポイント (デバイス) 全体での高度な脅威の検出および対応を有効にする | [概要](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)  | [エンドポイントでの検出と対応](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) |
| [Azure Active Directory (Azure AD) Identity Protection](/azure/active-directory/identity-protection/) | ID ベースのリスクの検出と修復、およびそれらのリスクの調査を自動化する | [概要](/azure/active-directory/identity-protection/overview-identity-protection) | [調査リスク](/azure/active-directory/identity-protection/howto-identity-protection-investigate-risk) |
| [Microsoft Cloud App Security](/cloud-app-security) | Microsoft とサードパーティのすべてのクラウド サービスを対象に、検出、調査、ガバナンスを行うクラウド アクセス セキュリティ ブローカー。 | [概要](/cloud-app-security/what-is-cloud-app-security) | [調査](/cloud-app-security/investigate) |

>[!Note]
>これらすべてのツールに、Microsoft 365 E5 Security アドオンを備えた Microsoft 365 E5 または Microsoft 365 E3 が必要です。
>

これらのツールを使用して、ランサムウェアの攻撃者による以下の一般的な脅威を検出し、対応します。

- 資格情報の盗用

   - Azure AD Identity Protection
   - Microsoft Defender for Identity
   - Microsoft Defender for Office 365

- デバイス侵害

   - Microsoft Defender for Endpoint
   - Microsoft Defender for Office 365

- 特権のエスカレーション

   - Azure AD Identity Protection
   - Microsoft Cloud App Security

- 悪意のあるアプリの振る舞い

   - Microsoft Cloud App Security

- データ放出、削除、またはアップロード

   - Microsoft Defender for Office 365
   - [異常検出ポリシー](/cloud-app-security/anomaly-detection-policy#ransomware-activity)を備えた Microsoft Cloud App Security

以下のツールでは Microsoft 365 Defender とそのポータル (共通の脅威コレクションおよび分析ポイントとしての https://security.microsoft.com)) を使用します。

- Microsoft Defender for Identity
- Microsoft Defender for Office 365
- Microsoft Defender for Endpoint
- Microsoft Cloud App Security

Microsoft 365 Defender は、脅威のシグナルをアラートにまとめ、接続されたアラートをインシデントにまとめることで、セキュリティ アナリストがランサムウェア攻撃のフェーズをより迅速に検出し、調査して修復できるようにします。

[試用版の環境を設定](/microsoft-365/security/defender/eval-overview)して、Microsoft 365 Defender の機能を評価することができます。

## <a name="resulting-configuration"></a>結果の構成

手順 1 および 2 のテナントのランサムウェア防止を次に示します。

![手順 2 の後の Microsoft 365 テナントのランサムウェア防止](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-architecture-step2.png)

## <a name="next-step"></a>次の手順

[![Microsoft 365 を使用してランサムウェアから保護するための手順 3](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step3.png)](ransomware-protection-microsoft-365-identities.md)

[手順 3](ransomware-protection-microsoft-365-identities.md) に進み、Microsoft 365 テナントで ID を保護します。
