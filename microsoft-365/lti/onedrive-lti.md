---
title: '[ツールMicrosoft OneDrive ラーニング相互運用性を使用する'
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
description: 新しいツール相互運用性アプリを使用して、課題の作成と採点、コース コンテンツの構築とキュレーション、ファイルMicrosoft OneDrive ラーニング共同作業を行います。
ms.openlocfilehash: 445c12077c7b7b61269c0bef9e216db0ff1ddfb2
ms.sourcegitcommit: b71a8fdda2746f18fde2c94d188be89f9cab45f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2021
ms.locfileid: "61578173"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>LTI Microsoft OneDriveキャンバスとの統合

LTI Microsoft OneDrive Canvas との統合は、2 つのステッププロセスです。 最初の手順では Canvas Microsoft OneDriveを有効にし、2 番目の手順では、Microsoft OneDrive内で LTI を使用できます。

## <a name="recommended-browser-settings"></a>推奨されるブラウザー設定

- Cookie は、ユーザーに対してMicrosoft OneDrive。
- ポップアップをブロックしない必要Microsoft OneDrive。

> [!NOTE]
> - Cookie は Chrome ブラウザーのシークレット モードでは既定では有効になっていません。有効にする必要があります。
> - Microsoft OneDrive LTI は、ブラウザーのプライベート モードMicrosoft Edgeします。 Cookie をブロックしていない (既定で有効になっている) 必要があります。

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Canvas Microsoft OneDrive LTI を有効にする

> [!IMPORTANT]
> この統合を実行するユーザーは、Canvas の管理者であり、テナントの管理者Microsoft 365必要があります。

1. <a href="https://onedrivelti.microsoft.com/admin" target="_blank">LTI 登録ポータルMicrosoft OneDriveサインインする</a>
1. [管理者の **同意] ボタンを** 選択し、アクセス許可を受け入れる。

> [!CAUTION]
> この手順を実行しない場合は、次の手順でエラーが発生し、エラーが発生すると、この手順を 1 時間実行できません。

3. [新しい **LTI テナントの作成] ボタンを選択** します。 [LTI 登録] ページでドロップダウン **で [Canvas]** を選択し、Canvas インスタンスのベース URL を入力します。

> [!NOTE]
> Canvas インスタンスが ( ) の場合 https://contoso.test.instructure.com https://contoso.test.instructure.com) は、完全な URL を入力する必要があります。

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI テナント管理ページ(LTI コンシューマー プラットフォームを選択するためのドロップダウン フィールドと URL テキスト フィールドを含む)。":::

4. [コピー] ボタンを選択して **JSON** をコピーします (右側のアイコンで、2 つのページが上に表示されます)。 これは、Canvas でキーを生成するために使用されます。

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="表示された JSON テキストをコピーし、Canvas でのキー生成に使用できるコピー ボタンを示す画像。":::

5. Canvas インスタンスに管理者としてサインインし、ページの左側にあるメニューから [開発者キー] を選択します。 ドロップダウンから、ページ右上のドロップダウンから **[LTI キー** ] を選択して開発者キーを作成します。

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="[開発者キー] が選択されている左側のナビゲーション バーと、ページの右側のドロップダウンから選択された LTI キー エントリを示すスクリーンショット。":::

6. [構成] ページの[メソッド] ドロップダウンで、[メソッドとして **JSON** を貼り付ける] を選択し、表示されるテキスト フィールドの手順 5 でコピーした JSON テキストを貼り付けます。
7. キーを保存すると、Off 状態の Canvas **で使用** できます。 キーを **オンに** し、[詳細] 列で指定したキーをコピーして、次の手順で使用します。

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="キーがオフの状態で設定されたキャンバス ページ。このキーをオンにし、このページの詳細列からキーをコピーする必要があります。":::

8. LTI 登録ポータルMicrosoft OneDriveに戻り、[Canvas Client ID] フィールドにキー **を貼り付** けます。 準備 **ができたら、[** 次へ] を選択します。

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="キーをコピーする必要がある JSON テキストとテキスト ボックスを示す LTI テナント登録ページ。":::

9. 変更を確認して保存します。 正常に登録されると、メッセージが表示されます。
10. 登録の詳細は、ホーム ページの **[LTI** テナントの表示] ボタンを選択して確認することもできます。

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>キャンバス コースMicrosoft OneDrive LTI を有効にする

キャンバス管理者は、すべてのコースMicrosoft OneDrive LTI を有効にできます。 LTI Microsoft OneDrive (すべてのコースではなく) で必要な場合、コースの教師は、コース設定内で同じ手順を実行する必要があります。

1. 管理者としてサインインし、[管理者] セクション **に設定** します。
2. [アプリ] **セクションに移動** し、[アプリ構成の表示 **] ボタンを選択** します。
3. [アプリの **追加] ボタンを** 選択します。
4. [構成の **種類] ドロップダウン** で、[クライアント ID 別 **] オプションを選択** します。
5. 以前に生成された開発者キーの値を [クライアント **ID]** フィールドに貼り付け、[送信] ボタン **を選択** します。

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="[構成の種類] ドロップダウン メニューの [クライアント ID 別] オプションを表示する [アプリの追加] ページ。":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>キャンバス 設定 LTI Microsoft OneDriveの共同作業

> [!NOTE]
> 教育者と学生が共同作業を行う場合は、共同作業の設定を有効にしない必要があります。 設定が有効になっていないか確認するには、以下の手順に従います。

1. 管理者としてサインインし、[管理者] セクション **に設定** します。
1. [機能 **オプション] セクションに** 移動し、[コース] セクション **に移動** します。
1. [外部 **コラボレーション ツール] 機能を** 有効に設定します。

> [!NOTE]
> コラボレーションは、個々の学生と学生のグループに割り当てることができます。 個々の学生への割り当ては、既定で動作します。 学生のグループに共同作業を割り当てるには、次の手順を実行します。

1. 管理者としてログインし、[開発者キー] **セクションに移動** します。
1. キーの値を指定して170000000000710を On に **設定します**。
