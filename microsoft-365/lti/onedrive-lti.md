---
title: Microsoft OneDrive LTI と Canvas を統合する
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: 新しい Microsoft OneDrive ラーニング Tools Interoperability App for Canvas を使用して、課題の作成と採点、コース コンテンツのビルドとキュレーション、ファイルでの共同作業をリアルタイムで行うことができます。
ms.openlocfilehash: ce02be23d98d1dc54ae02a21f9bf1678d06c3d8f
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747228"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Microsoft OneDrive LTI と Canvas を統合する

Microsoft OneDrive LTI と Canvas の統合は、2 つのステップ プロセスです。 最初の手順では Canvas でMicrosoft OneDriveを有効にし、2 番目の手順ではMicrosoft OneDrive LTI を Canvas コース内で使用できるようにします。

## <a name="recommended-browser-settings"></a>推奨されるブラウザー設定

- Microsoft OneDriveに対して Cookie を有効にする必要があります。
- ポップアップは、Microsoft OneDriveに対してブロックしないでください。

> [!NOTE]
> - Cookie は Chrome ブラウザーのシークレット モードでは既定では有効になっていないため、有効にする必要があります。
> - Microsoft OneDrive LTI は、Microsoft Edge ブラウザーのプライベート モードで動作します。 Cookie がブロックされていないことを確認します (既定で有効になっています)。

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>キャンバスで LTI のMicrosoft OneDriveを有効にする

> [!IMPORTANT]
> この統合を実行するユーザーは、Canvas の管理者であり、Microsoft 365 テナントの管理者である必要があります。

1. <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI 登録ポータル</a>にサインインする
1. **[管理者の同意**] ボタンを選択し、アクセス許可を受け入れます。

> [!CAUTION]
> この手順が実行されていない場合、次の手順ではエラーが発生し、エラーが発生した後にこの手順を 1 時間実行することはできません。

3. [ **新しい LTI テナントの作成** ] ボタンを選択します。 [LTI 登録] ページで、ドロップダウンで **[キャンバス** ] を選択し、Canvas インスタンスのベース URL を入力します。

> [!NOTE]
> たとえば、 https://contoso.test.instructure.comCanvas インスタンスが ](https://contoso.test.instructure.com)) の場合は、完全な URL を入力する必要があります。

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI テナント管理ページ。LTI コンシューマー プラットフォームを選択するためのドロップダウン フィールドと URL テキスト フィールド。":::

4. [コピー] ボタンを選択して JSON を **コピー** します (右側のアイコンで、2 つのページが互いに重なって表示されます)。 これは、Canvas でキーを生成するために使用されます。

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="表示された JSON テキストをコピーし、Canvas でキー生成に使用できるようにするコピー ボタンを示す画像。":::

5. 管理者として Canvas インスタンスにサインインし、ページの左側にあるメニューから **[開発者キー** ] を選択します。 ドロップダウンから、ページの右上にあるドロップダウンから **LTI キー** を選択して開発者キーを作成します。

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="開発者キーが選択された左側のナビゲーション バーと、ページの右側のドロップダウンから選択された LTI キー エントリを示すスクリーンショット。":::

6. [構成] ページの [メソッド] ドロップダウンで、 **メソッド** として **[JSON の貼り付け** ] を選択し、手順 4 でコピーした JSON テキストを表示されるテキスト フィールドに貼り付けます。

    > [!TIP]
    > **省略可能な手順:** 学校の教育者がコースのナビゲーションに表示されるリンクを自分で制御する場合は、コピーした JSON のパラメーターを変更 ``default`` できます。 パラメーターは ``default`` 自動的に ``enabled`` 設定されます。ただし、教師が自分の ``default`` コースのナビゲーションを選択できるようにパラメーター ``disabled`` を変更します。
    >
    > 教育者がコース ナビゲーション リンクを変更する方法の詳細については、「コース ナビゲーション リンク[の管理操作方法](https://community.canvaslms.com/t5/Instructor-Guide/How-do-I-manage-Course-Navigation-links/ta-p/1020)参照してください。

7. キーを保存すると、Canvas で **Off** 状態で使用できるようになります。 キーを **オンに** し、次の手順で使用する **[詳細** ] 列のキーをコピーします。

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="キーがオフの状態に設定されたキャンバス ページ。有効にする必要があり、このページの詳細列からキーをコピーする必要があります。":::

8. Microsoft OneDrive LTI 登録ポータルに戻り、**キャンバス クライアント ID** フィールドにキーを貼り付けます。 準備ができたら、[ **次へ** ] を選択します。

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="LTI テナント登録ページ。このページには、JSON テキストとキーをコピーするテキスト ボックスが表示されます。":::

9. 変更を確認して保存します。 登録が成功すると、メッセージが表示されます。
10. 登録の詳細は、ホーム ページの **[LTI テナントの表示** ] ボタンを選択して確認することもできます。

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>キャンバス コースで Microsoft OneDrive LTI を有効にする

キャンバス管理者は、すべてのコースで Microsoft OneDrive LTI を有効にすることができます。 特定のコース (およびすべてのコースではない) で LTI Microsoft OneDriveが必要な場合は、コースの設定内で同じ手順に従う必要があります。

1. 管理者としてサインインし、**設定** セクションに移動します。
2. **[アプリ**] セクションに移動し、[**アプリ構成の表示**] ボタンを選択します。
3. [ **アプリの追加] ボタンを** 選択します。
4. [ **構成の種類]** ドロップダウンで、[ **By Client ID** ] オプションを選択します。
5. 前に生成した開発者キーの値を **[クライアント ID** ] フィールドに貼り付けて、[ **送信]** ボタンを選択します。

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="[構成の種類] ドロップダウン メニューの [クライアント ID 別] オプションを示す [アプリの追加] ページ。":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>キャンバス コースでの Microsoft OneDrive LTI のコラボレーション 設定

> [!NOTE]
> 教育者と学生の共同作業を行うには、コラボレーション設定を有効にしないでください。 設定が有効になっていないことを確認するには、次の手順に従います。

1. 管理者としてサインインし、**設定** セクションに移動します。
1. **[機能オプション]** セクションに移動し、[**コース**] セクションに移動します。
1. **外部コラボレーション ツール機能を** 有効にしないように設定します。

> [!NOTE]
> コラボレーションは、個々の学生と学生のグループに割り当てることができます。 個々の学生への割り当ては既定で機能します。 学生のグループにコラボレーションを割り当てることができるようにするには、次の手順に従います。

1. 管理者としてログインし、[ **開発者キー]** セクションに移動します。
1. 値が170000000000710キーを見つけ、[ **オン]** に設定します。
