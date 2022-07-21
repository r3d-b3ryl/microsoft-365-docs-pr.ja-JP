---
title: Microsoft Teams のクラスと会議 LTI アプリと Desire2Learn Brightspace LMS を統合する
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-modern-desktop
- m365initiative-edu
ms.localizationpriority: medium
description: Desire2Learn (D2L) Brightspace LMS 用の Microsoft Learning Tools 相互運用性 (LTI) を使用して Teams のクラスと会議を作成および管理します。
ms.openlocfilehash: c3d551fcdc866c08437564addb1cd3cb9b144a75
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950812"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-lti-apps-within-desire2learn-brightspace-lms"></a>Desire2Learn Brightspace LMS 内で Microsoft Teams のクラスと会議の LTI アプリを統合する

このガイドでは、Desire2Learn (D2L) Brightspace LMS 用に Teams クラスと Teams Meetings LTI アプリの両方を登録するための IT 管理者の手順について説明します。

任意の LMS のすべての LTI アプリの管理の詳細については、「Microsoft [LMS Gateway for any LMS の管理」を](manage-microsoft-one-lti.md)参照してください。

Teams LTI アプリと Brightspace を統合する基本的な手順は次のとおりです。

1. [統合前の前提条件](#prerequisites-before-integration)。
1. [Brightspace で使用するために Microsoft LTI を登録します](#register-microsoft-teams-lti-for-use-in-brightspace)。
1. [Brightspace に Microsoft LTI アプリをデプロイします](#deploy-the-microsoft-lti-apps-to-brightspace)。
1. [Teams LTI アプリのリンクを教育者の Brightspace に追加します](#add-teams-lti-app-links-to-educators-brightspace)。

## <a name="prerequisites-before-integration"></a>統合前の前提条件

D2L Brightspace と Teams の統合が正しく機能するには、Brightspace と Teams が相互に通信するように設定する必要があります。

1. Teams クラスを機能させるには、 **Brightspace Course Connector** がインストールされ、正しく構成されている必要があります。 [次の手順に従って、Brightspace アカウントにコネクタをインストールします](https://community.brightspace.com/s/article/Getting-started-with-Brightspace-Course-Connector-for-Microsoft-Teams)。

   > [!NOTE]
   > Teams LTI ツールとの互換性を確保するために、コネクタを設定する場合は、[**統合の種類** の **クラス チーム**] を選択します。

2. Teams 会議は、コース コネクタなしで機能します。 ただし、 **クラス全体の追加** などの特定の機能は使用できません。 Teams Meetings LTI アプリ用の **Brightspace Course Connector** をインストールすることをお勧めします。

## <a name="register-microsoft-teams-lti-for-use-in-brightspace"></a>Brightspace で使用するために Microsoft Teams LTI を登録する

1. [Microsoft LMS Gateway](https://lti.microsoft.com/) にアクセスし、[**登録ポータルに移動**] ボタンを選択します。

2. *Microsoft 365 管理者アカウント* でサインインします。

3. サインイン後、[ **新しい登録の追加**] を選択します。

4. 登録 **する Teams Meetings LTI** または **Teams クラス LTI** のいずれかを選択し、[ **次へ**] を選択します。

5. 簡単に識別できる **登録** 名を入力し、LMS プラットフォームとして **D2L Brightspace** を選択します。 **[次へ]** を選択します。

6. Brightspace LMS サイトに追加する必要があるキーの一覧が表示されます。

7. 別のタブで Brightspace サイトを開きます。Microsoft LMS ゲートウェイ タブを閉じないでください。

8. Brightspace サイトで、**管理** > **Manage 機能拡張** に移動し、**LTI Advantage** を選択してから **ツールを登録します**。

9. **標準登録** を選択し、**Microsoft LTI キー** から対応するツール入力にキーをコピーします。
    1. Microsoft の **ターゲット リンク URL** キーは、Brightspace の **[ターゲット リンク URI]** フィールドに入力されます。
    1. Microsoft の **Open ID 接続 URL** キーは、Brightspace の **OpenID Connect ログイン URL** フィールドに入力されます。
    1. Microsoft の **リダイレクト URL** キーは、Brightspace の **[リダイレクト URL]** フィールドに移動します。

10. **[ドメイン**] フィールドに「`https://teams.microsoft.com`.

11. **[登録]** ボタンを選択します。

12. モーダルには Brightspace 登録の詳細が表示されます。 これらの値は、Microsoft LMS ゲートウェイに追加する必要があります。

13. **Microsoft LMS ゲートウェイ** タブで、**LMS 提供の登録キー** を選択します。

14. Brightspace の構成の詳細の値をコピーし、Microsoft **の LMS に** 貼り付けます。登録キーの手順に従います。

    次のように値を貼り付けます。

    | Brightspace で                         | Microsoft LTI 登録ポータルで |
    | -------------------------------------- | ------------------------------------ |
    | 発行者                                 | 発行者 ID URL                        |
    | クライアント ID                              | クライアント ID                            |
    | Brightspace キーセット URL                 | キーセット URL                           |
    | OpenID Connect 認証エンドポイント | プラットフォーム認証 URL          |

    **[次へ]** を選択します。

15. [ **校閲と追加] ページを確認** します。 エラーがない場合は、[ **保存して終了]** を選択します。 登録が成功したことを示すメッセージが表示されます。

Teams クラスまたは Teams Meetings LTI アプリの登録が完了しました。

他のアプリも追加する場合は、上記の手順を繰り返し、手順 4 で他の Teams LTI アプリを選択します。

## <a name="deploy-the-microsoft-lti-apps-to-brightspace"></a>Brightspace に Microsoft LTI アプリをデプロイする

Microsoft LTI アプリを登録したら、Brightspace サイトにアプリをデプロイする必要があります。

新しいデプロイを作成する手順を次に示します。

1. Brightspace サイトで、作成したツールを選択します。
2. デプロイ名を入力します。
3. **クラスリスト** と匿名を除くすべてのセキュリティ設定を選択 **します**。
4. 構成設定を設定しないでください。
5. **[デプロイの作成] を選択します**。

新しい LTI アプリを使用する **組織単位** を選択します。 **ルート組織** を選択するか、個々の組織単位の子を選択します。

## <a name="add-teams-lti-app-links-to-educators-brightspace"></a>Teams LTI アプリリンクを教育者の Brightspace に追加する

デプロイを作成した後、新しいリンクを作成します。 このリンクは、Microsoft LTI アプリを教育者の Brightspace エクスペリエンスに追加します。

1. Brightspace サイトで、作成したデプロイを選択します。
2. 下にスクロールし、[ **リンクの表示**] を選択します。
3. [ **新しいリンク]** を選択します。
4. 次の必要な詳細を入力します。
    1. *Microsoft LMS ゲートウェイ* からの **リダイレクト URL を** **URL** フィールドに貼り付けます。 この URL には、ゲートウェイの登録を表示することでアクセスできます。
    1. 種類を **[基本起動]** に設定します。
5. **[保存して閉じる]** をクリックします。

教育者は、Brightspace **[既存のコンテンツ** ] ドロップダウンで選択することで、Microsoft LTI アプリを追加できるようになりました。
