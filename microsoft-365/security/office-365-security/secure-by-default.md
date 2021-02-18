---
title: Office 365 でセキュリティ保護
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online Protection (EOP) の既定のセキュリティ設定の詳細
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288515"
---
# <a name="secure-by-default-in-office-365"></a>Office 365 でセキュリティ保護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

"既定でセキュリティ保護" は、できる限り安全な既定の設定を定義するために使用される用語です。

ただし、セキュリティと生産性のバランスを取る必要があります。 これには、次の間のバランス調整が含まれます。

- **使いやすさ**: 設定がユーザーの生産性を得る方法を取り入れるべきではありません。
- **リスク**: セキュリティによって重要なアクティビティがブロックされる可能性があります。
- **従来の** 設定 : 新しい最新の設定が改善された場合でも、ビジネス上の理由から、古い製品や機能の一部の構成を維持する必要がある場合があります。

Exchange Online にメールボックスがある Microsoft 365 組織は、Exchange Online Protection (EOP) によって保護されています。 この保護には以下が含まれます。

- マルウェアの疑いがあるメールは自動的に検疫され、受信者に通知されます。 [「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。
- 信頼度の高いフィッシングとして識別された電子メールは、スパム対策ポリシーアクションに従って処理されます。 [「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

EOP の詳細については [、「Exchange Online Protection の概要」を参照してください](exchange-online-protection-overview.md)。

Microsoft は既定でお客様のセキュリティを維持したいと考えていますので、一部のテナントのオーバーライドはマルウェアや信頼度の高いフィッシングには適用されません。 これらのオーバーライドには、次のものが含まれます。

- 許可された送信者リストまたは許可されたドメイン一覧 (スパム対策ポリシー)
- Outlook の差出人セーフ リスト
- IP 許可一覧 (接続フィルター)

これらのオーバーライドの詳細については、「差出人セーフ リストの作成 [」を参照してください](create-safe-sender-lists-in-office-365.md)。

> [!NOTE]
> EOP スパム対策ポリシーの信頼度の高いフィッシングメールの検出に関する[迷惑メール フォルダーにメッセージを移動する] アクションを廃止中です。 信頼度の高いフィッシング メッセージに対してこのアクションを使用するスパム対策ポリシーは、検疫メッセージに **変換されます**。 信頼 **度の高いフィッシング メッセージに** 対する電子メール アドレスへのリダイレクト アクションは影響を受けません。

既定では、セキュリティ保護はオンまたはオフにできる設定ではありません。ただし、このフィルター処理は、危険なメッセージや不要なメッセージをメールボックスから取り出し続ける方法です。 マルウェアと信頼度の高いフィッシング メッセージは検疫する必要があります。 管理者だけが、マルウェアまたは信頼度の高いフィッシングとして検疫されたメッセージを管理できます。また、そこから Microsoft に誤検知を報告することもできます。 詳細については [、「EOP で管理者として検疫済みメッセージとファイルを管理する」を参照してください。](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>これを行う理由の詳細

既定でセキュリティ保護されているという問題は、構成済みの例外によってメッセージの配信が許可される場合でも、悪意のあるメッセージを知っていた場合と同じアクションをメッセージに対して実行します。 これは、マルウェアに対して常に使用していたアプローチと同じであり、現在は、この同じ動作を信頼度の高いフィッシング メッセージに拡張しています。

このデータは、ユーザーが迷惑メール フォルダー内のメッセージ内の悪意のあるリンクをクリックする可能性が検疫の 30 倍高い可能性を示しています。 また、弊社のデータは、信頼度の高いフィッシング メッセージに対する誤検知率 (良いメッセージが悪いとマークされている) が非常に低いことを示し、管理者は管理者の送信で誤検知を解決できます。

また、スパム対策ポリシーと Outlook の差出人セーフ リストの許可された送信者と許可されたドメインリストが広すぎて、良い問題よりも多くの害を引き起こしている、と判断しました。

言い方をすると、セキュリティ サービスとして、ユーザーが侵害されるのを防ぐために、お客様の代わりに弊社が行動します。 

## <a name="exceptions"></a>例外

信頼度の高いフィッシング メッセージがフィルター処理をバイパスできる唯一のオーバーライドは、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) です。 メール フロー ルールを使用してフィルター処理をバイパスするには、「メール フロー ルールを使用してメッセージの SCL を設定する」 [を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

次のシナリオでは、オーバーライドの使用のみを検討する必要があります。

- フィッシング シミュレーション: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。
- Security/SecOps メールボックス: セキュリティ チームがフィルター処理されていないメッセージを取得するために使用する専用のメールボックス (良好と不良の両方)。 その後、Teams は悪意のあるコンテンツが含まれているか確認できます。
- サード パーティ製フィルター: ドメインの MX レコードが 365 を指していない場合、既定ではセキュリティで保護Office適用されません。
- 誤検知: 管理者の提出によって Microsoft によってまだ分析されている特定のメッセージを一 [時的に許可したい場合があります](admin-submission.md)。 すべてのオーバーライドと同様に、これらは一時的なものとしてお勧めします。
