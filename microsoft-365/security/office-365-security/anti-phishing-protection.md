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
description: 管理者は、フィッシング対策の保護機能について、Exchange Online Protection (EOP) と Microsoft Defender for Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a28e2ecc45be941dbd6e346f9918e1692357840
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218124"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>アプリ内のフィッシング対策Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。 フィッシングには特定のカテゴリがあります。 以下に例を示します。

- **スピアフィッシング** では、対象となる受信者に合わせて特別にカスタマイズされた、フォーカスのあるカスタマイズされたコンテンツを使用します (通常、攻撃者による受信者の偵察後)。

- **ホエーリング** では、組織内の役員などの高価値の対象者に向けて行うことで、最大の効果を発揮します。

- ビジネス メール侵害 **(BEC)** は、偽造された信頼できる送信者 (財務担当者、顧客、信頼できるパートナーなど) を使用して、受信者をだまして支払いの承認、資金の転送、顧客データの公開を行います。 [このビデオ](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)を見て詳細をご確認ください。

- **データ** を暗号化し、暗号化解除するための支払いを要求するランサムウェアは、ほとんどの場合、フィッシング メッセージから始まります。 フィッシング対策では、暗号化されたファイルの暗号化を解除することはできませんが、ランサムウェアの攻撃活動に関連する初期のフィッシング メッセージを検出することができます。 ランサムウェア攻撃からの回復の詳細については、「ランサムウェア攻撃から回復する」を参照[Microsoft 365。](recover-from-ransomware.md)

攻撃が複雑化する中、訓練を受けたユーザーが高度なフィッシング メッセージを識別することはさらに困難です。 幸い、Exchange Online Protection (EOP) と Microsoft Defender for microsoft Defender の追加機能Office 365役立ちます。

## <a name="anti-phishing-protection-in-eop"></a>EOP のフィッシング対策保護

EOP (つまり、microsoft Defender Microsoft 365を使用しない組織Office 365) には、フィッシングの脅威から組織を保護するのに役立つ機能が含まれている。

- **スプーフィン** グ インテリジェンス: スプーフィング インテリジェンスインサイトを使用して、外部ドメインおよび内部ドメインからのメッセージで検出されたスプーフィングされた送信者を確認し、検出された送信者を手動で許可またはブロックします。 詳細については、「[EOP でのスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。

- **EOP** のフィッシング対策ポリシー : スプーフィング インテリジェンスをオンまたはオフにし、Outlook で認証されていない送信者 ID をオンまたはオフにし、ブロックされたスプーフィングされた送信者のアクションを指定します。 詳細については [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

- **テナント許可/ブロック リストでなりすましされた送信者を許可またはブロックする**: スプーフィング インテリジェンス分析の判定を上書きすると、なりすましされた送信者は、手動で許可またはブロックするエントリとなり、「テナント許可/ブロックリスト」の **[なりすまし]** タブにのみ表示されます。 また、スプーフィング インテリジェンスで検出される前に、手動でなりすまし送信者の許可またはブロック エントリを作成することもできます。 詳細については、「[EOP でテナント許可/ブロック リストを管理する](tenant-allow-block-list.md)」を参照してください。

- **暗黙的な** 電子メール認証 : EOP は、送信者評価、送信者履歴、受信者の履歴、行動分析などの高度な手法を使用して、受信メール [(SPF、DKIM、](set-up-spf-in-office-365-to-help-prevent-spoofing.md)および [DMARC)](use-dmarc-to-validate-email.md)の標準的な電子メール認証チェックを強化し、偽造された送信者を識別するのに役立ちます。 [](use-dkim-to-validate-outbound-email.md) 詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の追加のフィッシング対策保護

Microsoft Defender for Office 365 には、次のより高度なフィッシング対策機能が含まれています。

- **microsoft Defender for Office 365** のフィッシング対策ポリシー: 特定のメッセージ送信者と送信者ドメイン、メールボックス インテリジェンス設定、および調整可能な高度なフィッシングしきい値に対する偽装保護設定を構成します。 詳細については[、「Microsoft Defender でフィッシング対策ポリシー](configure-mdo-anti-phishing-policies.md)を構成する」を参照Office 365。 EOP のフィッシング対策ポリシーと Office 365 用 Defender のフィッシング対策ポリシーの違いの詳細については、「Microsoft 365 のフィッシング対策ポリシー」[を参照してください](set-up-anti-phishing-policies.md)。
- **キャンペーン ビュー**: 機械学習などのヒューリスティックは、サービス全体と組織に対する協調フィッシング攻撃に関連するメッセージを特定して分析します。 詳細については[、「Microsoft Defender for microsoft Defender のキャンペーン ビュー」を参照Office 365。](campaigns.md)
- **攻撃シミュレーショントレーニング**: 管理者は、偽のフィッシング メッセージを作成し、教育ツールとして内部ユーザーに送信できます。 詳細については、「フィッシング攻撃 [をシミュレートする」を参照してください](attack-simulation-training.md)。

## <a name="other-anti-phishing-resources"></a>その他のフィッシング対策リソース

- エンド ユーザーの場合: フィッシング詐欺などのオンライン詐欺から身 [を守ります](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [フィッシングMicrosoft 365防止するために From アドレスを](how-office-365-validates-the-from-address.md)検証する方法。
