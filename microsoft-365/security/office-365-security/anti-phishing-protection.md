---
title: フィッシング対策保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) とMicrosoft Defender for Office 365のフィッシング対策保護機能について学習できます。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 766f366a12e46bc5c02796203420379bf0b64b3a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466836"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 でのフィッシング対策保護

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。 フィッシングには特定のカテゴリがあります。 以下に例を示します。

- **スピア フィッシングでは** 、対象となる受信者 (通常、攻撃者による受信者の偵察後) に特別に調整された、集中型のカスタマイズされたコンテンツが使用されます。

- **ホエーリング** では、組織内の役員などの高価値の対象者に向けて行うことで、最大の効果を発揮します。

- **ビジネスメール侵害 (BEC)** では、偽造された信頼できる送信者 (財務責任者、顧客、信頼されたパートナーなど) を使用して、受信者をだまして支払いの承認、資金の譲渡、顧客データの公開を行います。 [このビデオ](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)を見て詳細をご確認ください。

- データを暗号化し、暗号化解除するための支払いを要求する **ランサムウェア** は、ほとんどの場合、フィッシング メッセージから始まります。 フィッシング対策では、暗号化されたファイルの暗号化を解除することはできませんが、ランサムウェアの攻撃活動に関連する初期のフィッシング メッセージを検出することができます。 ランサムウェア攻撃からの回復の詳細については、「 [Microsoft 365 でのランサムウェア攻撃からの回復](recover-from-ransomware.md)」を参照してください。

攻撃の複雑さが増す中、訓練を受けたユーザーが高度なフィッシング メッセージを識別することは困難です。 さいわい、Exchange Online Protection (EOP) とMicrosoft Defender for Office 365の追加機能が役立ちます。

## <a name="anti-phishing-protection-in-eop"></a>EOP のフィッシング対策保護

EOP (つまり、Microsoft Defender for Office 365のない Microsoft 365 組織) には、フィッシングの脅威から組織を保護するのに役立つ機能が含まれています。

- **スプーフィング インテリジェンス**: スプーフィング インテリジェンス分析情報を使用して、検出されたスプーフィングされた送信者を外部および内部ドメインからのメッセージで確認し、検出された送信者を手動で許可またはブロックします。 詳細については、「[EOP でのスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。

- **EOP のフィッシング対策ポリシー**: スプーフィング インテリジェンスをオンまたはオフにし、Outlook で認証されていない送信者インジケーターをオンまたはオフにし、スプーフィングされた送信者をブロックするアクションを指定します。 詳細については、「[EOP のフィッシング対策ポリシーの構成](configure-anti-phishing-policies-eop.md)」を参照してください。

- **テナント許可/ブロック リストでスプーフィングされた送信者を許可またはブロック** する: スプーフィング インテリジェンス 分析情報の判定をオーバーライドすると、スプーフィングされた送信者は、テナント許可/ブロック リストの **[スプーフィングされた送信者** ] タブにのみ表示される手動の許可またはブロックエントリになります。 また、スプーフィング インテリジェンスで検出される前に、手動でなりすまし送信者の許可またはブロック エントリを作成することもできます。 詳細については、「[EOP でテナント許可/ブロック リストを管理する](manage-tenant-allow-block-list.md)」を参照してください。

- **暗黙的な電子メール認証**: EOP では、受信メール ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md) 、送信者の評判、送信者履歴、受信者履歴、動作分析、およびその他の高度な手法) の標準電子メール認証チェックが強化され、偽造された送信者を識別するのに役立ちます。 詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の追加のフィッシング対策保護

Microsoft Defender for Office 365 には、次のより高度なフィッシング対策機能が含まれています。

- **Microsoft Defender for Office 365のフィッシング対策ポリシー**: 特定のメッセージ送信者と送信者ドメインの偽装保護設定、メールボックス インテリジェンス設定、および調整可能な高度なフィッシングのしきい値を構成します。 詳細情報については、「[Microsoft Defender for Office 365 のフィッシング詐欺対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。 EOP のフィッシング対策ポリシーとDefender for Office 365のフィッシング対策ポリシーの違いの詳細については、[Microsoft 365 のフィッシング対策ポリシーに関するページを](set-up-anti-phishing-policies.md)参照してください。
- **キャンペーン ビュー**: 機械学習やその他のヒューリスティックは、サービス全体と組織に対する協調フィッシング攻撃に関与するメッセージを特定し、分析します。 詳細については、「[Office 365 ATP のキャンペーン ビュー](campaigns.md)」を参照してください。
- **攻撃シミュレーション トレーニング**: 管理者は偽のフィッシング メッセージを作成し、教育ツールとして内部ユーザーに送信できます。 詳細については、「 [フィッシング攻撃をシミュレートする](attack-simulation-training.md)」を参照してください。

## <a name="other-anti-phishing-resources"></a>その他のフィッシング対策リソース

- エンド ユーザーの場合: [フィッシング詐欺やその他のオンライン詐欺から身を守ります](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [Microsoft 365 が From アドレスを検証してフィッシングを防止する方法](how-office-365-validates-the-from-address.md)。
