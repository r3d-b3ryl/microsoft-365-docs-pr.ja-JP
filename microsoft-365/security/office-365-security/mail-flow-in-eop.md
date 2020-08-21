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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) でメール フローとルーティングを構成するオプションについて学習できます。
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827727"
---
# <a name="mail-flow-in-eop"></a>EOP のメール フロー

Exchange Online メールボックスを使用している Microsoft 365 組織、または Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、組織に送信されたすべてのメッセージは EOP を通って作業者に表示されます。 社内の受信ボックスにルーティングされる前に処理するために EOP を通じて通るメッセージのルーティング方法に関するオプションがあります。

## <a name="working-with-messages-and-message-access-options"></a>メッセージとメッセージ アクセス オプションの操作

EOP はメッセージのルーティング方法を柔軟に行います。 以下のトピックで、メール フロー プロセスの手順について説明します。

[ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) サービス ネットワーク境界で無効な受信者宛てのメッセージを拒否できるディレクトリ ベースのエッジ ブロック機能について説明します。

「[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。

組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。 サブドメインの詳細については [、「Exchange Online でサブドメインのメール フローを有効にする」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[コネクタを使用するメール フローを構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) するには、コネクタを導入し、それを使ってメール ルーティングをカスタマイズする方法を示します。 シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。

[コネクタのフィルター処理の強化は、EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) の前にメールがサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。

スタンドアロン EOP 組織では、迷惑メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされるのを、一組構成手順を実行する必要があります。 詳細については、ハイブリッド環境 [の [迷惑メール] フォルダーにスパムを配信するようにスタンドアロン EOP を構成する方法を詳しく説明しています](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 メッセージをそれぞれのユーザーの迷惑メール フォルダーに移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="verify-mail-flow"></a>メール フローを確認する

コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。

[Microsoft 365 コネクタを検証してメール フローをテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) すると、メール フローが正しくセットアップされているかどうかのテスト手順が提供されます。
