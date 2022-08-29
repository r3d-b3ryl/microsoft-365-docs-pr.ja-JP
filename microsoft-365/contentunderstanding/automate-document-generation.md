---
title: SharePoint Syntexと Power Automate (プレビュー) を使用してドキュメント生成を自動化する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: anrasto, shrganguly
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: SharePoint Syntexと Power Automate を使用してドキュメントやその他のコンテンツを自動的に作成する方法について説明します。
ms.openlocfilehash: ea8f380551d863a473c086112919cfb042a95594
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360644"
---
# <a name="automate-document-generation-with-sharepoint-syntex-and-power-automate-preview"></a>SharePoint Syntexと Power Automate (プレビュー) を使用してドキュメント生成を自動化する

SharePoint Syntexのコンテンツ アセンブリを Power Automate と共に使用すると、最新のテンプレートを使用してドキュメントの生成を自動化できます。 

このプレビュー バージョンは、SharePoint コネクタの Power Automate アクションです。 アクションは "SharePoint Syntexを使用してドキュメントを生成する (プレビュー)" という名前で、プレビューの機能が制限されています。 

## <a name="scope-of-the-preview"></a>プレビューのスコープ 

プレビューの現在のスコープでは、次のことができます。  

- ドキュメント生成の開始点として SharePoint リストを選択します。 つまり、リスト内のアイテムが追加、変更、または削除されたら、SharePoint リストの値を使用してドキュメントを生成します。 

- モダン テンプレートを選択し、選択した SharePoint リストの列にフィールドを関連付けます。 

プレビューは作成され、SharePoint Connector で次の 3 つのトリガーで動作するようにテストされます。

- アイテムを作成した場合
- アイテムを作成か変更した場合
- アイテムを削除した場合

## <a name="automate-document-generation"></a>ドキュメントの生成を自動化する 

モダン テンプレートと Power Automate を使用してドキュメントを自動的に生成するには、次の手順に従います。 

1. Power Automate にサインインします。

2. 左側のパネルで 、[コネクタ] を選択 **します**。 検索ボックスで *SharePoint* を検索し、 **SharePoint** コネクタを選択します。

3. SharePoint コネクタ ページで、自動ドキュメント生成プロセスの開始に使用するトリガーを選択します。 

    次の 3 つのトリガーのいずれかから始めることをお勧めします。

    - アイテムを作成した場合
    - アイテムを作成か変更した場合
    - アイテムを削除した場合

4. 次に、SharePoint サイトアドレスと SharePoint リストの名前を入力してトリガーを設定します。 **[新しい手順]** を選択します。 

   ![サンプル サイト アドレスとサイト名を示すドキュメントが作成または変更されたときのトリガーのスクリーンショット。](../media/content-understanding/document-generation-trigger.png)

5. SharePoint コネクタをもう一度選択します。 検索ボックスで、SharePoint Syntex **(プレビュー) を使用してドキュメントを生成** するアクションを検索して選択します。

   ![SharePoint Syntex (プレビュー) アクションを使用したドキュメントの生成を示す [SharePoint コネクタアクション] タブのスクリーンショット。](../media/content-understanding/document-generation-action.png) 

6. サイト情報を入力し、モダン テンプレートを含むドキュメント ライブラリを選択します。 

7. テンプレートを選択すると、テンプレート フィールドが表示されます。 フィールドをリスト内の列に関連付けます。 

    > [!NOTE]
    >このプレビューでは、テンプレート内のデータ マッピングはサポートされていません。 たとえば、テンプレート内のフィールドをマネージド メタデータ列に関連付けた場合、自動生成時に、このフィールドをリスト内の列に関連付けることができます。 

8. 完了したら、[ **保存]** を選択してフローを保存します。 

    > [!NOTE]
    > ドキュメント生成のためにユーザーが手動で値を追加する必要がないテンプレートを使用することをお勧めします。 テンプレートでフィールドに手動入力が必要な場合は、SharePoint リスト列にマッピングするのではなく、その値をフィールドに対して指定できます。<br><br> 現時点では、このアクションを使用して Word ドキュメント (.Docx) のみがサポートされています。  

## <a name="see-also"></a>関連項目

 [SharePoint Syntexでコンテンツ アセンブリを使用してドキュメントを作成する](content-assembly.md)
