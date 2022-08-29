---
title: Blackboard で Microsoft OneDrive LTI を使用する
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
ms.collection: m365initiative-edu
ms.localizationpriority: medium
description: 新しい Microsoft OneDrive Learning Tools Interoperability for Blackboard を使用して、課題の作成と採点、コース コンテンツの構築とキュレーション、ファイルでの共同作業をリアルタイムで行うことができます。
ms.openlocfilehash: 2fd03732a9426bb13176dbfc16a7c996767f5430
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388355"
---
# <a name="use-microsoft-onedrive-lti-with-blackboard"></a>Blackboard で Microsoft OneDrive LTI を使用する

Microsoft OneDrive LTI と Blackboard の統合は、2 段階のプロセスです。 最初の手順では、Microsoft OneDrive LTI を Blackboard コース内で使用できるようになり、2 番目の手順では Microsoft OneDrive for Blackboard が有効になります。

> [!IMPORTANT]
> この統合を実行するユーザーは、Blackboard の管理者であり、Microsoft 365 テナントの管理者である必要があります。

## <a name="recommended-browser-settings"></a>推奨されるブラウザー設定

- Microsoft OneDrive では Cookie を許可する必要があります。
- Microsoft OneDrive ではポップアップをブロックしないでください。

> [!NOTE]
>
> - Cookie は Chrome ブラウザーシークレット モードでは既定では許可されないため、許可する必要があります。
> - Microsoft OneDrive LTI は、Microsoft Edge ブラウザーのプライベート モードで動作します。 Cookie をブロックしていないことを確認します (既定では許可されています)。

## <a name="register-the-onedrive-lti-13-tool-in-blackboard"></a>OneDrive LTI 1.3 ツールを Blackboard に登録する

1. Blackboard の管理者パネルで、 **LTI ツール プロバイダー** を選択します。
2. [ **LTI 1.3 ツールの登録**] を選択します。
3. [クライアント ID] フィールドで、次の ID を入力またはコピーして貼り付けます。 ``78cd1b1c-ccbd-4318-9f90-22241f63b1f5``

   > [!NOTE]
   > このクライアント ID を追加すると、Blackboard で 2 つの異なる配置が構成されます。1 つは、コンテンツ マーケット、書籍、ツール、リッチ テキスト エディターからツールにアクセスできるようにする配置と、Ultra コースのオンラインコースのコースの [コンテンツの追加] メニューからツールにアクセスできる配置です。

4. **[送信]** を選択します。
5. **[ツールの状態]** ビューで事前に設定されたすべての設定を確認し、選択した **[ツールの状態**] ラウンド ボタンが **[承認済み**] になっていることを確認します。
6. **[教育機関ポリシー**] で、送信するユーザー フィールド **の [コース内のロール****] と [名前]** チェック ボックスをオンにします。 他のすべてのユーザー フィールドは省略可能ですが、OneDrive のインストールを将来の証明に残しておくことをお勧めします。
7. **現時点では、グレード サービス へのアクセスを許可** し **、メンバーシップ サービスへのアクセスを許可** することも省略可能ですが、LTI ツールの今後の更新に必要になる可能性があります。
8. **デプロイ ID をコピーします**。 Microsoft LTI ツールを構成するために必要になります。
9. [ **送信]** ボタンを選択して完了します。

## <a name="configure-the-microsoft-lti-tool-to-work-with-blackboard"></a>Blackboard で動作するように Microsoft LTI ツールを構成する

1. [Microsoft OneDrive LTI 登録ポータル](https://onedrivelti.microsoft.com/admin)にサインインします。
2. **[管理同意**] ボタンを選択し、アクセス許可を受け入れます。

    > [!CAUTION]
    > この手順が実行されていない場合、次の手順ではエラーが発生し、エラーが発生した後にこの手順を 1 時間実行することはできません。

3. [ **新しい LTI テナントの作成** ] ボタンを選択します。
4. [LTI 登録] ページで、[LTI コンシューマー プラットフォーム] ドロップダウンから **[Blackboard** ] を選択し、[ **次へ** ] ボタンを選択します。
5. ツールを Blackboard に登録するときにコピーした **デプロイ ID を** 貼り付けて、[ **次へ**] を選択します。
6. 変更を確認して保存します。 登録が成功すると、メッセージが表示されます。
7. 登録の詳細は、ホーム ページの **[LTI テナントの表示** ] ボタンを選択して確認することもできます。

これらの手順を完了すると、講師は、[コース コンテンツ] ページの [プラス] メニューを使用すると、OneDrive からドキュメントを開くことができるようになります。

## <a name="recommended-content"></a>推奨されるコンテンツ

[Microsoft Integrations for Blackboard](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft)

[Microsoft Teams クラスの統合](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft_Classes)
