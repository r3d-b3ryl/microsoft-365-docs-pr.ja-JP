---
title: 検疫された電子メール メッセージ
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
description: 管理者は、潜在的に危険なメッセージや望ましくないメッセージを保持するExchange Online Protection (EOP) の検疫について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac2d1bf550fd340c1e94ed5f3503352b40ba6556
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682771"
---
# <a name="quarantined-email-messages-in-eop-and-defender-for-office-365"></a>EOP とDefender for Office 365の検疫済み電子メール メッセージ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含むMicrosoft 365組織では、Exchange Onlineメールボックスがない場合は、検疫を使用して、潜在的に危険なメッセージや不要なメッセージを保持できます。

マルウェア対策ポリシーは _、マルウェアが_ 含まれている添付ファイルが見つかった場合、メッセージを自動的に検疫します。 詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。

既定では、スパム対策ポリシーはフィッシングと高信頼フィッシング メッセージを検疫し、スパム、信頼度の高いスパム、および一括メール メッセージをユーザーの迷惑メール フォルダーに配信します。 ただし、スパム対策ポリシーを作成してカスタマイズして、スパム、信頼度の高いスパム、および一括メール メッセージを検疫することもできます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

ユーザーと管理者の両方が、検疫されたメッセージを操作できます。

- _検疫ポリシーでは、_ メッセージが検疫された理由 (サポートされている機能の場合) に基づいて、検疫済みメッセージに対してユーザーが許可または許可しない操作を定義します。 既定の検疫ポリシーでは、以下で説明するように履歴機能が適用されます。 管理者は、ユーザーに対して制限の厳しい機能や制限の厳しい機能を定義するカスタム検疫ポリシーを作成して適用したり、検疫通知を有効にしたりできます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

- 管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを操作できます。 既定では、管理者のみが、マルウェア、高信頼フィッシング、またはメール フロー ルール (トランスポート ルールとも呼ばれます) の結果として検疫されたメッセージを操作できます。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- 既定では、ユーザーは受信者であり、メッセージがスパム、一括メール、またはフィッシングとして検疫された検疫済みメッセージを操作できます (信頼度の高いフィッシングではありません)。 詳細については、「 [EOP で検疫されたメッセージを検索してユーザーとして解放する」を](find-and-release-quarantined-messages-as-a-user.md)参照してください。

  ユーザーが独自の検疫済みフィッシング メッセージを管理できないようにするために、管理者は、スパム対策ポリシーの **フィッシングメール** フィルターの判定から検疫済みメッセージへのアクセスを拒否する検疫ポリシーを割り当てることができます。 詳細については、「 [スパム対策ポリシーの検疫ポリシーの割り当て](quarantine-policies.md#anti-spam-policies)[Quarantine ポリシー](quarantine-policies.md)」を参照してください。

- 管理者とユーザーは、検疫で誤検知を Microsoft に報告できます。

- 検疫済みメッセージの有効期限が切れる前に検疫に保持される期間は、メッセージが検疫された理由によって異なります。 メッセージを検疫する機能とそれに対応する保持期間を次の表に示します。

  |検疫の理由|既定の保有期間|カスタマイズ。|コメント|
  |---|---|:---:|---|
  |スパム対策ポリシーによって検疫されたメッセージ:スパム、高信頼スパム、フィッシング、高信頼フィッシング、または一括。|15 日間: <ul><li>既定のスパム対策ポリシー。</li><li>PowerShell で作成したスパム対策ポリシー。</li></ul> <p> Microsoft 365 Defender ポータルで作成したスパム対策ポリシーで 30 日間。|はい|スパム対策ポリシーでは、この値を (低く) 構成できます。 詳細については、「スパム [対策ポリシーの構成](configure-your-spam-filter-policies.md)」**の「この数日間の検疫でスパムを保持** する (_QuarantineRetentionPeriod_)」の設定を参照してください。|
  |フィッシング対策ポリシーによって検疫されたメッセージ: EOP のスプーフィング インテリジェンス。Defender for Office 365のユーザー偽装、ドメイン偽装、またはメールボックス インテリジェンス。|30 日間|はい|この保持期間は、スパム対策ポリシー **のこの数日間の検疫でのスパムの保持** (_QuarantineRetentionPeriod_) 設定によっても制御 **されます** 。 使用される保持期間は、受信者が定義されている最初に一致する **スパム対策** ポリシーの値です。|
  |マルウェア対策ポリシーによって検疫されたメッセージ (マルウェア メッセージ)。|15 日|いいえ||
  |Defender for Office 365のセーフ添付ファイル ポリシーによって検疫されたメッセージ (マルウェア メッセージ)。|15 日|いいえ||
  |メール フロー ルールによって検疫されたメッセージ: アクションは、 **メッセージをホストされた検疫に配信** する (_検疫) です_。|30 日間|いいえ||
  |SharePoint、OneDrive、Microsoft Teamsの添付ファイル (マルウェア ファイル) のセーフ添付ファイルによって検疫されたファイル。|15 日|いいえ||

  メッセージが検疫から期限切れになると、メッセージを回復できません。

検疫の詳細については、「 [検疫に](quarantine-faq.yml)関する FAQ」を参照してください。
