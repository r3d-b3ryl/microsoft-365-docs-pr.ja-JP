---
title: EOP のメール フロー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) でメールフローとルーティングを構成するためのオプションについて説明します。
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208332"
---
# <a name="mail-flow-in-eop"></a>EOP のメール フロー

Exchange Online メールボックスを使用する Microsoft 365 組織、または Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、組織に送信されるすべてのメッセージが EOP を経由してワーカーに表示されます。 EOP を経由して処理するメッセージを、ワーカーの受信トレイにルーティングする前にルーティングする方法についてのオプションが用意されています。

## <a name="working-with-messages-and-message-access-options"></a>メッセージとメッセージ アクセス オプションの操作

EOP は、メッセージのルーティング方法に柔軟性を提供します。 以下のトピックで、メール フロー プロセスの手順について説明します。

[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)サービスネットワーク境界で無効な受信者宛てのメッセージを拒否できるようにする、ディレクトリベースのエッジブロック機能について説明します。

「[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。

組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。 サブドメインの詳細については[、「Exchange Online でサブドメインのメールフローを有効にする」](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)を参照してください。

[コネクタを使用してメールフローを構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)するコネクタを導入し、それらを使用してメールルーティングをカスタマイズする方法を示します。 シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。

[コネクタの拡張フィルター処理](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)EOP の前に、メールがサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。

スタンドアロンの EOP 組織では、いくつかの構成手順を実行して、迷惑メールがそれぞれのユーザーの迷惑メールフォルダーに正しくルーティングされるようにする必要があります。 これらの詳細につい[ては、「Configure STANDALONE EOP to The 迷惑メールフォルダーにハイブリッド環境でスパムを配信する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参考にしてください。 メッセージを各ユーザーの [迷惑メール] フォルダーに移動しない場合は、スパム対策ポリシー (コンテンツフィルターポリシーとも呼ばれる) を編集して別のアクションを選択することができます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="verify-mail-flow"></a>メール フローを確認する

コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。

[Microsoft 365 コネクタを検証してメールフローをテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)するメールフローが正しく設定されていることをテストする手順を説明します。
