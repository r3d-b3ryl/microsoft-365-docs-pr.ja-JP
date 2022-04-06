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
ms.localizationpriority: medium
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理者は、メール フローとルーティングを構成するためのオプションについて、メール フロー (EOP) でExchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 296cd8aaa92005f094de2ee7d1c9f8bb9427df16
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681020"
---
# <a name="mail-flow-in-eop"></a>EOP のメール フロー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online メールボックスを持つ組織、または Exchange Online メールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織では、組織に送信されたメッセージはすべて EOP を通過してからワーカーに表示されます。 処理のために EOP を通過するメッセージをワーカー受信トレイにルーティングする方法に関するオプションがあります。

## <a name="working-with-messages-and-message-access-options"></a>メッセージとメッセージ アクセス オプションの操作

EOP は、メッセージのルーティング方法に柔軟性を提供します。 以下のトピックで、メール フロー プロセスの手順について説明します。

[無効な受信者に送信されるメッセージを拒否](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) するには、ディレクトリ ベースのエッジ ブロックを使用するサービス ネットワーク境界で無効な受信者のメッセージを拒否できるディレクトリ ベースのエッジ ブロック機能について説明します。

[EOP で受け入れドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) を表示または編集するには、EOP サービスに関連付けられているドメインを管理する方法について説明します。

組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。 サブドメインの詳細については、「サブドメインのメール フローを有効にする」を参照[Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[コネクタを使用してメール フロー](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) を構成すると、コネクタが導入され、それらを使用してメール ルーティングをカスタマイズする方法が示されます。 シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。

[拡張コネクタのフィルター処理では、](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) メールが EOP の前にサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。

EOP がオンプレミスの Exchange メールボックスを保護するハイブリッド環境では、オンプレミスのメールボックスでメール フロー ルール (トランスポート ルールとも呼ばれる) を構成する必要Exchange。 これらのメール フロー ルールは、EOP スパム フィルターの評決を変換し、メールボックス内の迷惑メール ルールがメッセージを迷惑メール フォルダーに移動できます。 詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。 各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="verify-mail-flow"></a>メール フローを確認する

コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](/exchange/standalone-eop/set-up-your-eop-service)」の「このタスクの検証方法」セクションを参照してください。

[メール フローをテストするには](/exchange/mail-flow-best-practices/test-mail-flow)、Microsoft 365コネクタを検証して、メール フローが正しく設定されていることをテストする手順を示します。
