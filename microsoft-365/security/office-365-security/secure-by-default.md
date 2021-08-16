---
title: 既定ではセキュリティで保護Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: セキュリティ保護 (EOP) の既定の設定Exchange Online Protection詳細
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0988e8f69c6459ece80df718f74940b1bb0e6c1cd7a62c98e02b3d4bb53f1c4d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "57002655"
---
# <a name="secure-by-default-in-office-365"></a>既定ではセキュリティで保護Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Secure by default" は、可能な限り最も安全な既定の設定を定義するために使用される用語です。

ただし、セキュリティと生産性のバランスを取る必要があります。 これには、次の分散が含まれます。

- **使いやすさ**: 設定の生産性を得る必要があります。
- **リスク**: セキュリティが重要なアクティビティをブロックする可能性があります。
- **従来の** 設定 : 新しい最新の設定が改善された場合でも、ビジネス上の理由から、古い製品や機能の一部の構成を維持する必要がある場合があります。

Microsoft 365メールボックスを持つ組織は、Exchange Online (EOP) によってExchange Online Protectionされます。 この保護には、次の機能が含まれます。

- マルウェアが疑われるメールは自動的に検疫され、受信者に通知されます。 [「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。
- 信頼度の高いフィッシングと識別された電子メールは、スパム対策ポリシーアクションに従って処理されます。 [「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

EOP の詳細については、「EOP の概要Exchange Online Protection[参照してください](exchange-online-protection-overview.md)。

Microsoft は既定で顧客のセキュリティを維持したいと考えていますので、一部のテナントの上書きはマルウェアや高信頼フィッシングには適用されません。 これらのオーバーライドには、次のものが含まれます。

- 許可された送信者リストまたは許可されたドメイン リスト (スパム対策ポリシー)
- Outlook セーフ送信者
- IP 許可一覧 (接続フィルター)

これらの上書きに関する詳細については、「差出人セーフ リストの作成 [」を参照してください](create-safe-sender-lists-in-office-365.md)。

> [!NOTE]
> EOP スパム対策 **ポリシーの** 信頼度の高いフィッシングメールの評決に対して、[メッセージを迷惑メールフォルダーに移動する] アクションは廃止されました。 信頼度の高いフィッシング メッセージにこのアクションを使用するスパム対策ポリシーは、検疫メッセージに **変換されます**。 信頼 **度の高いフィッシング メッセージ** の [電子メール アドレスにメッセージをリダイレクトする] アクションは影響を受けません。

既定ではセキュリティで保護は、オンまたはオフにできる設定ではなく、潜在的に危険なメッセージや望ましくないメッセージをメールボックスから守るフィルター処理の仕組みです。 マルウェアと高信頼のフィッシング メッセージは検疫する必要があります。 マルウェアまたは高信頼フィッシングとして検疫されたメッセージを管理できるのは管理者のみです。また、そこから Microsoft に誤検知を報告することもできます。 詳細については [、「EOP で検疫済みメッセージとファイルを管理者として管理する」を参照してください。](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>これを行う理由の詳細

既定でセキュリティで保護されるという考え方は、構成された例外がメッセージの配信を許可する場合でも、悪意のあるメッセージを知っていた場合と同じアクションを実行します。 これは、マルウェアで常に使用していたのと同じ方法で、この動作を信頼性の高いフィッシング メッセージに拡張しています。

データは、ユーザーが迷惑メール フォルダー内のメッセージと検疫の悪意のあるリンクをクリックする可能性が 30 倍高い可能性を示しています。 また、信頼度の高いフィッシング メッセージに対する誤検知率 (良いメッセージが悪いとマークされている) が非常に低いことを示し、管理者は管理者の申請で誤検知を解決できます。

また、Outlook のスパム対策ポリシーと セーフ Senders で許可されている送信者と許可されたドメイン リストが広すぎて、良いよりも害が大きいと判断しました。

別の言い方をすると、セキュリティ サービスとして、ユーザーが侵害されるのを防ぐために、お客様の代理として行動しています。

## <a name="exceptions"></a>例外

> [!NOTE]
> 2021 年 8 月には、既定でセキュリティで保護されたメール フロー Exchange (トランスポート ルールとも呼ばれる) に拡張されます。 メール フロー ルールを使用して、サード パーティのフィッシング シミュレーションやセキュリティ操作メールボックスへのフィルター処理されていない配信を許可する場合、最終的には、これらのルールを排除し、[](configure-advanced-delivery.md)機能が利用可能なときに高度な配信ポリシーの使用に切り替える必要があります。

信頼度の高いフィッシング メッセージがフィルター処理をバイパスできる唯一のオーバーライドは、メール フロー ルールです。 メール フロー ルールを使用してフィルター処理をバイパスするには、「メール フロー ルールを使用してメッセージに [SCL を設定する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)。

次のシナリオでは、オーバーライドの使用のみを検討する必要があります。

- フィッシング シミュレーション: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。
- セキュリティ/SecOps メールボックス: フィルター処理されていないメッセージを取得するためにセキュリティ チームが使用する専用のメールボックス (良いメールボックスと悪いメールボックスの両方)。 Teams、悪意のあるコンテンツが含まれているか確認できます。
- サード パーティ製のフィルター: ドメインの MX レコードがドメインの MX レコードを指していない場合、既定ではセキュリティで保護Office 365。
- 誤検知: 管理者の申請を介して Microsoft によって分析されている特定のメッセージを一時的に許可 [する場合があります](admin-submission.md)。 すべての上書きと同様に、一時的な上書きをお勧めします。
