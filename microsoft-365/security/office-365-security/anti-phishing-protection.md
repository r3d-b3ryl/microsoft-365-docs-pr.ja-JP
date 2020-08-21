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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) および Office 365 Advanced Threat Protection (Office 365 ATP) のフィッシング対策保護機能について学習できます。
ms.openlocfilehash: 5594c4e7033ab70a622403bca7759cd4b89f111a
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827447"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 でのフィッシング対策保護

*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。 フィッシングには、特定のカテゴリがあります。 たとえば、次のようにします。

- **スピア フィッシングでは、** 特にターゲットとなる受信者にカスタマイズされた (通常は、攻撃者による受信者の再調整後) にカスタマイズした、非常に焦点を置かれてカスタマイズされたコンテンツを使用します。

- **Whaling は** 、最大効果をもつ組織内のエグゼクティブまたはその他の価値の高いターゲットに向けられます。

- **ビジネス メールが侵害された業者 (BEC)** は、取り組みを取り入れてパートナーを本人が業者に取り入れて、顧客データの承認、行使いの促金を取り入れ、取り入れないように取り組むために取り組む目的で、業務上の信頼できる送信者 (BEC) を使用します。

- **ほとんどの場合、データを暗号化** し支払いを要求するランスパンダウェアは、ほとんどの場合、フィッシング メッセージで開始します。 フィッシング対策保護は、暗号化されたファイルの暗号化を解除する上では役立ちますが、ランサムウェア キャンペーンに関連付けられている最初のフィッシング メッセージを検出する上で役立ちます。 ランムウェア攻撃からの回復の詳細については [、「Microsoft 365 のランスムウェア攻撃からの回復」を参照してください](recover-from-ransomware.md)。

攻撃の複雑さが増すと、トレーニング済みユーザーはさらに複雑なフィッシング メッセージを識別するのは難しいものになります。 Exchange Online Protection (EOP) と Office 365 Advanced Threat Protection (Office 365 ATP) の追加機能が役立ちます。

## <a name="anti-phishing-protection-in-eop"></a>EOP のフィッシング対策保護

EOP (つまり、ATP を使用しない Microsoft 365 組織) には、フィッシングの脅威から組織を保護するために役立つ機能が含まれています。

- **スプーフィング インテリジェンス**: 内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。 詳細については、「EOP でス [プーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。

- **EOP のフィッシング対策**ポリシー: スプーフィング インテリジェンスを有効または無効にし、Outlook で認証されていない送信者識別情報をオンまたはオフにして、スプーフィングされた送信者 ([迷惑メール] フォルダーまたは検疫に移動) のアクションを指定する。 詳細については [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

- **暗黙的なメール認証**: EOP は、送信者評価、送信者履歴、受信者履歴、行きの分析、およびその他の高度な手法を使用して、受信メール (SPF、DKIM、DMARC) の電子メール認証チェックを強化して、偽の送信者を識別します。[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md) [DMARC](use-dmarc-to-validate-email.md) 詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Office 365 ATP の追加のフィッシング対策保護

Office 365 ATP には、次のより高度なフィッシング対策機能が含まれています。

- **ATP フィッシング対策**ポリシー: 新しいカスタム ポリシーを作成、偽装対策設定 (偽装からユーザーとドメインを保護)、メールボックス インテリジェンスの設定、および調整可能な高度なフィッシングしきい値。 詳細については [、「Microsoft 365 で ATP フィッシング対策ポリシーを構成する」を参照してください](configure-atp-anti-phishing-policies.md)。 フィッシング対策ポリシーと ATP フィッシング対策ポリシーの違いの詳細については、Microsoft 365 のフィッシ [ング対策ポリシーを参照してください](set-up-anti-phishing-policies.md)。

- **キャンペーン ビュー**: 機械学習とその他のヒューリスティックは、サービス全体および組織に対する調整されたフィッシング攻撃に関係するメッセージを特定して分析します。 詳細については、「[Office 365 ATP のキャンペーン ビュー](campaigns.md)」を参照してください。

- **攻撃シミュレータ**: 管理者は偽のフィッシング メッセージを作成し、教育ツールとして内部ユーザーに送信できます。 詳細については [、「Office 365 ATP」の「攻撃シミュレータ」を参照してください](attack-simulator.md)。

## <a name="other-anti-phishing-resources"></a>その他のフィッシング対策リソース

- エンド ユーザー向け: [フィッシング スキームや](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)オンライン切り取りから自分を保護します。

- [Microsoft 365 がフィッシングを防止するために From アドレスを検証する方法](how-office-365-validates-the-from-address.md)。
