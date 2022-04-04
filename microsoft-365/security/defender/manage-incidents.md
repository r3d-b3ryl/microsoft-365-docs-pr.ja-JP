---
title: インシデントを管理Microsoft 365 Defender
description: 状態の割り当てと更新を行う方法について説明します。
keywords: インシデント、インシデント、分析、応答、アラート、相関アラート、割り当て、更新、状態、管理、分類、microsoft、365、m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 14332b2787b59e2ef192741dc97e59a7c7cb5418
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499509"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>インシデントを管理Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

インシデント管理は、インシデントワークフローの時間を最適化し、脅威を迅速に含めて対処するために、インシデントの名前、割り当て、タグ付けを確実に行う上で重要です。

インシデント ポータル (&) **の&で**>インシデントからインシデントを管理 [Microsoft 365 Defender](https://security.microsoft.com)できます。security.microsoft.com。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="[インシデント] ページ (Microsoft 365 Defender ポータル)" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

インシデントを管理する方法は次のとおりです。

- [インシデント名を編集する](#edit-the-incident-name)
- [インシデント タグの追加](#add-incident-tags)
- [インシデントをユーザー アカウントに割り当てる](#assign-an-incident)
- [それらを解決する](#resolve-an-incident)
- [分類を指定する](#specify-the-classification)
- [コメントの追加](#add-comments)

インシデントを管理するには、インシデント用の[**インシデントの管理**] ウィンドウから行います。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="[インシデントの管理] ウィンドウ (Microsoft 365 Defender ポータル)" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

このウィンドウは、次の [インシデントの **管理** ] リンクから表示できます。

- インシデント キュー内のインシデントのプロパティ ウィンドウ。
- **インシデントの** 概要ページ。

あるインシデントから別のインシデントにアラートを移動する場合は、[アラート] タブからアラートを移動して、関連するすべてのアラートを含む大きいインシデントまたは小規模インシデントを作成することもできます。

## <a name="edit-the-incident-name"></a>インシデント名を編集する

Microsoft 365 Defender、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいて名前が自動的に割り当てされます。 これにより、インシデントの範囲をすばやく把握できます。 たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*

インシデント名は、[インシデントの管理] ウィンドウの **[インシデント名** ] フィールド **から編集** できます。

> [!NOTE]
> 自動インシデント名前付け機能のロールアウト前に存在していたインシデントは、その名前を保持します。

## <a name="add-incident-tags"></a>インシデント タグを追加する

共通した特徴を持つインシデントのグループにフラグを設定するなど、インシデントにカスタム タグを追加できます。 こうすることで、特定のタグを含むすべてのインシデントのインシデント キューを後からフィルター処理できます。

入力を開始すると、以前に使用したタグと選択したタグの一覧から選択できます。

## <a name="assign-an-incident"></a>インシデントの割り当て

インシデントがまだ割り当てられていない場合は、[割り当て] ボックスを選択し、ユーザー アカウントを指定できます。 インシデントを再割り当てするには、アカウント名の横にある "x" を選択して現在の割り当てアカウントを削除し、[割り当て] ボックス **を選択** します。 インシデントの所有権を割り当てると、関連付けられているすべてのアラートに同じ所有権が割り当てされます。

インシデント キューをフィルター処理することで、割り当てられたインシデントの一覧を取得できます。 

1. インシデント キューから、[フィルター] を **選択します**。
2. [インシデントの **割り当て** ] セクションで、[すべて選択] **をオフに** し、[割 **り当て済み] を選択します**。
3. [適用 **] を** 選択し、[フィルター] ウィンドウ **を閉** じます。

その後、ブラウザーに結果の URL をブックマークとして保存し、割り当てられたインシデントの一覧をすばやく表示できます。

## <a name="resolve-an-incident"></a>インシデントの解決

インシデントが修復された場合は、[インシデントの解決] **を** 選択してトグルを右に移動します。 インシデントを解決すると、インシデントに関連するリンクされたアラートとアクティブなアラートもすべて解決されます。

解決されないインシデントは、アクティブとして表示 **されます**。

## <a name="specify-the-classification"></a>分類を指定する

[分類 **] フィールド** で、インシデントが次のかどうかを指定します。

- **[設定しない** ] (既定)。
- **脅威の種類** に対して正の値を指定します。 実際の脅威を正確に示すインシデントには、この分類を使用します。 脅威の種類を指定すると、セキュリティ チームは脅威パターンを確認し、組織を防御するために行動できます。
- **アクティビティの種類を含む、予想** される情報アクティビティ。 このカテゴリのオプションを使用して、セキュリティ テスト、赤いチーム アクティビティ、信頼できるアプリとユーザーからの予期される異常な動作のインシデントを分類します。
- **検出した** インシデントの種類に対して誤検知は、技術的に不正確または誤解を招くため無視できます。

インシデントを分類し、その状態と種類を指定すると、時間のMicrosoft 365 Defenderの検出判定を向上するために、インシデントの調整に役立ちます。

## <a name="add-comments"></a>コメントを追加する

[コメント] フィールドを使用して、インシデントに複数のコメント **を追加** できます。 各コメントは、インシデントの履歴イベントに追加されます。 インシデントのコメントと履歴は、[概要] ページの [コメントと履歴] リンク **から確認** できます。

## <a name="next-steps"></a>次の手順

新しいインシデントについては、調査を開始 [します](investigate-incidents.md)。

インプロセス インシデントの場合は、調査を続行 [します](investigate-incidents.md)。

解決されたインシデントの場合は、インシデント後 [のレビューを実行します](first-incident-post.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの調査](investigate-incidents.md)
