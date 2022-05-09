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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 81cd2870ff3471fbd535415229b3ced20bba1fbf
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61372158"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365でのフィッシング対策の保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。 フィッシングには特定のカテゴリがあります。 例:

- **スピア フィッシングでは** 、対象となる受信者 (通常、攻撃者による受信者の偵察後) に特別に調整された、集中型のカスタマイズされたコンテンツが使用されます。

- **ホエーリング** では、組織内の役員などの高価値の対象者に向けて行うことで、最大の効果を発揮します。

- **ビジネスメール侵害 (BEC)** では、偽造された信頼できる送信者 (財務責任者、顧客、信頼されたパートナーなど) を使用して、受信者をだまして支払いの承認、資金の譲渡、顧客データの公開を行います。 [このビデオ](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)を見て詳細をご確認ください。

- データを暗号化し、暗号化解除するための支払いを要求する **ランサムウェア** は、ほとんどの場合、フィッシング メッセージから始まります。 フィッシング対策では、暗号化されたファイルの暗号化を解除することはできませんが、ランサムウェアの攻撃活動に関連する初期のフィッシング メッセージを検出することができます。 ランサムウェア攻撃からの回復の詳細については、「[Microsoft 365でのランサムウェア攻撃からの回復](recover-from-ransomware.md)」を参照してください。

攻撃の複雑さが増す中、訓練を受けたユーザーが高度なフィッシング メッセージを識別することは困難です。 さいわい、Exchange Online Protection (EOP) とMicrosoft Defender for Office 365の追加機能が役立ちます。

## <a name="anti-phishing-protection-in-eop"></a>EOP のフィッシング対策保護

EOP (つまり、Microsoft Defender for Office 365のない組織Microsoft 365) には、フィッシングの脅威から組織を保護するのに役立つ機能が含まれています。

- **スプーフィング インテリジェンス**: スプーフィング インテリジェンス分析情報を使用して、検出されたスプーフィングされた送信者を外部および内部ドメインからのメッセージで確認し、検出された送信者を手動で許可またはブロックします。 詳細については、「[EOP でのスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。

- **EOP のフィッシング対策ポリシー**: スプーフィング インテリジェンスのオンとオフを切り替え、Outlookで認証されていない送信者の識別をオンまたはオフにし、ブロックされたスプーフィングされた送信者のアクションを指定します。 詳細については、「 [EOP でフィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)」を参照してください。

- **テナント許可/ブロック リストでなりすましされた送信者を許可またはブロックする**: スプーフィング インテリジェンス分析の判定を上書きすると、なりすましされた送信者は、手動で許可またはブロックするエントリとなり、「テナント許可/ブロックリスト」の **[なりすまし]** タブにのみ表示されます。 また、スプーフィング インテリジェンスで検出される前に、手動でなりすまし送信者の許可またはブロック エントリを作成することもできます。 詳細については、「[EOP でテナント許可/ブロック リストを管理する](tenant-allow-block-list.md)」を参照してください。

- **暗黙的な電子メール認証**: EOP では、受信メール ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md) 、送信者の評判、送信者履歴、受信者履歴、動作分析、およびその他の高度な手法) の標準電子メール認証チェックが強化され、偽造された送信者を識別するのに役立ちます。 詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の追加のフィッシング対策保護

Microsoft Defender for Office 365 には、次のより高度なフィッシング対策機能が含まれています。

- **Microsoft Defender for Office 365のフィッシング対策ポリシー**: 特定のメッセージ送信者と送信者ドメインの偽装保護設定、メールボックス インテリジェンス設定、および調整可能な高度なフィッシングのしきい値を構成します。 詳細については、「[Microsoft Defender for Office 365でのフィッシング対策ポリシーの構成](configure-mdo-anti-phishing-policies.md)」を参照してください。 EOP のフィッシング対策ポリシーとDefender for Office 365のフィッシング対策ポリシーの違いの詳細については、「[Microsoft 365のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)」を参照してください。
- **キャンペーン ビュー**: 機械学習やその他のヒューリスティックは、サービス全体と組織に対する協調フィッシング攻撃に関与するメッセージを特定し、分析します。 詳細については、「[Microsoft Defender for Office 365のキャンペーン ビュー」を](campaigns.md)参照してください。
- **攻撃シミュレーション トレーニング**: 管理者は偽のフィッシング メッセージを作成し、教育ツールとして内部ユーザーに送信できます。 詳細については、「 [フィッシング攻撃をシミュレートする](attack-simulation-training.md)」を参照してください。

## <a name="other-anti-phishing-resources"></a>その他のフィッシング対策リソース

- エンド ユーザーの場合: [フィッシング詐欺やその他のオンライン詐欺から身を守ります](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [フィッシングを防ぐために差出人アドレスを検証Microsoft 365方法](how-office-365-validates-the-from-address.md)。
