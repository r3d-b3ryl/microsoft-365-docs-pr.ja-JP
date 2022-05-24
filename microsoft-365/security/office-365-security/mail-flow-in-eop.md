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
description: 管理Exchange Online Protection (EOP) でメール フローとルーティングを構成するためのオプションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: e0267af0297dce41657c76e97964e5c02fbe5815
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648747"
---
# <a name="mail-flow-in-eop"></a>EOP のメール フロー

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online メールボックスを持つMicrosoft 365組織、またはExchange Onlineメールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織では、ユーザーが表示される前に組織に送信されたすべてのメッセージが EOP を通過します。 EOP を通過するメッセージをユーザー メールボックスにルーティングする前に、処理のためにメッセージをルーティングする方法に関するオプションがあります。

## <a name="working-with-messages-and-message-access-options"></a>メッセージとメッセージ アクセス オプションの操作

EOP は、メッセージのルーティング方法に柔軟性を提供します。 以下のトピックで、メール フロー プロセスの手順について説明します。

[ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) サービス ネットワーク境界で無効な受信者のメッセージを拒否できるディレクトリ ベースのエッジ ブロック機能について説明します。

[EOP で承認済みドメインを表示または編集するには、EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) サービスに関連付けられているドメインを管理する方法について説明します。

組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。 サブドメインの詳細については、「[Exchange Onlineでサブドメインのメール フローを有効にする」を参照](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)してください。

[コネクタを使用してメール フローを構成すると、](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) コネクタが導入され、それらを使用してメール ルーティングをカスタマイズする方法が示されます。 シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。

[コネクタの拡張フィルター処理では、](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) EOP の前にメールがサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。

EOP がオンプレミスのExchangeメールボックスを保護するハイブリッド環境では、オンプレミスのExchangeでメール フロー ルール (トランスポート ルールとも呼ばれます) を構成する必要があります。 これらのメール フロー ルールは、メールボックス内の迷惑メール ルールがメッセージを迷惑メール フォルダーに移動できるように、EOP スパム フィルターの判定を変換します。 詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。 各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれます) を編集して、別のアクションを選択できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="verify-mail-flow"></a>メール フローを確認する

コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](/exchange/standalone-eop/set-up-your-eop-service)」の「このタスクの検証方法」セクションを参照してください。

[Microsoft 365 コネクタを検証してメール フローをテスト](/exchange/mail-flow-best-practices/test-mail-flow)すると、メール フローが正しく設定されていることをテストする手順が提供されます。
