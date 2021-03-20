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
description: 管理者は、Exchange Online Protection (EOP) でメール フローとルーティングを構成するためのオプションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 043f093c801725cdf006c7c3afe7672e67d9fcef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907028"
---
# <a name="mail-flow-in-eop"></a>EOP のメール フロー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online メールボックスを持つ Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、組織に送信されたメッセージはすべて、ワーカーが EOP を表示する前に EOP を通過します。 処理のために EOP を通過するメッセージをワーカー受信トレイにルーティングする方法に関するオプションがあります。

## <a name="working-with-messages-and-message-access-options"></a>メッセージとメッセージ アクセス オプションの操作

EOP は、メッセージのルーティング方法に柔軟性を提供します。 以下のトピックで、メール フロー プロセスの手順について説明します。

[無効な受信者に送信されるメッセージを拒否](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) するには、ディレクトリ ベースのエッジ ブロックを使用するサービス ネットワーク境界で無効な受信者のメッセージを拒否できるディレクトリ ベースのエッジ ブロック機能について説明します。

「[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。

組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。 サブドメインの詳細については、「Exchange Online でサブドメインのメール フローを有効 [にする」を参照してください](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[コネクタを使用してメール フロー](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) を構成すると、コネクタが導入され、それらを使用してメール ルーティングをカスタマイズする方法が示されます。 シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。

[拡張コネクタのフィルター処理では、](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) メールが EOP の前にサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。

スタンドアロンの EOP 組織では、いくつかの構成手順を実行して、迷惑メールが各ユーザーの迷惑メール フォルダーに正しくルーティングされるようにする必要があります。 詳細については、「スタンドアロン EOP を構成してハイブリッド環境の迷惑メール フォルダーにスパムを配信 [する」を参照してください](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="verify-mail-flow"></a>メール フローを確認する

コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。

[Microsoft 365](/exchange/mail-flow-best-practices/test-mail-flow) コネクタを検証してメール フローをテストすると、メール フローが正しく設定されていることをテストするための手順が提供されます。