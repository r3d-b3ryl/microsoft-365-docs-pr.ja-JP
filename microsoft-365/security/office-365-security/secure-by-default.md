---
title: Office 365の既定のセキュリティ保護
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online Protection (EOP) の既定のセキュリティで保護された設定の詳細を確認する
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 09395775cc5ecbd420dc7197664401c01c24d6c3
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664218"
---
# <a name="secure-by-default-in-office-365"></a>Office 365の既定のセキュリティ保護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Secure by default" は、可能な限り最も安全な既定の設定を定義するために使用される用語です。

ただし、セキュリティと生産性のバランスを取る必要があります。 これには、次の間でのバランスが含まれる場合があります。

- **使いやすさ**: 設定はユーザーの生産性の邪魔にならないはずです。
- **リスク**: セキュリティによって重要なアクティビティがブロックされる可能性があります。
- **従来の設定**: 新しい最新の設定が改善された場合でも、ビジネス上の理由から、古い製品と機能の一部の構成を維持する必要がある場合があります。

Exchange Onlineにメールボックスを持つMicrosoft 365組織は、Exchange Online Protection (EOP) によって保護されます。 この保護には、次のものが含まれます。

- マルウェアが疑われるメールは自動的に検疫されます。 検疫されたマルウェア メッセージについて受信者に通知されるかどうかは、検疫ポリシーとマルウェア対策ポリシーの設定によって制御されます。 詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。
- 高信頼フィッシングとして識別されたメールは、スパム対策ポリシーアクションに従って処理されます。 [EOP でのスパム対策ポリシーの構成に関するページを](configure-your-spam-filter-policies.md)参照してください。

EOP の詳細については、「[Exchange Online Protection概要」を](exchange-online-protection-overview.md)参照してください。

Microsoft では、お客様を既定でセキュリティで保護することを望んでいるため、一部のテナントのオーバーライドはマルウェアや信頼性の高いフィッシングには適用されません。 これらの上書きには、以下の項目が含まれます。

- 許可された送信者リストや許可されたドメイン リスト (スパム対策ポリシー)。
- Outlook の信頼できる差出人。
- IP 許可一覧 (接続フィルター ポリシー)。
- Exchangeメール フロー ルール (トランスポート ルールとも呼ばれます)

これらのオーバーライドの詳細については、「 [差出人セーフ リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

> [!NOTE]
> EOP スパム対策ポリシーでの **高信頼フィッシングメール** の判定に対する迷惑メール **フォルダーへのメッセージの移動** アクションは非推奨になりました。 このアクションを使用して信頼度の高いフィッシング メッセージを使用するスパム対策ポリシーは、 **検疫メッセージ** に変換されます。 信頼性の高いフィッシング **メッセージの電子メール アドレスに** メッセージをリダイレクトするアクションは影響を受けません。

既定ではセキュリティ保護はオンまたはオフにできる設定ではありませんが、潜在的に危険なメッセージや不要なメッセージをメールボックスから除外するために、フィルター処理がすぐに機能する方法です。 マルウェアと信頼度の高いフィッシング メッセージは検疫する必要があります。 既定では、管理者のみがマルウェアまたは高信頼フィッシングとして検疫されたメッセージを管理でき、そこから Microsoft に誤検知を報告することもできます。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

## <a name="more-on-why-were-doing-this"></a>これを行う理由の詳細

既定では、セキュリティで保護されるという考え方は、構成された例外によってメッセージの配信が許可される場合でも、悪意のあるメッセージを知っている場合に行うのと同じアクションをメッセージに対して実行することです。 これは、マルウェアで常に使用していたのと同じアプローチであり、現在は、この同じ動作を高信頼フィッシング メッセージに拡張しています。

このデータは、ユーザーが迷惑メール フォルダーのメッセージと検疫の 30 倍の悪意のあるリンクをクリックする可能性が高いことを示しています。 また、データは、信頼度の高いフィッシング メッセージに対する誤検知率 (不適切とマークされた良好なメッセージ) が非常に低いことを示しており、管理者は管理者の提出で誤検知を解決できます。

また、スパム対策ポリシーで許可されている送信者と許可されたドメイン リストと、Outlookの送信者セーフが広すぎて、良好なドメイン リストよりも害を及ぼしていると判断しました。

別の言い方として、セキュリティ サービスとして、ユーザーが侵害されるのを防ぐために、お客様に代わって対応しています。

## <a name="exceptions"></a>例外

次のシナリオでは、オーバーライドの使用のみを検討する必要があります。

- フィッシング シミュレーション: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。 フィッシング シミュレーション メッセージがフィルター処理されないようにするには、「 [高度な配信ポリシーでサード パーティのフィッシング シミュレーションを構成する](/microsoft-365/security/office-365-security/configure-advanced-delivery#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy)」を参照してください。
- Security/SecOps メールボックス: フィルター処理されていないメッセージ (良いメッセージと悪いメッセージの両方) を取得するためにセキュリティ チームが使用する専用メールボックス。 Teamsは、悪意のあるコンテンツが含まれているかどうかを確認できます。 詳細については、「 [高度な配信ポリシーで SecOps メールボックスを構成する](/microsoft-365/security/office-365-security/configure-advanced-delivery#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy)」を参照してください。
- サード パーティ製フィルター: 既定では、ドメインの MX レコードが Exchange Online Protection (contoso.mail.protection.outlook.com) に設定されている場合にのみセキュリティで保護されます。 別のサービスまたはデバイスに設定されている場合は、既定で [Secure をトランスポート ルール](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl) でオーバーライドして、すべてのスパム フィルター処理をバイパスできます。 Microsoft は、このルールが適用された高信頼フィッシングとしてメッセージを検出しても、受信トレイに配信されます。 
- 誤検知: [管理者の提出を介して](admin-submission.md) Microsoft によってまだ分析されている特定のメッセージを一時的に許可したい場合があります。 すべてのオーバーライドと同様に、一時的なオーバーライドを使用することをお勧めします。
