---
title: Microsoft Teamsクラスと会議を Open LMS と統合する
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
description: Microsoft OneDrive ラーニング Tools 相互運用性 for Open LMS を使用して、Teams クラスと会議を作成および管理します。
ms.openlocfilehash: 3f9feb5f45a0f1d814818edcb4171f28ef362fdb
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66044438"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-within-open-lms"></a>Open LMS 内でMicrosoft Teamsクラスと会議を統合する

> [!NOTE]
> 現時点では、Open LMS と Microsoft Teams LTI 統合はプライベート プレビューでのみ使用できます。
>
>プライベート プレビュー プログラムに参加する場合は、 [こちらにサインアップしてください](https://m365crmedu.powerappsportals.com/LMSSignup/)。

このガイドでは、open LMS で Teams クラスと Teams Meetings LTI アプリの両方を登録するための IT 管理者の手順について説明します。

任意の LMS のすべての LTI アプリの管理の詳細については、「Microsoft [LMS Gateway for any LMS の管理」を](manage-microsoft-one-lti.md)参照してください。

## <a name="prerequisites-before-set-up"></a>セットアップ前の前提条件

Open LMS とTeamsの統合が正しく機能するには、Open LMS とTeamsを設定して相互に通信する必要があります。

[Moodle プラグインをインストールして構成する手順に](open-lms-plugin-configuration.md)従います。

## <a name="register-microsoft-teams-lti-for-use-in-open-lms"></a>Open LMS で使用するために LTI Microsoft Teams登録する

> [!IMPORTANT]
> この統合を実行するユーザーは、Open LMS 管理者とMicrosoft 365テナント管理者である必要があります。

1. [Microsoft LMS Gateway](https://lti.microsoft.com/) にアクセスし、[**登録ポータルに移動**] ボタンを選択します。

2. Microsoft 365管理者アカウントでサインインします。

3. サインイン後、[ **新しい登録の追加**] を選択します。

4. Teams **会議 LTI** または **Teams クラス LTI** のいずれかを選択して登録し、[**次へ**] を選択します。

5. 簡単に識別できる **登録** 名を入力し、 **LMS プラットフォームとして [OPEN LMS** ] を選択します。 **[次へ]** を選択します。

6. Open LMS サイトに追加する必要があるキーの一覧が表示されます。

7. 別のタブで LMS を開きます。Microsoft LMS ゲートウェイ タブを閉じないでください。

8. Open LMS で、**サイト管理** > **プラグイン** > **アクティビティ モジュール** > **の外部ツール****管理ツール** > に移動します。

9. [ **ツールの管理** ] ページ **で、手動でツールを構成するを** 選択します。

10. [**ツールの設定]** で、[**Microsoft Teams クラス**] などの **ツール名** を入力します。 **LTI バージョン** の場合は、**LTI 1.3** を選択します。 **[公開キーの種類**] で、[**キーセット URL**] を選択します。

11. 次に、 **Microsoft LTI キー** から対応するツール入力にキーをコピーします。
    1. Microsoft の **ターゲット リンク URL** キーは Open LMS の **ツール URL** フィールドに入ります。
    1. Microsoft の **Open ID 接続 URL** キーは Open LMS の **[ログイン URL の開始]** フィールドに移動します。
    1. Microsoft の **リダイレクト URL** キーは Open LMS の **リダイレクト URI** フィールドに入ります。

12. [**変更の保存**] を選択します。

13. 新しいツールが、[OPEN LMS の **[ツールの管理**] ページの [**ツール**] セクションに表示されます。 リスト アイコンを選択すると、 **ツールの構成の詳細が** 表示されます。

14. [Microsoft LMS ゲートウェイ] タブに戻るします。**[次へ**] を選択して **、LMS で提供される登録キー** の手順に移動します。

15. Open LMS の **ツール構成の詳細** の値をコピーして、Microsoft の **LMS 提供の登録キー** ステップに貼り付けます。

  次のように値を貼り付けます。

  | Open LMS で | Microsoft LTI 登録ポータルで |
  | --------- | ------------------------------------ |
  | プラットフォーム ID | 発行者 ID URL |
  | クライアント ID | クライアント ID |
  | デプロイ ID | デプロイ ID |
  | 公開キーセットの URL | キーセット URL |
  | アクセス トークン URL | アクセス トークン URL |
  | 認証要求 URL | プラットフォーム認証 URL |

  **[次へ]** を選択します。

16. [ **校閲と追加] ページを確認** します。 エラーがない場合は、[ **保存して終了]** を選択します。 登録が成功したことを示すメッセージが表示されます。

Teams クラスまたは Teams Meetings LTI アプリの登録が完了しました。

他のアプリも追加する場合は、上記の手順を繰り返し、手順 4 で他の Teams LTI アプリを選択します。

### <a name="add-teams-lti-apps-to-educators-open-lms-courses"></a>Teams LTI アプリを教育者の Open LMS コースに追加する

LTI アプリTeams登録した後、教育者は Teams クラス アプリと Teams Meetings アプリを Open LMS コースに追加できます。

- [Teams クラス アプリの追加に関する教育者の指示](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-ac6a1e34-32f7-45e6-b83e-094185a1e78a)。
- [Teams Meetings アプリの追加に関する教育者の指示](https://support.microsoft.com/topic/use-microsoft-teams-meetings-in-your-lms-11b6095d-f90b-42b9-ab77-4dcff2bb3b76)。

## <a name="technical-requirements-to-launch-teams-lti-apps"></a>Teams LTI アプリを起動するための技術的要件

Open LMS 内で Teams LTI アプリを起動するには、いくつかの技術的要件を満たす必要があります。

> [!NOTE]
> IT 管理者と教育者は、LTI アプリ登録ポータルで LTI アプリを登録できます。

### <a name="it-admin-technical-requirements"></a>IT 管理者の技術的要件

- Moodle バージョン 3.10 以降を使用します。
- Moodle バージョン 3.10 以降の最新の Microsoft O365 プラグインをダウンロードします。
- LTI アプリ登録ポータルにアクセスして、LTI アプリを登録します。
  - デスクトップ デバイスで登録が完了している必要があります。
- Microsoft Edge、Google Chrome、Safari、Mozilla Firefox の最新バージョンをダウンロードします。

### <a name="educator-technical-requirements"></a>教育者の技術的要件

- IT 管理者がアプリを登録していない場合は、LTI アプリ登録ポータルにアクセスして LTI アプリを登録します。
  - デスクトップ デバイスで登録が完了している必要があります。
- Microsoft Edge、Google Chrome、Safari、Mozilla Firefox の最新バージョンをダウンロードします。
- [Open LMS でクラスと会議用の LTI アプリをTeamsします](#add-teams-lti-apps-to-educators-open-lms-courses)。

### <a name="student-technical-requirements"></a>学生の技術要件

- Open LMS でクラスと会議用の LTI アプリをTeamsします。
  - 学生は、Teams クラスまたは Meetings LTI アプリを追加するためのアクションを実行する必要はありません。
