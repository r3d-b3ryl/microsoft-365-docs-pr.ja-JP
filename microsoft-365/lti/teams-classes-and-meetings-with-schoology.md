---
title: Microsoft Teams 会議と Schoology LMS を統合する
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
description: Schoology LMS 用の Microsoft Learning Tools 相互運用性 (LTI) を使用して Teams 会議を作成および管理します。
ms.openlocfilehash: 970a568884b8f57677467615fe253135f793da8b
ms.sourcegitcommit: 9a7e853bb2f9d0ea377961d854d36b644799e5f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67364542"
---
# <a name="integrate-microsoft-teams-meetings-with-schoology-lms"></a>Microsoft Teams 会議と Schoology LMS を統合する

このガイドでは、Schoology に Teams Meetings LTI アプリを登録するための IT 管理者の手順について説明します。

Microsoft LTI の概要については、「 [Microsoft 製品と Learning Management System (LMS) の統合」](index.md)を参照してください。

> [!NOTE]
> この統合を実行するユーザーは、Schoology の管理者である必要があります。 ただし、Schoology **App Center** にアクセスできる Schoology ユーザーは、Microsoft Teams Meetings LTI アプリをインストールすることもできます。

## <a name="register-the-teams-meetings-lti-app-in-schoology"></a>Schoology で Teams Meetings LTI アプリを登録する

1. アプリをインストールして構成するアクセス権を持つ管理者として Schoology インスタンスにサインインします。
1. App [**Center**](https://app.schoology.com/apps) で **Microsoft Teams 会議** アプリにアクセスする場合は、この直接リンク [の Schoology 上の Microsoft Teams Meetings](https://app.schoology.com/apps/profile/6017478062) を開きます。
1. **[LTI 1.3 アプリのインストール**] ボタンを選択して、インストール プロセスを開始します。
1. [ **同意** する] ボタンを選択します。
1. 組織全体に対して、または自分のためだけにインストールする必要があるかどうかを確認するメッセージが表示されます。 [ **組織に追加]** を選択すると、[ **Organization Apps]** ページにリダイレクトされ、構成が完了します。
1. [**[組織アプリ] の一覧**](https://app.schoology.com/apps/school_apps)から **、Microsoft Teams 会議** アプリを探し、[**構成**] ボタンを選択します。
    1. アプリのデプロイに割り当てられているデプロイ **ID を** コピーします。
        1. この ID は、 **Microsoft LMS ゲートウェイ** の構成プロセスで使用されます。
1. [**[組織アプリ] の一覧**](https://app.schoology.com/apps/school_apps)から **、Microsoft Teams 会議** アプリを探し、[**インストールと削除**] ボタンを選択します。
    1. すべてのコースのアプリをインストールするには、[ **すべてのコース** ] チェック ボックスをオンにします。
        1. コースのすべてのメンバーがアプリを使用できるようにするには、[ **コース管理者のみ]** オプションをオンにしないでください。

> [!NOTE]
> すべてのコースにアプリをインストールしないことを選択した場合、 *Course Admins* は次のいずれかの方法でアプリをインストールする必要があります。
>
> 1. [組織アプリの一覧](https://app.schoology.com/apps/school_apps)に移動し、[**インストール/削除**] ボタンを選択し、アプリをインストールするコースを選択します。
> 1. または、コース左側のレール ナビゲーション メニューの下部にある [ **アプリのインストール** ] リンクを選択し、 **Microsoft Teams Meetings** アプリを選択してインストールすることもできます。

## <a name="configure-the-teams-meetings-lti-app-to-work-with-schoology"></a>Schoology で動作するように Teams Meetings LTI アプリを構成する

1. [Microsoft LMS Gateway](https://lti.microsoft.com/) にアクセスし、[**登録ポータルに移動**] ボタンを選択します。
1. Microsoft 365 管理者アカウントでサインインします。
1. **[管理同意**] ボタンを選択し、アクセス許可を受け入れます。
    1. この手順が実行されていない場合、次の手順ではエラーが発生し、エラーを受け取った後にこの手順を 1 時間実行することはできません。
1. [ **新しい LTI テナントの作成** ] ボタンを選択します。
1. [LTI 登録] ページで、[LTI コンシューマー プラットフォーム] ドロップダウンから **[Schoology** ] を選択し、[ **次へ** ] ボタンを選択します。
1. Schoology にツールを登録するときにコピーした **展開 ID を** 貼り付けて、[ **次へ**] を選択します。
1. 変更を確認して保存します。 登録が成功すると、メッセージが表示されます。
1. 登録の詳細は、ホーム ページの **[LTI テナントの表示** ] ボタンを選択して確認することもできます。

これらの手順を完了すると、教師は Teams Meetings LTI アプリを使用できるようになります。
