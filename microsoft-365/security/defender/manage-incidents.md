---
title: Microsoft 365 Defender でのインシデントの管理
description: 状態の割り当てと更新を行う方法について説明します。
keywords: インシデント、インシデント、警告、関連付けられた警告、割り当て、更新、状態、管理、分類、microsoft、365、m365
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
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760070"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender でのインシデントの管理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

インシデント管理は、脅威を確実に含め、対処する上で重要です。

Microsoft 365 セキュリティ センター (& >) のクイック 起動時に、インシデント とアラートのインシデントを[管理 security.microsoft.com。](https://security.microsoft.com)  次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント キューの例":::

インシデントを管理する方法は次のとおりです。

- インシデント名を変更する
- インシデント タグを追加します。
- インシデントをユーザー アカウントに割り当てる
- それらを解決する 
- 分類と決定を設定する
- コメントを追加します。

インシデントを管理するには、[インシデントの **管理] ウィンドウ** でインシデントを管理できます。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="インシデントの [インシデントの管理] ウィンドウの例":::

このウィンドウは、次の [インシデントの **管理** ] リンクから表示できます。

- インシデント キュー内のインシデントのプロパティ ウィンドウ。
- **インシデントの** 概要ページ。

調査中に、あるインシデントから別のインシデントにアラートを移動する場合は、[アラート] タブからアラートを移動することもできます。これにより、関連するすべてのアラートを含む大小のインシデントを作成できます。

## <a name="edit-the-incident-name"></a>インシデント名を編集する

インシデントには、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいて、名前が自動的に割り当てられます。 これにより、インシデントの範囲をすばやく理解できます。 たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*

インシデント名は、[インシデントの管理] ウィンドウの **[インシデント名** ] フィールド **から編集** できます。

> [!NOTE]
> 自動インシデント名前付け機能のロールアウト前に存在していたインシデントは、その名前を保持します。

## <a name="add-incident-tags"></a>インシデント タグを追加する

たとえば、共通の特性を持つインシデントのグループにフラグを設定する場合など、インシデントにカスタム タグを追加できます。 後で、特定のタグを含むすべてのインシデントに対してインシデント キューをフィルター処理できます。

入力を開始すると、選択したタグの一覧から選択できます。

## <a name="assign-incidents"></a>インシデントを割り当てる

インシデントがまだ割り当てられていない場合は、[割り当て] **を選択して** ユーザー アカウントを指定できます。 これにより、インシデントの所有権と、インシデントに関連付けられているすべてのアラートが割り当てされます。

## <a name="resolve-incident"></a>インシデントの解決

インシデントが修復された場合は、[インシデントの解決] **を** 選択してトグルを右に移動します。 インシデントを解決すると、インシデントに関連するリンクされたアラートとアクティブなアラートもすべて解決されます。

解決されないインシデントは、Active として表示 **されます**。

## <a name="set-the-classification-and-determination"></a>分類と決定を設定する

インシデント分類は、分類フィールドから構成する、本当のアラートか誤ったアラートか **です** 。 

それが本当の警告である場合は、[決定] フィールドで脅威の種類も **指定する必要** があります。 脅威の種類を指定すると、セキュリティ チームは脅威パターンを確認し、組織を防御するために行動できます。 

## <a name="add-comments"></a>コメントを追加する

[コメント] フィールドを使用して、インシデントに複数のコメント **を追加** できます。 各コメントは、インシデントの履歴イベントに追加されます。 インシデントのコメントと履歴は、[概要] ページの[コメントと履歴] リンク **から確認** できます。
