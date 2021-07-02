---
title: '[ツールOneDrive ラーニング相互運用性を使用する'
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 新しいツール相互運用性アプリを使用して、割り当ての作成と採点、コース コンテンツの構築とキュレーション、ファイルOneDrive ラーニング共同作業を行います。
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256986"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>キャンバスMicrosoft OneDrive LTI を使用する

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="integrate-with-canvas"></a>Canvas との統合

この統合を実行するユーザーは、Canvas の管理者であり、テナントの管理者Microsoft 365があります。

1. テナント管理者アカウントを使用Microsoft Azureポータルにサインインします。 Azure テナント管理者には、グループ管理者の役割も必要です。

    ![グループ管理者が強調表示されている](../media/lti-media/lti-group-admin.png)

2. LTI ポータルで Microsoft [OneDriveサインインします](https://odltiappnl.azurewebsites.net/admin)。

3. サインインを完了するためのアクセス許可を受け入れる。

    ![アクセス許可を受け入れる](../media/lti-media/lti-permissions.png)

4. **[LTI テナントの追加] を選択します**。

     ![LTI テナントの追加](../media/lti-media/lti-add-tenant.png)

5. ドロップダウン **から [キャンバスとして LTI コンシューマー** **プラットフォーム** ] を選択します。

6. [ **キャンバスベース URL] を選択し** 、[次へ] を **選択します**。

    ![[キャンバス] を選択し、ベース URL を追加する](../media/lti-media/lti-canvas-base-url.png)

   次の画面には、機密であるフィールドが表示されます。

7. ? **から [次へ** ] を選択します。 」ページが表示されます。 レビュー担当者はここで空白を入力できますか?

8. [ **次へ** ] を選択すると、機密の情報が表示されます。

   Azure portal の最後の画面には、Canvas インスタンスを追加するための次の手順が表示されます。

9. この画面から開発者キーをコピーします。 Canvas インスタンスを作成するときに使用します。

## <a name="add-the-canvas-instance"></a>Canvas インスタンスの追加

1. Canvas インスタンスで、[管理者開発者キー **] の選択**  >  **を解除します**。

2. [開発者 **キー] のドロップダウンで [LTI** キー **] を選択します**。

   ![LTI 開発者キーを取得する](../media/lti-media/lti-developer-keys.png)

3. 開発者キーをここに貼り付けます。

     ![開発者キーを貼り付ける](../media/lti-media/lti-developer-keys.png)

   キーが OFF モードで **作成** される

   ![オフ モードで作成された開発者キー](../media/lti-media/lti-copy-developer-keys.png)

4. 強調表示されたテキストをコピーします。
    これは、LTI ポータルのクライアント ID Microsoft OneDrive機能します。

5. LTI ポータルの **[クライアント ID]** フィールドにテキストMicrosoft OneDrive貼り付け、[次へ] を **選択します**。

6. **[保存]** を選択します。

7. [LTI テナントの表示] **を選択して設定を表示します**。
