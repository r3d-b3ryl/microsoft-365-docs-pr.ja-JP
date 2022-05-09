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
description: SharePoint Syntex、SharePoint リスト、Microsoft Teams、Power AutomateのMicrosoft 365 ソリューションを使用してコントラクトを管理する方法について説明します。
ms.openlocfilehash: 86ccbeef283b165e178b12debd3ae99f982afc04
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189239"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Microsoft 365 ソリューションを使用して契約を管理する

この記事では、Microsoft 365のSharePoint Syntexとコンポーネントを使用して、組織のコントラクト管理ソリューションを作成する方法について説明します。 これにより、独自のビジネス ニーズに合ったソリューションを計画および作成するのに役立つフレームワークが提供されます。 このソリューションではコントラクト管理について説明していますが、作業明細書や請求書など、他のドキュメント管理ソリューションを作成するように調整できます。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWJUR0]

</br>

## <a name="identify-the-business-problem"></a>ビジネス上の問題を特定する

コントラクト管理システムを計画する最初の手順は、解決しようとしている問題を理解することです。 このソリューションでは、次の 4 つの重要な問題に対処する必要があります。

- **コントラクトを識別します**。 組織は、請求書、契約、作業明細書など、多くのドキュメントで動作します。  電子メールで送信されるデジタル資産もあれば、従来のメールを通じて送信される紙の資産もあります。 他のすべてのドキュメントからすべての顧客契約を識別し、それをそのように分類する方法が必要です。

- **契約承認の履歴を追跡します**。 組織には、契約が承認されたか拒否されたか、支払いが処理されたかどうかを確認する信頼性の高い方法が必要です。 

- **契約の承認を管理するサイト**。 組織は、必要なすべての利害関係者が契約を簡単に確認できるコラボレーション サイトを設定する必要があります。 利害関係者は、必要に応じて契約全体を確認できる必要がありますが、ほとんどの場合、各契約からいくつかの重要なフィールド (顧客名、PO 番号、総コストなど) が表示されることを考慮します。 利害関係者は、受信契約を簡単に承認または拒否できる必要があります。

- **確認されたコントラクトをルーティングします**。 承認されたコントラクトと拒否されたコントラクトは、特定のワークフローを経由してルーティングする必要があります。 承認されたコントラクトは、支払い処理のためにサード パーティのアプリケーションにルーティングする必要があります。 拒否されたコントラクトは、追加のレビューのためにルーティングする必要があります。

## <a name="overview-of-the-solution"></a>ソリューションの概要

  ![SharePoint Syntex、SharePoint リスト、Teams、Power Automateを使用したソリューションの図。](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

このコントラクト管理ソリューションガイダンスには、Microsoft 365の 4 つのコンポーネントが含まれています。

- **Microsoft SharePoint Syntex**: コントラクト ファイルを識別して分類し、そこから適切なデータを抽出するモデルを作成します。

- **Microsoft SharePoint リスト**: モダン SharePoint リストで使用できる書式を使用して、ビジネスに適した形式でコントラクトを表示します。

- **Microsoft Teams**: Teams チャネルと関連タブの機能を使用して、関係者が契約を確認および管理できるようにします。

- **Power Automate**: フローを使用して、承認プロセスを通じて契約をガイドし、その後、支払いのためのサード パーティのアプリケーションに移動します。

### <a name="how-it-all-works"></a>すべて動作する方法

  ![ドキュメントのアップロード、データの抽出、関係者への通知、契約の承認または拒否を行うワークフローを示すソリューションの図。](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. ドキュメントは、SharePointドキュメント ライブラリにアップロードされます。 SharePoint Syntexドキュメント理解モデルがドキュメント ライブラリに適用されています。 各ファイルをチェックして、検索対象としてトレーニングされた "コントラクト" コンテンツ タイプと一致するかどうかを確認します。 一致するものが見つかると、ファイルが "コントラクト" として分類され、ドキュメントのコンテンツ タイプが更新されます。

2. また、このモデルは、利害関係者が関心を持つ各コントラクト ファイル ( *クライアント*、 *契約業者*、 *料金など*) から特定のデータを取り出します。

    次のページは、モデルが識別するようにトレーニングされるコントラクトの例です。

      ![コントラクトの例。](../media/content-understanding/contract.png)

3. Microsoft Teamsでは、すべての利害関係者は、ドキュメント ライブラリ内のすべてのコントラクトが承認または拒否のために表示される安全なTeams チャネルのメンバーです。 Teams機能を使用すると、新しい契約を確認する必要があるときに、すべての利害関係者に通知されます。

4. Power Automateを使用すると、契約はTeams チャネルの承認プロセスを通じて移動されます。 メンバーが契約を承認すると、契約の状態が承認済みに変更され、すべてのメンバーにTeamsの投稿が通知され、契約が支払いの準備ができていることを示す明細が作成されます。 このプロセスを拡張して、支払いのためにサード パーティの財務アプリケーションに直接書き込むことができます。

5. メンバーがコントラクトを拒否すると、状態が拒否に変更され、すべてのメンバーにTeams投稿によって通知されます。

6. このソリューションの最終的な結果は、組織の自動化されたビジネス プロセスです。 従業員は、Teamsのカスタム タイル ビューを簡単に使用して、ドキュメントの承認ワークフローを開始および監視できます。 

     ![[コントラクト] タブ。](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>ライセンスの要件

このソリューションは、Microsoft 365 Enterprise (E1、E3、E5、F3) または Business (Basic、Standard、またはプレミアム) ライセンスの一部として利用可能なすべての機能に依存しています。

- Microsoft SharePoint Syntex
- Microsoft Teams
- Power Automate

### <a name="learn-how-to-use-sharepoint-syntex"></a>SharePoint Syntexを使用する方法について説明します

SharePoint Syntexの新機能 SharePoint Syntexを使用して、AI を使用してコンテンツを管理する方法について説明します。

SharePoint Syntexラーニング パス[を使用した概要](/learn/paths/syntex-get-started)では、ドキュメントの理解とフォーム処理モデルを使用して、ドキュメントを分類し、テキストを抽出し、ドキュメントにラベルを付けて、迅速かつ簡単に知識管理を行う方法について説明します。

## <a name="create-the-solution"></a>ソリューションを作成する

次のセクションでは、コントラクト管理ソリューションを構成する方法について詳しく説明します。 次の 3 つの手順に分かれています。

- [手順 1.SharePoint Syntexを使用してコントラクト ファイルを識別し、データを抽出する](solution-manage-contracts-step1.md)
- [手順 2.Microsoft Teamsを使用してコントラクト管理チャネルを作成する](solution-manage-contracts-step2.md)
- [手順 3.Power Automateを使用して、コントラクトを処理するフローを作成する](solution-manage-contracts-step3.md)
