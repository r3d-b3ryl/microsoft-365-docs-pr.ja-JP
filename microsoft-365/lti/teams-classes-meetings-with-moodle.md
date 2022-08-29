---
title: Microsoft Teams のクラスと会議を Moodle と統合する
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
description: Teams のクラスと会議を作成して管理します。Microsoft OneDrive Learning Tools の相互運用性 for Moodle を使用します。
ms.openlocfilehash: e570b35f80203268a947a22ec8bdbc023a90854b
ms.sourcegitcommit: 9a4b0bc6a3ba076ecc392260efe7d2e1b655cde8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67420026"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-within-moodle"></a>Moodle 内で Microsoft Teams のクラスと会議を統合する

このガイドでは、Teams クラスと Teams Meetings LTI アプリの両方を Moodle に登録するための IT 管理者の手順について説明します。

任意の LMS のすべての LTI アプリの管理の詳細については、「Microsoft [LMS Gateway for any LMS の管理」を](manage-microsoft-one-lti.md)参照してください。

## <a name="prerequisites-before-set-up"></a>セットアップ前の前提条件

Moodle と Teams の統合が正しく機能するには、互いに通信するように Moodle と Teams を設定する必要があります。

[Moodle プラグインをインストールして構成する手順に](moodle-plugin-configuration.md)従います。

## <a name="register-microsoft-teams-lti-for-use-in-moodle"></a>Moodle で使用するために Microsoft Teams LTI を登録する

この統合を実行するユーザーは、Moodle 管理者と Microsoft 365 テナント管理者である必要があります。

1. [Microsoft LMS Gateway](https://lti.microsoft.com/) にアクセスし、[**登録ポータルに移動**] ボタンを選択します。

2. Microsoft 365 管理者アカウントでサインインします。

3. サインイン後、[ **新しい登録の追加**] を選択します。

4. 登録 **する Teams Meetings LTI** または **Teams クラス LTI** のいずれかを選択し、[ **次へ**] を選択します。

5. 簡単に識別できる **登録** 名を入力し、LMS プラットフォームとして **[Moodle** ] を選択します。 [**次へ**] を選択します。

6. Moodle サイトに追加する必要があるキーの一覧が表示されます。

7. 別のタブで Moodle を開きます。Microsoft LMS ゲートウェイ タブを閉じないでください。

8. Moodle で、**サイト管理** > **プラグイン** > **アクティビティ モジュール** > **の外部ツール****管理ツール** > に移動します。

9. [ **ツールの管理** ] ページ **で、手動でツールを構成するを** 選択します。

10. [**ツールの設定]** で、**Microsoft Teams クラス** などの **ツール名** を入力します。 **LTI バージョン** の場合は、**LTI 1.3** を選択します。 **[公開キーの種類**] で、[**キーセット URL**] を選択します。

11. 次に、 **Microsoft LTI キー** から対応するツール入力にキーをコピーします。
    1. Microsoft の **ターゲット リンク URL** キーは、Moodle の **[ツール URL]** フィールドに移動します。
    1. Microsoft の **Open ID 接続 URL** キーは、Moodle の **[ログイン URL の開始]** フィールドに移動します。
    1. Microsoft の **リダイレクト URL** キーは、Moodle の **リダイレクト URI** フィールドに入ります。

12. **[変更の保存]** を選択します。

13. 新しいツールが、Moodle の [**ツールの管理**] ページの [**ツール**] セクションに表示されます。 リスト アイコンを選択すると、 **ツールの構成の詳細が** 表示されます。

14. [Microsoft LMS ゲートウェイ] タブに戻るします。**[次へ**] を選択して **、LMS で提供される登録キー** の手順に移動します。

15. Moodle の **ツール構成の詳細** の値をコピーして、Microsoft **の LMS 提供の登録キー** ステップに貼り付けます。

    次のように値を貼り付けます。

    | On Moodle | Microsoft LTI 登録ポータルで |
    | --------- | ------------------------------------ |
    | プラットフォーム ID | 発行者 ID URL |
    | クライアント ID | クライアント ID |
    | デプロイ ID | デプロイ ID |
    | 公開キーセットの URL | キーセット URL |
    | アクセス トークン URL | アクセス トークン URL |
    | 認証要求 URL | プラットフォーム認証 URL |

    >[!NOTE]
    > Microsoft LMS ゲートウェイからの要求に対して、公開キーセットの URL がネットワーク設定によって制限されていないことを確認します。

    [**次へ**] を選択します。

16. [ **校閲と追加] ページを確認** します。 エラーがない場合は、[ **保存して終了]** を選択します。 登録が成功したことを示すメッセージが表示されます。

Teams クラスまたは Teams Meetings LTI アプリの登録が完了しました。

他のアプリも追加する場合は、上記の手順を繰り返し、手順 4 で他の Teams LTI アプリを選択します。

### <a name="add-teams-lti-apps-to-educators-moodle-courses"></a>Teams LTI アプリを教育者の Moodle コースに追加する

Teams LTI アプリを登録した後、教師は Teams クラス アプリと Teams 会議アプリを Moodle コースに追加できます。

- [Teams クラス アプリの追加に関する教育者の手順](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-ac6a1e34-32f7-45e6-b83e-094185a1e78a)。
- [Teams Meetings アプリの追加に関する教育者の指示](https://support.microsoft.com/topic/use-microsoft-teams-meetings-in-your-lms-11b6095d-f90b-42b9-ab77-4dcff2bb3b76)。

## <a name="technical-requirements-to-launch-teams-lti-apps"></a>Teams LTI アプリを起動するための技術的要件

Moodle 内で Teams LTI アプリを起動するには、いくつかの技術的要件を満たす必要があります。

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
- [Moodle のクラスと会議用の Teams LTI アプリ](#add-teams-lti-apps-to-educators-moodle-courses)。

### <a name="student-technical-requirements"></a>学生の技術要件

- Moodle のクラスと会議用の Teams LTI アプリ。
  - 学生は、Teams クラスまたは会議 LTI アプリを追加するためのアクションを実行する必要はありません。
