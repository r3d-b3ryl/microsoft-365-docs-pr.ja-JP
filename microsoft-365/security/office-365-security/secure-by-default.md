---
title: Office 365 で既定でセキュリティ保護されている
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online Protection (EOP) の [既定でセキュリティ保護] の設定についての詳細情報
ms.openlocfilehash: 758d2169d80630a38c0b498e8c1848568e5ec941
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602043"
---
# <a name="secure-by-default-in-office-365"></a>Office 365 で既定でセキュリティ保護されている

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[既定でセキュリティ保護] は、可能な限り最も安全な既定の設定を定義するために使用される用語です。

ただし、セキュリティは生産性にバランスをとる必要があります。 これには、次のようなバランスを含めることができます。

- **有用性**: 設定は、ユーザーの生産性を向上させることはできません。
- **リスク**: セキュリティが重要なアクティビティをブロックする可能性があります。
- **従来の設定**: 新しい高度な設定が改善された場合でも、以前の製品や機能のいくつかの構成は、ビジネス上の理由から維持する必要があります。

Exchange Online のメールボックスを使用する Microsoft 365 組織は、Exchange Online Protection (EOP) によって保護されています。 この保護には次のものが含まれます。

- 疑いのあるマルウェアを含む電子メールは自動的に検疫され、受信者に通知されます。 [EOP でマルウェア対策ポリシーを構成するを](configure-anti-malware-policies.md)参照してください。
- 精度の高いフィッシングとして識別されたメールは、スパム対策ポリシーアクションに従って処理されます。 [EOP の「スパム対策ポリシーの構成」を](configure-your-spam-filter-policies.md)参照してください。

EOP の詳細については、「 [Exchange Online Protection の概要](exchange-online-protection-overview.md)」を参照してください。

Microsoft は、お客様を既定で安全なものにすることを目的としているため、一部のテナントの上書きは、マルウェアや高精度のフィッシングには適用されません。 これらのオーバーライドは次のとおりです。

- 許可された送信者リストまたは許可されたドメインリスト (スパム対策ポリシー)
- Outlook の差出人セーフリスト
- IP 許可一覧 (接続フィルター)

これらのオーバーライドの詳細については、「 [安全な送信者リストを作成](create-safe-sender-lists-in-office-365.md)する」を参照してください。

既定では、オンまたはオフにすることはできますが、潜在的に危険または不要なメッセージをメールボックスから保持するために、ボックスからフィルター処理を実行する方法は、セキュリティで保護されています。 マルウェアと信頼度の高いフィッシングメッセージは検疫される必要があります。 マルウェアまたは信頼度の高いフィッシングとして検疫されたメッセージを管理できるのは管理者のみです。また、そこから Microsoft に誤検知を報告することもできます。 詳細については、「 [EOP で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

## <a name="more-on-why-were-doing-this"></a>これを実行する理由について

既定でセキュリティ保護されているのは、次のようになります。このメッセージが悪意のあるメッセージを受け取った場合に実行するのと同じ操作を実行しています。 これは、マルウェアに対して使用したのと同じ方法ですので、これと同じ動作を高信頼性のフィッシングメッセージにまで拡大しています。 このデータは、信頼度の高いフィッシングメッセージの誤検知率が非常に低いことを示しており、管理者が送信した場合には、管理者が誤検知を解決できます。 また、このデータは、Outlook のスパム対策ポリシーと安全な送信者の許可された送信者の一覧および許可されるドメインの一覧が大きすぎて、正常ではなくなったことも示しています。

別の方法として、セキュリティサービスとして、ユーザーが危険にさらされないようにすることをお勧めします。 さらに、既定でのセキュリティ保護は、スパム対策ポリシーで信頼度の高いフィッシングメッセージに対して使用可能なオプションを完全に引き継ぐものではありません。 検疫は推奨されていますが、常に使用可能になっている他のアクションは引き続き利用できます ([迷惑メール] フォルダーに移動するか、電子メールアドレスにリダイレクトします)。

## <a name="exceptions"></a>例外

高信頼フィッシングメッセージがフィルターをバイパスすることを許可する唯一のオーバーライドは、Exchange メールフロールール (トランスポートルールとも呼ばれます) です。 メールフロールールを使用してフィルター処理をバイパスするには、「 [メールフロールールを使用してメッセージに SCL を設定](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)する」を参照してください。

次のシナリオでは、オーバーライドの使用を検討する必要があります。

- フィッシングのシミュレーション: 実際の攻撃が組織に影響を与える前に、脆弱性のあるユーザーを特定するのに役立つ、シミュレートされた攻撃。
- セキュリティ/SecOps メールボックス: セキュリティチームがフィルター処理されていないメッセージを取得するために使用する専用のメールボックス (良好および不良)。 チームは、悪意のあるコンテンツが含まれているかどうかを確認することができます。
- サードパーティ製のフィルター: サードパーティ製のフィルターによってメールフィルターが管理されるため、サードパーティベンダーによっては EOP (SCL =-1) をオフにすることをお勧めします。 Microsoft [Defender For Office 365](office-365-atp.md)の EOP が必要な場合は、EOP をオフにすることはお勧めしません。 代わりに、 [コネクタの拡張フィルター処理](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)を有効にすることをお勧めします。
- 誤検知: Microsoft によって引き続き分析されている特定のメッセージを、 [管理者送信で](admin-submission.md)一時的に許可することができます。 すべてのオーバーライドと同様に、一時的なものにすることをお勧めします。
