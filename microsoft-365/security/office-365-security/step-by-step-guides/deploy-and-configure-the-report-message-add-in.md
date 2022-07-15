---
title: レポート メッセージ アドインを展開して構成する
description: セキュリティ管理者向け Microsoft のフィッシング レポート アドインを展開して構成する手順
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 36e3fe25444f57de4cd43d67cab5a99f546a0f13
ms.sourcegitcommit: a209c9f86a7b4340a426c4cfed2d36a388c71124
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66798221"
---
# <a name="deploy-and-configure-the-report-message-add-in-to-users"></a>レポート メッセージ アドインを展開し、ユーザーに構成します。

Outlook 用のレポート メッセージとレポートフィッシング アドインを使用すると、Microsoft とその関係者に簡単にフィッシングを報告して分析を行うことができます。また、 [申請ポータル](https://security.microsoft.com/reportsubmission?viewid=user)の管理者向けのトリアージも簡単です。 

Defender for Office 365のライセンスを取得しているかどうかに応じて、アラート&自動調査と応答 (AIR) などの機能も追加されます。これにより、セキュリティ運用スタッフの負担が軽減されます。 このガイドでは、Microsoft Defender for Office 365 チームが推奨するアドインデプロイの構成について説明します。

## <a name="choose-between-which-add-in-to-deploy"></a>展開するアドインを選択する

- レポート フィッシング アドインには、フィッシング メッセージのみを報告するオプションが用意されています
- レポート メッセージ アドインには、迷惑メール (偽陽性)、フィッシング メッセージではなく、迷惑メールを報告するオプションが用意されています。


## <a name="what-youll-need"></a>必要なもの

-   Exchange Online Protection (一部の機能ではプラン 2 Defender for Office 365必要)
-   十分なアクセス許可 (アドイン展開のグローバル管理者、カスタマイズ用のセキュリティ管理者)
- 次の手順を実行するために 5 ~ 10 分

## <a name="deploy-the-add-in-for-users"></a>ユーザー用のアドインをデプロイする

1.  Microsoft 365 管理センターに **ログイン** します。  https://admin.microsoft.com.
1.  左側のナビゲーションで[ **すべて表示** ]、[ **設定]** の順に展開し、[ **統合アプリ**] を選択します。
1.  読み込まれたページで、 **Get Apps キーを押します**。
1.  表示されるページの右上の [検索] ボックスに「 **レポート メッセージ** 」または「 **フィッシング詐欺の報告**」と入力し、[ **検索**] を選択します。
1.  検索結果内の選択したアプリで **[今すぐ取得** ] を押します (発行元は **Microsoft Corporation**)。
1.  表示されるポップアップで、アドインをデプロイするユーザーを選択します。 テストを行う場合は、特定のグループを使用する必要がある場合は、選択を行ったときに組織全体に対して構成します。それ以外の場合は **、[次へ]** を押します。
1.  アクセス許可、情報、および機能を確認し、 **次へ** キーを押します。
1.  **[展開の完了]** を押します (アドインが Outlook クライアントに自動的に表示されるまでに 12 ~ 24 時間かかることがあります)。

## <a name="configure-the-add-in-for-users"></a>ユーザーのアドインを構成する
1.  Microsoft Security ポータルhttps://security.microsoft.comに **ログイン** します。.
2.  左側のナビゲーションにある **[Email & コラボレーション**] で、[**ポリシー&ルール**] を選択します。
3.  **[脅威ポリシー**] を選択します。
4.  [**その他**] 見出しの下にある [**ユーザーが報告したメッセージの設定**] を選択します。
5.  **Microsoft Outlook レポート メッセージ ボタン** が **[オン]** に切り替されていることを確認します。
6.  [ **報告されたメッセージを送信]** で **Microsoft** を選択します (推奨)。
7.  [ **レポートする場合はユーザーが選択できるようにする** ] がオフになっていることを確認し、[ **常にメッセージを報告する** ] が選択されていることを確認します。
8.  **[保存]** を押します。

## <a name="optional-steps--configure-notifications"></a>オプションの手順 - 通知を構成する

1.  前の手順の構成ページで、 **ユーザー レポート エクスペリエンス** の下で、必要に応じてポップアップのタイトルと本文を報告する前と後を構成します。 レポートの前に確認する機能も有効になっている場合、エンド ユーザーには **[レポートの前に確認する]** ポップアップが表示されます。
2.  内部組織のメールボックスから通知を受け取る場合は、[**送信者として使用する電子メール アドレスOffice 365指定** する] を選択し、組織内で有効なメールボックスを検索して通知を送信します。
3.  [**通知のカスタマイズ]** を押して、報告されたメッセージを管理者が確認した後にレポート ユーザーに送信されるテキストを設定します。マーク &通知を使用して、**フィッシング、****迷惑メール** & **の脅威が** 見つかりませんオプションを構成します。
4.  [ **フッター** ] タブで、通知用に送信するグローバル フッターと、必要に応じて組織のロゴを選択します。


### <a name="further-reading"></a>その他の読み取り
ユーザーが報告したメッセージ設定の詳細を確認[する ユーザーが報告したメッセージ設定 - Office 365 |Microsoft Docs](../user-submission.md)

レポート メッセージまたはレポート フィッシング アドインを[有効にする レポート メッセージまたはレポート フィッシング アドインを有効にする - Office 365 |Microsoft Docs](../enable-the-report-message-add-in.md)
