---
title: 検疫済み電子メール メッセージ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理者は、潜在的に危険なメッセージまたは望ましくないメッセージExchange Online Protection (EOP) の検疫について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58097b5dba60c1ea085ea6e78c878982abe24021
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60668456"
---
# <a name="quarantined-email-messages-in-eop-and-defender-for-office-365"></a>EOP および Defender で検疫された電子メール Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、潜在的に危険なメッセージや望ましくないメッセージを保持するために検疫を利用できます。

マルウェア対策ポリシーは、添付ファイルにマルウェアが含まれていると検出された場合、メッセージを自動的に検疫します。 詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

既定では、スパム対策はフィッシングメッセージと高信頼フィッシング メッセージを検疫し、スパム、高信頼スパム、バルク メール メッセージをユーザーの迷惑メール フォルダーに配信します。 ただし、スパム対策ポリシーを作成およびカスタマイズして、スパム、高信頼スパム、バルク メール メッセージを検疫することもできます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

ユーザーと管理者の両方が検疫済みメッセージを処理できます。

- _検疫ポリシーは、_ メッセージが検疫された理由 (サポートされている機能の場合) に基づいて、検疫されたメッセージに対してユーザーが許可される操作または実行しない操作を定義します。 既定の検疫ポリシーは、以下で説明するように履歴機能を適用します。 管理者は、ユーザーに対して制限の少ない機能または制限の厳しい機能を定義するカスタム検疫ポリシーを作成して適用し、検疫通知を有効にできます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

- 管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを処理できます。 既定では、マルウェア、高信頼フィッシング、またはメール フロー ルール (トランスポート ルールとも呼ばれる) の結果として検疫されたメッセージを管理者だけが処理できます。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- 既定では、ユーザーは受信者であり、メッセージがスパム、バルク メール、またはフィッシング (高信頼フィッシングではない) として検疫された検疫済みメッセージを操作できます。 詳細については、「EOP で検疫済みメッセージをユーザーとして検索して解放する [」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

  ユーザーが検疫済みフィッシング メッセージを管理するのを防ぐために、管理者はスパム対策ポリシーのフィッシングメール フィルターの評決から検疫済みメッセージへのアクセスを拒否する検疫ポリシーを割り当てできます。 詳細については、「スパム対策[ポリシーで検疫ポリシー](quarantine-policies.md#anti-spam-policies)を割り当てる」を[参照してください](quarantine-policies.md)。

- 管理者とユーザーは、検疫中に誤検知を Microsoft に報告できます。

- 検疫済みメッセージが期限切れになる前に検疫に保持される期間は、メッセージが検疫された理由によって異なります。 メッセージとその対応する保持期間を検疫する機能については、次の表で説明します。

  <br>

  ****

  |検疫の理由|既定の保持期間|カスタマイズ可能ですか?|コメント|
  |---|:---:|:---:|---|
  |スパム対策ポリシーによって検疫されたメッセージ: スパム、高信頼スパム、フィッシング、高信頼フィッシング、またはバルク。|30 日間|はい|スパム対策ポリシーでこの値を構成 (低く) できます。 詳細については、「スパム **対策ポリシーの** 構成」の「この日数の検疫にスパムを保持する (_QuarantineRetentionPeriod_) 」 [の設定を参照してください](configure-your-spam-filter-policies.md)。|
  |フィッシング対策ポリシーによって検疫されたメッセージ: EOP のスプーフィング インテリジェンス。Defender のユーザー偽装、ドメイン偽装、またはメールボックス インテリジェンスOffice 365。|30 日間|はい|この保持期間は、スパム対策ポリシーの [この日数の検疫にスパムを保持する **(** _QuarantineRetentionPeriod)_ 設定によって **も** 制御されます。 使用される保持期間は、受信者が定義されている最初に一致するスパム対策ポリシーの値です。|
  |マルウェア対策ポリシー (マルウェア メッセージ) によって検疫されたメッセージ。|15 日|いいえ||
  |Defender の添付ファイル セーフによって検疫されたメッセージ (マルウェア Office 365メッセージ)。|15 日|いいえ||
  |メール フロー ルールによって検疫されたメッセージ: アクションは、メッセージをホストされた検疫 (検疫)**に配信**_します_。|30 日間|いいえ||
  |[添付ファイル] セーフ、SharePoint、OneDrive(マルウェア ファイルMicrosoft Teams) によって検疫されたファイル。|15 日|いいえ||
  |

  検疫からメッセージの有効期限が切れると、メッセージを回復できません。

検疫の詳細については、「検疫に関するよく寄せられる [質問」を参照してください](quarantine-faq.yml)。
