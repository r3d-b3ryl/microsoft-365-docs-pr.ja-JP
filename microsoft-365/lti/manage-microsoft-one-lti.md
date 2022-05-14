---
title: 任意の LMS の Microsoft LMS ゲートウェイを管理する
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: 表示、削除、編集、トラブルシューティングなど、Microsoft LMS Gateway の主要な管理タスクを実行する方法について説明します。
ms.openlocfilehash: 769670a710e24d89dd3e201ac433ac8ccbcffd1a
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65414796"
---
# <a name="manage-microsoft-lms-gateway-for-any-lms"></a>任意の LMS の Microsoft LMS ゲートウェイを管理する

Microsoft LMS Gateway は、Canvas、Blackboard、Moodle を含む複数の LMS と統合されています。

この記事では、IT 管理者が Microsoft LMS Gateway の主要な管理タスクに関する手順を説明します。

- [LTI 登録を表示します](#view-an-lti-registration)。
- [LTI 登録を削除します](#delete-an-lti-registration)。
- [LTI 登録を編集します](#edit-an-lti-registration)。
- [Microsoft LMS ゲートウェイに関する問題のトラブルシューティングを行います](#troubleshoot-issues-with-microsoft-lms-gateway)。
- [Microsoft LMS Gateway に関する問題を報告します](#report-problems-with-lti-registration-portal)。

## <a name="view-an-lti-registration"></a>LTI 登録を表示する

LTI 登録の詳細を表示する場合は、次の手順に従います。

1. [Microsoft LMS ゲートウェイ](https://lti.microsoft.com/)にアクセスします。
2. Microsoft 365管理者アカウントでサインインします。
3. 登録の一覧で、表示する LTI 登録を見つけます。
4. リストの横にある **目のアイコン** を選択します。
5. 登録の詳細パネルが開きます。

## <a name="delete-an-lti-registration"></a>LTI 登録を削除する

LTI 登録を削除する場合は、次の手順に従います。

1. [Microsoft LMS ゲートウェイ](https://lti.microsoft.com/)にアクセスします。
2. Microsoft 365管理者アカウントでサインインします。
3. 登録リストで、削除する LTI 登録を見つけます。
4. リストの横にある **ごみ箱アイコン** を選択します。
5. 確認ダイアログ ボックスで、[ **削除** ] を選択して削除を確認します。
6. 削除されると、成功メッセージが表示されます。

## <a name="edit-an-lti-registration"></a>LTI 登録を編集する

現時点では、追加後の既存の LTI 登録の編集はサポートされていません。

LTI 登録を変更するには、次の手順を実行する必要があります。

1. [既存の登録を削除します](#delete-an-lti-registration)。
2. 新しい登録を追加します。

## <a name="troubleshoot-issues-with-microsoft-lms-gateway"></a>Microsoft LMS Gateway に関する問題のトラブルシューティング

Microsoft LMS Gateway で問題が発生している場合は、トラブルシューティングに役立ついくつかの操作を以下に示します。

### <a name="issues-while-launching-an-lti-app-from-the-lms"></a>LMS から LTI アプリを起動中の問題

教育者は、LMS で Microsoft LTI アプリを起動する際に問題が発生する可能性があります。

その場合は、一般的な問題とその解決方法を次に示します。

- **Cookie が見つかりません**
  - ブラウザーの設定で **LMS URL** に対してサード パーティの Cookie を許可する必要があります。
  - これらの Cookie は、IMS 仕様に従って LTI 1.3 ハンドシェイクを完了するために必要です。
  - ブラウザーの Cookie 設定を更新する方法については、「ブラウザー [で LMS URL の Cookie を許可](browser-cookies.md)する」を参照してください。

- **登録の詳細が見つかりません**
  - この問題は、LTI アプリの登録が完了しなかった場合、または Microsoft LMS ゲートウェイで登録が削除された場合に発生します。
  - IT 管理者は、LTI アプリの登録を完了する必要があります。

- **LMS の一部の詳細が無効です**
  - この問題は、アプリ起動要求で LMS から送信された詳細が IMS LTI 1.3 仕様と一致しない場合に発生します。
  - 問題が解決しない場合、IT 管理者は [Microsoft の教育サポート チーム](https://edusupport.microsoft.com/support?product_id=lti_apps&platform_id=web) に連絡する必要があります。

### <a name="issues-with-signing-in-to-the-microsoft-lms-gateway"></a>Microsoft LMS ゲートウェイへのサインインに関する問題

Microsoft LMS ゲートウェイにサインインすると、登録ページへのアクセスに問題が発生したり、サインイン エラーが表示されたりすることがあります。

サインインに関する一般的な問題とその解決方法を次に示します。

- **承認エラー**
  - "アカウントにこのページにアクセスするアクセス許可がありません" というエラー メッセージが表示された場合は、次のいずれかを実行します。
    - アカウントが登録済みテナントに属していないか、または
    - このアカウントは、教育者または管理者に属していません。

  - どちらの場合も、[ **アカウントの切り替え&サインアウト** ] ボタンが表示されます。
    - このボタンを選択するか、ユーザー プロファイル メニューの下にある **[サインアウト** ] ボタンを選択します。
    - テナント、教育者、または管理者に属するアカウントでサインインします。

  - テナントが登録されていない場合は、IT 管理者が LTI 統合を登録する前に登録する必要があります。

  - これらの手順を試してもこのエラーが表示される場合は、サインアウトしてもう一度サインインします。
    - また、Microsoft LMS Gateway `https://login.microsoftonline.com/`と .
    - もう一度サインインしてみてください。
    - 問題が解決しない場合は、右上の [問題の **報告** ] リンクを選択して問題を報告します。

- **認証エラー**
  - エラー メッセージが表示された場合は、「認証に失敗しました。 もう一度やり直してください」と、サインイン セッションの有効期限が切れている可能性があります。
    - サインアウトしてもう一度サインインします。
    - また、Microsoft LMS Gateway `https://login.microsoftonline.com/`と .
    - もう一度サインインしてみてください。
    - 問題が解決しない場合は、右上の [問題の **報告** ] リンクを選択して問題を報告します。

- **その他のエラー**
  - その他のすべてのエラーについては、"問題が発生しました。" というエラー メッセージが表示されます。 後でもう一度お試しください。」
    - これは内部処理エラーである可能性があります。
    - 数時間後にもう一度サインインしてみてください。
      - [ **ホーム ページに移動** ] ボタンを選択します。 これにより、ランディング ページに戻ります。
      - [ **登録ポータルに移動** ] ボタンを選択して、Microsoft LMS ゲートウェイに戻ります。

### <a name="report-problems-with-lti-registration-portal"></a>LTI 登録ポータルに関する問題を報告する

LTI 登録ポータルの問題を報告したり、フィードバックを送信したりするには、次の手順に従います。

1. LTI 登録ポータルで、ページ ヘッダーの **疑問符アイコン** を選択します。
2. ドロップダウンで、[ **問題の報告**] を選択します。
3. Microsoft Education サポート ページが開きます。 Microsoft 365資格情報を使用してサインインします。
4. フォームに入力して送信します。
