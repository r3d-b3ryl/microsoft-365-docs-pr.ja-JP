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
description: 管理者は、Exchange Online Protection (EOP) と Microsoft Defender for Office 365 のフィッシング対策保護機能について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4fef8aa30f2b41c0ba84a6535969b12448e80562
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289055"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 のフィッシング対策保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。 フィッシングには特定のカテゴリがあります。 例:

- **スピア フィッシング** は、対象の受信者に合わせて特別にカスタマイズされた、集中したカスタマイズされたコンテンツを使用します (通常は、攻撃者による受信者の再調整後)。

- **Whaling は** 、最大限の効果を得る上で、組織内の役員や他の価値の高いターゲットに向けられたものになります。

- ビジネス メール侵害 **(BEC)** では、偽造された信頼できる差出人 (財務責任者、顧客、信頼できるパートナーなど) を使用して、受信者をだまして支払いの承認、資金の移転、顧客データの公開を行います。

- **データ** を暗号化し、暗号化を解除するために支払いを要求するランサムウェアは、ほとんどの場合、フィッシング メッセージから始まります。 フィッシング対策保護は、暗号化されたファイルの暗号化を解除するのに役立ちますが、ランサムウェア キャンペーンに関連付けられている最初のフィッシング メッセージを検出するのに役立ちます。 ランサムウェア攻撃からの回復の詳細については [、「Microsoft 365](recover-from-ransomware.md)でランサムウェア攻撃から回復する」を参照してください。

攻撃の複雑さを増す中、訓練を受けたユーザーが高度なフィッシング メッセージを識別することはさらに困難です。 幸いなことに、Exchange Online Protection (EOP) と Microsoft Defender for Office 365 の追加機能が役立ちます。

## <a name="anti-phishing-protection-in-eop"></a>EOP のフィッシング対策保護

EOP (つまり、Microsoft Defender for Office 365 を使用しない Microsoft 365 組織) には、フィッシングの脅威から組織を保護するのに役立つ機能が含されています。

- **スプーフィング インテリジェンス**: 内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。 詳細については [、「EOP でスプーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。

- **EOP** のフィッシング対策ポリシー: スプーフィング インテリジェンスを有効またはオフにし、Outlook で認証されていない送信者の識別をオンまたはオフにし、ブロックされたスプーフィングされた送信者のアクションを指定します (迷惑メール フォルダーまたは検疫に移動)。 詳細については [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

- **暗黙的** な電子メール認証 : EOP は、送信者評価、送信者履歴、受信者履歴、行動分析、および偽造された送信者を識別するためのその他の高度な手法を使用して、受信メール [(SPF、DKIM、](set-up-spf-in-office-365-to-help-prevent-spoofing.md)および [DMARC)](use-dmarc-to-validate-email.md)の標準的な電子メール認証チェックを強化します。 [](use-dkim-to-validate-outbound-email.md) 詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の追加のフィッシング対策保護

Microsoft Defender for Office 365 には、次のより高度なフィッシング対策機能が含まれています。

- **Office 365** 向け Microsoft Defender のフィッシング対策ポリシー: 新しいカスタム ポリシーの作成、偽装対策設定の構成 (偽装からユーザーとドメインを保護する)、メールボックス インテリジェンス設定、および調整可能な高度なフィッシングしきい値。 詳細については [、「Microsoft Defender for Office 365」](configure-atp-anti-phishing-policies.md)を参照してください。 EOP のフィッシング対策ポリシーと Defender for Office 365 のフィッシング対策ポリシーの違いの詳細については [、「Microsoft 365](set-up-anti-phishing-policies.md)のフィッシング対策ポリシー」を参照してください。

- **キャンペーン ビュー**: 機械学習などのヒューリスティックは、サービス全体と組織に対する調整されたフィッシング攻撃に関与するメッセージを特定して分析します。 詳しくは [、Microsoft Defender 365 のキャンペーン Officeをご覧](campaigns.md)ください。

- **攻撃シミュレータ**: 管理者は、偽のフィッシング メッセージを作成し、教育ツールとして内部ユーザーに送信できます。 詳細については [、Microsoft Defender の攻撃シミュレータ (Office 365)](attack-simulator.md)を参照してください。

## <a name="other-anti-phishing-resources"></a>その他のフィッシング詐欺対策リソース

- エンド ユーザーの場合: フィッシング詐欺や他の形式のオンライン詐欺から [自分自身を保護します](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [Microsoft 365 がフィッシング詐欺を防ぐために From アドレスを検証する方法](how-office-365-validates-the-from-address.md)。
