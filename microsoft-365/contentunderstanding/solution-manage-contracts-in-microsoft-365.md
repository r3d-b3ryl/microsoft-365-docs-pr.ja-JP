---
title: Microsoft 365 ソリューションを使用して契約を管理する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- m365solution-managecontracts
- m365solution-overview
search.appverid: ''
ms.localizationpriority: medium
ROBOTS: ''
description: Microsoft 365 SharePoint Syntex、Microsoft 365、SharePoint、およびMicrosoft TeamsのPower Automate。
ms.openlocfilehash: 86ccbeef283b165e178b12debd3ae99f982afc04
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189239"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Microsoft 365 ソリューションを使用して契約を管理する

この記事では、組織の契約管理ソリューションを作成する方法について説明します。SharePoint Syntexおよびコンポーネントを使用Microsoft 365。 独自のビジネス ニーズに合ったソリューションの計画と作成に役立つフレームワークを提供します。 このソリューションでは契約管理について説明しますが、作業明細書や請求書など、他のドキュメント管理ソリューションを作成するためにそれを調整できます。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWJUR0]

</br>

## <a name="identify-the-business-problem"></a>ビジネス上の問題を特定する

契約管理システムを計画する最初の手順は、解決しようとしている問題を理解する方法です。 このソリューションでは、次の 4 つの重要な問題に対処する必要があります。

- **コントラクトを識別します**。 組織は、請求書、契約、作業明細書など、多くのドキュメントを処理します。  電子メールで送信されるデジタルアセットと、従来のメールを介して送信される紙のアセットがあります。 他のすべてのドキュメントからすべての顧客契約を識別し、それらを分類する方法が必要です。

- **契約承認の履歴を追跡します**。 組織では、契約が承認または却下されたかどうか、および支払いが処理されたかどうかを確認するための信頼性の高い方法が必要です。 

- **契約の承認を管理するサイト**。 組織では、必要なすべての関係者が契約を簡単に確認できる共同作業サイトをセットアップする必要があります。 利害関係者は、必要に応じて契約全体を確認できる必要がありますが、主に各契約の主要なフィールド (顧客名、PO 番号、総コストなど) を確認する必要があります。 関係者は、受信した契約を簡単に承認または拒否できる必要があります。

- **レビューされた契約をルーティングします**。 承認済みおよび却下された契約は、特定のワークフローを通じてルーティングする必要があります。 承認された契約は、支払い処理のためにサードパーティアプリケーションにルーティングする必要があります。 拒否された契約は、追加のレビューのためにルーティングする必要があります。

## <a name="overview-of-the-solution"></a>ソリューションの概要

  ![リスト、リスト、SharePoint Syntex、SharePoint、およびTeamsを使用Power Automate。](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

この契約管理ソリューション のガイダンスには、次の 4 つのコンポーネントMicrosoft 365。

- **Microsoft SharePoint Syntex:** コントラクト ファイルを識別して分類し、そこから適切なデータを抽出するモデルを作成します。

- **Microsoft SharePointリスト**: モダン リストで使用できる書式を使用SharePointビジネスに優しい形式で契約を提示します。

- **Microsoft Teams**: 関係者が契約を確認および管理Teams、チャネルと関連付けられたタブの機能を使用します。

- **Power Automate:** フローを使用して、承認プロセスを通じて契約をガイドし、その後、支払いのためにサードパーティ製のアプリケーションに案内します。

### <a name="how-it-all-works"></a>すべての動作方法

  ![ドキュメントのアップロード、データの抽出、関係者への通知、契約の承認または却下を行うワークフローを示すソリューションの図。](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. ドキュメントは、ドキュメント ライブラリSharePointアップロードされます。 ドキュメント SharePoint Syntexモデルがドキュメント ライブラリに適用されています。 各ファイルをチェックして、探すトレーニングを受けた "コントラクト" コンテンツ タイプと一致するコンテンツ タイプが一致する場合を確認します。 一致が見つかった場合は、ファイルを "コントラクト" として分類し、ドキュメントのコンテンツ タイプを更新します。

2. また、このモデルは、関係者が関心を持つ各契約ファイル (クライアント、請負業者、手数料の金額など) から特定のデータを *引き出します*。

    次のページは、モデルが識別するためにトレーニングされる契約の例です。

      ![コントラクトの例。](../media/content-understanding/contract.png)

3. このMicrosoft Teams、すべての関係者は、ドキュメント ライブラリ内Teams承認または却下のために表示されるセキュリティで保護されたチャネルのメンバーです。 新しいTeamsを使用すると、すべての関係者に新しい契約を確認する必要があるときに通知されます。

4. 契約を使用Power Automate、契約は、契約チャネルの承認プロセスをTeamsされます。 メンバーが契約を承認すると、契約の状態が承認済みに変更され、すべてのメンバーに Teams 投稿を通じて通知され、契約が支払いの準備ができていることを示す明細が作成されます。 このプロセスは、支払いのためにサードパーティの金融アプリケーションに直接書き込むまで拡張できます。

5. メンバーが契約を拒否すると、ステータスが拒否に変更され、すべてのメンバーに通知が投稿Teamsされます。

6. このソリューションの最後の結果は、組織の自動化されたビジネス プロセスです。 従業員は、ドキュメントの承認ワークフローを開始Teamsカスタム タイル ビューを簡単に使用できます。 

     ![[契約] タブ。](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>ライセンスの要件

このソリューションは、Microsoft 365 Enterprise (E1、E3、E5、F3) または Business (Basic、Standard、または プレミアム) ライセンスの一部として利用できる次の機能に依存します。

- Microsoft SharePoint Syntex
- Microsoft Teams
- Power Automate

### <a name="learn-how-to-use-sharepoint-syntex"></a>アプリの使い方SharePoint Syntex

新しいSharePoint Syntex? AI を使用してコンテンツSharePoint Syntexを管理する方法について学習します。

[SharePoint Syntex](/learn/paths/syntex-get-started)ラーニング パスを使用すると、ドキュメントの理解モデルとフォーム処理モデルを使用してドキュメントを分類し、テキストを抽出し、ドキュメントにラベルを付け、すばやく簡単に知識を管理する方法について説明します。

## <a name="create-the-solution"></a>ソリューションの作成

次のセクションでは、契約管理ソリューションを構成する方法について詳しく説明します。 次の 3 つの手順に分かれています。

- [手順 1.契約ファイルSharePoint Syntexデータの抽出に使用する方法](solution-manage-contracts-step1.md)
- [手順 2.契約Microsoft Teamsチャネルを作成するには、次の情報を使用します。](solution-manage-contracts-step2.md)
- [手順 3.契約Power Automate処理するフローを作成するには、次の手順を実行します。](solution-manage-contracts-step3.md)
