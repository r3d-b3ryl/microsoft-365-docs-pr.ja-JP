---
title: Microsoft Purview コンプライアンス マネージャーで評価テンプレートを作成する
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Purview コンプライアンス マネージャーで評価用のテンプレートを作成する方法について説明します。 書式設定された Excel ファイルを使用してテンプレートを作成および変更します。
ms.openlocfilehash: f7198d9b7bb9c30d388924d9c1b16a79e86bb8ee
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638666"
---
# <a name="create-an-assessment-template-in-microsoft-purview-compliance-manager"></a>Microsoft Purview コンプライアンス マネージャーで評価テンプレートを作成する

コンプライアンス マネージャーでカスタム評価用の独自の新しいテンプレートを作成するには、特別に書式設定された Excel スプレッドシートを使用して、必要なコントロール データを組み立てます。 スプレッドシートを完了すると、コンプライアンス マネージャーにインポートされます。

スプレッドシートの書式設定の詳細については、「Excel を使用 [した評価テンプレート データの書式設定](compliance-manager-templates-format-excel.md)」を参照してください。

## <a name="required-roles"></a>必要な役割

グローバル管理者またはコンプライアンス マネージャー管理ロールを持つユーザーのみが、テンプレートを作成および変更できます。 [ロールとアクセス許可](compliance-manager-setup.md#set-user-permissions-and-assign-roles)の詳細については、こちらを参照してください。

## <a name="create-new-template-in-compliance-manager"></a>コンプライアンス マネージャーで新しいテンプレートを作成する

1. コンプライアンス マネージャーの **[評価テンプレート** ] ページに移動します。
2. [ **新しいテンプレートの作成**] を選択します。 テンプレート作成ウィザードが開きます。
3. 作成するテンプレートの種類を選択します。 この場合は、[ **カスタム テンプレートの作成**] を選択し、[ **次へ**] を選択します。
4. **[ファイルのアップロード**] 画面で [**参照**] を選択し、必要なすべてのテンプレート データを含む書式設定された Excel ファイルを見つけてアップロードします。
5. ファイルに問題がない場合は、アップロードされたファイルの名前が表示されます。 [**次へ**] を選んで続行します。 (ファイルを変更する必要がある場合は、[ **別のファイルのアップロード**] を選択します)。
    - ファイルにエラーがある場合は、上部にエラー メッセージが表示されます。 ファイルを修正し、もう一度アップロードする必要があります。 スプレッドシートの書式設定が正しくない場合や、特定のフィールドに無効な情報がある場合、エラーが発生します。
6. **[校閲と終了]** 画面には、改善アクションとコントロールの数とテンプレートの最大スコアが表示されます。 承認する準備ができたら、[テンプレートの作成] を選択 **します。** (変更する必要がある場合は、[ **戻る**] を選択します)。
7. 最後の画面では、新しいテンプレートが作成されたことを確認します。 **[完了] を** 選択してウィザードを終了します。
8. 新しいテンプレートの詳細ページに移動し、 [評価を作成](compliance-manager-assessments.md#create-assessments)できます。
