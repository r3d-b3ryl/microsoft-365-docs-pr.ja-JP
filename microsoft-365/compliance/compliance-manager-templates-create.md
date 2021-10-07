---
title: Microsoft コンプライアンス マネージャーで評価テンプレートを作成する
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンス マネージャーで評価用のテンプレートを作成する方法について説明します。 書式設定されたファイルを使用してテンプレートを作成Excelします。
ms.openlocfilehash: 5db58b1032f5c654f1c02b81c7d1b6929a9078c7
ms.sourcegitcommit: 81533e5d3e1aee0823539a7c9bdc20dba6541a02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2021
ms.locfileid: "60223520"
---
# <a name="create-an-assessment-template-in-microsoft-compliance-manager"></a>Microsoft コンプライアンス マネージャーで評価テンプレートを作成する

コンプライアンス マネージャーでカスタム評価用の独自の新しいテンプレートを作成するには、特別に書式設定されたスプレッドシートExcelを使用して、必要なコントロール データを組み立てます。 スプレッドシートが完成すると、コンプライアンス マネージャーにインポートされます。

スプレッドシートの書式設定の詳細については、「評価テンプレート データの書式設定」[を参照Excel。](compliance-manager-templates-format-excel.md)

## <a name="required-roles"></a>必須の役割

テンプレートを作成および変更できるのは、グローバル管理者またはコンプライアンス マネージャーの管理役割を持つユーザーのみです。 役割とアクセス [許可について詳しくは、次のページをご覧ください](compliance-manager-setup.md#set-user-permissions-and-assign-roles)。

## <a name="create-new-template-in-compliance-manager"></a>コンプライアンス マネージャーで新しいテンプレートを作成する

1. コンプライアンス マネージャーの **[評価テンプレート]** ページに移動します。
2. [新 **しいテンプレートの作成] を選択します**。 テンプレート作成ウィザードが開きます。
3. 作成するテンプレートの種類を選択します。 この場合は、[カスタム テンプレートの **作成] を選択し**、[次へ] を **選択します**。
4. [ファイルの **アップロード] 画面** で、[参照] を選択して、必要なすべてのテンプレート データを含むExcelファイルを検索してアップロードします。
5. ファイルに問題がない場合は、アップロードしたファイルの名前が表示されます。 [**次へ**] を選んで続行します。 (ファイルを変更する必要がある場合は、別 **のアップロードを選択します**)。
    - ファイルにエラーが発生した場合は、上部にエラー メッセージが表示されます。 ファイルを修正し、もう一度アップロードする必要があります。 スプレッドシートが正しく書式設定されていない場合、または特定のフィールドに無効な情報が含まれている場合、エラーが発生します。
6. [ **レビューと終了] 画面** には、改善アクションとコントロールの数とテンプレートの最大スコアが表示されます。 承認する準備ができたら、[テンプレートの作成] **を選択します。** (変更が必要な場合は、[戻る] **を選択** します)。
7. 最後の画面で、新しいテンプレートが作成されたのが確認されます。 [完了 **] を** 選択してウィザードを終了します。
8. 新しいテンプレートの詳細ページにアクセスし、評価を [作成できます](compliance-manager-assessments.md#create-assessments)。
