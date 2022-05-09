---
title: Microsoft 365 Defenderでインシデントを管理する
description: 状態の割り当てと更新を行う方法について説明します。
keywords: インシデント, インシデント, 分析, 応答, アラート, 相関アラート, 割り当て, 更新, 状態, 管理, 分類, microsoft, 365, m365
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
# <a name="manage-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defenderでインシデントを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

インシデント管理は、インシデントワークフローの時間を最適化し、脅威をより迅速に含めて対処するために、インシデントの名前付け、割り当て、およびタグ付けを確実にするために重要です。

インシデント&**アラート>インシデントからインシデント** を管理するには、Microsoft 365 Defender ポータル ([security.microsoft.com](https://security.microsoft.com)) をクイック起動します。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 Defender ポータルのインシデント ページ" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

インシデントを管理する方法を次に示します。

- [インシデント名を編集する](#edit-the-incident-name)
- [インシデント タグを追加する](#add-incident-tags)
- [インシデントをユーザー アカウントに割り当てる](#assign-an-incident)
- [それらを解決する](#resolve-an-incident)
- [分類を指定する](#specify-the-classification)
- [コメントを追加する](#add-comments)

インシデントを管理するには、インシデント用の[**インシデントの管理**] ウィンドウから行います。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Microsoft 365 Defender ポータルの [インシデントの管理] ウィンドウ" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

このウィンドウは、次のページの [ **インシデントの管理** ] リンクから表示できます。

- インシデント キュー内のインシデントの [プロパティ] ウィンドウ。
- インシデント **の概要** ページ。

あるインシデントから別のインシデントにアラートを移動する場合は、[ **アラート]** タブからアラートを移動して、関連するすべてのアラートを含む大規模または小規模のインシデントを作成することもできます。

## <a name="edit-the-incident-name"></a>インシデント名を編集する

Microsoft 365 Defenderは、影響を受けるエンドポイントの数、影響を受けたユーザー、検出ソース、カテゴリなどのアラート属性に基づいて名前を自動的に割り当てます。 これにより、インシデントの範囲をすばやく把握できます。 たとえば、 *複数のソースによって報告された複数のエンドポイントに対する多段階インシデント。*

インシデント名は、[インシデントの **管理**] ウィンドウの [**インシデント名**] フィールドから編集できます。

> [!NOTE]
> 自動インシデントの名前付け機能のロールアウト前に存在していたインシデントは、その名前を保持します。

## <a name="add-incident-tags"></a>インシデント タグを追加する

共通した特徴を持つインシデントのグループにフラグを設定するなど、インシデントにカスタム タグを追加できます。 こうすることで、特定のタグを含むすべてのインシデントのインシデント キューを後からフィルター処理できます。

入力を開始すると、以前に使用したタグと選択したタグの一覧から選択できます。

## <a name="assign-an-incident"></a>インシデントを割り当てる

インシデントがまだ割り当てられていない場合は、[ **割り当て** 対象] ボックスを選択し、ユーザー アカウントを指定できます。 インシデントを再割り当てするには、アカウント名の横にある [x] を選択して現在の割り当てアカウントを削除し、[ **割り当て先** ] ボックスを選択します。 インシデントの所有権を割り当てると、それに関連付けられているすべてのアラートに同じ所有権が割り当てられます。

インシデント キューをフィルター処理することで、割り当てられたインシデントの一覧を取得できます。 

1. インシデント キューから [フィルター] を選択 **します**。
2. [ **インシデントの割り当て** ] セクションで、[ **すべて選択]** をオフにして、[ **自分に割り当てる]** を選択します。
3. [ **適用]** を選択し、[ **フィルター** ] ウィンドウを閉じます。

その後、ブラウザーに結果の URL をブックマークとして保存し、割り当てられたインシデントの一覧をすばやく表示できます。

## <a name="resolve-an-incident"></a>インシデントを解決する

インシデントが修復された場合は、[ **インシデントの解決** ] を選択してトグルを右に移動します。 インシデントを解決すると、インシデントに関連するすべてのリンクされたアクティブなアラートも解決されることに注意してください。

解決されていないインシデントが **アクティブ** として表示されます。

## <a name="specify-the-classification"></a>分類を指定する

[ **分類** ] フィールドで、インシデントが次のかどうかを指定します。

- **未設定** (既定値)。
- **脅威** の種類を持つ真の陽性。 実際の脅威を正確に示すインシデントには、この分類を使用します。 脅威の種類を指定すると、セキュリティ チームは脅威パターンを確認し、組織を防御するために行動できます。
- アクティビティの種類を含む **、情報に関する期待される** アクティビティ。 このカテゴリのオプションを使用して、セキュリティ テスト、赤いチーム アクティビティ、信頼できるアプリやユーザーからの予期される異常な動作のインシデントを分類します。
- 検出したインシデントの種類に対する **誤検知** は、技術的に不正確または誤解を招く可能性があるため、無視できます。

インシデントを分類し、その状態と種類を指定すると、Microsoft 365 Defenderを調整して、時間の経過と共に検出の判断が向上します。

## <a name="add-comments"></a>コメントを追加する

[コメント] フィールドを使用して、インシデントに複数の **コメント** を追加できます。 各コメントは、インシデントの履歴イベントに追加されます。 インシデントのコメントと履歴は、[**概要**] ページの [**コメントと履歴**] リンクから確認できます。

## <a name="next-steps"></a>次の手順

新しいインシデントの場合は、 [調査](investigate-incidents.md)を開始します。

インプロセス インシデントの場合は、 [調査](investigate-incidents.md)を続行します。

解決されたインシデントについては、 [インシデント後のレビューを実行します](first-incident-post.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの調査](investigate-incidents.md)
