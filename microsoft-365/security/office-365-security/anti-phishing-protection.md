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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) と Microsoft Defender for microsoft Defender for Officeできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a100e28ddee1629b2fe35e28742a43b891d13e57
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570614"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 のフィッシング対策保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。 フィッシングには特定のカテゴリがあります。 例:

- **スピアフィッシング** では、対象となる受信者に合わせて特別にカスタマイズされた、フォーカスのあるカスタマイズされたコンテンツを使用します (通常、攻撃者による受信者の偵察後)。

- **捕鯨は** 、組織内の幹部または他の高価値ターゲットに対して、最大限の効果を得る方向に向けられる。

- ビジネス メール侵害 **(BEC)** は、偽造された信頼できる送信者 (財務担当者、顧客、信頼できるパートナーなど) を使用して、受信者をだまして支払いの承認、資金の転送、顧客データの公開を行います。 詳しくは、このビデオ [をご覧ください](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)。

- **データ** を暗号化し、暗号化解除するための支払いを要求するランサムウェアは、ほとんどの場合、フィッシング メッセージから始まります。 フィッシング対策保護は、暗号化されたファイルの暗号化を解除するのに役立ちますが、ランサムウェア キャンペーンに関連付けられている最初のフィッシング メッセージを検出するのに役立ちます。 ランサムウェア攻撃からの回復の詳細については [、「Microsoft 365](recover-from-ransomware.md)のランサムウェア攻撃から回復する」を参照してください。

攻撃が複雑化する中、訓練を受けたユーザーが高度なフィッシング メッセージを識別することはさらに困難です。 幸いなことに、Exchange Online Protection (EOP) と Microsoft Defender for microsoft Defender for Office機能が役立ちます。

## <a name="anti-phishing-protection-in-eop"></a>EOP のフィッシング対策保護

EOP (つまり、Microsoft Defender Office 365 を使用しない Microsoft 365 組織) には、フィッシングの脅威から組織を保護するのに役立つ機能が含まれている。

- **スプーフィング インテリジェンス**: 内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。 詳細については [、「EOP でスプーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。

- **EOP** のフィッシング対策ポリシー : スプーフィング インテリジェンスをオンまたはオフにし、Outlook で認証されていない送信者 ID をオンまたはオフにし、ブロックされたスプーフィングされた送信者のアクションを指定します (迷惑メール フォルダーまたは検疫に移動)。 詳細については [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

- **暗黙的な** 電子メール認証 : EOP は、送信者評価、送信者履歴、受信者の履歴、行動分析などの高度な手法を使用して、受信メール [(SPF、DKIM、](set-up-spf-in-office-365-to-help-prevent-spoofing.md)および [DMARC)](use-dmarc-to-validate-email.md)の標準的な電子メール認証チェックを強化し、偽造された送信者を識別するのに役立ちます。 [](use-dkim-to-validate-outbound-email.md) 詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の追加のフィッシング対策保護

Microsoft Defender for Office 365 には、次のより高度なフィッシング対策機能が含まれています。

- **microsoft Defender for Office 365** のフィッシング対策ポリシー: 新しいカスタム ポリシーを作成し、偽装対策設定 (偽装からユーザーとドメインを保護する)、メールボックス インテリジェンス設定、および調整可能な高度なフィッシングしきい値を構成します。 詳細については、「Configure anti-フィッシング ポリシー in [Microsoft Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。 EOP のフィッシング対策ポリシーと defender for Office 365 のフィッシング対策ポリシーの違いの詳細については [、「Microsoft 365](set-up-anti-phishing-policies.md)のフィッシング対策ポリシー」を参照してください。

- **キャンペーン ビュー**: 機械学習などのヒューリスティックは、サービス全体と組織に対する協調フィッシング攻撃に関連するメッセージを特定して分析します。 詳細については、「キャンペーン ビュー in [Microsoft Defender for microsoft Defender for Office 365」を参照してください](campaigns.md)。

- **攻撃シミュレーター**: 管理者は、偽のフィッシング メッセージを作成し、教育ツールとして内部ユーザーに送信できます。 詳細については [、「Attack Simulator in Microsoft Defender for Office 365」を参照してください](attack-simulator.md)。

## <a name="other-anti-phishing-resources"></a>その他のフィッシング対策リソース

- エンド ユーザーの場合: フィッシング詐欺などのオンライン詐欺から身 [を守ります](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [フィッシングを防止するために、Microsoft 365 が From アドレスを検証する方法](how-office-365-validates-the-from-address.md)。
