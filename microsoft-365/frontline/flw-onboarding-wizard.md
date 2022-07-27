---
title: 現場担当者オンボード ウィザードを使用して、現場の従業員を稼働させます
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: 現場担当者オンボード ウィザードを使用して、組織内の現場のワーカーとマネージャーに合わせて調整された Teams でエクスペリエンスをすばやく展開する方法について説明します。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: b927f3109013ccb0b4570ae0d592c4360ac196dc
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994921"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>現場担当者オンボード ウィザードを使用して、現場の従業員を稼働させます

## <a name="overview"></a>概要

Microsoft 365 管理センターの現場担当者オンボード ウィザードを使用すると、フロントライン ワーカーを組織に簡単にオンボードできます。 ウィザードを使用すると、現場の従業員に合わせて調整されたエクスペリエンスを Microsoft Teams にすばやく展開できます。 ウィザードを使用すると、組織内の現場担当者に対する Teams のパイロット展開を簡単に開始できます。

ウィザードは、現場担当者のチームを設定し、各チーム メンバーにライセンスと [ポリシー パッケージ](/microsoftteams/policy-packages-flw?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json) を割り当てます。 チームを最初から作成するか、[チーム テンプレート](/microsoftteams/get-started-with-teams-templates-in-the-admin-console)から作成し、ユーザーを追加してロールを割り当てることができます。 このロールによって、ウィザードが各ユーザーに割り当てるポリシー パッケージが決まります。

現在、ウィザードでは、実行するたびに 100 人のユーザーを追加できます。 間もなく 1 回の実行あたりのユーザー数を増やすことに取り組んでいます。 最新の更新プログラムについては、こちらを参照してください。

このウィザードは、少なくとも 1 つの [F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline)を持つすべての組織で使用できます。 ウィザードは、組織内のさまざまな場所またはサイトの最前線の従業員に Teams をロールアウトするために必要な回数だけ実行できます。

ウィザードを実行して現場の従業員をオンボードする方法の概要については、この短いビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> ウィザードでは、 [秘密度ラベル](/microsoftteams/sensitivity-labels) はまだサポートされていません。 組織でチームを作成するために秘密度ラベルが必要な場合は、ウィザードがMicrosoft 365 管理センターに表示されません。

## <a name="run-the-wizard"></a>セットアップ ウィザードを実行する

1. Microsoft 365 管理センターの左側のナビゲーションで [[管理センター](https://admin.microsoft.com/)] を展開し、[**Exchange**] を選びます。 **[アプリとメール**] セクションに移動し、[**現場の従業員を稼働させる**] で [**表示**] を選択します。 ここでは、現場担当者向けの Microsoft 365 が提供する機能の詳細を確認できます。

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Microsoft 365 管理センターの 現場担当者オンボード エクスペリエンスの詳細ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. 準備ができたら、[**開始**] を選択してウィザードを実行します。

3. チームの名前を入力し、1 人以上のチーム所有者を追加して、プライバシー設定を選択します。 次に、チームをゼロから作成するか、チーム テンプレートから作成するかを選択します。 チーム テンプレートには、特定のビジネス ニーズまたはプロジェクトに合わせてチームを最適化する定義済みのチャネルとタブが用意されています。

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="ウィザードの [チームのセットアップ] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. チームに新しいメンバーを追加します。 組み込みタブ内のタスクに対してカスタム グループを追加することもできます。 グループを追加する場合は、グループ自体ではなく、グループ内の各ユーザーにライセンスとポリシー パッケージが直接割り当てられていることに注意してください。

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="チームにユーザーとグループを追加するウィザードの [ユーザーの追加] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. 各チーム メンバーに次のいずれかのロールを割り当てます: 現場担当者、現場マネージャー、なし。 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="チーム メンバーにロール、場所、ライセンスを割り当てるウィザードの [ジョブ ロールの割り当て] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    現場担当者または現場マネージャー ロールを割り当てることで、そのユーザーはポリシー パッケージを受け取ります。 ポリシー パッケージは、自分のロールに合わせて調整されたエクスペリエンスを Teams で作成します。 このエクスペリエンスには、正常な現場担当者と現場マネージャーのコミュニケーションとコラボレーションのための事前ピン留めされたアプリとポリシーが含まれます。

    次に、場所を選択し、各チーム メンバーに Microsoft 365 F ライセンスを割り当てます。 十分なライセンスがない場合は、[**ライセンスの購入**] を選択してライセンスを追加購入できます。  

6. ウィザードの完了後に状態メールを受け取るユーザーを選択します。 電子メールには、ウィザードが&mdash;チームを作成し、チームメンバーを追加し、各チームメンバーにライセンスとポリシー パッケージを割り当てることによって実行されたアクションに関する成功と失敗の情報が含まれています。 この情報を使用して、発生する可能性があるエラーのトラブルシューティングを行います。

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="ウィザードの [状態メール受信者の追加] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. [変更の確認と確認] ページで、選択内容を確認し、**[確認]** を選択します。

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="チームの設定を確認するウィザードの [チームの確認] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-review-team.png":::

    ウィザードによってチームが作成され、チーム メンバーにライセンスとポリシー パッケージが割り当てられます。 完了までに数分かかる場合があります。その後、選択した受信者が状態メールを受信します。

8. あなたは途中ですが、まだ完了していません。 次に、この記事の [ウィザードを実行した後の操作](#what-to-do-after-running-the-wizard) に関するセクションを確認します。

## <a name="what-to-do-after-running-the-wizard"></a>ウィザードの実行後の操作

ウィザードを実行した後は、次のことを行う必要があります。

- 現場担当者と現場マネージャーに Teams ライセンスが割り当てられていることを知らせます。
- 組織で共有デバイスを使用している場合は、Teams がそれらのデバイスにインストールされていることを確認します。 チームに追加したユーザーには、Teams を開くよう求めるウェルカム メールが届きます。
- 組織で "Bring your own device" (BYOD) モデルを使用している場合は、チームに追加した各ユーザーに、Teams をダウンロードしてデバイスにインストールする必要があることをチームに知らせます。 また、Teams のダウンロードを求めるウェルカム メールも送信されます。

    > [!NOTE]
    > F1 ライセンスには電子メール アクセスが含まれていないため、F1 ライセンスを持つユーザーはウェルカム メールを受け取りません。  

フロントラインの従業員が初めて Teams を開くと、チーム内のすべてのチャットとチャネル、通話、タスク管理を含む、カスタマイズされた初回実行エクスペリエンスが提供されます。

## <a name="related-articles"></a>関連記事

- [フロントライン マネージャーと現場担当者用の Teams ポリシー パッケージ](/microsoftteams/policy-packages-flw?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams でポリシー パッケージを管理する](/microsoftteams/manage-policy-packages)
- [管理コンソールで Teams テンプレートを使用する](/microsoftteams/get-started-with-teams-templates-in-the-admin-console)
