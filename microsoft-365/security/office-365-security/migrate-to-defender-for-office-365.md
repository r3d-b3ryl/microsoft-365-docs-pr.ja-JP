---
title: サード パーティの保護サービスからMicrosoft Defender for Office 365に移行する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: サードパーティの保護サービスや Google Postini、Barracuda Spam and Virus Firewall、Cisco IronPort などのデバイスから保護をMicrosoft Defender for Office 365に移行する正しい方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00051effd6ee77fd29ba0a5a07ee27c9113a439
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2022
ms.locfileid: "64704825"
---
# <a name="migrate-from-a-third-party-protection-service-or-device-to-microsoft-defender-for-office-365"></a>サード パーティの保護サービスまたはデバイスからMicrosoft Defender for Office 365に移行する

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

Microsoft 365の前に存在する既存のサードパーティの保護サービスまたはデバイスが既にある場合は、このガイドを使用して保護をMicrosoft Defender for Office 365に移行し、統合管理エクスペリエンスの利点、コストの削減 (既に支払っている製品を使用)、および統合セキュリティを備えた成熟した製品を得ることができます。 保護。 詳細については、「[Microsoft Defender for Office」を](https://www.microsoft.com/security/business/threat-protection/office-365-defender)参照してください。

このガイドでは、移行に関する具体的で実用的な手順について説明し、次の事実を前提としています。

- Microsoft 365メールボックスは既にありますが、現在、電子メール保護にサード パーティのサービスまたはデバイスを使用しています。 インターネットからのメールは、Microsoft 365組織に配信される前に保護サービスを経由し、Microsoft 365保護は可能な限り低くなります (完全にはオフになることはありません。マルウェア保護は常に適用されます)。

  :::image type="content" source="../../media/mdo-migration-before.png" alt-text="メールは、Microsoft 365に配信する前に、サードパーティの保護サービスまたはデバイスを介してインターネットからフローします。" lightbox="../../media/mdo-migration-before.png":::

- Defender for Office 365による保護については、調査と検討の段階を超えています。 組織に適しているかどうかを判断するためにDefender for Office 365を評価する必要がある場合は、「[試用Microsoft Defender for Office 365](try-microsoft-defender-for-office-365.md)」で説明されているオプションを検討することをお勧めします。

- Defender for Office 365 ライセンスは既に購入済みです。

- 既存のサード パーティの保護サービスを廃止する必要があります。つまり、最終的には、電子メール ドメインの MX レコードをMicrosoft 365する必要があります。 完了すると、インターネットからのメールはMicrosoft 365に直接流れ込み、Exchange Online Protection (EOP) とDefender for Office 365によって排他的に保護されます。

  :::image type="content" source="../../media/mdo-migration-after.png" alt-text="メールはインターネットからMicrosoft 365に送信されます。" lightbox="../../media/mdo-migration-after.png":::

Defender for Office 365を優先して既存の保護サービスを排除することは、軽んじてはいけない大きなステップであり、変更を急ぐ必要もありません。 この移行ガイドのガイダンスは、ユーザーへの中断を最小限に抑えて、適切な方法で保護を移行するのに役立ちます。

非常に高度な移行手順を次の図に示します。 実際の手順については、この記事の後半の「 [移行プロセス」](#the-migration-process) というセクションを参照してください。

:::image type="content" source="../../media/mdo-migration-overview.png" alt-text="サード パーティの保護ソリューションまたはデバイスからDefender for Office 365への移行プロセス" lightbox="../../media/mdo-migration-overview.png":::

## <a name="why-use-the-steps-in-this-guide"></a>このガイドの手順を使用する理由

IT 業界では、驚きは一般的に悪い。 事前の思慮深いテストを行わずに MX レコードをMicrosoft 365を指すように反転するだけで、多くの驚きが生じます。 例:

- ユーザーまたは先行ユーザーは、既存の保護サービスをカスタマイズして最適なメール配信を行うために多くの時間と労力を費やしている可能性があります (つまり、ブロックする必要があるものをブロックし、許可する必要がある内容を許可します)。 Defender for Office 365では、現在の保護サービスのすべてのカスタマイズが必要であるとは言えないことがほぼ確実です。 また、Defender for Office 365では、現在の保護サービスで発生しなかった、または必要とされなかった新しい問題 (許可またはブロック) が導入される可能性も非常に高くなります。
- ヘルプ デスクとセキュリティ担当者は、Defender for Office 365で何をすべきかを知る必要があります。 たとえば、ユーザーが不足しているメッセージについて不平を言った場合、ヘルプ デスクは、そのメッセージの場所や検索方法を知っていますか? 既存の保護サービスのツールに精通していることを確認している可能性がありますが、Defender for Office 365のツールについてはどうでしょうか。

これに対し、この移行ガイドの手順に従うと、移行に関して次の具体的な利点が得られます。

- ユーザーの中断を最小限に抑える。
- 管理への移行の進行状況と成功について報告するときに使用できるDefender for Office 365からの目標データ。
- ヘルプ デスクとセキュリティ担当者の早期の関与と指示。

Defender for Office 365が組織にどのような影響を与えるかを理解すればするほど、ユーザー、ヘルプ デスク担当者、セキュリティ担当者、および管理の移行が向上します。

この移行ガイドでは、発生した問題に迅速に対応できるように、Defender for Office 365がユーザーとそのメールに与える影響を監視およびテストできるように、段階的に "ダイヤルを回す" 計画を提供します。

## <a name="the-migration-process"></a>移行プロセス

サード パーティの保護サービスからDefender for Office 365に移行するプロセスは、次の表に示すように 3 つのフェーズに分けることができます。

:::image type="content" source="../../media/phase-diagrams/migration-phases.png" alt-text="Defender for Office 365に移行するプロセス" lightbox="../../media/phase-diagrams/migration-phases.png":::

|段階|説明|
|---|---|
|[移行の準備](migrate-to-defender-for-office-365-prepare.md)|<ol><li>[既存の保護サービスで設定をインベントリする](migrate-to-defender-for-office-365-prepare.md#inventory-the-settings-at-your-existing-protection-service)</li><li>[Microsoft 365で既存の保護構成を確認する](migrate-to-defender-for-office-365-prepare.md#check-your-existing-protection-configuration-in-microsoft-365)</li><li>[メール ルーティングの構成を確認する](migrate-to-defender-for-office-365-prepare.md#check-your-mail-routing-configuration)</li><li>[メッセージを変更する機能をMicrosoft 365に移動する](migrate-to-defender-for-office-365-prepare.md#move-features-that-modify-messages-into-microsoft-365)</li><li>[スパムと一括ユーザー エクスペリエンスを定義する](migrate-to-defender-for-office-365-prepare.md#define-spam-and-bulk-user-experiences)</li><li>[優先度アカウントを特定して指定する](migrate-to-defender-for-office-365-prepare.md#identify-and-designate-priority-accounts)</li></ol>|
|[Defender for Office 365を設定する](migrate-to-defender-for-office-365-setup.md)|<ol><li>[パイロット ユーザーの配布グループを作成する](migrate-to-defender-for-office-365-setup.md#step-1-create-distribution-groups-for-pilot-users)</li><li>[ユーザー メッセージ レポートのユーザー送信を構成する](migrate-to-defender-for-office-365-setup.md#step-2-configure-user-submission-for-user-message-reporting)</li><li>[SCL=-1 メール フロー ルールを維持または作成する](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)</li><li>[コネクタの拡張フィルター処理を構成する](migrate-to-defender-for-office-365-setup.md#step-4-configure-enhanced-filtering-for-connectors)</li><li>[パイロット保護ポリシーを作成する](migrate-to-defender-for-office-365-setup.md#step-5-create-pilot-protection-policies)</li></ol>|
|[Defender for Office 365にオンボードする](migrate-to-defender-for-office-365-onboard.md)|<ol><li>[セキュリティ Teamsのオンボードを開始する](migrate-to-defender-for-office-365-onboard.md#step-1-begin-onboarding-security-teams)</li><li>[(省略可能)既存の保護サービスによるフィルター処理からパイロット ユーザーを除外する](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)</li><li>[スプーフィング インテリジェンスを調整する](migrate-to-defender-for-office-365-onboard.md#step-3-tune-spoof-intelligence)</li><li>[偽装保護とメールボックス インテリジェンスを調整する](migrate-to-defender-for-office-365-onboard.md#step-4-tune-impersonation-protection-and-mailbox-intelligence)</li><li>[ユーザー提出のデータを使用して測定と調整を行う](migrate-to-defender-for-office-365-onboard.md#step-5-use-data-from-user-submissions-to-measure-and-adjust)</li><li>[(省略可能)パイロットにユーザーを追加して反復処理する](migrate-to-defender-for-office-365-onboard.md#step-6-optional-add-more-users-to-your-pilot-and-iterate)</li><li>[Microsoft 365保護をすべてのユーザーに拡張し、SCL=-1 メール フロー ルールを無効にする](migrate-to-defender-for-office-365-onboard.md#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)</li><li>[MX レコードを切り替える](migrate-to-defender-for-office-365-onboard.md#step-8-switch-your-mx-records)</li></ol>|

## <a name="next-step"></a>次のステップ

- [フェーズ 1: 準備](migrate-to-defender-for-office-365-prepare.md)に進みます。
