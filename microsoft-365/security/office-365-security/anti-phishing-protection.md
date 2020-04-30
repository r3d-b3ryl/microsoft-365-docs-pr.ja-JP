---
title: Microsoft 365 でのフィッシング対策保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: Microsoft 365 では、既定では、フィッシング攻撃に対するさまざまな保護を提供しており、Office 365 Advanced Threat Protection (ATP) のその他の機能も利用できます。 このトピックでは、Microsoft 365 でのフィッシング対策のオプションと戦略について学習し、実装するために使用できるオンラインリソースについて説明します。
ms.openlocfilehash: bdab6c05fb9be85c2ffb4914390ecc893fdd162b
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949371"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 でのフィッシング対策保護

*フィッシング*正規または信頼された送信者からのメッセージの機密情報を盗もうとする電子メール攻撃。 フィッシングには特定のカテゴリがあります。 次に例を示します。

- **スピアーフィッシング**は、目的の受信者に特化した、非常に集中的でカスタマイズされたコンテンツを使用します (通常は、攻撃者による受信者の偵察後)。

- **Whaling**は、組織内のエグゼクティブまたはその他の高価値のターゲットに対して最大の効果を与えるように指示されます。

- **ビジネスメールの侵害 (BEC)** は、受信者が支払いを承認したり、ファンドを転送したり、顧客データを公開したりするための取り組みで、偽造された信頼できる送信者 (金融責任者、顧客、信頼できるパートナーなど) を使用します。

- データを暗号化し、暗号化を解除するために支払いを要求する**ランサムウェア**は、常にフィッシングメッセージで開始します。 フィッシング対策保護は暗号化されたファイルの解読には役立ちませんが、ランサムウェアキャンペーンに関連付けられている最初のフィッシングメッセージを検出するのに役立ちます。 ランサムウェア攻撃からの回復の詳細については、「 [Microsoft 365 のランサムウェアからの回復](recover-from-ransomware.md)」を参照してください。

攻撃の複雑さが増すにつれて、熟練したユーザーが高度なフィッシングメッセージを識別することが困難になります。 幸いなことに、Exchange Online Protection (EOP) と、Microsoft 365 Advanced Threat Protection (ATP) の追加機能が役立ちます。

## <a name="anti-phishing-protection-in-eop"></a>EOP でのフィッシング対策保護

EOP (つまり、ATP を使用しない Microsoft 365 組織) には、組織をフィッシング脅威から保護するのに役立つ機能が含まれています。

- **スプーフィング インテリジェンス**: 内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。 詳細については、「[Microsoft 365 でのスプーフィング インテリジェンスを設定する](learn-about-spoof-intelligence.md)」を参照してください。

- **EOP のフィッシング対策ポリシー**: スプーフィングインテリジェンスを有効または無効にしたり、Outlook で認証されていない送信者の識別を有効または無効にしたり、ブロックされた送信者に対するアクションを指定したりします ([迷惑メール] フォルダーまたは検疫に移動)。 詳細については、「 [CONFIGURE EOP」の「フィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)」を参照してください。

- **暗黙的な電子メール認証**: EOP では、受信電子メールの標準の電子メール認証チェック ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [dkim](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)) を使用して、送信者評価、送信者履歴、受信者履歴、動作分析、その他の高度な手法を使用して偽造された送信者を特定できます。 詳細については、「[Microsoft 365 のメール認証](email-validation-and-authentication.md)」をご覧ください。

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Office 365 ATP の追加のフィッシング対策保護

Office 365 ATP には、追加の高度なフィッシング対策機能が含まれています。

- **ATP のフィッシング対策ポリシー**: 新しいカスタムポリシーを作成し、偽装の設定 (ユーザーとドメインを偽装から保護)、メールボックスインテリジェンスの設定、および詳細なフィッシングしきい値を調整します。 詳細については、「 [Microsoft 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。 フィッシング対策ポリシーと ATP のフィッシング対策ポリシーの相違点の詳細については、「 [Microsoft 365 のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)」を参照してください。

- [**キャンペーンビュー**]: コンピューター学習およびその他のヒューリスティックは、サービスと組織全体に対して、組織的なフィッシング攻撃に関係するメッセージを識別して分析します。 詳細については、「[Office 365 ATP のキャンペーン ビュー](campaigns.md)」を参照してください。

- **アタックシミュレータ**: 管理者は偽のフィッシングメッセージを作成し、それを教育ツールとして内部ユーザーに送信できます。 詳細については、「 [Office 365 ATP」の「アタックシミュレータ」](attack-simulator.md)を参照してください。

## <a name="other-anti-phishing-resources"></a>その他のフィッシング対策リソース

- エンドユーザーの場合:[フィッシング対策やその他の形式のオンライン詐欺から保護](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)します。

- [Microsoft 365 がフィッシングを防ぐために差出人アドレスを検証する方法](how-office-365-validates-the-from-address.md)。