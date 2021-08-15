---
title: EOP のメール フロー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理者は、メール フローとルーティングを構成するためのオプションについて、メール フロー (EOP) でExchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21702d1b7c57e1d102503cc806fa5699627eedabbb0945e34be91c2c2eb1fedf
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "56884572"
---
# <a name="mail-flow-in-eop"></a>EOP のメール フロー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online メールボックスまたはスタンドアロン Exchange Online Protection (EOP) 組織が Exchange Online メールボックスを持つ組織では、組織に送信されたメッセージはすべて、ワーカーが EOP を表示する前に EOP を通過します。 処理のために EOP を通過するメッセージをワーカー受信トレイにルーティングする方法に関するオプションがあります。

## <a name="working-with-messages-and-message-access-options"></a>メッセージとメッセージ アクセス オプションの操作

EOP は、メッセージのルーティング方法に柔軟性を提供します。 以下のトピックで、メール フロー プロセスの手順について説明します。

[無効な受信者に送信されるメッセージを拒否](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) するには、ディレクトリ ベースのエッジ ブロックを使用するサービス ネットワーク境界で無効な受信者のメッセージを拒否できるディレクトリ ベースのエッジ ブロック機能について説明します。

[EOP で受け入れドメインを表示または編集するには、EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) サービスに関連付けられているドメインを管理する方法について説明します。

組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。 サブドメインの詳細については、「メール のサブドメインのメール フローを有効にする」[を参照Exchange Online。](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[コネクタを使用してメール フロー](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) を構成すると、コネクタが導入され、それらを使用してメール ルーティングをカスタマイズする方法が示されます。 シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。

[拡張コネクタのフィルター処理では、](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) メールが EOP の前にサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。

EOP がオンプレミスの Exchange メールボックスを保護するハイブリット環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。 各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="verify-mail-flow"></a>メール フローを確認する

コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](/exchange/standalone-eop/set-up-your-eop-service)」の「このタスクの検証方法」セクションを参照してください。

[メール フローをテストするには](/exchange/mail-flow-best-practices/test-mail-flow)、Microsoft 365コネクタを検証して、メール フローが正しく設定されていることをテストする手順を示します。
