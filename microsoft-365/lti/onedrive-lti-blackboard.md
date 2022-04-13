---
title: LTI Microsoft OneDrive Blackboard と統合する
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
ROBOTS: NOINDEX, NOFOLLOW
description: 新しい Microsoft OneDrive ラーニング Tools Interoperability for Blackboard を使用して、課題の作成と採点、コース コンテンツのビルドとキュレーション、ファイルでの共同作業をリアルタイムで行うことができます。
ms.openlocfilehash: 7e43ff51a069db55be06236fb0318aa4453d8feb
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824654"
---
# <a name="integrate-microsoft-onedrive-lti-with-blackboard"></a>LTI Microsoft OneDrive Blackboard と統合する

LTI Microsoft OneDrive Blackboard と統合することは、2 段階のプロセスです。 最初の手順では、Microsoft OneDrive LTI を Blackboard コース内で使用できるようにし、2 番目の手順では Blackboard のMicrosoft OneDriveをオンにします。

> [!IMPORTANT]
> この統合を実行するユーザーは、Blackboard の管理者であり、Microsoft 365 テナントの管理者である必要があります。

## <a name="recommended-browser-settings"></a>推奨されるブラウザー設定

- Microsoft OneDriveに対して Cookie を許可する必要があります。
- ポップアップは、Microsoft OneDriveに対してブロックしないでください。

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
6. **[教育機関ポリシー**] で、送信するユーザー フィールド **の [コース内のロール****] と [名前]** チェック ボックスをオンにします。 他のすべてのユーザー フィールドは省略可能ですが、今後のインストールOneDriveの証明に残しておくことをお勧めします。
7. **現時点では、グレード サービス へのアクセスを許可** し **、メンバーシップ サービスへのアクセスを許可** することも省略可能ですが、LTI ツールの今後の更新に必要になる可能性があります。
8. **デプロイ ID をコピーします**。 Microsoft LTI ツールを構成するために必要になります。
9. [ **送信]** ボタンを選択して完了します。

## <a name="configure-the-microsoft-lti-tool-to-work-with-blackboard"></a>Blackboard で動作するように Microsoft LTI ツールを構成する

1. [Microsoft OneDrive LTI 登録ポータルにサインインします](https://onedrivelti.microsoft.com/admin)。
2. **[管理者の同意**] ボタンを選択し、アクセス許可を受け入れます。

> [!CAUTION]
> この手順が実行されていない場合、次の手順ではエラーが発生し、エラーが発生した後にこの手順を 1 時間実行することはできません。

3. [ **新しい LTI テナントの作成** ] ボタンを選択します。
4. [LTI 登録] ページで、[LTI コンシューマー プラットフォーム] ドロップダウンから **[Blackboard** ] を選択し、[ **次へ** ] ボタンを選択します。
5. ツールを Blackboard に登録するときにコピーした **デプロイ ID を** 貼り付けて、[ **次へ**] を選択します。
6. 変更を確認して保存します。 登録が成功すると、メッセージが表示されます。
7. 登録の詳細は、ホーム ページの **[LTI テナントの表示** ] ボタンを選択して確認することもできます。

これらの手順を完了すると、インストラクタは、[コース コンテンツ] ページの [プラス] メニューを使用すると、OneDriveからドキュメントを開くことができるようになります。

## <a name="recommended-content"></a>推奨されるコンテンツ

[Microsoft Integrations for Blackboard](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft)

[Microsoft Teams クラスの統合](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft_Classes)
