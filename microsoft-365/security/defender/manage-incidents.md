---
title: インシデントを管理Microsoft 365 Defender
description: 状態の割り当てと更新を行う方法について説明します。
keywords: インシデント、インシデント、分析、応答、アラート、相関アラート、割り当て、更新、状態、管理、分類、microsoft、365、m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 41a0c893e193c8690c0c50e5b12ecc8630b9a899
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58570415"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>インシデントを管理Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

インシデント管理は、脅威を確実に含め、対処する上で重要です。

インシデント ポータル **(&)** の&で>インシデントからのインシデントを [security.microsoft.com 管理](https://security.microsoft.com)Microsoft 365 Defenderします。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント キューの例。":::

インシデントを管理する方法は次のとおりです。

- [インシデント名を編集する](#edit-the-incident-name)
- [インシデント タグを追加する](#add-incident-tags)
- [インシデントを自分に割り当てる](#assign-incidents)
- [それらを解決する](#resolve-an-incident)
- [分類と決定を設定する](#set-the-classification-and-determination)
- [コメントを追加する](#add-comments)

インシデントを管理するには、[インシデントの **管理] ウィンドウ** でインシデントを管理できます。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="インシデントの [インシデントの管理] ウィンドウの例。":::

このウィンドウは、次の [インシデントの **管理** ] リンクから表示できます。

- インシデント キュー内のインシデントのプロパティ ウィンドウ。
- **インシデントの** 概要ページ。

あるインシデントから別のインシデントにアラートを移動する場合は、[アラート] タブからアラートを移動して、関連するすべてのアラートを含む大きいインシデントまたは小規模インシデントを作成することもできます。

## <a name="edit-the-incident-name"></a>インシデント名を編集する

Microsoft 365 Defender影響を受けるエンドポイントの数、影響を受けるユーザー、検出ソース、カテゴリなどのアラート属性に基づいて、名前が自動的に割り当てされます。 これにより、インシデントの範囲をすばやく理解できます。 たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*

インシデント名は、[インシデントの管理] ウィンドウの **[インシデント名** ] フィールド **から編集** できます。

> [!NOTE]
> 自動インシデント名前付け機能のロールアウト前に存在していたインシデントは、その名前を保持します。

## <a name="add-incident-tags"></a>インシデント タグを追加する

たとえば、共通の特性を持つインシデントのグループにフラグを設定する場合など、インシデントにカスタム タグを追加できます。 後で、特定のタグを含むすべてのインシデントに対してインシデント キューをフィルター処理できます。

入力を開始すると、選択したタグの一覧から選択できます。

## <a name="assign-incidents"></a>インシデントを割り当てる

インシデントを割り当てるには、[割り当て **] を選択します**。 これにより、インシデントの所有権と、インシデントに関連付けられているすべてのアラートがユーザー アカウントに割り当てされます。

インシデント キューをフィルター処理することで、割り当てられたインシデントの一覧を取得できます。 

1. インシデント キューから、[フィルター] を **選択します**。
2. [インシデントの **割り当て** ] セクションで、[すべて選択] **をオフに** し、[割 **り当て済み] を選択します**。
3. [適用 **] を** 選択し、[フィルター] ウィンドウ **を閉** じます。

その後、ブラウザーに結果の URL をブックマークとして保存し、割り当てられたインシデントの一覧をすばやく表示できます。

## <a name="resolve-an-incident"></a>インシデントの解決

インシデントが修復された場合は、[インシデントの解決] **を** 選択してトグルを右に移動します。 インシデントを解決すると、インシデントに関連するリンクされたアラートとアクティブなアラートもすべて解決されます。

解決されないインシデントは、Active として表示 **されます**。

## <a name="set-the-classification-and-determination"></a>分類と決定を設定する

インシデント分類は、分類フィールドから構成する、本当のアラートか誤ったアラートか **です** 。 

それが本当の警告である場合は、[決定] フィールドで脅威の種類も **指定する必要** があります。 脅威の種類を指定すると、セキュリティ チームは脅威パターンを確認し、組織を防御するために行動できます。 

## <a name="add-comments"></a>コメントを追加する

[コメント] フィールドを使用して、インシデントに複数のコメント **を追加** できます。 各コメントは、インシデントの履歴イベントに追加されます。 インシデントのコメントと履歴は、[概要] ページの[コメントと履歴] リンク **から確認** できます。

## <a name="next-steps"></a>次の手順

新しいインシデントについては、調査を開始 [します](investigate-incidents.md)。

インプロセス インシデントの場合は、調査を続行 [します](investigate-incidents.md)。

解決されたインシデントの場合は、インシデント後 [のレビューを実行します](first-incident-post.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの調査](investigate-incidents.md)
