---
title: 迷惑メールとバルク メールの違い
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の迷惑メール (スパム) と一括メール (灰色のメール) の違いについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5117954e668c4e64444628078f38dab61b0597cb
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441791"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP での迷惑メールと一括メールの違いは何ですか?

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含む Microsoft 365 組織では、Exchange Onlineメールボックスがない場合、お客様は「迷惑メールと一括メールの違いは何ですか?」 このトピックでは、その違いと、EOP で使用できるコントロールについて説明します。

- **迷惑メール** はスパムです。これは、迷惑なメッセージで、普遍的に必要とされないメッセージ (正常に識別される) です。 既定では、EOP は、ソースメールサーバーの評価に基づいてスパムを拒否します。 メッセージが送信元 IP の検査を通過した場合は、スパムフィルタリングに送信されます。 迷惑メールフィルターによってメッセージがスパムとして分類された場合、メッセージは (既定では) 対象の受信者に配信されて、[迷惑メール] フォルダーに移動します。

  - 迷惑メールフィルター の判定を実行するアクションを構成できます。 手順については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

  - また、スパム分類の判定に同意できない場合は、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」に記載されているように、いくつかの方法でスパムまたは非スパムであると思われるメッセージを Microsoft に報告することができます。

- **バルクメール** (_グレーメール_ としても知られています) は、もう少し分類が困難です。 迷惑メールは常に脅威であるのに対し、多くの場合、バルクメールは1回限りの広告、またはマーケティングメッセージです。 バルクメールメッセージを必要としている (実際に、あえてサインアップしてバルクメールを受信する）ユーザもいます。一方、バルクメールをスパムだと感じるユーザもいます。 たとえば、一部のユーザーは Contoso Corporation からの広告メールまたは次回のサイバー セキュリティに関するカンファレンスの招待状を受信したいと思っているのに対して、その他のユーザーはこれらのメッセージをスパムと見なしている場合です。

  一括メールの識別方法の詳細については、 [EOP の一括苦情レベル (BCL) に](bulk-complaint-level-values.md)関するページを参照してください。

## <a name="how-to-manage-bulk-email"></a>バルク メールの管理方法

バルクメールへの反応が多様であるため、すべての組織に適用される汎用的なガイダンスはありません。

スパム対策ポリシーには、バルクメールを迷惑メールとして識別するために使用される既定の BCL しきい値があります。 管理者はしきい値を増減できます。 詳細については、次のトピックをご覧ください。

- [EOP でスパム対策ポリシーを構成します](configure-your-spam-filter-policies.md)。

- 「[EOP のスパム対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)」

見落としがちなもう１つの対策オプションとして、ユーザーがバルクメールを受信することについて苦情をしていても、スパムフィルタリングを通過する信頼できる送信者からのメッセージを EOP にしている場合は、ユーザーはバルクメールのメッセージに配信停止オプションがあるかどうかを確認するようにしてください。

## <a name="how-to-tune-bulk-email"></a>一括メールを調整する方法

2022 年 9 月に、Microsoft Defender for Office 365 プラン 2 のお客様は[高度な捜索](/microsoft-365/security/defender/advanced-hunting-overview)から BCL にアクセスできます。 この機能を使用すると、管理者は、組織にメールを送信したすべての一括送信者と、対応する BCL 値と受信した電子メール 量を確認できます。 一括送信者にドリルダウンするには、**Email & コラボレーション** スキーマの **EmailEvents** テーブルの他の列を使用します。 詳細については、「 [EmailEvents](/microsoft-365/security/defender/advanced-hunting-emailevents-table)」を参照してください。

たとえば、Contoso がスパム対策ポリシーで現在の一括しきい値を 7 に設定している場合、Contoso の受信者は受信トレイに BCL \< 7 を持つすべての送信者から電子メールを受信します。 管理者は、次のクエリを実行して、組織内のすべての一括送信者の一覧を取得できます。

```console
EmailEvents
| where BulkComplaintLevel >= 1 and Timestamp > datetime(2022-09-XXT00:00:00Z)
| summarize count() by SenderMailFromAddress, BulkComplaintLevel
```

このクエリを使用すると、管理者は必要な送信者と望ましくない送信者を識別できます。 一括送信者の BCL スコアが一括しきい値を満たしていない場合、管理者は [分析のために送信者のメッセージを Microsoft に送信](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)できます。これにより、送信者が許可エントリとしてテナント許可/ブロック リストに追加されます。

計画 2 Defender for Office 365ない組織では、[脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)を使用して、必要な一括送信者と望ましくない一括送信者を特定できます。

1. [脅威の保護の状態] レポートに<https://security.microsoft.com/reports/URLProtectionActionReport>移動し、[スパムEmail **してデータを**\>表示する] でフィルター処理 **します**。
 
2. 一括メールをフィルター処理し、調査するメールを選択し、電子メール エンティティをクリックして送信者の詳細を確認します。 Email エンティティは、Defender for Office 365プラン 2 のお客様にのみ使用できます。

3. 必要な送信者と望ましくない送信者を特定したら、一括しきい値を目的のレベルに調整します。 BCL スコアが一括しきい値に収まらない一括送信者がある場合は、 [分析のために Microsoft にメッセージを送信](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)します。これにより、送信者が許可エントリとしてテナント許可/ブロック リストに追加されます。

管理者は、再コミットされた一括しきい値に従うか、組織のニーズに合った一括しきい値を選択できます。
